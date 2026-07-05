---
title: "Worklog Tuần 7"
date: 2026-07-03
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Tìm hiểu vai trò của Amazon API Gateway trong serverless backend.
* Cấu hình API Gateway bằng AWS SAM để nhận HTTP request từ frontend.
* Tìm hiểu cách API Gateway chuyển request thành event cho Lambda.
* Phân biệt public route và protected route.
* Tìm hiểu Cognito JWT Authorizer để bảo vệ API.
* Test các route public như `GET /health` và `GET /jobs/search`.
* Tìm hiểu frontend gửi token qua header `Authorization: Bearer <id_token>`.
* Ghi nhận Lambda có thể lấy user từ JWT claims, đặc biệt là `claims.sub`.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | **Tìm hiểu API Gateway và HTTP routes** <br>- Tìm hiểu vai trò API Gateway <br>- Tìm hiểu cách định nghĩa HTTP route <br>- Ghi nhận flow frontend gọi backend | 01/06/2026 | 01/06/2026 | Amazon API Gateway Documentation |
| 2 | **Cấu hình public route cho backend** <br>- Tìm hiểu public API <br>- Xem cách định nghĩa route trong SAM <br>- Chuẩn bị route không cần xác thực | 02/06/2026 | 02/06/2026 | AWS SAM API Guide |
| 3 | **Tìm hiểu protected route và Cognito JWT Authorizer** <br>- Tìm hiểu protected API <br>- Tìm hiểu cách JWT Authorizer validate request <br>- Ghi nhận access control dựa trên token | 03/06/2026 | 03/06/2026 | API Gateway JWT Authorizer Documentation |
| 4 | **Test public endpoint như /health và /jobs/search** <br>- Test concept endpoint `/health` <br>- Test concept endpoint `/jobs/search` <br>- Kiểm tra status code và response | 04/06/2026 | 04/06/2026 | API testing notes |
| 5 | **Tìm hiểu cách lấy claims.sub từ token trong Lambda** <br>- Tìm hiểu requestContext authorizer claims <br>- Tìm hiểu cách Lambda nhận diện user đã đăng nhập <br>- Chuẩn bị cho API theo user | 05/06/2026 | 05/06/2026 | Cognito JWT Claims Documentation |

### Kết quả đạt được tuần 7:

* **Hiểu API Gateway là lớp trung gian giữa frontend và Lambda:** Nắm được vai trò nhận HTTP request và invoke Lambda.
* **Biết định nghĩa route HTTP trong SAM:** Hiểu cách mô tả route backend bằng template.
* **Phân biệt public API và protected API:** Biết route nào có thể public và route nào cần xác thực.
* **Hiểu JWT Authorizer giúp xác thực người dùng:** Nắm được cách token được dùng để bảo vệ API.
* **Có nền tảng cho API theo user:** Chuẩn bị cho save favorite job, upload CV, analyze CV/job và matching history.
