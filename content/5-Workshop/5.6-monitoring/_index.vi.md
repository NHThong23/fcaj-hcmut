---
title : "Giám sát"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

Một chủ đề SNS + ba cảnh báo CloudWatch bao phủ từng tầng có thể gặp sự cố. Khi một cảnh báo kích hoạt, nó sẽ gửi thông báo đến chủ đề SNS — đăng ký email hoặc webhook để nhận cảnh báo.

#### SNS Topic

```hcl
resource "aws_sns_topic" "alarms" {
  name = "infra-alarms"
  tags = { Name = "infra-alarms" }
}
```

#### Alarms

| Alarm | Metric | Ngưỡng | Logic |
|-------|--------|--------|-------|
| `alb-5xx-errors` | `HTTPCode_Target_5XX_Count` | > 5 trong 2 chu kỳ 1 phút | Ứng dụng trả về lỗi cho người dùng |
| `rds-cpu-high` | `CPUUtilization` | > 80% trong 2 chu kỳ 5 phút | Cơ sở dữ liệu đang chịu áp lực — cần mở rộng hoặc tối ưu truy vấn |
| `asg-below-min-size` | `GroupTotalInstances` | < 2 trong 2 chu kỳ 5 phút | Máy chủ ảo (Instance) không khởi chạy được hoặc bị terminate |

#### ALB 5xx

```hcl
resource "aws_cloudwatch_metric_alarm" "alb_5xx" {
  alarm_name          = "alb-5xx-errors"
  comparison_operator = "GreaterThanThreshold"
  evaluation_periods  = 2
  threshold           = 5
  period              = 60
  namespace           = "AWS/ApplicationELB"
  metric_name         = "HTTPCode_Target_5XX_Count"
  statistic           = "Sum"
  treat_missing_data  = "notBreaching"

  dimensions = {
    LoadBalancer = aws_lb.main.arn_suffix
  }

  alarm_actions = [aws_sns_topic.alarms.arn]
  ok_actions    = [aws_sns_topic.alarms.arn]
}
```

`treat_missing_data = "notBreaching"` — nếu ALB không có lưu lượng truy cập (do đó không có điểm dữ liệu 5xx), thì không có vấn đề gì. Chỉ kích hoạt báo động khi có dữ liệu vượt ngưỡng.

#### RDS CPU

```hcl
resource "aws_cloudwatch_metric_alarm" "rds_cpu" {
  alarm_name          = "rds-cpu-high"
  comparison_operator = "GreaterThanThreshold"
  evaluation_periods  = 2
  threshold           = 80
  period              = 300
  namespace           = "AWS/RDS"
  metric_name         = "CPUUtilization"
  statistic           = "Average"
  treat_missing_data  = "notBreaching"

  dimensions = {
    DBInstanceIdentifier = aws_db_instance.main.identifier
  }

  alarm_actions = [aws_sns_topic.alarms.arn]
  ok_actions    = [aws_sns_topic.alarms.arn]
}
```

CPU 80% duy trì trong 10 phút (2 × 5 phút). Với `db.t4g.micro` 2 vCPU, điều này có nghĩa cơ sở dữ liệu đang bị giới hạn CPU. Hướng xử lý: nâng cấp instance class hoặc thêm read replica.

#### ASG Dưới Mức Tối Thiểu

```hcl
resource "aws_cloudwatch_metric_alarm" "asg_below_min" {
  alarm_name          = "asg-below-min-size"
  comparison_operator = "LessThanThreshold"
  evaluation_periods  = 2
  threshold           = var.asg_min_size
  period              = 300
  namespace           = "AWS/AutoScaling"
  metric_name         = "GroupTotalInstances"
  statistic           = "Average"
  treat_missing_data  = "breaching"

  dimensions = {
    AutoScalingGroupName = aws_autoscaling_group.app.name
  }

  alarm_actions = [aws_sns_topic.alarms.arn]
  ok_actions    = [aws_sns_topic.alarms.arn]
}
```

`treat_missing_data = "breaching"` — ngược lại với hai alarm trên. Nếu không thể lấy dữ liệu từ ASG, nghĩa là có vấn đề. Không giống ALB (không lưu lượng = bình thường), ASG (không dữ liệu = bản thân ASG có thể đã bị xóa hoặc hỏng).

#### Tại Sao Chọn Ba loại báo động Này?

- **ALB 5xx** — phát hiện lỗi ứng dụng, triển khai thất bại, phụ thuộc ngoài bị gián đoạn
- **RDS CPU** — phát hiện vấn đề hiệu suất truy vấn, thiếu index, tăng đột biến lưu lượng
- **ASG dưới mức tối thiểu** — phát hiện lỗi khởi chạy instance, AZ outage, giới hạn instance type

Mỗi alarm bao phủ một chế độ lỗi khác nhau. Kết hợp lại chúng cung cấp đủ tín hiệu để biết khi nào cần điều tra mà không tạo ra quá nhiều nhiễu.
