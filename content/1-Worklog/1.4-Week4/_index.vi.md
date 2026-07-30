---
title: "Nhật ký Tuần 4"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4

- Bắt đầu lập trình Backend: triển khai các API cốt lõi cho dự án LMS
- Thiết lập môi trường DynamoDB local và kết nối với server

### Các công việc cần triển khai trong tuần này

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Clone repository về máy, cài đặt dependencies <br> - Cấu hình biến môi trường (.env) cho MySQL và DynamoDB <br> - Chạy thử server local, kiểm tra endpoint `/health` | 06/07/2026 | 06/07/2026 |  |
| 3   | - Xây dựng API đăng nhập/đăng ký với JWT <br> - Tạo model User và middleware xác thực <br> - Test API với Postman: `POST /auth/login`, `POST /users` | 07/07/2026 | 07/07/2026 | |
| 4   | - Phát triển API Classes & Courses: GET, POST, PUT, DELETE <br> - Viết model Class, Course, truy vấn DynamoDB với GSI <br> - Chạy script `seed_sample_data.sh` để nạp dữ liệu mẫu | 08/07/2026 | 08/07/2026 |  |
| 5   | - Phát triển API Schedules & Grades <br> - Thiết kế schema bảng StudentSchedule <br> - Viết controller và route cho chức năng xem thời khóa biểu, điểm số | 09/07/2026 | 09/07/2026 | |
| 6   | - Code review các API đã viết, sửa lỗi và tối ưu <br> - Họp nhóm kiểm tra tiến độ và lên kế hoạch tuần 5 | 10/07/2026 | 10/07/2026 | |

### Kết quả đạt được sau tuần 4

- Backend chạy ổn định trên môi trường local với DynamoDB và MySQL
- Hoàn thiện các API nền tảng: Auth, Users, Classes, Courses, Schedules, Grades
- Database đã có dữ liệu mẫu sẵn sàng cho việc test và phát triển Frontend
