---
title: "Worklog Tuần 2"
date: 2026-07-03
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* Tìm hiểu kiến trúc mạng cơ bản trong AWS thông qua Amazon VPC.
* Phân biệt các thành phần mạng chính như VPC, Subnet, Internet Gateway, Route Table và Security Group.
* Hiểu sự khác nhau giữa Public Subnet và Private Subnet.
* Tìm hiểu cách triển khai Amazon EC2 trong môi trường mạng AWS.
* Tìm hiểu cách kết nối đến EC2 instance bằng SSH hoặc các công cụ hỗ trợ như MobaXterm, PuTTY hoặc VS Code Remote SSH.
* Tìm hiểu vai trò của NAT Gateway trong việc cho phép tài nguyên ở Private Subnet truy cập Internet chiều ra.
* Ghi nhận các tài nguyên mạng AWS có thể phát sinh chi phí trong quá trình thực hành.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | **Tìm hiểu Amazon VPC** <br>- Tìm hiểu khái niệm Virtual Private Cloud <br>- Phân tích vai trò của VPC trong việc tạo mạng riêng trên AWS <br>- So sánh VPC với mạng nội bộ trong hệ thống backend truyền thống | 27/04/2026 | 27/04/2026 | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/) |
| 2 | **Tìm hiểu Subnet, Route Table và Internet Gateway** <br>- Phân biệt Public Subnet và Private Subnet <br>- Tìm hiểu cách Route Table điều hướng traffic <br>- Tìm hiểu vai trò của Internet Gateway trong việc cho phép subnet public truy cập Internet | 28/04/2026 | 28/04/2026 | AWS VPC User Guide |
| 3 | **Tìm hiểu Security Group** <br>- Tìm hiểu Security Group như firewall ở cấp instance <br>- Phân tích inbound rule và outbound rule <br>- Ghi nhận rủi ro khi mở port public quá rộng, đặc biệt là port SSH 22 | 29/04/2026 | 29/04/2026 | AWS Security Group Documentation |
| 4 | **Tìm hiểu Amazon EC2 trong VPC** <br>- Tìm hiểu cách EC2 được đặt trong subnet <br>- Phân tích điều kiện để EC2 trong public subnet có thể truy cập từ Internet <br>- Tìm hiểu key pair, public IP và security group khi kết nối EC2 | 30/04/2026 | 30/04/2026 | [Amazon EC2 Documentation](https://docs.aws.amazon.com/ec2/) |
| 5 | **Tìm hiểu NAT Gateway và chi phí liên quan** <br>- Tìm hiểu cách NAT Gateway hỗ trợ private subnet truy cập Internet chiều ra <br>- Phân biệt NAT Gateway với Internet Gateway <br>- Ghi nhận NAT Gateway và Elastic IP có thể phát sinh chi phí nếu không xóa sau khi thực hành | 01/05/2026 | 01/05/2026 | AWS NAT Gateway Documentation |

### Kết quả đạt được tuần 2:

* **Hiểu được vai trò của Amazon VPC:** Nắm được VPC là mạng riêng ảo dùng để đặt và quản lý tài nguyên AWS như EC2, Lambda, RDS hoặc các tài nguyên backend khác.
* **Phân biệt được Public Subnet và Private Subnet:** Hiểu rằng Public Subnet có route ra Internet Gateway, còn Private Subnet không public trực tiếp ra Internet.
* **Nắm được vai trò của Route Table:** Hiểu Route Table quyết định traffic trong subnet sẽ đi đâu, ví dụ đi nội bộ trong VPC, đi ra Internet Gateway hoặc đi qua NAT Gateway.
* **Hiểu được Security Group:** Biết Security Group hoạt động như firewall ở cấp tài nguyên, dùng để kiểm soát inbound và outbound traffic.
* **Biết các điều kiện cơ bản để kết nối EC2:** Nắm được EC2 cần public IP, key pair hợp lệ, route table đúng và Security Group mở port phù hợp nếu muốn SSH từ bên ngoài.
* **Hiểu được vai trò của NAT Gateway:** Biết NAT Gateway giúp tài nguyên trong Private Subnet truy cập Internet chiều ra mà không cần public trực tiếp tài nguyên đó.
* **Nhận thức được rủi ro chi phí:** Ghi nhận NAT Gateway, Elastic IP, EC2 instance và traffic có thể phát sinh chi phí nếu không kiểm soát hoặc không xóa sau khi thực hành.
