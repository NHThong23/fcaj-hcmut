---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6

- Triển khai toàn bộ ứng dụng lên hạ tầng AWS
- Cấu hình domain và CI/CD để tự động hóa quy trình deploy

### Các công việc cần triển khai trong tuần này

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Deploy Backend lên EC2: cài Node.js, PM2, clone repo <br> - Cấu hình biến môi trường (.env) cho production <br> - Kiểm tra Backend hoạt động qua public IP | 20/07/2026 | 20/07/2026 | |
| 3   | - Build Frontend với Vite: `npm run build` <br> - Upload bản build lên S3 bucket <br> - Cấu hình S3 static website hosting | 21/07/2026 | 21/07/2026 | |
| 4   | - Thiết lập CloudFront distribution trỏ đến S3 bucket <br> - Cấu hình CORS giữa Frontend (CloudFront) và Backend (EC2) <br> - Kiểm tra ứng dụng chạy hoàn chỉnh trên môi trường production | 22/07/2026 | 22/07/2026 | |
| 5   | - Cấu hình DynamoDB trên AWS (thay vì local) <br> - Chạy script setup_dynamodb.sh và seed_sample_data.sh trên môi trường thật <br> - Kiểm tra kết nối Backend → DynamoDB AWS | 23/07/2026 | 23/07/2026 | |
| 6   | - Thiết lập CI/CD cơ bản với GitHub Actions: tự động deploy khi push code <br> - Kiểm thử toàn bộ luồng: đăng nhập, xem khóa học, làm quiz, nộp bài <br> - Ghi nhận và sửa các lỗi phát sinh trên production | 24/07/2026 | 24/07/2026 | |

### Kết quả đạt được sau tuần 6

- Ứng dụng LMS đã chạy hoàn chỉnh trên AWS: Frontend qua CloudFront, Backend trên EC2, dữ liệu trên DynamoDB
- CI/CD pipeline hoạt động, tự động deploy khi có thay đổi code
- Toàn bộ chức năng hoạt động ổn định trên môi trường production
