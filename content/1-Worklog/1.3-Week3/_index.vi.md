---
title: "Worklog Tuần 3"
date: 2026-07-03
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Tìm hiểu cách triển khai và truy cập Amazon EC2 instance.
* Ôn lại sự khác nhau giữa EC2 trong Public Subnet và Private Subnet.
* Tìm hiểu SSH, key pair, public IP, Security Group và Route Table khi kết nối EC2.
* Tìm hiểu các công cụ và cách truy cập như SSH, VS Code Remote SSH, MobaXterm, PuTTY và AWS Systems Manager Session Manager.
* Phân tích các lỗi thường gặp khi không SSH được vào EC2 như sai key pair, chưa mở port 22, Security Group sai, instance không có public IP hoặc Route Table chưa có Internet Gateway.
* Tìm hiểu vì sao không nên mở SSH public quá rộng và có thể dùng Session Manager để truy cập an toàn hơn.

### Các công việc cần triển khai trong tuần này:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | **Tìm hiểu lại EC2 trong Public/Private Subnet** <br>- Ôn cách EC2 được đặt trong subnet <br>- So sánh cách truy cập public và private <br>- Xác định khi nào cần public IP | 04/05/2026 | 04/05/2026 | Amazon EC2 và VPC documentation |
| 2 | **Tìm hiểu key pair, public IP và SSH** <br>- Tìm hiểu SSH authentication bằng key pair <br>- Tìm hiểu vai trò của public IP khi truy cập từ bên ngoài <br>- Ghi nhận yêu cầu của SSH client | 05/05/2026 | 05/05/2026 | Amazon EC2 User Guide |
| 3 | **Tìm hiểu Security Group inbound/outbound rule** <br>- Ôn cách Security Group hoạt động <br>- Phân tích inbound rule cho SSH port 22 <br>- Kiểm tra cấu hình outbound traffic | 06/05/2026 | 06/05/2026 | AWS Security Group Documentation |
| 4 | **Kiểm tra các lỗi phổ biến khi không SSH được vào EC2** <br>- Kiểm tra sai key pair <br>- Kiểm tra thiếu public IP hoặc route table sai <br>- Kiểm tra Security Group và cấu hình network | 07/05/2026 | 07/05/2026 | EC2 troubleshooting guide |
| 5 | **Tìm hiểu Session Manager như hướng truy cập an toàn hơn** <br>- Tìm hiểu AWS Systems Manager Session Manager <br>- So sánh Session Manager với SSH public <br>- Ghi nhận lợi ích giảm mở SSH ra Internet | 08/05/2026 | 08/05/2026 | AWS Systems Manager Documentation |

### Kết quả đạt được tuần 3:

* **Hiểu quy trình cơ bản để truy cập EC2:** Nắm được các điều kiện chính cần có để kết nối đến EC2 instance.
* **Biết điều kiện cần để SSH vào EC2 trong Public Subnet:** Hiểu EC2 cần public IP, key pair hợp lệ, Route Table đúng và Security Group mở port phù hợp.
* **Phân biệt vai trò của các thành phần kết nối:** Hiểu vai trò của key pair, public IP, Route Table và Security Group.
* **Biết kiểm tra lỗi kết nối theo từng lớp:** Có thể kiểm tra lỗi EC2 theo từng bước từ quyền truy cập, instance đến network.
* **Hiểu lợi ích bảo mật của Session Manager:** Biết Session Manager giúp giảm nhu cầu mở SSH public và hỗ trợ truy cập EC2 an toàn hơn.
