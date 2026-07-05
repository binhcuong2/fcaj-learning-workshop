---
title: "Worklog Tuần 10"
date: 2026-07-03
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* Tìm hiểu luồng upload CV trong AI Job Matching Platform.
* Tìm hiểu vai trò của Amazon S3 trong lưu file CV.
* Phân tích flow Frontend -> API Gateway -> Lambda Upload CV -> Amazon S3.
* Tìm hiểu backend nhận request upload CV từ frontend.
* Tìm hiểu metadata file CV gồm userId, file name, file type, S3 object key và upload time.
* Tìm hiểu thiết kế S3 key để dễ truy xuất CV theo user.
* Tìm hiểu bảo mật upload file như không public CV bucket, không hard-code bucket name nếu có thể cấu hình bằng environment variable, không lưu nội dung CV nhạy cảm vào log và chỉ cho user truy cập file thuộc về chính họ.
* Tìm hiểu `cvKey` là input cho CV Matching Flow.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | **Tìm hiểu flow upload CV từ frontend đến backend** <br>- Tìm hiểu upload request flow <br>- Kiểm tra frontend-to-API integration <br>- Xác định trách nhiệm backend upload | 22/06/2026 | 22/06/2026 | API integration notes |
| 2 | **Tìm hiểu S3 bucket và object key cho file CV** <br>- Tìm hiểu S3 object storage <br>- Xem chiến lược đặt key <br>- Kết nối user identity với file path | 23/06/2026 | 23/06/2026 | Amazon S3 Documentation |
| 3 | **Tìm hiểu Lambda xử lý metadata file CV** <br>- Xem các field metadata file <br>- Tìm hiểu upload time và file type handling <br>- Chuẩn bị metadata cho bước truy xuất sau | 24/06/2026 | 24/06/2026 | Lambda and S3 Notes |
| 4 | **Tìm hiểu bảo mật khi lưu CV trên S3** <br>- Tìm hiểu private bucket <br>- Tránh log nội dung CV nhạy cảm <br>- Kiểm tra concept access theo ownership | 25/06/2026 | 25/06/2026 | S3 Security Best Practices |
| 5 | **Tìm hiểu cách cvKey kết nối upload CV với CV Matching Flow** <br>- Tìm hiểu `cvKey` định danh CV đã upload <br>- Kết nối upload output với matching input <br>- Chuẩn bị cho AI evaluation flow | 26/06/2026 | 26/06/2026 | Project architecture notes |

### Kết quả đạt được tuần 10:

* **Hiểu S3 phù hợp để lưu file PDF thay vì DynamoDB:** Biết S3 phù hợp cho object/file storage.
* **Phân biệt file PDF và metadata/kết quả:** Hiểu PDF lưu ở S3 còn metadata hoặc kết quả có thể lưu ở DynamoDB.
* **Hiểu vai trò của cvKey:** Biết `cvKey` liên kết file CV đã upload với các bước xử lý sau.
* **Có nền tảng kết nối upload CV với AI evaluation:** Chuẩn bị cho CV Matching Flow.
* **Nhận thức rủi ro bảo mật và chi phí:** Biết file người dùng cần kiểm soát quyền truy cập và theo dõi chi phí lưu trữ.
