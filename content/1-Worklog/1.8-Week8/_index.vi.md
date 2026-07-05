---
title: "Worklog Tuần 8"
date: 2026-07-03
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Tìm hiểu luồng thu thập dữ liệu việc làm trong AI Job Matching Platform.
* Tìm hiểu Lambda lấy dữ liệu job từ SerpApi Google Jobs API.
* Tìm hiểu vai trò của Amazon SQS trong việc tách bước fetch jobs và xử lý jobs.
* Tìm hiểu pipeline Fetch Jobs Lambda -> Raw Jobs Queue -> Process Jobs Lambda -> Normalize/Deduplicate Lambda -> DynamoDB Jobs Table.
* Tìm hiểu chuẩn hóa dữ liệu job gồm title, company name, location, posted date và hash.
* Tìm hiểu deduplication bằng hash và fuzzy matching.
* Ghi nhận dữ liệu từ API ngoài có thể không đồng nhất, thiếu field, trùng dữ liệu và không được hard-code API key.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | **Tìm hiểu SerpApi Google Jobs API và dữ liệu job thô** <br>- Tìm hiểu response từ external job API <br>- Xem các field job thô <br>- Ghi nhận vấn đề dữ liệu không đồng nhất | 08/06/2026 | 08/06/2026 | SerpApi Documentation |
| 2 | **Tìm hiểu Fetch Jobs Lambda và Raw Jobs Queue** <br>- Tìm hiểu trách nhiệm fetch Lambda <br>- Tìm hiểu lý do gửi raw jobs vào SQS <br>- Ghi nhận decoupling bằng queue | 09/06/2026 | 09/06/2026 | Amazon SQS Documentation |
| 3 | **Tìm hiểu Process Jobs Lambda và Normalize/Deduplicate Lambda** <br>- Tìm hiểu pipeline xử lý <br>- Tìm hiểu flow normalization <br>- Ghi nhận mục tiêu deduplication | 10/06/2026 | 10/06/2026 | AWS Lambda and SQS Guide |
| 4 | **Tìm hiểu chuẩn hóa title, company, location và posted date** <br>- Tìm hiểu các field job phổ biến <br>- Tìm hiểu mục tiêu cleanup dữ liệu <br>- Chuẩn bị job record nhất quán | 11/06/2026 | 11/06/2026 | Data normalization notes |
| 5 | **Tìm hiểu lưu job đã xử lý vào DynamoDB Jobs Table** <br>- Tìm hiểu cấu trúc item DynamoDB <br>- Tìm hiểu output sau hash/fuzzy matching <br>- Kết nối dữ liệu job với search và matching | 12/06/2026 | 12/06/2026 | DynamoDB Documentation |

### Kết quả đạt được tuần 8:

* **Hiểu lý do tách job ingestion thành nhiều bước:** Biết vì sao cần tách fetch, process, normalize và storage.
* **Biết vai trò của SQS:** Hiểu SQS giúp giảm coupling giữa fetch và process.
* **Hiểu vì sao cần normalize trước khi lưu DynamoDB:** Biết dữ liệu cần được chuẩn hóa để dễ tìm kiếm và matching.
* **Hiểu deduplication:** Nắm được hash và fuzzy matching hỗ trợ phát hiện job trùng.
* **Có nền tảng cho search jobs và matching:** Chuẩn bị dữ liệu job để so sánh với CV/job description.
