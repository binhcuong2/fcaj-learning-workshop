---
title: "Worklog Tuần 9"
date: 2026-07-03
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Tìm hiểu cách frontend Next.js/React kết nối Cognito qua `aws-amplify`.
* Cấu hình `.env.local` cho AWS Region, Cognito User Pool ID, App Client ID và OAuth domain/callback URL nếu dùng Google Login.
* Tách logic auth ra service riêng thay vì đặt trong UI component.
* Làm việc với các hàm auth như registerWithEmail, confirmRegister, loginWithEmail, logout, getAuthUser và getIdToken.
* Hoàn thiện Google Login, Forgot Password và Reset Password.
* Tìm hiểu cách frontend lấy ID Token để gọi API backend cần xác thực.
* Kiểm tra lỗi thường gặp như sai User Pool ID, App Client ID, region, callback/logout URL, user chưa confirm email, password không đúng policy hoặc Google OAuth sai redirect URI.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | **Cấu hình Amplify Auth và biến môi trường frontend** <br>- Cấu hình biến môi trường liên quan đến Auth <br>- Kiểm tra region và Cognito IDs <br>- Kiểm tra OAuth settings khi cần | 15/06/2026 | 15/06/2026 | Amplify Auth Documentation |
| 2 | **Tách auth logic vào service** <br>- Tách auth operations khỏi UI component <br>- Định nghĩa các hàm auth dùng lại <br>- Cải thiện khả năng bảo trì | 16/06/2026 | 16/06/2026 | Frontend architecture notes |
| 3 | **Hoàn thiện login/register/confirm/logout/get token** <br>- Hoàn thiện concept register, confirm, login, logout và get token <br>- Kiểm tra các lỗi thường gặp <br>- Ghi nhận session flow | 17/06/2026 | 17/06/2026 | Cognito Auth Guide |
| 4 | **Hoàn thiện Google Login** <br>- Kiểm tra OAuth domain và callback URL <br>- Tìm hiểu Hosted UI/federated login flow <br>- Ghi nhận lỗi redirect configuration | 18/06/2026 | 18/06/2026 | Cognito Google IdP Documentation |
| 5 | **Hoàn thiện Forgot Password và Reset Password** <br>- Tìm hiểu recovery flow <br>- Kiểm tra confirmation code handling <br>- Kết nối password recovery với auth service | 19/06/2026 | 19/06/2026 | Amplify Password Recovery Guide |

### Kết quả đạt được tuần 9:

* **Hiểu cách frontend kết nối Cognito qua Amplify Auth:** Nắm được luồng kết nối auth từ frontend đến Cognito.
* **Biết tách auth logic khỏi component UI:** Giúp code dễ bảo trì và tái sử dụng hơn.
* **Hiểu vai trò `.env.local`:** Biết file này chứa cấu hình môi trường và không nên commit lên GitHub.
* **Hoàn thiện các auth flow chính:** Bao gồm login email/password, Google Login, Forgot Password và Reset Password.
* **Biết lấy ID Token cho protected API:** Chuẩn bị cho logout, route protection, upload CV và matching history.
