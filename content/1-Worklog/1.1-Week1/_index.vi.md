---
title: "Worklog Tuần 1"
date: 2026-04-20
weight: 1
chapter: false
pre: "<b>1.1.</b> "
---

### Mục tiêu tuần 1:
* Onboarding, hòa nhập với môi trường làm việc và các thành viên trong đội ngũ.
* Nghiên cứu tổng quan hạ tầng toàn cầu của AWS và tư duy phân quyền hệ thống.
* Thiết lập môi trường làm việc cục bộ, cấu hình bảo mật tài khoản và cài đặt bộ công cụ phát triển (Dev Tools).

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | ------------ | --------------- | --------------- |
| 2   | - Tham gia chương trình Onboarding và làm quen nội quy nội bộ.<br>- Đọc hiểu lý thuyết tổng quan về hạ tầng toàn cầu AWS Global Infrastructure (Regions, AZs, Edge Locations). | 17/04/2026 | 17/04/2026 | <https://aws.amazon.com/about-aws/global-infrastructure/> |
| 3   | - Khởi tạo tài khoản AWS thực tập sinh.<br>- Khám phá giao diện trực quan trên AWS Management Console.<br>- Cấu hình lớp bảo mật MFA (Multi-Factor Authentication) ban đầu cho tài khoản. | 18/04/2026 | 21/04/2026 | <https://aws.amazon.com/free/> |
| 4   | - Nghiên cứu sâu về dịch vụ IAM (Identity and Access Management): Định nghĩa và phân biệt User, Group, Role, Policy.<br>- Thực hành phân quyền cơ bản tuân thủ nghiêm ngặt nguyên tắc tối thiểu quyền lực "Least Privilege". | 22/04/2026 | 22/04/2026 | <https://docs.aws.amazon.com/iam/> |
| 5   | - Bắt đầu cài đặt bộ công cụ phát triển cốt lõi trên máy cục bộ:<br>&emsp; + AWS CLI (Cấu hình Access Key/Secret Key để liên kết tài khoản)<br>&emsp; + Visual Studio Code & các extension hỗ trợ Cloud/DevOps | 23/04/2026 | 23/04/2026 | <https://docs.aws.amazon.com/cli/> |
| 6   | - Tiếp tục hoàn thiện cài đặt môi trường container hóa và kiểm soát phiên bản:<br>&emsp; + Git / GitHub (Cấu hình SSH Keys)<br>&emsp; + Docker Desktop (Thiết lập môi trường ảo hóa)<br>- Chạy thử các lệnh CLI cơ bản và xử lý (troubleshoot) các lỗi cấu hình môi trường phát sinh. | 24/04/2026 | 24/04/2026 | <https://docs.docker.com/desktop/> |

### Kết quả đạt được tuần 1:

* **Môi trường & Quy trình:** Hoàn thành các thủ tục nhập môn Onboarding, nắm rõ văn hóa và quy trình phối hợp công việc trong đội ngũ nội bộ.
* **Tư duy hạ tầng Cloud:** Hiểu rõ cách phân bổ hạ tầng vật lý (Regions/AZs) của AWS để phục vụ bài toán thiết kế hệ thống có tính sẵn sàng cao (High Availability).
* **Quản lý tài khoản & Bảo mật:**
  * Kích hoạt lớp bảo mật MFA thành công cho tài khoản thực tập sinh để ngăn chặn các rủi ro an ninh cơ bản.
  * Nắm vững tư duy phân quyền với IAM, viết được các Policy cơ bản bằng JSON và phân biệt rõ ràng khi nào nên áp dụng IAM User, Group hoặc IAM Role.
* **Bộ công cụ phát triển (Dev Tools Setup):** Dành đủ thời gian để cấu hình hoàn chỉnh và giải quyết triệt để các xung đột môi trường cục bộ:
  * **AWS CLI:** Cấu hình thành công bộ định danh Access Key / Secret Key, thiết lập mặc định Region và format hiển thị dữ liệu dạng `json`.
  * **Visual Studio Code:** Chuẩn hóa môi trường viết code.
  * **Git / GitHub:** Đồng bộ mã nguồn thông qua phương thức xác thực bảo mật SSH Keys.
  * **Docker Desktop:** Kích hoạt ảo hóa thành công (WSL2/Hyper-V), sẵn sàng cho các tác vụ đóng gói ứng dụng bằng container sau này.