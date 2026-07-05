---
title: "Week 7 Worklog"
date: 2026-07-03
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Understand the role of Amazon API Gateway in a serverless backend.
* Configure API Gateway with AWS SAM to receive HTTP requests from the frontend.
* Learn how API Gateway transforms an HTTP request into a Lambda event.
* Distinguish between public routes and protected routes.
* Understand Cognito JWT Authorizer for API protection.
* Test public routes such as `GET /health` and `GET /jobs/search`.
* Learn how the frontend sends tokens through the `Authorization: Bearer <id_token>` header.
* Understand how Lambda can read user data from JWT claims, especially `claims.sub`.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | **API Gateway and HTTP routes** <br>- Studied API Gateway purpose <br>- Reviewed HTTP route definition <br>- Learned frontend-to-backend routing flow | 01/06/2026 | 01/06/2026 | Amazon API Gateway Documentation |
| 2 | **Public backend routes** <br>- Reviewed public API concept <br>- Studied route definition in SAM <br>- Prepared routes that do not require authentication | 02/06/2026 | 02/06/2026 | AWS SAM API Guide |
| 3 | **Protected routes and Cognito JWT Authorizer** <br>- Studied protected API design <br>- Learned how JWT Authorizer validates requests <br>- Reviewed token-based access control | 03/06/2026 | 03/06/2026 | API Gateway JWT Authorizer Documentation |
| 4 | **Testing public endpoints** <br>- Tested `/health` endpoint concept <br>- Tested `/jobs/search` endpoint concept <br>- Reviewed status codes and responses | 04/06/2026 | 04/06/2026 | API testing notes |
| 5 | **Reading claims.sub in Lambda** <br>- Studied requestContext authorizer claims <br>- Learned how Lambda identifies authenticated users <br>- Prepared for user-specific API features | 05/06/2026 | 05/06/2026 | Cognito JWT Claims Documentation |

### Week 7 Achievements:

* **Understood API Gateway:** Learned that API Gateway is the middleware layer between frontend and Lambda.
* **Learned HTTP route definition:** Understood how routes can be defined in AWS SAM.
* **Distinguished public and protected APIs:** Learned when authentication is required and when routes can remain public.
* **Understood JWT Authorizer:** Learned how JWT Authorizer helps validate authenticated users.
* **Prepared for user-based APIs:** Built the foundation for favorite jobs, CV upload, CV analysis, and matching history.
