---
title: "Worklog Tuần 5"
date: 2026-07-03
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Tìm hiểu AWS SAM và file `template.yaml`.
* Tìm hiểu cách định nghĩa Lambda, DynamoDB, API Gateway hoặc resource serverless bằng SAM.
* Tìm hiểu cấu trúc backend serverless gồm function handler, service layer, repository layer, event test JSON và DynamoDB table.
* Tìm hiểu nguyên tắc không đặt toàn bộ business logic trong Lambda handler.
* Tìm hiểu DynamoDB theo hướng nghĩ query trước, thiết kế table sau.
* Tìm hiểu Partition Key, Sort Key, GSI, Query, Scan và PAY_PER_REQUEST.
* Ghi nhận các tài nguyên có thể phát sinh chi phí như Lambda invocation, DynamoDB, API Gateway và CloudWatch Logs.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | **Tìm hiểu AWS SAM và vai trò của template.yaml** <br>- Tìm hiểu cấu trúc project SAM <br>- Tìm hiểu vai trò của `template.yaml` <br>- Ghi nhận cách định nghĩa infrastructure bằng code | 18/05/2026 | 18/05/2026 | AWS SAM Documentation |
| 2 | **Tìm hiểu Lambda handler, service layer và repository layer** <br>- Tìm hiểu cách tách backend code <br>- So sánh handler logic và service logic <br>- Tìm hiểu repository truy cập DynamoDB | 19/05/2026 | 19/05/2026 | AWS Lambda Best Practices |
| 3 | **Tìm hiểu cách dùng event JSON để test Lambda** <br>- Tạo sample event payload <br>- Test Lambda với input giả lập <br>- Kiểm tra validation và response output | 20/05/2026 | 20/05/2026 | Lambda Console Testing Guide |
| 4 | **Tìm hiểu thiết kế DynamoDB theo access pattern** <br>- Tìm hiểu partition key và sort key <br>- Tìm hiểu cách dùng GSI <br>- Phân biệt Query và Scan | 21/05/2026 | 21/05/2026 | DynamoDB Developer Guide |
| 5 | **Ghi nhận các điểm cần kiểm soát chi phí khi deploy serverless resource** <br>- Ghi nhận chi phí Lambda invocation <br>- Ghi nhận DynamoDB on-demand capacity <br>- Ghi nhận API Gateway và CloudWatch Logs cost factors | 22/05/2026 | 22/05/2026 | AWS Pricing Documentation |

### Kết quả đạt được tuần 5:

* **Hiểu SAM giúp quản lý infrastructure serverless:** Nắm được SAM hỗ trợ định nghĩa và triển khai tài nguyên serverless.
* **Biết template.yaml định nghĩa tài nguyên backend:** Hiểu `template.yaml` dùng để định nghĩa Lambda, API và DynamoDB.
* **Hiểu flow backend:** Nắm được flow Lambda Function -> Service -> Repository -> DynamoDB.
* **Hiểu vì sao DynamoDB cần thiết kế theo access pattern:** Biết cần nghĩ query trước khi thiết kế table.
* **Có nền tảng triển khai các phần sau:** Chuẩn bị kiến thức cho job ingestion, search jobs, Cognito và CV matching.
