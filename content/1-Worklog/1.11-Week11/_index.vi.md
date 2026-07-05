---
title: "Worklog Tuần 11"
date: 2026-07-03
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Phân tích CV Matching Flow trong AI Job Matching Platform.
* Xác định các bước chính gồm Matching Trigger, Text Extraction, AI Evaluation và Result Storage.
* Xác định input gồm userId, cvKey và jobId.
* Test Lambda bằng event giả lập API Gateway trên Lambda Console.
* Phân tích Lambda lấy CV từ S3 thông qua cvKey.
* Tìm hiểu trích xuất text từ PDF để chuẩn bị dữ liệu cho AI model.
* Phân tích lấy Job Description từ DynamoDB Jobs Table.
* Tìm hiểu AI đánh giá độ phù hợp giữa CV text và Job Description.
* Thiết kế output JSON gồm overallScore, skillsScore, experienceScore, educationScore, summary, matchedSkills, missingSkills và suggestions.
* Ghi nhận Bedrock bị quota/throttling HTTP 429 và test Gemini API local như PoC fallback với model `models/gemini-3.1-flash-lite`.
* Phân biệt rõ target production architecture là Amazon Bedrock, còn Gemini là local PoC/testing fallback.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | **Phân tích Matching Trigger và input userId/cvKey/jobId** <br>- Phân tích userId, cvKey và jobId <br>- Xem API Gateway event shape <br>- Chuẩn bị Lambda Console test event | 29/06/2026 | 29/06/2026 | Project CV Matching notes |
| 2 | **Tìm hiểu Text Extraction từ CV PDF trong S3** <br>- Tìm hiểu cvKey trỏ đến S3 object <br>- Tìm hiểu nhu cầu extract text từ PDF <br>- Chuẩn bị CV text làm input cho AI | 30/06/2026 | 30/06/2026 | Amazon S3 and Textract notes |
| 3 | **Tìm hiểu lấy Job Description từ DynamoDB** <br>- Xem Jobs Table lookup bằng jobId <br>- Xác định các field job description <br>- Kết nối dữ liệu job với evaluation prompt | 01/07/2026 | 01/07/2026 | DynamoDB Jobs Table notes |
| 4 | **Thiết kế AI Evaluation output JSON schema** <br>- Thiết kế score schema dạng JSON <br>- Bao gồm scores, summary, matched skills, missing skills và suggestions <br>- Chuẩn bị output dễ hiển thị trên frontend | 02/07/2026 | 02/07/2026 | AI evaluation schema notes |
| 5 | **Ghi nhận Bedrock 429 và test Gemini PoC fallback** <br>- Ghi nhận lỗi Bedrock HTTP 429 <br>- Test Gemini local PoC fallback <br>- Xác nhận request liên tiếp thành công và JSON đúng schema | 03/07/2026 | 03/07/2026 | Bedrock/Gemini testing notes |

### Kết quả đạt được tuần 11:

* **Hiểu CV Matching Flow gồm nhiều bước:** Nắm được flow không chỉ là gọi AI mà gồm trigger, extract text, evaluate và lưu kết quả.
* **Xác định input tối thiểu:** Hiểu cần userId, cvKey và jobId để đánh giá CV với job.
* **Biết dùng Lambda Console event để test flow:** Có thể giả lập API Gateway event để test Lambda.
* **Hiểu vai trò cvKey:** Biết cvKey dùng để truy xuất CV từ S3.
* **Chuẩn hóa JSON output:** Thiết kế output để frontend dễ hiển thị kết quả matching.
* **Nhận diện rủi ro quota/throttling:** Ghi nhận rủi ro khi dùng managed AI service.
* **Chuẩn bị nội dung workshop:** Có đủ nội dung cho phần `5-CV-Matching-Flow`.
