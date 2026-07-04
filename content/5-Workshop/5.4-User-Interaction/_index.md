---
title : "User Interaction"
date: 2026-07-03
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

#### Overview

In this section, we will explore the architecture and detailed data flows for the components that directly handle user interactions within the Job-Matching platform.

The core modules include:
1. **API Gateway & WAF:** Managing request routing, CORS, and protecting endpoints from web application vulnerabilities.
2. **User Authentication (Cognito Auth):** Setting up sign-up, sign-in, and securing API requests with JWT Tokens.
3. **Databases & Storage (DynamoDB & S3):** Saving favorite jobs in DynamoDB and managing resume PDFs in S3.
4. **Core API Lambdas:** Business logic coordinating job queries and resume uploads via AWS Lambda.
5. **Frontend Hosting (Amplify):** Hosting the Next.js application with continuous deployment.

#### Content

1. [API Gateway & WAF](5.4.1-API-Gateway-WAF/)
2. [Cognito Auth](5.4.2-Cognito-Auth/)
3. [Databases & Storage](5.4.3-Databases-Storage/)
4. [Core API Lambdas](5.4.4-Core-API-Lambdas/)
5. [Frontend Hosting (Amplify)](5.4.5-Frontend-Hosting-Amplify/)
