---
title: "Worklog Tuần 7"
date: 2026-06-01
weight: 7
chapter: false
pre: "<b>1.7.</b> "
---

### Mục tiêu tuần 7:

* Tiếp cận và làm chủ tư duy đóng gói ứng dụng hiện đại thông qua công nghệ ảo hóa cấp độ hệ điều hành (Containerization) với Docker.
* Nắm vững quy trình viết Dockerfile để tự động hóa việc đóng gói mã nguồn thành các Docker Image độc lập và chạy thử nghiệm container cục bộ.
* Sử dụng Visual Studio Code để tổng rà soát, chuẩn hóa cấu trúc và biên soạn hoàn chỉnh chuỗi báo cáo công việc (Worklog) từ Tuần 1 đến Tuần 6.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | ------------ | --------------- | --------------- |
| 2   | - Tìm hiểu tổng quan về **Docker và Container**: Định nghĩa, kiến trúc cốt lõi và sự khác biệt giữa Container với máy ảo truyền thống (Virtual Machines).<br>- Tiến hành tải xuống, cài đặt và cấu hình tối ưu **Docker Desktop** trên máy tính cục bộ. | 01/06/2026 | 01/06/2026 | <https://docs.docker.com/get-started/> |
| 3   | - Nghiên cứu sâu bộ ba thành phần cốt lõi của Docker: **Docker Image, Container và Dockerfile**.<br>- Thực hành các nhóm lệnh điều khiển Docker cơ bản (Quản lý vòng đời container: `docker run`, `docker ps`, `docker stop`, `docker rm`, `docker images`). | 02/06/2026 | 02/06/2026 | <https://docs.docker.com/engine/reference/commandline/cli/> |
| 4   | - **Thực hành Đóng gói Ứng dụng (Containerization):**<br>&emsp; + Viết một tệp cấu hình `Dockerfile` hoàn chỉnh cho một mã nguồn ứng dụng mẫu (Node.js, Python hoặc Web tĩnh).<br>&emsp; + Thực hiện lệnh `docker build` để đóng gói thành sản phẩm Image hoàn chỉnh và tiến hành chạy thử nghiệm (`docker run`) cục bộ. | 03/06/2026 | 03/06/2026 | IDE / Docker CLI |
| 5   | - **Biên soạn Chuỗi Báo cáo trên VS Code (Phần 1):**<br>&emsp; + Sử dụng **Visual Studio Code** để tập hợp lại toàn bộ ghi chú thực hành, mã nguồn bài tập từ Tuần 1 đến Tuần 3.<br>&emsp; + Rà soát tính đồng bộ, sửa lỗi định dạng Markdown bằng trình xem trước trực quan trên IDE. | 04/06/2026 | 04/06/2026 | Visual Studio Code / Markdown |
| 6   | - **Hoàn thiện Chuỗi Báo cáo trên VS Code (Phần 2):**<br>&emsp; + Tiếp tục sử dụng **Visual Studio Code** để biên soạn và chuẩn hóa dữ liệu kỹ thuật chi tiết cho các tuần từ Tuần 4 đến Tuần 6.<br>&emsp; + Đóng gói thành công toàn bộ chuỗi tài liệu **Worklog từ Tuần 1 đến Tuần 7** đạt chuẩn kỹ thuật doanh nghiệp. | 05/06/2026 | 06/06/2026 | Visual Studio Code / Markdown |

### Kết quả đạt được tuần 7:

* **Tư duy và Kỹ năng Container hóa (Docker Mastery):**
  * Hiểu rõ bản chất của công nghệ Container, phân biệt được cơ chế chia sẻ nhân (Kernel sharing) giúp tối ưu tài nguyên vượt trội so với ảo hóa phần cứng của VM.
  * Sử dụng thành thạo các câu lệnh điều khiển dòng lệnh của Docker để quản trị, kiểm tra trạng thái hoạt động, đọc logs và dọn dẹp tài nguyên lưu trữ cục bộ.
  * Tự tay thiết kế cấu trúc `Dockerfile` chuẩn hóa, hiểu cách tối ưu số lượng layer và build thành công sản phẩm Docker Image từ mã nguồn ứng dụng.
* **Hệ thống hóa Tài liệu Kỹ thuật chuyên nghiệp trên Visual Studio Code:**
  * Khai thác hiệu quả môi trường **Visual Studio Code** để biên soạn, tối ưu hóa cấu trúc hiển thị và quản lý mã nguồn tài liệu Markdown một cách trực quan, khoa học.
  * Hoàn thành xuất sắc việc rà soát, đồng bộ và đóng gói trọn vẹn chuỗi báo cáo tài liệu **Worklog từ Tuần 1 đến Tuần 6**, ghi chú rõ ràng từ lý thuyết, quy trình thực thi cho đến các bước troubleshooting lỗi hệ thống.