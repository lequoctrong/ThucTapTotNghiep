---
title: "Worklog Tuần 12"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu triển khai:

* **Triển khai Kiến trúc static Frontend Web qua Amazon S3:** Khởi tạo một instance Amazon S3 bucket có tính sẵn sàng cao và bảo mật, được tối ưu hóa để lưu trữ và phân phối các tài nguyên tĩnh production (`index.html`, các gói Javascript bundle, cấu trúc asset) cho giao diện dashboard phía client-side của **PharmaCare AI**.
* **Tăng tốc mạng lưới phân phối nội dung toàn cầu (CDN) qua Amazon CloudFront:** Thiết lập một distribution Amazon CloudFront cấu hình edge-cached ánh xạ tới static origin S3, cung cấp cơ chế bảo mật HTTPS bắt buộc, giảm độ trễ phản hồi phía client và áp dụng các chiến lược bộ nhớ đệm nghiêm ngặt ở cấp độ Edge.
* **Xử lý định tuyến SPA Client-Side & Quản lý bộ nhớ đệm tùy chỉnh:** Khắc phục lỗi định tuyến phía client của ứng dụng trang đơn (SPA) bằng cách cấu hình các trang phản hồi lỗi tùy chỉnh `403` và `404` để tự động fallback mượt mà về `/index.html`. Xử lý quản lý bộ nhớ đệm phân phối thông qua quy trình xóa cache (invalidation) hệ thống một cách có mục tiêu.
* **Đồng bộ hóa tích hợp định danh phân tán & Lên kế hoạch quản lý tên miền:** Cập nhật các endpoint phân phối production trực tiếp vào ranh giới chuyển hướng (redirect) của Amazon Cognito User Pool, đồng thời tận dụng cổng quản lý Amazon Route 53 để chuẩn bị kế hoạch phân định tài nguyên tên miền tùy chỉnh.

---

### Các công việc cần triển khai trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành |
| :--- | :--- | :--- | :--- |
| 2 | **Khởi tạo kiến trúc S3 Static Bucket:** <br> - Cấu hình khởi tạo tài nguyên lưu trữ tĩnh độc nhất `pharmacare-frontend-web-phu-2026` tại khu vực `ap-southeast-1`. | 20/07/2026 | 20/07/2026 |
| 3 | **Biên dịch Frontend Production & Triển khai Đối tượng:** <br> - Biên dịch các file tĩnh React production tại môi trường local và đồng bộ hóa các gói raw bundle (`assets/`, `index.html`, `favicon.svg`) trực tiếp vào thư mục asset S3 mục tiêu. | 21/07/2026 | 21/07/2026 |
| 4 | **Thiết lập CDN CloudFront Distribution:** <br> - Triển khai mạng lưới `pharmacare-frontend-distribution` sử dụng nền tảng cluster edge toàn cầu. <br> - Chỉ định cấu hình Default Root Object trỏ an toàn về `/index.html`. | 22/07/2026 | 22/07/2026 |
| 5 | **Cấu hình Phản hồi lỗi SPA & Xóa bộ nhớ đệm CDN:** <br> - Cấu hình các trang lỗi tùy chỉnh của CloudFront để chuyển đổi các bất thường `403`/`404` quay về mã HTTP `200` tại `/index.html`. <br> - Kích hoạt tác vụ xóa cache asset (invalidation) nhắm mục tiêu vào đường dẫn `/*`. | 23/07/2026 | 23/07/2026 |
| 6 | **Tích hợp Định danh Cognito & Lên kế hoạch Domain Route 53:** <br> - Ràng buộc tên miền production CloudFront CDN đang hoạt động vào các tham số Callback và Sign-out được cho phép trong Cognito. <br> - Kiểm tra tính khả dụng của vùng tên miền `pharmacare.ai`. | 24/07/2026 | 24/07/2026 |

---

### Chi tiết quá trình thực hiện:

Trong chu kỳ triển khai tuần này, đội ngũ kỹ sư hạ tầng đã xây dựng lớp phân phối công khai của hệ thống, đưa kiến trúc web từ các môi trường chạy local riêng lẻ lên một lộ trình phân phối production trên cloud chuẩn doanh nghiệp:

#### 1. Khởi tạo môi trường lưu trữ Cloud thông qua Amazon S3
* Khởi động quy trình thiết lập thông qua giao diện điều khiển Amazon S3 Storage để triển khai một container chứa asset độc lập mang tên `pharmacare-frontend-web-phu-2026`.
* Ánh xạ vùng lưu trữ vào cấu trúc node APAC tại địa phương (`ap-southeast-1` Vùng Singapore) chạy một storage tier mục đích chung Global Namespace tiêu chuẩn để duy trì đồng bộ hóa asset nghiêm ngặt.

![Cấu hình các tham số S3 Bucket](/ThucTapTotNghiep/images/deploy1.jpg)

![Xác nhận cấp phát instance S3 Bucket trống ban đầu](/ThucTapTotNghiep/images/deploy2.jpg)

#### 2. Biên dịch và đồng bộ hóa các sản phẩm tĩnh của ứng dụng
* Chạy các script deployment tại local trên source code dự án để kết xuất các package chunk đã được tối ưu hóa cho production.
* Đồng bộ hóa và đẩy các lớp cấu trúc (bao gồm các thư mục hệ thống `assets/`, `index.html`, `favicon.svg`, và các định dạng vector tùy chỉnh `icons.svg`) trực tiếp vào engine lưu trữ asset S3 với sự đồng bộ timestamp đầy đủ.

![Kiểm tra các đối tượng tĩnh đã tải lên trong S3 Bucket](/ThucTapTotNghiep/images/deploy3.jpg)

#### 3. Triển khai mạng lưới phân phối toàn cầu Amazon CloudFront Distribution
* Triển khai một lớp CDN cluster cho môi trường production dưới tên nhận diện hệ thống `pharmacare-frontend-distribution`.
* Engine tại các edge node vừa thiết lập đã cấu hình thành công profile URL động (`d3tm5364zrtmpq.cloudfront.net`), đảm bảo các tham số tối ưu hóa bộ nhớ đệm toàn cầu và thiết lập Default Root Object to intercept các yêu cầu trực tiếp tại tệp `index.html`.

![Kiểm tra trang tổng quan cấu hình chung của CloudFront](/ThucTapTotNghiep/images/deploy4.jpg)

#### 4. Tối ưu hóa các tuyến định tuyến SPA Client-Side & Thực hiện Xóa bộ nhớ đệm (Invalidation)
* Do React sử dụng mô hình định tuyến Virtual DOM (client-side routing), các hoạt động truy cập liên kết sâu (deep-linking) trực tiếp thường dẫn đến các lỗi tìm kiếm đối tượng tiêu chuẩn của AWS.
* Giải quyết triệt để vấn đề kiến trúc này bằng cách xây dựng các chiến lược đánh chặn tùy chỉnh trong Error Pages: ánh xạ các mã bất thường `403` và `404` để định hướng trực tiếp vào `/index.html` đi kèm một cấu trúc ghi đè phản hồi HTTP thành `200 OK`.

![Cấu hình phản hồi trang lỗi tùy chỉnh cho tính tương thích SPA](/ThucTapTotNghiep/images/deploy5.jpg)

* Kích hoạt một yêu cầu xóa cache hạ tầng (`Invalidation ID: I22BWFD9RT2N26X729DOHWEPR9`) chỉ định rõ ràng cho pattern đường dẫn `/*`. Thao tác này buộc CloudFront hủy bỏ các lớp cache cũ trên tất cả các edge node toàn cầu và truy xuất mã nguồn mới nhất từ S3 origin.

![Thực hiện theo dõi tác vụ xóa bộ nhớ đệm Asset Cache Invalidation](/ThucTapTotNghiep/images/deploy6.png)

#### 5. Ràng buộc các vùng Callback định danh & Kiểm tra tính khả dụng của Tên miền
* Mở không gian làm việc Amazon Cognito Identity Management để mở rộng cấu hình cho App Client `pharmacare-web-client`.
* Ràng buộc các cấu hình đường dẫn URL production đã xác thực (`https://d3tm5364zrtmpq.cloudfront.net/`) trực tiếp song song với các đường dẫn môi trường phát triển local (`http://localhost:5173/`) dưới các bộ tham số **Allowed callback URLs** và **Allowed sign-out URLs**, cho phép lớp UI cloud thực hiện các quy trình ủy quyền OAuth2 một cách an toàn.

![Cập nhật ranh giới chuyển hướng Amazon Cognito App Client](/ThucTapTotNghiep/images/deploy7.png)

* Di chuyển đến cổng đăng ký tên miền Amazon Route 53 để lên kế hoạch ánh xạ mục tiêu cho domain doanh nghiệp (`pharmacare.ai`). Hệ thống phát hiện trạng thái lock đăng ký hiện tại trên tên miền chính và khuyến nghị các bản ghi dự phòng để thiết lập sơ đồ DNS production vào tuần tới.

![Kiểm tra cấu hình đăng ký vùng Domain trong Route 53](/ThucTapTotNghiep/images/deploy8.jpg)

---

### Kết quả đạt được tuần 12:
* **Phân phối Production tĩnh không cần máy chủ (Zero-Server):** Di chuyển thành công từ các runner cục bộ local sang một cấu trúc CDN serverless có khả năng mở rộng mạnh mẽ, kết hợp các tham số hosting của Amazon S3 với các cạnh phân phối của Amazon CloudFront.
* **Đồng bộ định tuyến định danh OAuth2:** Các giao diện callback được phép bên trong thư mục Amazon Cognito đã được đội ngũ kỹ sư cập nhật an toàn để chấp nhận các bắt tay bảo mật đến từ URL CloudFront công khai.
* **Hoàn thiện hành vi ứng dụng trang đơn (SPA):** Đạt được sự linh hoạt định tuyến trình duyệt gốc trên tất cả các trang động React thông qua cơ chế ghi đè điều hướng lỗi CloudFront, đồng thời đảm bảo mã nguồn triển khai theo thời gian thực thông qua các lệnh invalidation mục tiêu.