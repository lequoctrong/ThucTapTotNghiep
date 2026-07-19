---
title: "Worklog Tuần 9"
date: 2026-06-15
weight: 9
chapter: false
pre: "<b>1.9.</b> "
---

### Mục tiêu tuần 9:

* Tìm hiểu và thành thạo giải pháp quản lý, lưu trữ kho ảnh container tập trung trên Cloud bằng Amazon ECR.
* Nắm vững các khái niệm và cơ chế điều phối container nâng cao của Amazon ECS (Cluster, Task Definition, Service).
* Triển khai thành công ứng dụng container hóa trên môi trường Serverless (AWS Fargate), kết hợp cấu hình mạng và phân quyền an toàn.
* Tối ưu hóa chi phí bằng cách thực hiện quy trình dọn dẹp (clean up) tài nguyên sau khi hoàn thành thực hành.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | ------------ | --------------- | --------------- |
| 2   | - Tìm hiểu dịch vụ lưu trữ kho ảnh **Amazon ECR** (Elastic Container Registry) trên đám mây.<br>- **Thực hành với AWS CLI:** Tiến hành xác thực (authenticate), gắn thẻ (`docker tag`) và đẩy (`docker push`) Docker Image từ máy cục bộ lên Amazon ECR. | 15/06/2026 | 16/06/2026 | <https://docs.aws.amazon.com/ecr/> |
| 3   | - Nghiên cứu các khái niệm cốt lõi của dịch vụ điều phối container **Amazon ECS** (Elastic Container Service).<br>- Phân biệt chi tiết vai trò cấu trúc giữa: **Cluster** (Cụm tài nguyên), **Task Definition** (Bản thiết kế container) và **Service** (Trạng thái duy trì). | 16/06/2026 | 16/06/2026 | <https://docs.aws.amazon.com/ecs/> |
| 4   | - **Thực hành Thiết lập Hạ tầng Mạng & Bảo mật cho ECS:**<br>&emsp; + Quy hoạch mạng (VPC, Subnets) an toàn để phân phối các ECS Tasks.<br>&emsp; + Phân quyền chặt chẽ với IAM Role (Task Role / Task Execution Role) và cấu hình lớp tường lửa Security Group. | 17/06/2026 | 17/06/2026 | AWS Management Console |
| 5   | - **Thực hành Triển khai Container Serverless:**<br>&emsp; + Tạo Task Definition trỏ đến Image trên ECR và khởi chạy ứng dụng mẫu dạng Container sử dụng kiến trúc Serverless với **AWS Fargate** (không cần quản lý máy chủ EC2).<br>&emsp; + Kiểm tra luồng truy cập của ứng dụng qua Internet. | 18/06/2026 | 18/06/2026 | AWS ECS Console |
| 6   | - **Kiểm tra, Dọn dẹp Tài nguyên & Biên soạn Worklog:**<br>&emsp; + Kiểm tra log ứng dụng, tối ưu hóa tài nguyên và thực hiện quy trình hủy/xóa (clean up) các dịch vụ ECR, ECS, Fargate để tránh phát sinh chi phí ngoài ý muốn.<br>&emsp; + Viết và chuẩn hóa tài liệu **Worklog Tuần 9**. | 19/06/2026 | 20/06/2026 | AWS Console / Markdown Editor |

### Kết quả đạt được tuần 9:

* **Quản lý Kho ảnh Container đám mây (Amazon ECR):**
  * Làm chủ dòng lệnh AWS CLI để tương tác với kho lưu trữ từ xa: Đăng nhập thành công, thay đổi tag định danh và đẩy các Docker Image cục bộ lên môi trường lưu trữ tập trung Amazon ECR an toàn.
* **Tư duy Điều phối Container Serverless (ECS & AWS Fargate):**
  * Nắm vững kiến thức chuyên sâu về Amazon ECS, hiểu rõ vòng đời vận hành của một container từ bước lập cấu hình (Task Definition) cho đến quản lý vận hành (Service).
  * Khởi chạy thành công ứng dụng container hóa trên nền tảng AWS Fargate, hiểu được lợi ích của việc chạy container dạng Serverless khi không phải lo nghĩ về gánh nặng quản trị hay vá lỗi cho hệ điều hành máy chủ (EC2).
* **Thiết lập An ninh Hệ thống mạng mã hóa:**
  * Cấu hình chính xác phân vùng mạng VPC/Subnet và viết luật Security Group hợp lệ cho phép các tác vụ ECS Task giao tiếp an toàn.
  * Phân biệt và áp dụng chuẩn xác IAM Task Role (quyền của ứng dụng bên trong container) và Task Execution Role (quyền của ECS agent kéo image từ ECR).
* **Kiểm soát Tối ưu Chi phí (Cost Awareness):**
  * Hình thành thói quen vận hành đám mây chuẩn nghiệp dư: Thực thi kiểm tra hệ thống và dọn dẹp sạch sẽ (clean up) mọi tài nguyên thừa sau bài Lab, ngăn chặn triệt để các nguy cơ phát sinh hóa đơn tự động ngoài ý muốn.