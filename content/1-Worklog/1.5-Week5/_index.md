---
title: "Week 5 Worklog"
date: 2026-07-03
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Learn AWS SAM and the role of the `template.yaml` file.
* Understand how SAM defines Lambda, DynamoDB, API Gateway, and other serverless resources.
* Study backend serverless structure including function handler, service layer, repository layer, test events, and DynamoDB tables.
* Understand why all business logic should not be placed directly inside the Lambda handler.
* Learn DynamoDB design by thinking about query patterns before table design.
* Study Partition Key, Sort Key, GSI, Query, Scan, and PAY_PER_REQUEST.
* Identify cost-related resources such as Lambda invocation, DynamoDB, API Gateway, and CloudWatch Logs.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | **AWS SAM and template.yaml** <br>- Studied SAM project structure <br>- Learned the role of `template.yaml` <br>- Reviewed how infrastructure is defined as code | 18/05/2026 | 18/05/2026 | AWS SAM Documentation |
| 2 | **Lambda handler, service layer, and repository layer** <br>- Studied backend code separation <br>- Compared handler logic and service logic <br>- Reviewed repository access to DynamoDB | 19/05/2026 | 19/05/2026 | AWS Lambda Best Practices |
| 3 | **Event JSON for Lambda testing** <br>- Created sample event payloads <br>- Tested Lambda behavior with simulated input <br>- Reviewed validation and response output | 20/05/2026 | 20/05/2026 | Lambda Console Testing Guide |
| 4 | **DynamoDB access pattern design** <br>- Studied partition key and sort key design <br>- Reviewed GSI usage <br>- Compared Query and Scan behavior | 21/05/2026 | 21/05/2026 | DynamoDB Developer Guide |
| 5 | **Serverless cost control points** <br>- Reviewed Lambda invocation cost <br>- Reviewed DynamoDB on-demand capacity <br>- Noted API Gateway and CloudWatch Logs cost factors | 22/05/2026 | 22/05/2026 | AWS Pricing Documentation |

### Week 5 Achievements:

* **Understood AWS SAM:** Learned that SAM helps manage serverless infrastructure and application resources.
* **Understood template.yaml:** Learned that `template.yaml` defines backend resources such as Lambda functions, APIs, and DynamoDB tables.
* **Understood backend structure:** Learned the flow Lambda Function -> Service -> Repository -> DynamoDB.
* **Understood DynamoDB design principles:** Learned why DynamoDB should be designed based on access patterns.
* **Built implementation foundation:** Prepared the foundation for job ingestion, search jobs, Cognito authentication, and CV matching.
