---
title: "Worklog Tuần 5"
date: 2026-05-18
weight: 5
chapter: false
pre: "<b>1.5.</b> "
---

### Mục tiêu tuần 5:

* Rà soát, đánh giá và tối ưu hóa cấu hình bảo mật cho toàn bộ tài nguyên đã khởi tạo (EC2, S3, IAM).
* Nâng cao năng lực quản trị hạ tầng thông qua giao diện dòng lệnh AWS CLI thay vì thao tác đồ họa (Console).
* Tổng hợp kiến thức thực tế, chuẩn hóa quy trình thao tác để đóng gói và cập nhật tài liệu hướng dẫn nội bộ.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | ------------ | --------------- | --------------- |
| 2   | - Thực hiện **AWS EC2 Review**: Kiểm tra trạng thái hoạt động, tối ưu hóa kích thước instance.<br>- Đánh giá cấu hình **Security Group**, rà soát và thắt chặt các luật Inbound (chỉ mở port cần thiết, hạn chế `0.0.0.0/0`). | 18/05/2026 | 19/05/2026 | AWS Management Console |
| 3   | - Thực hiện **Amazon S3 Basics Review** & **IAM Fundamentals**: Kiểm tra tính an toàn của dữ liệu, rà soát các Bucket có nguy cơ lộ lọt thông tin (Public Access).<br>- Kiểm tra lại danh sách IAM User, thu hồi các Access Key cũ không sử dụng để đảm bảo an toàn an ninh. | 19/05/2026 | 19/05/2026 | <https://docs.aws.amazon.com/iam/> |
| 4   | - Nghiên cứu tài liệu **AWS CLI Introduction** (Cú pháp câu lệnh, cấu trúc JSON Output, cách sử dụng các tham số lọc dữ liệu như `--query` và `--filter`).<br>- Học cách tra cứu nhanh tài liệu dòng lệnh thông qua lệnh `aws help`. | 20/05/2026 | 20/05/2026 | <https://docs.aws.amazon.com/cli/> |
| 5   | - **Thực hành Thao tác với AWS CLI:**<br>&emsp; + Sử dụng terminal để liệt kê tài nguyên (`aws ec2 describe-instances`, `aws s3 ls`, `aws iam list-users`).<br>&emsp; + Thực hành tạo mới và cấu hình một Security Group hoàn chỉnh hoàn toàn bằng dòng lệnh CLI. | 21/05/2026 | 21/05/2026 | Terminal / AWS CLI |
| 6   | - **Tổng hợp & Đóng gói Tài liệu Nội bộ:**<br>&emsp; + Ghi lại nhật ký, tổng hợp toàn bộ mã lỗi và cách xử lý trong suốt quá trình cấu hình thực hành.<br>&emsp; + Hỗ trợ biên soạn, cập nhật và chuẩn hóa tài liệu hướng dẫn kỹ thuật nội bộ cho đội ngũ. | 22/05/2026 | 23/05/2026 | Bản tin nội bộ / Markdown Editor |

### Kết quả đạt được tuần 5:

* **Quản trị Bảo mật & Tối ưu Tài nguyên (Audit & Review):**
  * Hoàn thành kiểm tra và chuẩn hóa cấu hình bảo mật cho toàn bộ EC2, S3 Buckets và IAM Users; đóng các cổng dịch vụ thừa và chặn các dải IP không an toàn.
  * Nắm vững tư duy rà soát lỗ hổng an ninh (Security Auditing) trên môi trường Cloud thực tế.
* **Thành thạo Thao tác Dòng lệnh (AWS CLI Proficiency):**
  * Chuyển đổi thành công từ tư duy quản trị giao diện (Click-ops) sang quản trị bằng dòng lệnh (CLI).
  * Sử dụng thành thạo các câu lệnh truy vấn dữ liệu cốt lõi, biết cách lọc dữ liệu JSON trả về để trích xuất thông tin tài nguyên một cách nhanh chóng.
  * Tự thực hiện tạo lập và cấu hình tường lửa Security Group thành công thông qua AWS CLI.
* **Kỹ năng Đóng gói Kiến thức (Documentation & Knowledge Sharing):**
  * Xây dựng và cập nhật thành công bộ tài liệu hướng dẫn kỹ thuật nội bộ, ghi chú rõ ràng các bước thực hành kèm các lỗi (troubleshooting) thường gặp.
  * Nâng cao kỹ năng viết tài liệu chuẩn kỹ thuật (Technical Writing), sẵn sàng cho việc bàn giao hoặc phối hợp công việc trong đội ngũ.