---
title: "Worklog Tuần 4"
date: 2026-05-11
weight: 4
chapter: false
pre: "<b>1.4.</b> "
---

### Mục tiêu tuần 4:

* Làm quen với tư duy thiết kế hệ thống hiện đại qua mô hình máy chủ ảo hóa ẩn danh (Serverless) và tự động hóa.
* Nắm vững nguyên lý hoạt động cốt lõi của hàm xử lý tính toán AWS Lambda và kiến trúc hướng sự kiện (Event-driven Architecture).
* Thực hành xây dựng và phân phối API không máy chủ bằng cách tích hợp Lambda với Amazon API Gateway.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | ------------ | --------------- | --------------- |
| 2   | - Tìm hiểu khái niệm tổng quan về mô hình **Introduction to Serverless** và lợi ích so với kiến trúc truyền thống.<br>- Nghiên cứu tài liệu **AWS Lambda Fundamentals** (Cách thức hoạt động, Execution Role, Timeout, Memory). | 11/05/2026 | 11/05/2026 | <https://docs.aws.amazon.com/lambda/> |
| 3   | - Nghiên cứu sâu về kiến trúc hướng sự kiện **Event-driven Architecture** trên đám mây.<br>- Tìm hiểu các cơ chế kích hoạt hàm (Event Triggers) từ các nguồn dữ liệu khác nhau trên AWS (như S3, CloudWatch, hoặc API). | 12/05/2026 | 12/05/2026 | <https://aws.amazon.com/event-driven-architecture/> |
| 4   | - Tìm hiểu lý thuyết nền tảng về dịch vụ quản lý API **API Gateway Basics**.<br>- Nghiên cứu các khái niệm về HTTP API, REST API, cơ chế định tuyến (Routing) và tích hợp (Integration) với các dịch vụ backend. | 13/05/2026 | 13/05/2026 | <https://docs.aws.amazon.com/apigateway/> |
| 5   | - **Thực hành Khởi tạo & Kích hoạt Hàm:**<br>&emsp; + Tạo một AWS Lambda function cơ bản (sử dụng Node.js hoặc Python) trên Console.<br>&emsp; + Thực hành cấu hình và giả lập các Event Payload để kích hoạt (trigger) kiểm tra hoạt động của Lambda function. | 14/05/2026 | 14/05/2026 | AWS Management Console |
| 6   | - **Thực hành Tích hợp hệ thống Serverless API:**<br>&emsp; + Khởi tạo một HTTP/REST API trên Amazon API Gateway.<br>&emsp; + Cấu hình tích hợp (Integration) để API Gateway gọi trực tiếp đến AWS Lambda function.<br>&emsp; + Triển khai (Deploy) API và sử dụng các công cụ (Web Browser/Postman) để kiểm tra luồng dữ liệu đầu cuối. | 15/05/2026 | 16/05/2026 | AWS Console / API Client |

### Kết quả đạt được tuần 4:

* **Tư duy Kiến trúc Không máy chủ (Serverless Mindset):**
  * Nắm vững triết lý thiết kế của Serverless, hiểu rõ lợi ích về mặt tối ưu chi phí (Pay-as-you-go) và giảm thiểu gánh nặng quản trị hạ tầng vật lý.
  * Hiểu sâu cơ chế hoạt động của AWS Lambda, cách cấu hình bộ nhớ, thời gian chạy tối đa (Timeout) và vai trò của IAM Execution Role trong việc phân quyền cho hàm.
* **Tự động hóa dựa trên Sự kiện (Event-driven Automation):**
  * Làm chủ tư duy lập trình hướng sự kiện, biết cách thiết lập và cấu hình các Event Source để tự động kích hoạt mã nguồn khi có biến động hệ thống.
* **Phân phối Serverless API:**
  * Hiểu rõ vai trò cửa ngõ của Amazon API Gateway trong việc tiếp nhận, định tuyến và bảo mật các luồng yêu cầu HTTP từ Internet.
  * Triển khai xây dựng thành công một hệ thống API Serverless hoàn chỉnh: Người dùng gọi API Gateway -> Kích hoạt AWS Lambda xử lý -> Trả kết quả về cho client một cách mượt mà.