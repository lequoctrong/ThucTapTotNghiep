---
title: "Worklog Tuần 6"
date: 2026-05-25
weight: 6
chapter: false
pre: "<b>1.6.</b> "
---

### Mục tiêu tuần 6:

* Thực hành xây dựng và quản trị vòng đời máy chủ ảo Amazon EC2 nâng cao theo tiêu chuẩn và hướng dẫn trực tiếp từ Mentor.
* Làm chủ cơ chế phân quyền bảo mật không dùng mã định danh bằng cách áp dụng IAM Role cho tài nguyên hệ thống.
* Tích hợp toàn diện các dịch vụ cốt lõi: Cấu hình EC2 tự động tương tác lưu trữ dữ liệu trên S3 và giám sát hiệu năng qua CloudWatch.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | ------------ | --------------- | --------------- |
| 2   | - Làm hướng dẫn chuẩn hóa quy trình **Amazon EC2 Management**.<br>- Thực hành khởi tạo, cấu hình nâng cao và tối ưu hóa các thông số vận hành của EC2 instance theo yêu cầu thực tế. | 25/05/2026 | 25/05/2026 | Hướng dẫn từ Mentor / AWS Console |
| 3   | - Nghiên cứu sâu về giải pháp bảo mật nâng cao **IAM Roles and Policies**.<br>- Phân biệt rõ cơ chế hoạt động của IAM Role (Ủy quyền tạm thời) so với IAM User (Cấp Access Key cố định) nhằm giảm thiểu rủi ro lộ lọt thông tin. | 26/05/2026 | 26/05/2026 | <https://docs.aws.amazon.com/iam/> |
| 4   | - Tìm hiểu nâng cao về **Amazon S3 Storage Management** (Quản lý bảo mật dữ liệu, cơ chế mã hóa tệp tin và kiểm soát phiên bản nâng cao).<br>- Thiết lập sơ đồ kết nối an toàn để chuẩn bị cho bài toán tích hợp giữa EC2 và S3. | 27/05/2026 | 27/05/2026 | <https://docs.aws.amazon.com/s3/> |
| 5   | - **Thực hành Tích hợp Bảo mật hệ thống (Labs):**<br>&emsp; + Viết một IAM Policy định dạng JSON cấp quyền truy cập S3, sau đó đóng gói vào một IAM Role dành riêng cho EC2.<br>&emsp; + Gán (attach) IAM Role này vào EC2 instance và thực hành dùng dòng lệnh để tương tác với S3 bucket mà không cần cấu hình Access Key cục bộ. | 28/05/2026 | 29/05/2026 | AWS Management Console / Terminal |
| 6   | - **Thực hành Giám sát Tài nguyên nâng cao:**<br>&emsp; + Ứng dụng **AWS CloudWatch Basics** để thiết lập các biểu đồ theo dõi (Dashboards) tùy biến cho EC2 instance.<br>&emsp; + Cấu hình thu thập log hệ thống, theo dõi chặt chẽ trạng thái hoạt động của tài nguyên và báo cáo tiến độ tuần lên Mentor. | 29/05/2026 | 30/05/2026 | <https://docs.aws.amazon.com/cloudwatch/> |

### Kết quả đạt được tuần 6:

* **Quản trị Máy chủ Chuẩn Doanh nghiệp (EC2 Management):**
  * Hoàn thành xuất sắc bài thực hành khởi tạo và cấu hình tối ưu máy chủ EC2 theo đúng quy trình và tiêu chuẩn kỹ thuật được Mentor hướng dẫn.
* **Làm chủ Tư duy Bảo mật Đám mây (IAM Security):**
  * Nắm vững kiến thức cốt lõi về IAM Roles, hiểu rõ cách thức phân quyền an toàn cho ứng dụng chạy trên EC2 thông qua cơ chế nhận diện tạm thời (Temporary Credentials), loại bỏ hoàn toàn việc lưu cứng Access Key độc hại trên máy chủ.
* **Tích hợp Tự động hóa hệ thống:**
  * Triển khai thành công luồng tích hợp thực tế: Máy chủ EC2 sử dụng đặc quyền của IAM Role để tự động hóa việc upload/download và quản lý dữ liệu trực tiếp trên Amazon S3 Storage một cách mượt mà và bảo mật.
* **Giám sát & Quản lý Trực quan (CloudWatch):**
  * Làm chủ giao diện theo dõi của CloudWatch, tự tay xây dựng được biểu đồ giám sát hiệu năng (Dashboards) trực quan để kiểm soát tài nguyên hệ thống, sẵn sàng phát hiện nhanh các sự cố bất thường.