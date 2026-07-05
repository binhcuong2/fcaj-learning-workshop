---
title: "Week 3 Worklog"
date: 2026-07-03
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Learn how to deploy and access Amazon EC2 instances.
* Review the difference between EC2 instances in Public Subnets and Private Subnets.
* Understand SSH, key pairs, public IP addresses, Security Groups, and Route Tables when connecting to EC2.
* Explore access methods such as SSH, VS Code Remote SSH, MobaXterm, PuTTY, and AWS Systems Manager Session Manager.
* Analyze common EC2 connection issues such as wrong key pair, closed port 22, incorrect Security Group, missing public IP, or missing Internet Gateway route.
* Understand why SSH should not be opened too broadly and how Session Manager can provide safer access.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | **EC2 in Public and Private Subnets** <br>- Reviewed how EC2 is launched inside a subnet <br>- Compared public and private access patterns <br>- Identified when public IP access is required | 04/05/2026 | 04/05/2026 | Amazon EC2 and VPC documentation |
| 2 | **Key pair, public IP, and SSH** <br>- Studied SSH authentication with key pairs <br>- Learned the role of public IP in external access <br>- Reviewed SSH client requirements | 05/05/2026 | 05/05/2026 | Amazon EC2 User Guide |
| 3 | **Security Group inbound and outbound rules** <br>- Reviewed Security Group behavior <br>- Analyzed inbound rule for SSH port 22 <br>- Reviewed outbound traffic configuration | 06/05/2026 | 06/05/2026 | AWS Security Group Documentation |
| 4 | **Common EC2 SSH connection errors** <br>- Checked key pair mismatch <br>- Checked missing public IP and route table issues <br>- Checked Security Group and network configuration problems | 07/05/2026 | 07/05/2026 | EC2 troubleshooting guide |
| 5 | **Session Manager for safer EC2 access** <br>- Learned the purpose of AWS Systems Manager Session Manager <br>- Compared Session Manager with public SSH access <br>- Identified the security benefit of reducing public SSH exposure | 08/05/2026 | 08/05/2026 | AWS Systems Manager Documentation |

### Week 3 Achievements:

* **Understood the basic EC2 access flow:** Learned the main conditions required to connect to an EC2 instance.
* **Identified requirements for SSH access:** Understood that EC2 in a Public Subnet needs a public IP, valid key pair, correct Route Table, and proper Security Group rules.
* **Distinguished key networking components:** Understood the roles of key pair, public IP, Route Table, and Security Group.
* **Learned layered troubleshooting:** Gained the ability to check EC2 connection issues step by step across access, instance, and network layers.
* **Understood Session Manager benefits:** Learned that Session Manager can reduce public SSH exposure and provide a safer EC2 access method.
