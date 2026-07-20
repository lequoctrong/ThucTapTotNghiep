---
title: "Worklog Tuần 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* **Xây dựng kiến trúc Backend:** Khởi tạo dự án Backend theo mô hình nhiều tầng (Controller, Service, Repository) và thiết lập kết nối với cơ sở dữ liệu PostgreSQL.
* **Phát triển RESTful API:** Xây dựng các API cốt lõi quản lý Người dùng, Sản phẩm và Danh mục thuốc phục vụ cho ứng dụng Frontend.
* **Tích hợp xác thực người dùng:** Triển khai cơ chế đăng ký, đăng nhập và phân quyền truy cập sử dụng phương thức xác thực JWT Authentication.
* **Kiểm thử API và chuẩn hóa tài liệu:** Kiểm thử toàn bộ các endpoint bằng Postman và xây dựng tài liệu Swagger/OpenAPI hoàn chỉnh.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành |
| :--- | :--- | :--- | :--- |
| 2 | **Khởi tạo Backend Project:** <br> - Khởi tạo dự án Spring Boot/Node.js. <br> - Cấu hình chuỗi kết nối PostgreSQL và xây dựng cấu trúc thư mục Controller - Service - Repository. | 22/06/2026 | 22/06/2026 |
| 3 | **Phát triển API Quản lý Người dùng:** <br> - Xây dựng các endpoint Đăng ký và Đăng nhập. <br> - Triển khai luồng xác thực JWT và cơ chế băm mật khẩu bảo mật. | 23/06/2026 | 23/06/2026 |
| 4 | **Phát triển API Quản lý Sản phẩm:** <br> - Xây dựng đầy đủ các thao tác CRUD cho sản phẩm, danh mục và tồn kho. <br> - Liên kết các mô hình dữ liệu (Data Models) với tầng lưu trữ PostgreSQL. | 24/06/2026 | 24/06/2026 |
| 5 | **Xây dựng API Giỏ hàng & Đơn hàng:** <br> - Phát triển các endpoint chức năng để quản lý các mục trong giỏ hàng. <br> - Triển khai quy trình tạo đơn hàng và cập nhật dữ liệu trạng thái thanh toán. | 25/06/2026 | 25/06/2026 |
| 6 | **Kiểm thử API & Hoàn thiện Swagger:** <br> - Thực hiện kiểm thử và xác thực tự động các endpoint bằng Postman. <br> - Sinh tài liệu cấu trúc Swagger/OpenAPI và tối ưu hóa các bộ lọc xử lý ngoại lệ toàn cục (Global Exception Handlers). | 26/06/2026 | 26/06/2026 |

---

### Chi tiết quá trình thực hiện:

Trong tuần này, đội ngũ kỹ sư tập trung xây dựng tầng Backend của hệ thống Pharmacare AI, đóng vai trò là lớp điều phối trung gian cốt lõi kết nối giao diện phía máy khách (Client) với cơ sở dữ liệu quan hệ PostgreSQL.

#### Tổng quan về kiến trúc hệ thống
Dưới đây là sơ đồ bố trí hạ tầng đám mây AWS toàn diện được triển khai để xử lý định tuyến API bảo mật, các lớp thực thi tính toán, điều phối AI tạo sinh, và đồng bộ hóa bộ lưu trữ quan hệ/vector:

![Sơ đồ kiến trúc hệ thống Pharmacare AI](/ThucTapTotNghiep/images/kientruc3.jpg)

#### 1. Khởi tạo Dự án Backend

* Khởi tạo mã nguồn backend theo mô hình phân tách tầng rõ ràng, bao gồm các thành phần: Controller, Service, Repository và Entity.
* Cấu hình kết nối cơ sở dữ liệu PostgreSQL thông qua các công cụ mã hóa ánh xạ quan hệ đối tượng (ORM) tiêu chuẩn (Spring Data JPA / Prisma / Sequelize).
* Thiết lập các quy tắc quản lý cấu hình biến môi trường tập trung và các trình xử lý nhật ký hệ thống (Application Logging).

#### 2. Phát triển API Người dùng

* Xây dựng các endpoint độc lập quản lý việc đăng ký tài khoản, xác thực thông tin và phân phối hồ sơ người dùng.
* Thực thi nghiêm ngặt các quy định bảo mật bằng cách mã hóa mật khẩu qua thuật toán BCrypt trước khi đồng bộ hóa xuống tầng lưu trữ dữ liệu.
* Triển khai các bộ lọc xác thực JWT không trạng thái (Stateless) để quản lý các yêu cầu xác thực đa nguồn (Cross-Origin) và kiểm soát truy cập dựa trên vai trò (RBAC).

#### 3. Kỹ thuật API Quản lý Sản phẩm

* Phát triển các endpoint dạng mô-đun xử lý các thay đổi về dữ liệu sản phẩm, bao gồm: tạo mới, đọc, cập nhật, xóa (CRUD) và lọc dữ liệu theo các tiêu chí nâng cao.
* Cấu trúc các lược đồ dữ liệu (Data Schemas) xử lý phân loại danh mục thuốc chuyên dụng cùng với việc tính toán số lượng tồn kho khả dụng.
* Tích hợp các ràng buộc kiểm tra tính hợp lệ của dữ liệu đầu vào (Payload Validation) và thiết lập các trình xử lý ngoại lệ nghiệp vụ toàn cục.

#### 4. Tích hợp API Giỏ hàng và Đơn hàng

* Thiết lập các endpoint quản lý các thay đổi của giỏ hàng trong thời gian thực, hỗ trợ thêm mới, sửa đổi số lượng và xóa bỏ sản phẩm một cách an toàn.
* Lập trình các quy trình giao dịch chuyển đổi các thực thể giỏ hàng đang chờ xử lý của người dùng thành đơn hàng thanh toán hoàn chỉnh.
* Đồng bộ hóa mượt mà các cập nhật hoàn thành đơn hàng tiếp theo bên trong các lược đồ cơ sở dữ liệu quan hệ.

#### 5. Kiểm thử và Chuẩn hóa Đặc tả API

* Tiến hành kiểm thử tích hợp nghiêm ngặt từ đầu đến cuối (End-to-End) trên tất cả các endpoint bằng cách sử dụng bộ công cụ Postman.
* Đánh giá các trường hợp lỗi biên (Edge-case), giảm thiểu dữ liệu lỗi không mong muốn trong khi tinh chỉnh các thông báo lỗi trả về chi tiết và trực quan.
* Sinh tài liệu đặc tả cấu trúc Swagger/OpenAPI trực quan, tạo điều kiện thuận lợi cho việc tích hợp độc lập với đội ngũ Frontend ở các chu kỳ tiếp theo.

---

### Kết quả đạt được tuần 10:

* Thiết lập và vận hành thành công kiến trúc kỹ thuật Backend theo mô hình nhiều tầng.
* Xây dựng và xác thực thành công các RESTful API hoạt động ổn định, hỗ trợ cho các dịch vụ cốt lõi: Người dùng, Sản phẩm và Đơn hàng.
* Triển khai lớp bảo mật JWT không trạng thái để giảm thiểu tối đa các rủi ro lộ lọt thông tin ở vành đai và thực thi cơ chế xác thực tài nguyên mạnh mẽ.
* Hoàn thiện các tài liệu Swagger hợp chuẩn và vượt qua các bài kiểm tra tích hợp thông qua Postman, sẵn sàng phối hợp kết nối với các thành phần Frontend ở các tuần làm việc kế tiếp.