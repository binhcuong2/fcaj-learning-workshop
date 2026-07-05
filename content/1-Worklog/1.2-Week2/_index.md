---
title: "Week 2 Worklog"
date: 2026-07-03
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* Learn the basic AWS networking architecture through Amazon VPC.
* Distinguish between core networking components such as VPC, Subnet, Internet Gateway, Route Table, and Security Group.
* Understand the difference between Public Subnet and Private Subnet.
* Learn how Amazon EC2 is deployed within an AWS network environment.
* Learn how to connect to an EC2 instance using SSH or tools such as MobaXterm, PuTTY, or VS Code Remote SSH.
* Understand the role of NAT Gateway in allowing resources in a Private Subnet to access the Internet outbound.
* Identify AWS networking resources that may generate costs during hands-on practice.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | **Amazon VPC fundamentals** <br>- Studied the concept of Virtual Private Cloud <br>- Analyzed the role of VPC in creating a private network on AWS <br>- Compared VPC with internal networking in traditional backend systems | 27/04/2026 | 27/04/2026 | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/) |
| 2 | **Subnet, Route Table, and Internet Gateway** <br>- Distinguished between Public Subnet and Private Subnet <br>- Learned how Route Tables control traffic routing <br>- Studied the role of Internet Gateway in allowing public subnets to access the Internet | 28/04/2026 | 28/04/2026 | AWS VPC User Guide |
| 3 | **Security Group** <br>- Studied Security Group as an instance-level firewall <br>- Analyzed inbound rules and outbound rules <br>- Identified the risk of opening public ports too broadly, especially SSH port 22 | 29/04/2026 | 29/04/2026 | AWS Security Group Documentation |
| 4 | **Amazon EC2 inside a VPC** <br>- Learned how EC2 instances are placed inside subnets <br>- Analyzed the requirements for an EC2 instance in a public subnet to be reachable from the Internet <br>- Studied key pair, public IP, and security group requirements for EC2 access | 30/04/2026 | 30/04/2026 | [Amazon EC2 Documentation](https://docs.aws.amazon.com/ec2/) |
| 5 | **NAT Gateway and related costs** <br>- Learned how NAT Gateway allows private subnet resources to access the Internet outbound <br>- Distinguished NAT Gateway from Internet Gateway <br>- Noted that NAT Gateway and Elastic IP may generate costs if not deleted after practice | 01/05/2026 | 01/05/2026 | AWS NAT Gateway Documentation |

### Week 2 Achievements:

* **Understood the role of Amazon VPC:** Learned that VPC is a virtual private network used to place and manage AWS resources such as EC2, Lambda, RDS, or other backend resources.
* **Distinguished between Public Subnet and Private Subnet:** Understood that a Public Subnet has a route to an Internet Gateway, while a Private Subnet is not directly exposed to the Internet.
* **Understood the role of Route Table:** Learned that Route Tables determine where subnet traffic is routed, such as within the VPC, to an Internet Gateway, or through a NAT Gateway.
* **Understood Security Group:** Learned that Security Group works as a resource-level firewall to control inbound and outbound traffic.
* **Learned the basic requirements for EC2 access:** Understood that an EC2 instance needs a public IP, valid key pair, correct route table, and appropriate Security Group rules to allow SSH access from outside.
* **Understood the role of NAT Gateway:** Learned that NAT Gateway allows resources in a Private Subnet to access the Internet outbound without exposing those resources publicly.
* **Recognized cost risks:** Noted that NAT Gateway, Elastic IP, EC2 instances, and network traffic may generate costs if they are not monitored or deleted after practice.
