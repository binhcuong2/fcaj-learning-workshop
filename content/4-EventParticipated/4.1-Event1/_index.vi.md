---
title: "FCAJ Community Day - Tháng 5 2026"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

## Thông tin sự kiện

| Hạng mục | Nội dung |
| --- | --- |
| Tên sự kiện | FCAJ Community Day |
| Thời gian | 09:00 - 12:00, Thứ Bảy, 23/05/2026 |
| Địa điểm | Bitexco Financial Tower, Thành phố Hồ Chí Minh |
| Hình thức tham gia | Tham gia trực tiếp |
| Vai trò | Người tham dự, lắng nghe chia sẻ kỹ thuật, ghi nhận bài học và kết nối cộng đồng |

## Vai trò khi tham gia

Trong sự kiện này, tôi tham gia với vai trò là người học và thành viên cộng đồng FCAJ. Mục tiêu chính của tôi là lắng nghe các chia sẻ thực tế từ diễn giả, ghi nhận các xu hướng mới liên quan đến AI, CloudFront, LLM và Multi-Agent System, đồng thời liên hệ các kiến thức này với quá trình học AWS và dự án AI Job Matching Platform.

Bên cạnh việc theo dõi nội dung trình bày, tôi cũng tập trung ghi chú các ý tưởng có thể áp dụng vào đồ án, đặc biệt là cách xây dựng ngữ cảnh cho AI, cách tối ưu phân phối nội dung bằng CloudFront và cách kiểm soát hành vi của hệ thống AI khi đưa vào ứng dụng thực tế.

## Nội dung chính của sự kiện

| Thời gian | Nội dung | Diễn giả / Nhóm trình bày | Điểm chính ghi nhận |
| --- | --- | --- | --- |
| 08:30 - 09:00 | Check-in và ổn định chỗ ngồi tại tầng 26 | Ban tổ chức | Người tham dự check-in, ổn định vị trí và chuẩn bị cho chương trình. |
| 09:00 - 09:30 | Context Is Everything: Making AI Actually Work for You | Tinh Truong | AI không chỉ phụ thuộc vào prompt, mà còn phụ thuộc rất lớn vào context. Muốn AI trả lời hiệu quả cần cung cấp đúng dữ liệu, đúng mục tiêu và đúng bối cảnh. |
| 09:30 - 09:45 | Friendly AI Assistant with Amazon Quick | Anh Pham | Giới thiệu các khả năng hỗ trợ phân tích dữ liệu, tạo workflow bằng ngôn ngữ tự nhiên và chia sẻ insight trong nhóm. |
| 09:45 - 10:25 | From Edge To Origin: CloudFront as Your Foundation | Thinh Nguyen | Trình bày vai trò của Amazon CloudFront trong phân phối nội dung, tối ưu chi phí, tăng hiệu năng, bảo mật và độ tin cậy. |
| 10:25 - 10:55 | 36 hrs with LotusHacks - Building UTMorpho from Idea to Reality | Team VIB | Chia sẻ quá trình biến ý tưởng thành sản phẩm trong 36 giờ, từ brainstorm, xác định vấn đề, xây dựng demo đến rút kinh nghiệm sau hackathon. |
| 10:55 - 11:00 | Break | Ban tổ chức | Nghỉ giải lao ngắn giữa các phiên. |
| 11:00 - 11:30 | Non-Determinism of "Deterministic" LLM Settings | Duc Dao | Làm rõ hiểu lầm rằng `temperature = 0` luôn tạo kết quả tất định; trong thực tế, tối ưu hóa inference vẫn có thể tạo ra khác biệt. |
| 11:30 - 12:00 | Enterprise-Grade Multi-Agent System: The Case of Startup Credit Scoring | Vy Lam | Trình bày cách thiết kế hệ thống Multi-Agent cho bài toán chấm điểm tín dụng startup, có xét đến guardrails, compliance và ROI. |

## Bài học rút ra

### 1. AI cần context tốt hơn, không chỉ cần prompt hay

Phần chia sẻ về context giúp tôi nhìn lại cách sử dụng AI trong học tập và làm project. Trước đây, tôi thường tập trung nhiều vào việc viết prompt, nhưng sự kiện cho thấy prompt chỉ là một phần. Để AI đưa ra kết quả tốt, cần cung cấp thêm bối cảnh như mục tiêu, dữ liệu liên quan, vai trò của người dùng, giới hạn hệ thống và định dạng đầu ra mong muốn.

Bài học này có thể áp dụng trực tiếp vào phần AI Matching trong dự án AI Job Matching Platform. Khi đánh giá CV với job description, nếu chỉ gửi dữ liệu thô cho model thì kết quả có thể thiếu ổn định. Thay vào đó, cần thiết kế input có cấu trúc rõ ràng, bao gồm CV text, job description, tiêu chí chấm điểm và JSON schema đầu ra.

### 2. CloudFront không chỉ dùng để tăng tốc website

Phần CloudFront giúp tôi hiểu rõ hơn rằng CDN không chỉ phục vụ static website, mà còn có thể là nền tảng quan trọng cho hiệu năng, bảo mật, độ tin cậy và tối ưu chi phí. Tư duy “Edge to Origin” giúp tôi hình dung tốt hơn cách một request đi từ người dùng đến hệ thống backend.

Kiến thức này hữu ích khi triển khai các ứng dụng web trên cloud, đặc biệt là các hệ thống có frontend, file tĩnh, API hoặc nội dung cần phân phối nhanh đến người dùng.

### 3. LLM không hoàn toàn ổn định dù cấu hình có vẻ tất định

Phần trình bày về non-determinism của LLM là một điểm đáng chú ý. Tôi rút ra rằng ngay cả khi đặt `temperature = 0`, hệ thống AI vẫn có thể cho ra kết quả khác nhau do các tối ưu hóa trong quá trình inference.

Điều này đặc biệt quan trọng khi dùng AI trong các chức năng có yêu cầu output theo schema, ví dụ như CV matching. Để giảm rủi ro, hệ thống cần có schema validation, retry strategy, fallback handling và kiểm tra dữ liệu đầu ra trước khi lưu vào database hoặc hiển thị cho người dùng.

### 4. Multi-Agent phù hợp với bài toán phức tạp, nhưng không nên lạm dụng

Phần Multi-Agent System giúp tôi hiểu rằng không phải bài toán nào cũng cần nhiều agent. Với các tác vụ đơn giản, Single Agent có thể đủ. Multi-Agent chỉ nên dùng khi bài toán có nhiều bước, nhiều vai trò, cần kiểm tra chéo hoặc cần mô phỏng một quy trình nghiệp vụ phức tạp.

Đây là góc nhìn quan trọng khi thiết kế hệ thống AI: không nên chọn kiến trúc phức tạp chỉ vì công nghệ mới, mà cần dựa trên nhu cầu thật của bài toán.

## Đóng góp cá nhân sau sự kiện

Sau khi tham gia sự kiện, tôi tổng hợp lại các nội dung có liên quan đến quá trình học AWS và dự án nhóm. Một số điểm tôi có thể áp dụng gồm:

- Áp dụng tư duy context rõ ràng khi thiết kế prompt/schema cho AI Evaluation.
- Lưu ý kiểm tra tính ổn định của output khi gọi AI model.
- Cân nhắc CloudFront trong các use case cần tối ưu phân phối nội dung hoặc static assets.
- Ghi nhận cách trình bày sản phẩm của nhóm UTMorpho để học cách mô tả problem, solution, demo và lesson learned rõ ràng hơn.
- Chia sẻ lại với nhóm về việc không nên xem AI output là tuyệt đối đúng nếu chưa có validation.

## Hình ảnh minh chứng tham gia

![Check-in tại sự kiện FCAJ Community Day](/images/4-EventParticipated/event1-1.jpg)

## Tổng kết

FCAJ Community Day là một sự kiện có giá trị vì nội dung không chỉ dừng lại ở việc giới thiệu công nghệ, mà còn cung cấp góc nhìn thực tế về cách sử dụng AI, thiết kế hạ tầng cloud và xây dựng hệ thống AI có kiểm soát. Sau sự kiện, tôi hiểu rõ hơn rằng để ứng dụng AI hiệu quả trong một hệ thống thật, cần kết hợp cả ba yếu tố: dữ liệu/ngữ cảnh tốt, kiến trúc cloud phù hợp và cơ chế kiểm soát output chặt chẽ.
