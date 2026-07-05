---
title: "Meetup 06/06/2026"
date: 2026-06-06
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

## Thông tin sự kiện

| Hạng mục | Nội dung |
| --- | --- |
| Tên sự kiện | Meetup 06/06/2026 |
| Thời gian | 09:00 - 12:00, Thứ Bảy, 06/06/2026 |
| Địa điểm | Bitexco Financial Tower, Thành phố Hồ Chí Minh |
| Hình thức tham gia | Tham gia cùng cộng đồng FCAJ |
| Vai trò | Người tham dự, lắng nghe chia sẻ kỹ thuật, ghi chú nội dung và rút ra bài học áp dụng cho quá trình học AWS/project |
| Minh chứng | Hình ảnh tham gia sự kiện và tài liệu slide từ các speaker |

## Vai trò khi tham gia

Trong sự kiện này, tôi tham gia với vai trò là người học và thành viên của cộng đồng FCAJ. Mục tiêu chính của tôi là lắng nghe các chia sẻ thực tế từ nhiều góc nhìn khác nhau: containerization, real-time communication, cybersecurity, GraphRAG, kỹ năng làm việc nhóm và lộ trình phát triển nghề nghiệp trong mảng Cloud/DevOps.

Khác với một buổi học chỉ tập trung vào một dịch vụ AWS cụ thể, meetup này giúp tôi nhìn rộng hơn về cách các công nghệ được kết hợp trong hệ thống thực tế. Tôi tập trung ghi chú những nội dung có thể liên hệ với dự án AI Job Matching Platform, đặc biệt là Docker, API Gateway WebSocket, AWS WAF, Machine Learning, Amazon Bedrock, Amazon Neptune và cách tổ chức làm việc nhóm.

## Nội dung chính của sự kiện

| Chủ đề | Speaker | Nội dung chính | Điểm tôi ghi nhận |
| --- | --- | --- | --- |
| Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets | Nguyễn Quốc Bảo | Trình bày cách kết nối Godot client với AWS WebSocket API để xây dựng game multiplayer. Kiến trúc sử dụng API Gateway WebSocket, Lambda và DynamoDB để xử lý kết nối, matchmaking và trạng thái người chơi. | Hiểu rõ hơn cách WebSocket khác với REST API truyền thống. Với các ứng dụng cần cập nhật trạng thái liên tục, WebSocket phù hợp hơn request/response thông thường. |
| Docker - A Containerization Technology | Bảo Huỳnh | Giới thiệu virtualization, containerization, Docker image, Docker container, Dockerfile và các use case như CI/CD, microservices, môi trường dev/test và cloud-native application. | Rút ra rằng Docker giúp giảm lỗi khác biệt môi trường kiểu “chạy được trên máy mình nhưng lỗi ở máy khác”. Đây là vấn đề rất thực tế khi làm nhóm. |
| AWS Neptune for Building a Graph Knowledge Base for GraphRAG | Việt Phát | Trình bày RAG, giới hạn của RAG truyền thống, GraphRAG, multi-hop reasoning, Amazon Bedrock Knowledge Bases, Neptune Analytics và custom pipeline với LlamaIndex/Amazon Neptune. | Hiểu rằng GraphRAG phù hợp khi dữ liệu có nhiều quan hệ giữa các thực thể. Đây là hướng có thể nghiên cứu thêm cho các hệ thống AI cần suy luận theo quan hệ. |
| Combining AWS WAF with Machine Learning for Cyber Attack Detection on AWS | Lê Hoàng Gia Đại | Trình bày AWS WAF, giới hạn của rule-based detection, NIDS, sử dụng Machine Learning để phát hiện bất thường, dataset CSE-CIC-IDS2018 và kiến trúc triển khai trên AWS. | Nhận ra rằng bảo mật không nên chỉ dựa vào rule tĩnh. Với các hành vi mới hoặc bất thường, ML có thể hỗ trợ phát hiện tốt hơn nếu dữ liệu đủ chất lượng. |
| Cách làm việc nhóm hiệu quả | Trương Huy Phước | Chia sẻ các nguyên tắc làm việc nhóm như thống nhất mục tiêu, phân chia công việc theo thế mạnh, giao tiếp rõ ràng và trách nhiệm cá nhân. Đồng thời gợi ý công cụ như Trello, Slack, Discord, Google Workspace. | Nội dung này liên hệ trực tiếp với quá trình làm project nhóm. Nếu không thống nhất task, deadline và cách giao tiếp, team rất dễ trùng việc hoặc bỏ sót việc. |
| From IT Helpdesk to Senior Sysadmin | Trần Trung Vinh | Chia sẻ hành trình từ IT Helpdesk đến Senior Sysadmin, các kỹ năng cần xây dựng như troubleshooting, Linux, networking, lab thực hành, cloud mindset, IaC, Docker và DevOps culture. | Bài học quan trọng là không nên học quá nhiều thứ cùng lúc mà thiếu thực hành. Cần xây nền tảng vững và làm project/lab thật để tạo năng lực. |

## Bài học rút ra

### 1. Docker giúp chuẩn hóa môi trường phát triển

Phần Docker giúp tôi hiểu rõ hơn sự khác nhau giữa virtual machine và container. Virtual machine cần một hệ điều hành đầy đủ cho từng máy ảo, trong khi container chia sẻ kernel với host nên nhẹ hơn, khởi động nhanh hơn và phù hợp với cloud-native application.

Bài học này rất thực tế khi làm project nhóm. Nếu mỗi thành viên dùng một môi trường khác nhau, lỗi cấu hình và dependency có thể xảy ra thường xuyên. Docker giúp đóng gói ứng dụng cùng dependency, từ đó giảm rủi ro lệch môi trường giữa local, staging và production.

### 2. WebSocket phù hợp với hệ thống cần cập nhật trạng thái liên tục

Phần Godot Client với AWS WebSockets giúp tôi hiểu rõ hơn cách API Gateway WebSocket có thể duy trì kết nối hai chiều giữa client và backend. Khác với REST API, WebSocket phù hợp với các use case cần phản hồi gần thời gian thực như game multiplayer, chat hoặc trạng thái phiên làm việc.

Điểm tôi chú ý là kiến trúc serverless vẫn có thể xử lý kết nối real-time bằng cách kết hợp API Gateway WebSocket, Lambda và DynamoDB. Tuy nhiên, cũng cần quan tâm đến stale connections, chi phí DynamoDB Scan và việc Lambda không lưu state lâu dài trong bộ nhớ.

### 3. GraphRAG mở rộng khả năng của RAG truyền thống

Phần GraphRAG giúp tôi hiểu rằng RAG truyền thống phù hợp khi cần truy xuất đoạn văn bản liên quan, nhưng có thể gặp giới hạn khi câu hỏi cần suy luận qua nhiều thực thể hoặc nhiều quan hệ. GraphRAG giải quyết vấn đề này bằng cách tổ chức dữ liệu dưới dạng knowledge graph.

Với các hệ thống AI phức tạp, việc kết hợp Amazon Bedrock và Amazon Neptune có thể giúp mô hình không chỉ tìm thông tin, mà còn hiểu quan hệ giữa các thực thể. Đây là hướng đáng quan tâm nếu sau này dự án cần phân tích dữ liệu có nhiều mối liên kết, ví dụ kỹ năng - công việc - kinh nghiệm - ngành nghề.

### 4. Bảo mật cloud cần kết hợp nhiều lớp

Phần AWS WAF kết hợp Machine Learning cho thấy rule-based security có giá trị nhưng không đủ cho mọi tình huống. AWS WAF có thể chặn các mẫu tấn công phổ biến như SQL Injection, XSS, bot traffic hoặc brute force, nhưng các tấn công mới hoặc hành vi bất thường có thể cần phân tích dựa trên dữ liệu.

Bài học tôi rút ra là khi thiết kế hệ thống cloud, cần nhìn bảo mật theo nhiều lớp: WAF, logging, monitoring, anomaly detection, alerting và phản ứng sự cố. Với project có API public, việc kiểm soát request bất thường và log hành vi là yếu tố nên được cân nhắc sớm.

### 5. Làm việc nhóm cần rõ mục tiêu, rõ vai trò và rõ trách nhiệm

Phần teamwork giúp tôi nhìn lại cách làm việc trong project nhóm. Một team không chỉ cần người giỏi kỹ thuật, mà còn cần thống nhất mục tiêu, chia việc hợp lý, giao tiếp rõ và có trách nhiệm với deadline.

Tôi nhận ra rằng nhiều lỗi trong project không đến từ code mà đến từ việc thiếu thống nhất: không biết ai làm gì, task nào đã xong, file nào là bản mới nhất hoặc deadline nào cần ưu tiên. Vì vậy, việc dùng công cụ quản lý như Trello, Google Workspace, Slack/Discord và quy ước Git rõ ràng là rất cần thiết.

### 6. Lộ trình nghề nghiệp Cloud/DevOps cần nền tảng và thực hành liên tục

Phần chia sẻ từ IT Helpdesk đến Senior Sysadmin giúp tôi hiểu rằng phát triển nghề nghiệp trong ngành IT cần thời gian và sự tích lũy. Các kỹ năng như Linux, networking, troubleshooting, automation, Docker và cloud không nên học theo kiểu chỉ đọc lý thuyết, mà cần lab và project thực tế.

Bài học quan trọng nhất là không nên test trực tiếp trên production và cần có tư duy vận hành an toàn. Đây là tư duy rất quan trọng khi làm với AWS vì một cấu hình sai có thể ảnh hưởng đến bảo mật, chi phí hoặc khả năng hoạt động của hệ thống.

## Đóng góp cá nhân sau sự kiện

Sau sự kiện, tôi tổng hợp lại các nội dung có liên quan đến quá trình học AWS và dự án nhóm. Một số điểm tôi có thể áp dụng gồm:

- Ghi nhận Docker là hướng tốt để đồng nhất môi trường phát triển giữa các thành viên.
- Liên hệ API Gateway WebSocket với các use case cần kết nối real-time, dù hiện tại dự án AI Job Matching Platform chủ yếu dùng HTTP API.
- Cân nhắc AWS WAF, logging và monitoring nếu hệ thống có API public.
- Tìm hiểu thêm GraphRAG như một hướng mở rộng cho các bài toán AI có quan hệ dữ liệu phức tạp.
- Áp dụng nguyên tắc làm việc nhóm rõ task, rõ deadline, rõ trách nhiệm để tránh trùng việc hoặc bỏ sót việc.
- Rút kinh nghiệm về lộ trình học Cloud/DevOps: cần xây nền tảng networking, Linux, serverless, Docker và làm nhiều lab thực tế.

## Hình ảnh tham gia

![Hình ảnh tham gia Meetup 06/06/2026](/images/4-EventParticipated/event2.jpg)

## Tổng kết

Meetup 06/06/2026 mang lại cho tôi góc nhìn rộng hơn về hệ sinh thái công nghệ hiện đại. Các chủ đề không chỉ xoay quanh AWS mà còn mở rộng sang Docker, WebSocket, Machine Learning, GraphRAG, teamwork và phát triển nghề nghiệp. Sau sự kiện, tôi hiểu rõ hơn rằng để xây dựng một hệ thống cloud tốt, người học không chỉ cần biết từng dịch vụ riêng lẻ mà còn cần biết cách kết hợp công nghệ, kiểm soát rủi ro, làm việc nhóm và duy trì tư duy học tập liên tục.
