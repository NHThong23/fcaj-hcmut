---
title: "Nhật ký Tuần 8"
date: 2026-08-07
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8

- Tự học và thực hành các dịch vụ AWS nâng cao: Lambda, API Gateway, ECS (Fargate), WAF
- Kết hợp lý thuyết và thực hành qua các workshop/hands-on lab chính thức của AWS
- Nắm được khi nào nên dùng từng dịch vụ và cách phối hợp chúng trong một kiến trúc thực tế

### Các công việc cần triển khai trong tuần này

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | **Lambda Workshop - Optimizing EC2 Costs with Lambda** <br> - Làm theo workshop 7 bước: giới thiệu → chuẩn bị → tạo tag cho instance → tạo IAM role cho Lambda → viết Lambda function (Python) tự động start/stop EC2 theo lịch → kiểm tra kết quả → dọn dẹp tài nguyên | 03/08/2026 | 03/08/2026 | [AWS Study Group - Lambda Workshop](https://000022.awsstudygroup.com/) |
| 3   | **API Gateway Workshop - Serverless Front-end with API Gateway** <br> - Làm theo workshop 5 bước: deploy front-end → cấu hình API Gateway kết nối Lambda + DynamoDB → test API bằng Postman → test API với front-end → dọn dẹp tài nguyên | 04/08/2026 | 04/08/2026 | [AWS Study Group - API Gateway Workshop](https://000135.awsstudygroup.com/) |
| 4   | **ECS Workshop - Deploy Applications on Amazon ECS** <br> - Làm theo workshop 10 bước: chuẩn bị môi trường → viết Dockerfile, push lên ECR → tạo ECS Cluster (Fargate) → tạo Task Definition → cấu hình ALB → tạo ECS Service → kiểm tra kết quả → dọn dẹp tài nguyên | 05/08/2026 | 05/08/2026 | [AWS Study Group - ECS Workshop](https://000016.awsstudygroup.com/) |
| 5   | **AWS WAF Workshop - AWS Web Application Firewall** <br> - Làm theo workshop 4 bước: giới thiệu WAF → chuẩn bị môi trường → thực hành cấu hình Web ACL, rule groups, IP set, rate limiting → dọn dẹp tài nguyên | 06/08/2026 | 06/08/2026 | [AWS Study Group - WAF Workshop](https://000026.awsstudygroup.com/) |
| 6   | **Vận dụng & So sánh các dịch vụ** <br> - Tổng hợp kiến thức 4 dịch vụ: điểm mạnh, điểm yếu, use case phù hợp cho từng dịch vụ <br> - So sánh các mô hình triển khai: Serverless (Lambda) vs Container (ECS) vs VM (EC2) – chọn gì, khi nào? | 07/08/2026 | 07/08/2026 | |

### Kết quả đạt được sau tuần 8

- Hoàn thành 4 workshop: Lambda (tự động start/stop EC2), API Gateway (serverless front-end + Lambda + DynamoDB), ECS (Docker → ECR → Fargate), WAF (Web ACL, rate limiting)
- Nắm được sự khác biệt giữa 3 mô hình Serverless – Container – VM và use case phù hợp cho từng dịch vụ
