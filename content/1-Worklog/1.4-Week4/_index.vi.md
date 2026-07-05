---
title: "Worklog Tuần 4"
date: 2026-07-03
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Tìm hiểu mô hình serverless trên AWS.
* Tìm hiểu vai trò của AWS Lambda, Amazon API Gateway, Amazon DynamoDB và Amazon CloudWatch Logs.
* Tìm hiểu cách Lambda nhận event, xử lý logic và trả response.
* Tìm hiểu API Gateway là cổng nhận request HTTP từ frontend.
* Tìm hiểu DynamoDB ở mức cơ bản gồm Table, Item, Partition Key, Sort Key, Query và Scan.
* Thực hành hoặc theo dõi cách test Lambda bằng JSON event giả lập.
* Tìm hiểu CloudWatch Logs để kiểm tra lỗi Lambda.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | **Tìm hiểu mô hình serverless và lợi ích** <br>- Tìm hiểu serverless architecture <br>- So sánh serverless với quản lý server truyền thống <br>- Ghi nhận lợi ích vận hành | 11/05/2026 | 11/05/2026 | AWS Serverless Documentation |
| 2 | **Tìm hiểu AWS Lambda và xử lý event** <br>- Tìm hiểu Lambda handler <br>- Tìm hiểu event input và response output <br>- Ghi nhận cách đặt backend logic | 12/05/2026 | 12/05/2026 | AWS Lambda Documentation |
| 3 | **Tìm hiểu API Gateway và Lambda event** <br>- Tìm hiểu HTTP routes <br>- Tìm hiểu cách API Gateway chuyển request sang Lambda <br>- Ôn flow frontend gọi backend | 13/05/2026 | 13/05/2026 | Amazon API Gateway Documentation |
| 4 | **Tìm hiểu DynamoDB cơ bản** <br>- Tìm hiểu Table, Item, Partition Key và Sort Key <br>- Phân biệt Query và Scan <br>- Ghi nhận access pattern trong NoSQL | 14/05/2026 | 14/05/2026 | Amazon DynamoDB Documentation |
| 5 | **Tìm hiểu CloudWatch Logs và test Lambda bằng event JSON** <br>- Test Lambda bằng sample JSON event <br>- Kiểm tra execution logs <br>- Tìm hiểu cách log hỗ trợ debug lỗi | 15/05/2026 | 15/05/2026 | CloudWatch Logs Documentation |

### Kết quả đạt được tuần 4:

* **Hiểu serverless giúp giảm việc quản lý server:** Nắm được serverless giảm phần vận hành server trực tiếp.
* **Biết Lambda dùng để xử lý backend logic:** Hiểu Lambda nhận event, xử lý logic và trả response.
* **Hiểu API Gateway là lớp nhận request từ frontend:** Nắm được API Gateway là entry point HTTP cho backend serverless.
* **Nắm được DynamoDB cơ bản:** Hiểu DynamoDB là NoSQL database phù hợp cho truy vấn theo key.
* **Biết test Lambda bằng JSON event:** Có thể test logic Lambda trước khi nối với frontend.
