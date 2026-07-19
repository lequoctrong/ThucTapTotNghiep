---
title: "Worklog Tuần 3"
date: 2026-05-04
weight: 3
chapter: false
pre: "<b>1.3.</b> "
---

### Mục tiêu tuần 3:

* Tìm hiểu hệ thống giám sát và quản lý tài nguyên tập trung trên môi trường điện toán đám mây.
* Thành thạo kỹ năng theo dõi hiệu năng hệ thống, phân tích dữ liệu nhật ký (logs) và thiết lập cơ chế cảnh báo tự động.
* Làm quen với các công cụ tối ưu hóa chi phí và kiểm tra sức khỏe kiến trúc hệ thống theo tiêu chuẩn AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | ------------ | --------------- | --------------- |
| 2   | - Tìm hiểu tổng quan về dịch vụ giám sát **Amazon CloudWatch** (Concepts: Metrics, Namespaces, Dimensions).<br>- Nghiên cứu lý thuyết về **Basic Monitoring & Logging** trên môi trường Cloud đám mây. | 04/05/2026 | 04/05/2026 | <https://docs.aws.amazon.com/cloudwatch/> |
| 3   | - Tìm hiểu cách thức thu thập và phân tích dữ liệu hiệu năng hệ thống máy chủ (CPU, Network, Disk).<br>- Học cách sử dụng CloudWatch Logs để truy vấn và kiểm tra các hoạt động nhật ký của EC2 instance. | 05/05/2026 | 05/05/2026 | <https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/> |
| 4   | - Nghiên cứu cơ chế hoạt động của **CloudWatch Alarms** và các trạng thái cảnh báo (OK, ALARM, INSUFFICIENT_DATA).<br>- Tìm hiểu tổng quan về **AWS Trusted Advisor** để kiểm tra và tối ưu hệ thống theo 5 khía cạnh cốt lõi. | 06/05/2026 | 06/05/2026 | <https://aws.amazon.com/premiumsupport/technology/trusted-advisor/> |
| 5   | - **Thực hành Giám sát & Đặt Ngưỡng:**<br>&emsp; + Truy cập CloudWatch Console để xem biểu đồ Metrics và Logs thực tế của EC2 instance tạo từ tuần trước.<br>&emsp; + Cấu hình tạo một **CloudWatch Alarm** cơ bản để cảnh báo khi mức sử dụng CPU của EC2 vượt ngưỡng cho phép. | 07/05/2026 | 08/05/2026 | AWS Management Console |
| 6   | - **Thực hành Quản lý Chi phí:**<br>&emsp; + Khám phá giao diện **AWS Billing Dashboard & AWS Cost Management**.<br>&emsp; + Tìm hiểu cách theo dõi chi phí thực tế, dự báo chi phí và thiết lập ngân sách (AWS Budgets) cảnh báo vượt hạn mức Free Tier. | 08/05/2026 | 09/05/2026 | AWS Billing Console |

### Kết quả đạt được tuần 3:

* **Tư duy Giám sát & Quản trị nhật ký (Monitoring & Logging):**
  * Nắm vững kiến thức cốt lõi về Amazon CloudWatch, hiểu rõ cấu trúc tổ chức dữ liệu dạng Metrics, Thống kê (Statistics) và Nhật ký (Logs) trên môi trường AWS.
  * Thành thạo kỹ năng xem, truy vấn dữ liệu log và theo dõi các chỉ số hiệu năng thời gian thực của máy chủ ảo EC2 instance.
* **Cơ chế Cảnh báo Tự động:**
  * Cấu hình triển khai thành công tính năng CloudWatch Alarms, thiết lập các bộ quy tắc giám sát tự động để kịp thời phát hiện biến động tài nguyên hệ thống (như quá tải CPU).
* **Quản lý Chi phí & Tối ưu Hệ thống:**
  * Làm quen và sử dụng thành thạo AWS Billing Dashboard để kiểm soát chi phí sử dụng dịch vụ đám mây một cách minh bạch.
  * Thiết lập thành công các bộ cảnh báo ngân sách giúp chủ động theo dõi hạn mức sử dụng tài nguyên, tránh phát sinh chi phí ngoài ý muốn trong quá trình thực tập.
  * Hiểu cách tận dụng các khuyến nghị từ AWS Trusted Advisor để kiểm tra hệ thống về mặt bảo mật, hiệu năng và tối ưu hóa chi phí.