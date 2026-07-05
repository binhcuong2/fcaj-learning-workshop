---
title: "Week 9 Worklog"
date: 2026-07-03
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Learn how a Next.js/React frontend connects to Cognito through `aws-amplify`.
* Configure `.env.local` for AWS Region, Cognito User Pool ID, App Client ID, and OAuth domain/callback URL if Google Login is used.
* Separate authentication logic into a service layer instead of placing it directly in UI components.
* Work with auth functions such as registerWithEmail, confirmRegister, loginWithEmail, logout, getAuthUser, and getIdToken.
* Complete Google Login, Forgot Password, and Reset Password flows.
* Learn how the frontend gets an ID Token to call protected backend APIs.
* Review common auth errors such as wrong User Pool ID, App Client ID, region, callback/logout URL, unconfirmed email, password policy mismatch, or OAuth redirect mismatch.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | **Amplify Auth and frontend environment variables** <br>- Configured Auth-related environment variables <br>- Reviewed Cognito region and IDs <br>- Checked OAuth settings when needed | 15/06/2026 | 15/06/2026 | Amplify Auth Documentation |
| 2 | **Separate auth logic into a service** <br>- Moved auth operations away from UI components <br>- Defined reusable auth functions <br>- Improved maintainability | 16/06/2026 | 16/06/2026 | Frontend architecture notes |
| 3 | **Email/password auth flow** <br>- Completed register, confirm, login, logout, and token retrieval concepts <br>- Reviewed error cases <br>- Checked user session flow | 17/06/2026 | 17/06/2026 | Cognito Auth Guide |
| 4 | **Google Login** <br>- Reviewed OAuth domain and callback URL <br>- Checked Hosted UI/federated login flow <br>- Identified redirect configuration issues | 18/06/2026 | 18/06/2026 | Cognito Google IdP Documentation |
| 5 | **Forgot Password and Reset Password** <br>- Studied recovery flow <br>- Reviewed confirmation code handling <br>- Connected password recovery with auth service | 19/06/2026 | 19/06/2026 | Amplify Password Recovery Guide |

### Week 9 Achievements:

* **Understood frontend-to-Cognito integration:** Learned how the frontend connects to Cognito through Amplify Auth.
* **Separated auth logic from UI:** Improved structure by keeping auth operations outside components.
* **Understood environment configuration:** Learned the role of `.env.local` and why it should not be committed to GitHub.
* **Completed core auth flows:** Covered email/password login, Google Login, Forgot Password, and Reset Password.
* **Prepared protected API access:** Learned how to get an ID Token for backend APIs.
