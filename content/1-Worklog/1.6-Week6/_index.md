---
title: "Week 6 Worklog"
date: 2026-07-03
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Understand the role of Amazon Cognito in user authentication.
* Study User Pool, App Client, email verification, JWT Token, ID Token, Access Token, and Refresh Token.
* Configure Cognito using AWS SAM.
* Set up email and password registration and login.
* Configure App Client without client secret because the frontend runs in the browser.
* Add frontend outputs such as User Pool ID, App Client ID, and Region.
* Test Cognito with AWS CLI for sign up, confirm sign up, login, and token refresh.
* Understand how the frontend gets an ID Token to call protected APIs.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | **User Pool and App Client** <br>- Studied Cognito User Pool <br>- Learned the purpose of App Client <br>- Reviewed authentication flow components | 25/05/2026 | 25/05/2026 | Amazon Cognito Documentation |
| 2 | **Cognito in SAM template** <br>- Reviewed SAM resource definition <br>- Added Cognito-related configuration conceptually <br>- Identified required outputs for frontend | 26/05/2026 | 26/05/2026 | AWS SAM and Cognito Documentation |
| 3 | **Email verification and password policy** <br>- Studied user verification flow <br>- Reviewed password requirements <br>- Identified common signup errors | 27/05/2026 | 27/05/2026 | Cognito User Pool Guide |
| 4 | **AWS CLI auth testing** <br>- Tested sign up flow <br>- Tested confirm sign up and login flow <br>- Reviewed refresh token behavior | 28/05/2026 | 28/05/2026 | AWS CLI Cognito Commands |
| 5 | **ID Token and protected API usage** <br>- Studied JWT token usage <br>- Learned how frontend sends token to backend <br>- Prepared for JWT Authorizer integration | 29/05/2026 | 29/05/2026 | Cognito JWT Documentation |

### Week 6 Achievements:

* **Understood Cognito authentication:** Learned that Cognito manages registration, login, and authentication.
* **Distinguished User Pool and App Client:** Understood the role of each Cognito component.
* **Understood browser App Client configuration:** Learned why frontend browser applications should not use an App Client Secret.
* **Learned independent auth testing:** Understood how to test auth flow with AWS CLI before frontend integration.
* **Prepared for protected APIs:** Built the foundation for protecting APIs with Cognito JWT Authorizer.
