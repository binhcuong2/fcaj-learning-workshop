---
title: "Meetup 06/06/2026"
date: 2026-06-06
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

## Event Information

| Item | Details |
| --- | --- |
| Event name | Meetup 06/06/2026 |
| Time | 09:00 - 12:00, Saturday, 06/06/2026 |
| Location | Bitexco Financial Tower, Ho Chi Minh City |
| Participation format | Participated with the FCAJ community |
| Role | Participant, technical learner, note taker, and project learner |
| Proof | Event photo and speaker slide materials |

## Participation Role

In this event, I participated as a learner and a member of the FCAJ community. My main goal was to learn from practical sharing sessions across different areas, including containerization, real-time communication, cybersecurity, GraphRAG, teamwork, and career development in Cloud/DevOps.

Unlike a learning session focused on only one AWS service, this meetup helped me see how different technologies can be combined in real systems. I focused on noting down ideas that could be connected to the AI Job Matching Platform project, especially Docker, API Gateway WebSocket, AWS WAF, Machine Learning, Amazon Bedrock, Amazon Neptune, and teamwork practices.

## Main Event Content

| Topic | Speaker | Main Content | My Notes |
| --- | --- | --- | --- |
| Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets | Nguyen Quoc Bao | Presented how to connect Godot clients with AWS WebSocket API for multiplayer games. The architecture used API Gateway WebSocket, Lambda, and DynamoDB to manage connections, matchmaking, and player state. | I understood how WebSocket differs from traditional REST APIs. For applications that require continuous state updates, WebSocket is more suitable than normal request/response patterns. |
| Docker - A Containerization Technology | Bao Huynh | Introduced virtualization, containerization, Docker image, Docker container, Dockerfile, and use cases such as CI/CD, microservices, dev/test environments, and cloud-native applications. | Docker helps reduce environment mismatch issues such as “it works on my machine but fails on another machine,” which is very practical for team projects. |
| AWS Neptune for Building a Graph Knowledge Base for GraphRAG | Viet Phat | Explained RAG, limitations of traditional RAG, GraphRAG, multi-hop reasoning, Amazon Bedrock Knowledge Bases, Neptune Analytics, and custom pipelines with LlamaIndex/Amazon Neptune. | GraphRAG is useful when data contains many relationships between entities. It is worth exploring for AI systems that require relationship-based reasoning. |
| Combining AWS WAF with Machine Learning for Cyber Attack Detection on AWS | Le Hoang Gia Dai | Presented AWS WAF, limitations of rule-based detection, NIDS, Machine Learning for anomaly detection, the CSE-CIC-IDS2018 dataset, and AWS deployment architecture. | Security should not rely only on static rules. ML can help detect new or abnormal behaviors when good data is available. |
| Effective Teamwork | Truong Huy Phuoc | Shared principles of teamwork such as clear goals, task assignment based on strengths, open communication, and personal accountability. Also introduced tools such as Trello, Slack, Discord, and Google Workspace. | This topic is directly related to my team project. Without clear tasks, deadlines, and communication rules, a team can easily duplicate work or miss important tasks. |
| From IT Helpdesk to Senior Sysadmin | Tran Trung Vinh | Shared a practical career journey from IT Helpdesk to Senior Sysadmin, including troubleshooting, Linux, networking, hands-on labs, cloud mindset, Infrastructure as Code, Docker, and DevOps culture. | The key lesson is not to learn too many things at once without practice. Building strong fundamentals and doing real projects/labs are more important. |

## Lessons Learned

### 1. Docker helps standardize development environments

The Docker session helped me understand the difference between virtual machines and containers. A virtual machine needs a full guest operating system, while a container shares the host kernel, making it lighter, faster to start, and more suitable for cloud-native applications.

This lesson is very practical for team projects. If each member uses a different environment, dependency and configuration issues can happen frequently. Docker helps package applications with their dependencies, reducing environment differences between local, staging, and production.

### 2. WebSocket is suitable for systems that require continuous state updates

The Godot Client with AWS WebSockets session helped me understand how API Gateway WebSocket can maintain bidirectional communication between clients and backend services. Unlike REST APIs, WebSocket is more suitable for use cases that require near real-time responses, such as multiplayer games, chat systems, or session state updates.

One important point is that serverless architecture can still support real-time communication by combining API Gateway WebSocket, Lambda, and DynamoDB. However, the system must also handle stale connections, DynamoDB Scan costs, and the fact that Lambda does not keep long-lived state in memory.

### 3. GraphRAG extends the capability of traditional RAG

The GraphRAG session helped me understand that traditional RAG is useful for retrieving relevant text passages, but it may be limited when a question requires reasoning across multiple entities or relationships. GraphRAG addresses this by organizing data as a knowledge graph.

For complex AI systems, combining Amazon Bedrock and Amazon Neptune can help the model not only retrieve information but also understand relationships between entities. This is worth exploring if a future project needs to analyze connected data, such as skills, jobs, experience, and career domains.

### 4. Cloud security should be designed in multiple layers

The AWS WAF and Machine Learning session showed that rule-based security is valuable but not enough for every situation. AWS WAF can block common attack patterns such as SQL Injection, XSS, bot traffic, and brute force, but new attacks or abnormal behavior may require data-driven detection.

My takeaway is that cloud security should be designed with multiple layers, including WAF, logging, monitoring, anomaly detection, alerting, and incident response. For projects with public APIs, detecting unusual request patterns and collecting logs should be considered early.

### 5. Teamwork requires clear goals, roles, and accountability

The teamwork session helped me reflect on my own team project process. A team does not only need technical skills; it also needs shared goals, suitable task assignment, clear communication, and accountability for deadlines.

I realized that many project issues do not come from code but from misalignment: unclear ownership, unclear task status, outdated files, or unclear priorities. Therefore, tools such as Trello, Google Workspace, Slack/Discord, and clear Git conventions are useful for team collaboration.

### 6. A Cloud/DevOps career path requires fundamentals and continuous practice

The career journey from IT Helpdesk to Senior Sysadmin showed me that professional growth in IT takes time and accumulation. Skills such as Linux, networking, troubleshooting, automation, Docker, and cloud should not be learned only through theory. They need hands-on labs and real projects.

The most important lesson is to avoid testing directly in production and to maintain an operational safety mindset. This is very important when working with AWS because a wrong configuration can affect security, cost, or system availability.

## Personal Contribution After the Event

After the event, I summarized the topics that were relevant to my AWS learning process and team project. The points I could apply include:

- Recognizing Docker as a good direction for standardizing development environments across team members.
- Connecting API Gateway WebSocket with real-time use cases, even though the current AI Job Matching Platform mainly uses HTTP APIs.
- Considering AWS WAF, logging, and monitoring for systems with public APIs.
- Exploring GraphRAG as a possible direction for AI problems with complex data relationships.
- Applying teamwork principles such as clear tasks, clear deadlines, and clear responsibilities to avoid duplicated or missed work.
- Learning that a Cloud/DevOps path requires strong foundations in networking, Linux, serverless, Docker, and real hands-on labs.

## Proof of Participation

![Photo from Meetup 06/06/2026](/images/4-EventParticipated/event2.jpg)

## Summary

Meetup 06/06/2026 gave me a broader view of the modern technology ecosystem. The sessions were not limited to AWS services but also covered Docker, WebSocket, Machine Learning, GraphRAG, teamwork, and career development. After the event, I understood that building a good cloud system requires more than knowing individual services. It also requires combining technologies, controlling risks, collaborating effectively, and maintaining continuous learning.
