---
title: "Worklog Tuần 6"
date: 2026-07-03
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Tìm hiểu vai trò của Amazon Cognito trong xác thực người dùng.
* Tìm hiểu User Pool, App Client, email verification, JWT Token, ID Token, Access Token và Refresh Token.
* Cấu hình Cognito bằng AWS SAM.
* Thiết lập đăng ký và đăng nhập bằng email/password.
* Cấu hình App Client không dùng client secret vì frontend chạy trên browser.
* Thêm output cho frontend gồm User Pool ID, App Client ID và Region.
* Test Cognito bằng AWS CLI như sign up, confirm sign up, login và refresh token.
* Tìm hiểu cách frontend lấy ID Token để gọi API cần xác thực.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | **Tìm hiểu User Pool và App Client** <br>- Tìm hiểu Cognito User Pool <br>- Tìm hiểu vai trò App Client <br>- Ôn các thành phần trong auth flow | 25/05/2026 | 25/05/2026 | Amazon Cognito Documentation |
| 2 | **Cấu hình Cognito trong SAM template** <br>- Xem cách định nghĩa resource trong SAM <br>- Ghi nhận cấu hình Cognito cần có <br>- Xác định output cần cho frontend | 26/05/2026 | 26/05/2026 | AWS SAM và Cognito Documentation |
| 3 | **Cấu hình email verification và password policy** <br>- Tìm hiểu flow xác thực email <br>- Tìm hiểu yêu cầu password <br>- Ghi nhận lỗi thường gặp khi signup | 27/05/2026 | 27/05/2026 | Cognito User Pool Guide |
| 4 | **Test sign up, confirm sign up và login bằng AWS CLI** <br>- Test luồng sign up <br>- Test confirm sign up và login <br>- Tìm hiểu refresh token behavior | 28/05/2026 | 28/05/2026 | AWS CLI Cognito Commands |
| 5 | **Tìm hiểu ID Token và cách dùng token gọi protected API** <br>- Tìm hiểu JWT token <br>- Tìm hiểu frontend gửi token đến backend <br>- Chuẩn bị cho JWT Authorizer | 29/05/2026 | 29/05/2026 | Cognito JWT Documentation |

### Kết quả đạt được tuần 6:

* **Hiểu Cognito giúp quản lý đăng ký, đăng nhập và xác thực:** Nắm được vai trò của Cognito trong authentication flow.
* **Phân biệt User Pool và App Client:** Hiểu vai trò của từng thành phần trong Cognito.
* **Hiểu vì sao frontend browser không dùng App Client Secret:** Biết không nên đặt secret trong ứng dụng chạy trên trình duyệt.
* **Biết test auth flow độc lập bằng AWS CLI:** Có thể kiểm tra sign up, confirm và login trước khi tích hợp frontend.
* **Có nền tảng bảo vệ API:** Chuẩn bị kiến thức để dùng Cognito JWT Authorizer cho protected API.
