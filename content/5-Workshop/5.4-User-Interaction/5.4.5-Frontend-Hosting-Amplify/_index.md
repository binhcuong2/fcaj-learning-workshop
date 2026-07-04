---
title : "Frontend Application Deployment (Frontend Hosting Amplify)"
date: 2026-07-03
weight : 5
chapter : false
pre : " <b> 5.4.5. </b> "
---

Deploy and distribute the Next.js user interface application using **AWS Amplify Hosting** with automatic CI/CD configured to trigger when source code is pushed to GitHub.

---

## 1. Detailed Data Flow
* **Application Initialization:** Client loads the webpage -> Reads environment configuration files loaded at build time -> Initializes Amplify Auth SDK settings.
* **Static Route Protection (Routing Protection):**
  * When a user accesses protected paths such as `/favorites`, `/upload-cv`, or `/matching`.
  * The frontend calls the `fetchAuthSession()` function to check the current session.
  * If the session is empty: Redirects the user to the `/login` page.
  * If the session exists: Renders the user interface and retrieves the corresponding token to prepare for API calls.

---

## 2. Deployment Guide on Amplify Console

1. **Link Git Repository:**
   * Go to the AWS Console -> AWS Amplify -> Select **Create new app**.
   * Choose your source code provider (e.g. **GitHub**) and connect the repository containing the `Jobs-Matching-Platform` project.
   * Select the deployment branch (e.g. `main` or `dev`).

2. **Configure Environment Variables in Amplify Console:**
   * Navigate to **Hosting** -> **Environment variables**.
   * Add the required environment variables (described in the configuration section below) with their respective backend outputs obtained after SAM deployment.

![Amplify Environment Variables](/images/5-Workshop/5.4-User-Interaction/amplify-environment-variables.png)

3. **Enable Continuous Deployment:**
   * Click **Save and deploy**.
   * Every time a new commit is pushed to the chosen Git branch, AWS Amplify will automatically trigger the build and deployment pipeline for the frontend without downtime.

![Amplify Deployment Status](/images/5-Workshop/5.4-User-Interaction/amplify-deploy-success.png)

---

## 3. Environment & Build Configuration

### A. Environment Variables
When hosting the application on the AWS Amplify Console, the following environment variables must be defined so that the client points to the correct backend endpoint:

* **`NEXT_PUBLIC_API_BASE_URL`**: Root URL of the API Gateway to fetch data. Example value: `https://38ethw76uh.execute-api.ap-southeast-1.amazonaws.com/dev`
* **`NEXT_PUBLIC_AWS_REGION`**: AWS Region hosting the Cognito User Pool. Example value: `ap-southeast-1`
* **`NEXT_PUBLIC_COGNITO_USER_POOL_ID`**: Cognito User Pool ID. Example value: `ap-southeast-1_xxxxx`
* **`NEXT_PUBLIC_COGNITO_USER_POOL_CLIENT_ID`**: Cognito App Client ID. Example value: `xxxxxxxxxxxxxx`

### B. Build Settings (`amplify.yml`)
Amplify will automatically detect the Next.js configuration. Ensure the Amplify build spec matches your project's Next.js setup:

```yaml
version: 1
frontend:
  phases:
    preBuild:
      commands:
        - cd frontend
        - npm ci
    build:
      commands:
        - npm run build
  artifacts:
    baseDirectory: frontend/.next
    files:
      - '**/*'
  cache:
    paths:
      - frontend/node_modules/**/*
      - frontend/.next/cache/**/*
```
