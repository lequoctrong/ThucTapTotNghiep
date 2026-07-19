---
title: "Worklog Tuần 8"
date: 2026-06-08
weight: 8
chapter: false
pre: "<b>1.8.</b> "
---

### Mục tiêu tuần 8:

* Triển khai bài Lab tổng hợp (Comprehensive Lab) để liên kết, vận hành và kiểm tra kết nối đồng bộ giữa các dịch vụ cốt lõi trên AWS.
* Thực hành phát hiện, phân tích và xử lý triệt để các xung đột hệ thống mạng, phân quyền và lưu trữ phát sinh trong quá trình cấu hình thực tế.
* Sử dụng Visual Studio Code để chuẩn hóa cấu trúc, biên soạn và đóng gói hoàn chỉnh chuỗi báo cáo công việc (Worklog) cho cả Tuần 7 và Tuần 8.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | ------------ | --------------- | --------------- |
| 2   | - **Bài Lab Tổng Hợp - Khởi tạo Hạ tầng:**<br>&emsp; + Phân quyền Người dùng/Nhóm người dùng nghiêm ngặt bằng **AWS IAM**.<br>&emsp; + Khởi chạy máy ảo **Amazon EC2** trong mạng bảo mật và cấu hình dịch vụ lưu trữ đối tượng **Amazon S3**. | 08/06/2026 | 08/06/2026 | AWS Management Console |
| 3   | - **Bài Lab Tổng Hợp - Tích hợp & Giám sát:**<br>&emsp; + Cấu hình kiểm tra toàn diện kết nối giữa EC2, IAM và S3.<br>&emsp; + Thiết lập **Amazon CloudWatch** để cấu hình bảng giám sát và theo dõi chặt chẽ trạng thái hoạt động theo thời gian thực của toàn bộ tài nguyên. | 09/06/2026 | 09/06/2026 | <https://docs.aws.amazon.com/> |
| 4   | - **Ghi nhật ký & Xử lý sự cố (Troubleshooting):**<br>&emsp; + Lưu lại chi tiết (Copy/Logs) toàn bộ quá trình thực thi quy trình.<br>&emsp; + Tập trung phân tích, rà soát và xử lý các vấn đề lỗi kết nối mạng, từ chối quyền truy cập (Access Denied) dính phải trong bài Lab. | 10/06/2026 | 10/06/2026 | Terminal Logs / Nhật ký thực hành |
| 5   | - **Biên soạn Báo cáo Kỹ thuật trên VS Code (Phần 1):**<br>&emsp; + Sử dụng **Visual Studio Code** để hệ thống hóa thông tin, viết và cấu trúc tài liệu **Worklog Tuần 7** về mảng Công nghệ Container hóa Docker.<br>&emsp; + Rà soát định dạng hiển thị Markdown trực quan trên IDE. | 11/06/2026 | 11/06/2026 | Visual Studio Code / Markdown |
| 6   | - **Hoàn thiện chuỗi tài liệu Báo cáo trên VS Code (Phần 2):**<br>&emsp; + Tiếp tục sử dụng **Visual Studio Code** để biên soạn chi tiết dữ liệu cho **Worklog Tuần 8** dựa trên kết quả thực thi bài Lab tổng hợp và nhật ký fix bug.<br>&emsp; + Kiểm tra liên kết cấu trúc, chuẩn hóa mã nguồn Markdown và xuất bản tệp báo cáo hoàn chỉnh. | 12/06/2026 | 13/06/2026 | Visual Studio Code / Markdown |

### Kết quả đạt được tuần 8:

* **Làm chủ Kiến trúc Tích hợp Hệ thống (AWS System Integration):**
  * Hoàn thành xuất sắc bài Lab tổng hợp quy mô lớn, vận hành thành công luồng xử lý khép kín: Khởi tạo thực thể phân quyền (IAM) -> Quản lý tính toán (EC2) -> Đồng bộ lưu trữ dữ liệu (S3) -> Giám sát tập trung (CloudWatch).
  * Đảm bảo tính bảo mật tuyệt đối giữa các dịch vụ nhờ cấu hình chính xác các luật tường lửa và chính sách phân quyền.
* **Kỹ năng Xử lý sự cố Thực tế (Troubleshooting & Remediation):**
  * Định vị chính xác các điểm nghẽn hệ thống (Network bottleneck, IAM Access Denied) và ghi lại toàn bộ quy trình xử lý lỗi làm tài liệu kỹ thuật sau này.
* **Thành thạo Đóng gói Tài liệu Kỹ thuật trên Visual Studio Code:**
  * Sử dụng thành thạo môi trường **Visual Studio Code** cùng các extension hỗ trợ để biên soạn, tối ưu và quản lý mã nguồn tài liệu định dạng Markdown một cách trực quan, khoa học.
  * Hoàn thiện và xuất bản thành công hai bộ báo cáo **Worklog Tuần 7 và Tuần 8** đạt chuẩn kỹ thuật doanh nghiệp, đảm bảo tính mạch lạc từ lý thuyết đến thực hành xử lý lỗi sự cố.