---
title: "AI Gateway – Giải pháp quản lý AI trên AWS với Amazon Bedrock và Amazon API Gateway"
date: 2026-07-03
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

## Đặt vấn đề và giải pháp AI Gateway

Khi các ứng dụng AI tạo sinh ngày càng được sử dụng rộng rãi trong doanh nghiệp, việc cho phép mọi hệ thống truy cập trực tiếp vào mô hình AI có thể dẫn đến nhiều vấn đề như khó kiểm soát chi phí, thiếu cơ chế phân quyền và khó theo dõi mức độ sử dụng.

Để giải quyết vấn đề này, AWS đề xuất mô hình AI Gateway, sử dụng Amazon API Gateway làm lớp trung gian giữa người dùng và Amazon Bedrock. Kiến trúc này giúp doanh nghiệp kiểm soát quyền truy cập, giới hạn số lượng yêu cầu, theo dõi chi phí và tăng cường bảo mật khi triển khai các ứng dụng Generative AI.

Mô hình này sử dụng Amazon API Gateway làm lớp truy cập phía trước Amazon Bedrock. Giải pháp hỗ trợ nhiều tính năng quan trọng như xác thực và phân quyền người dùng thông qua các hệ thống nhận dạng hiện có (ví dụ: JWT), quản lý hạn mức sử dụng, điều tiết lưu lượng truy cập, quản lý vòng đời API, triển khai thử nghiệm (Canary Release) và tăng cường bảo mật thông qua AWS WAF. Ngoài ra, API Gateway còn hỗ trợ cơ chế truyền phản hồi theo thời gian thực (Streaming Response), cho phép kết quả từ mô hình AI được gửi trực tiếp đến người dùng ngay khi được tạo ra thay vì phải chờ hoàn tất toàn bộ quá trình xử lý.

Nhờ những khả năng này, AI Gateway không chỉ đóng vai trò là cổng truy cập vào Amazon Bedrock mà còn giúp doanh nghiệp kiểm soát chi phí, tăng cường bảo mật và quản lý việc sử dụng AI hiệu quả hơn ở quy mô lớn. Kiến trúc tham chiếu này cung cấp cho bạn khả năng kiểm soát chi tiết quyền truy cập LLM bằng cách sử dụng các dịch vụ AWS được quản lý hoàn toàn, hoạt động minh bạch đối với các ứng dụng khách và tích hợp liền mạch vào môi trường doanh nghiệp hiện có.

## Các thành phần cốt lõi của giải pháp

Giải pháp bao gồm năm thành phần cốt lõi:

*   **Amazon Route 53 (Quản lý Custom Domain Routing):** Chịu trách nhiệm cho phép người dùng truy cập AI Gateway thông qua tên miền riêng của doanh nghiệp thay vì sử dụng domain mặc định của Amazon API Gateway. Điều này giúp hệ thống chuyên nghiệp hơn và dễ dàng tích hợp vào hạ tầng hiện có của tổ chức.
*   **Amazon API Gateway (Cổng truy cập hợp nhất):** Đóng vai trò là điểm tiếp nhận (Entry Point) cho toàn bộ request gửi đến hệ thống AI. Dịch vụ này cung cấp nhiều tính năng quan trọng như xác thực (Authorization), điều tiết lưu lượng (Request Throttling), quản lý vòng đời (Lifecycle Management), giới hạn tần suất (Rate Limiting) và giám sát (Monitoring), giúp doanh nghiệp kiểm soát quyền truy cập, quản lý lưu lượng, theo dõi hoạt động và đảm bảo tính ổn định, bảo mật.
*   **AWS Lambda Authorizer (Xác thực và phân quyền linh hoạt):** Chịu trách nhiệm xử lý phân quyền cho các request (ví dụ: xác thực JWT Token với các hệ thống Authentication hiện có). Đối với từng nhu cầu cụ thể, bạn có thể xây dựng logic xác thực riêng trong Lambda Authorizer, tích hợp với Amazon Cognito User Pools hoặc sử dụng các cơ chế phân quyền khác của API Gateway.
*   **Lambda Integration (Định tuyến và ký Request động):** Hoạt động như một Dynamic Request Forwarder có nhiệm vụ ký các request đến bằng AWS Credentials và định tuyến chúng đến các Amazon Bedrock Endpoints phù hợp. Thành phần này giữ nguyên toàn bộ thông tin request ban đầu (bao gồm API Action và Parameters) để hỗ trợ các API của Amazon Bedrock mà không cần thay đổi mã nguồn client.
*   **Amazon Bedrock (Nền tảng dịch vụ AI):** Cung cấp quyền truy cập trực tiếp đến các Foundation Models và các khả năng AI mạnh mẽ khác.

## Ưu điểm và Kết luận

Ưu điểm lớn nhất của kiến trúc này là tính minh bạch đối với các ứng dụng khách (Client Applications) và thiết kế sẵn sàng cho tương lai (Future-Proof Design). Các client có thể tiếp tục sử dụng AWS SDKs (như Boto3) để truy cập các chức năng của Amazon Bedrock (như LLMs và Knowledge Bases) tương tự như khi gọi trực tiếp API, trong khi AI Gateway âm thầm xử lý việc xác thực, quản lý hạn mức và các tác vụ quản trị khác ở phía sau.

Mô hình này cung cấp một phương thức có khả năng mở rộng để quản lý quyền truy cập vào các mô hình nền tảng thông qua Amazon Bedrock. Ban đầu được phát triển và triển khai thành công bởi Dynatrace để phục vụ cơ sở người dùng toàn cầu, giải pháp này đã chứng minh hiệu quả tối ưu ở quy mô doanh nghiệp. Bằng cách tận dụng các tính năng mạnh mẽ của Amazon API Gateway, các tổ chức có thể thiết lập các biện pháp kiểm soát cần thiết trong khi vẫn duy trì được toàn bộ lợi ích của kiến trúc serverless.

---

*Link bài viết gốc:* [Building an AI Gateway to Amazon Bedrock with Amazon API Gateway](https://aws.amazon.com/blogs/architecture/building-an-ai-gateway-to-amazon-bedrock-with-amazon-api-gateway/)