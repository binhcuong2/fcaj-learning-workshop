---
title: "Workshop"
date: 2026-07-03
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Serverless Jobs Matching Platform

#### Overview

In this workshop, you will build the **Jobs Matching Platform** - an automated system for aggregating job listings and evaluating candidate profiles (CVs) entirely using AWS Serverless services (AWS Lambda, DynamoDB, SQS, S3, API Gateway, Cognito, EventBridge, WAF, and Amplify).

You will configure and build:
+ **Jobs Ingestion Pipeline** - Automate fetching job listings using EventBridge, Lambda, SQS, and saving them to DynamoDB.
+ **User Interaction** - Secure API Gateway, Cognito User Pools for authentication, DynamoDB for database storage, Lambda business APIs, and deploy the Frontend with AWS Amplify.
+ **CV Matching Flow** - Process uploaded CVs in S3, extract content using Lambda, call the Gemini API for suitability evaluation, and store results.
+ **Operations & Security** - Configure IAM policies, API key rotation, CloudWatch monitoring & alarms, and AWS Budgets for cost control.

#### Content

1. [Introduction](5.1-Workshop-overview/)
2. [Prerequiste](5.2-Prerequiste/)
3. [Jobs Ingestion Pipeline](5.3-Job-Ingestion/)
4. [User Interaction](5.4-User-Interaction/)
5. [CV Matching Flow](5.5-CV-Matching-Flow/)
6. [Operations & Security](5.6-Operations-Security/)
7. [Cleanup](5.7-Cleanup/)