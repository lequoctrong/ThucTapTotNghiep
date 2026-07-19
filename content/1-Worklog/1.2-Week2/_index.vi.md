---
title: "Worklog Tuần 2"
date: 2026-04-27
weight: 2
chapter: false
pre: "<b>1.2.</b> "
---

### Mục tiêu tuần 2:
* Tìm hiểu sâu và thành thạo các dịch vụ cốt lõi: Điện toán (EC2), Lưu trữ (S3) và Mạng (VPC).
* Nắm vững tư duy bảo mật mạng cơ bản (Security Group & NACL) và cơ chế chứng thực khóa công khai (Key Pair).
* Thực hành xây dựng môi trường đám mây: Khởi chạy máy chủ, cấu hình IP tĩnh, upload/download dữ liệu và thiết lập kết nối từ xa an toàn.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | ------------ | --------------- | --------------- |
| Hai | - Tìm hiểu dịch vụ điện toán **Amazon EC2 Basics** (Instance Types, Public/Private/Elastic IP).<br>- Đọc hiểu lý thuyết dịch vụ lưu trữ đối tượng **Amazon S3 Storage** (Buckets, Objects, S3 Classes). | 27/04/2026 | 27/04/2026 | <https://docs.aws.amazon.com/ec2/> <br> <https://docs.aws.amazon.com/s3/> |
| Ba | - **Thực hành Amazon S3:**<br>&emsp; + Khởi tạo S3 Bucket cá nhân.<br>&emsp; + Thực hành upload, download, quản lý dữ liệu đối tượng và cấu hình quyền truy cập cơ bản. | 28/04/2026 | 28/04/2026 | AWS Management Console |
| Tư | - Nghiên cứu tài liệu **Introduction to Networking on AWS** (Tìm hiểu tổng quan về VPC, Subnets, Internet Gateway).<br>- Phân biệt cơ chế bảo mật tầng mạng giữa **Security Group** (Stateful) và **NACL** (Stateless). | 29/04/2026 | 29/04/2026 | <https://docs.aws.amazon.com/vpc/> |
| Năm | - **Thực hành Cấu hình Mạng & Máy chủ:**<br>&emsp; + Tạo Key Pair và thiết lập Security Group/NACL tuân thủ an toàn an ninh mạng.<br>&emsp; + Tiến hành Launch một Amazon EC2 instance chạy hệ điều hành Linux. | 30/04/2026 | 30/04/2026 | AWS Management Console |
| Sáu | - **Thực hành Cấu hình IP & Định tuyến:**<br>&emsp; + Tạo, cấp phát và gắn (associate) Elastic IP (EIP) vào EC2 instance vừa tạo.<br>&emsp; + Kiểm tra bảng định tuyến (Route Table) đảm bảo instance có thể giao tiếp internet. | 01/05/2026 | 01/05/2026 | AWS Management Console |


### Kết quả đạt được tuần 2:

* **Quản trị Máy chủ & Lưu trữ (EC2 & S3):**
  * Hiểu rõ cơ chế hoạt động của Amazon EC2, phân biệt được Public IP, Private IP, Elastic IP và biết cách chọn cấu hình Instance phù hợp.
  * Thành thạo thao tác lưu trữ trên Amazon S3, biết cách tạo bucket, truyền tải dữ liệu an toàn và hiểu các lớp lưu trữ để tối ưu chi phí.
* **Tư duy Hệ thống Mạng & Tường lửa (VPC, SG, NACL):**
  * Nắm vững kiến thức nền tảng về cấu trúc mạng VPC và các thành phần định tuyến internet trên Cloud.
  * Phân biệt rõ ràng vai trò của Security Group (tường lửa cấp instance) và NACL (tường lửa cấp subnet) để thiết lập các luật Inbound/Outbound hợp lệ.
* **Triển khai Môi trường Thực tế:**
  * Khởi chạy thành công Linux EC2 instance và gắn Elastic IP cố định để đảm bảo IP không bị thay đổi khi restart máy chủ.
  * Sử dụng Key Pair an toàn để thiết lập kết nối SSH thành công từ máy tính cá nhân vào máy chủ EC2.
  * Tự giải quyết được các lỗi mất kết nối mạng (Network Timeout) thường gặp nhờ tư duy xử lý sự cố liên quan đến Routing và Firewall.