---
title: "Worklog Tuần 1"
date: 2026-07-03
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1:

* Làm quen với cấu trúc chương trình học, cách ghi nhận tiến độ và yêu cầu của báo cáo dạng workshop.
* Tìm hiểu vai trò của AWS Identity and Access Management (IAM) trong việc quản lý định danh và phân quyền trên AWS.
* Phân biệt các thành phần IAM cơ bản như IAM User, IAM Group, IAM Role và IAM Policy.
* Tìm hiểu nguyên tắc Least Privilege để cấp quyền tối thiểu cần thiết cho người dùng hoặc dịch vụ.
* Tìm hiểu AWS Budget để theo dõi chi phí sử dụng AWS và hạn chế rủi ro phát sinh phí ngoài dự kiến.
* Nhận diện lý do không nên dùng root account cho các thao tác học tập hoặc triển khai thông thường.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | **Làm quen với chương trình học và cấu trúc workshop** <br>- Xem tổng quan các mục cần hoàn thành trong báo cáo <br>- Nắm cách tổ chức nội dung theo từng tuần <br>- Xác định cách ghi worklog gồm công việc đã làm và kết quả đạt được | 20/04/2026 | 20/04/2026 | Tài liệu hướng dẫn chương trình / FCAJ workshop template |
| 2 | **Tìm hiểu AWS IAM** <br>- Tìm hiểu IAM User, IAM Group, IAM Role và IAM Policy <br>- Phân tích vai trò của IAM trong việc kiểm soát truy cập tài nguyên AWS <br>- So sánh IAM với cơ chế phân quyền trong backend/web application | 21/04/2026 | 21/04/2026 | [AWS IAM Documentation](https://docs.aws.amazon.com/iam/) |
| 3 | **Tìm hiểu Access Control trong IAM** <br>- Tìm hiểu cách cấp quyền cho user/group/role <br>- Tìm hiểu cách policy quyết định action nào được phép hoặc bị từ chối <br>- Ghi nhận rủi ro khi cấp quyền quá rộng | 22/04/2026 | 22/04/2026 | [Lab 02: AWS IAM Access Control](https://000002.awsstudygroup.com/) |
| 4 | **Tìm hiểu nguyên tắc Least Privilege** <br>- Tìm hiểu lý do chỉ nên cấp quyền tối thiểu cần thiết <br>- Ghi nhận các lỗi thường gặp như dùng AdministratorAccess quá rộng hoặc dùng root account cho công việc hằng ngày | 23/04/2026 | 23/04/2026 | AWS Security Best Practices |
| 5 | **Tìm hiểu AWS Budget và kiểm soát chi phí** <br>- Tìm hiểu cách AWS Budget hỗ trợ theo dõi chi phí <br>- Tìm hiểu Cost Budget và cảnh báo ngân sách <br>- Ghi nhận các tài nguyên AWS có thể phát sinh chi phí khi thực hành | 24/04/2026 | 24/04/2026 | [Lab 07: Cost Management with AWS Budget](https://000007.awsstudygroup.com/) |

### Kết quả đạt được tuần 1:

* **Hiểu được vai trò của IAM trong AWS:** Nắm được IAM là dịch vụ cốt lõi dùng để quản lý định danh, phân quyền và kiểm soát truy cập vào tài nguyên AWS.
* **Phân biệt được các thành phần IAM cơ bản:** Hiểu sự khác nhau giữa IAM User, IAM Group, IAM Role và IAM Policy, từ đó biết khi nào nên dùng từng thành phần.
* **Nắm được nguyên tắc Least Privilege:** Hiểu rằng không nên cấp quyền quá rộng nếu không cần thiết, vì điều này có thể tạo rủi ro bảo mật cho tài khoản AWS.
* **Nhận thức được rủi ro khi dùng root account:** Biết rằng root account chỉ nên dùng cho các thao tác đặc biệt, không nên dùng cho công việc học tập hoặc triển khai hằng ngày.
* **Hiểu cách AWS Budget hỗ trợ kiểm soát chi phí:** Nắm được vai trò của Budget trong việc theo dõi chi phí, cảnh báo ngân sách và hạn chế rủi ro phát sinh phí ngoài dự kiến.
* **Tạo nền tảng cho các tuần tiếp theo:** Có kiến thức cơ bản về bảo mật và chi phí để tiếp tục học networking, EC2, serverless và các dịch vụ AWS khác.
