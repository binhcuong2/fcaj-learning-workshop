---
title: "FCAJ Community Day - May 2026"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

## Event Information

| Item | Details |
| --- | --- |
| Event name | FCAJ Community Day |
| Time | 09:00 - 12:00, Saturday, 23/05/2026 |
| Location | Bitexco Financial Tower, Ho Chi Minh City |
| Participation format | On-site participation |
| Role | Participant, technical learner, note taker, and community member |

## Participation Role

In this event, I participated as a learner and a member of the FCAJ community. My main goal was to learn from practical sharing sessions, capture key insights about AI, CloudFront, LLMs, and Multi-Agent Systems, and connect these lessons with my AWS learning process and the AI Job Matching Platform project.

In addition to following the presentations, I focused on noting down ideas that could be applied to my project, especially how to provide better context to AI systems, how CloudFront supports content delivery, and how to control AI behavior when integrating it into real applications.

## Main Event Content

| Time | Session | Speaker / Team | Key Notes |
| --- | --- | --- | --- |
| 08:30 - 09:00 | Check-in and seating on the 26th floor | Organizing team | Participants checked in, settled into the venue, and prepared for the event. |
| 09:00 - 09:30 | Context Is Everything: Making AI Actually Work for You | Tinh Truong | AI does not only depend on prompts. It strongly depends on context, including relevant data, goals, constraints, and user intent. |
| 09:30 - 09:45 | Friendly AI Assistant with Amazon Quick | Anh Pham | Introduced capabilities for data exploration, workflow automation using natural language, and sharing insights within a team. |
| 09:45 - 10:25 | From Edge To Origin: CloudFront as Your Foundation | Thinh Nguyen | Explained how Amazon CloudFront supports content delivery, cost optimization, performance, security, and reliability. |
| 10:25 - 10:55 | 36 hrs with LotusHacks - Building UTMorpho from Idea to Reality | Team VIB | Shared the journey of turning an idea into a working product within 36 hours, from brainstorming and problem framing to demo and lessons learned. |
| 10:55 - 11:00 | Break | Organizing team | Short break between sessions. |
| 11:00 - 11:30 | Non-Determinism of "Deterministic" LLM Settings | Duc Dao | Clarified the misconception that `temperature = 0` always guarantees deterministic output. Inference optimizations may still cause variations. |
| 11:30 - 12:00 | Enterprise-Grade Multi-Agent System: The Case of Startup Credit Scoring | Vy Lam | Presented a Multi-Agent architecture for startup credit scoring, with attention to guardrails, compliance, and ROI. |

## Lessons Learned

### 1. AI needs better context, not only better prompts

The session about context helped me rethink how I use AI in both learning and project development. Previously, I focused mainly on writing prompts, but the event showed that prompts are only one part of the process. To make AI outputs useful, the system needs clear goals, relevant data, user intent, constraints, and expected output format.

This lesson is directly applicable to the AI Matching feature in the AI Job Matching Platform. When evaluating a CV against a job description, sending raw data to the model may produce unstable results. A better approach is to provide structured input, including CV text, job description, scoring criteria, and a strict JSON output schema.

### 2. CloudFront is not only for speeding up websites

The CloudFront session helped me understand that a CDN is not only used for static website acceleration. It can also become an important foundation for performance, security, reliability, and cost optimization. The “Edge to Origin” mindset gave me a clearer view of how requests travel from users to backend systems.

This knowledge is useful when deploying web applications on the cloud, especially systems that include frontend assets, APIs, or content that needs to be delivered efficiently to users.

### 3. LLMs are not always fully stable even with deterministic-looking settings

The session about LLM non-determinism was one of the most important technical takeaways for me. I learned that even when `temperature = 0`, an AI system may still produce different outputs because of inference optimizations.

This is especially important for features that require structured output, such as CV matching. To reduce risk, the system should include schema validation, retry strategies, fallback handling, and output verification before storing results in a database or showing them to users.

### 4. Multi-Agent architecture is useful for complex problems, but should not be overused

The Multi-Agent System session helped me understand that not every problem requires multiple agents. For simple tasks, a Single Agent may be sufficient. Multi-Agent design is more suitable when the problem has multiple steps, multiple roles, cross-checking requirements, or a complex business workflow.

This is an important design perspective: the architecture should be selected based on the real needs of the problem, not simply because the technology is new.

## Personal Contribution After the Event

After attending the event, I summarized the parts that were relevant to my AWS learning process and team project. The points I could apply include:

- Applying clearer context design when building prompts and schemas for AI Evaluation.
- Paying attention to AI output stability when calling AI models.
- Considering CloudFront for use cases that require optimized content delivery or static asset distribution.
- Learning from the UTMorpho team's presentation structure, especially how to explain the problem, solution, demo, and lessons learned.
- Sharing with the team that AI output should not be treated as fully reliable unless validation is implemented.

## Proof of Participation

![Check-in at FCAJ Community Day](/images/4-EventParticipated/event1-1.jpg)

## Summary

FCAJ Community Day was valuable because it did not only introduce new technologies but also provided practical perspectives on AI usage, cloud infrastructure, and controlled AI system design. After the event, I understood that applying AI effectively in a real system requires three elements: good data and context, suitable cloud architecture, and strong output validation.
