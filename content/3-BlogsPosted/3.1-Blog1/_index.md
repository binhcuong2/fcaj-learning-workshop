---
title: "AI Gateway – AI Management Solution on AWS with Amazon Bedrock and Amazon API Gateway"
date: 2026-07-03
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

## The Challenge and the AI Gateway Solution

As generative AI applications become increasingly widespread within enterprises, allowing every system direct access to AI models can lead to various challenges, such as difficulties in cost control, lack of authorization mechanisms, and challenges in tracking usage metrics.

To address this issue, AWS proposes the AI Gateway model, using Amazon API Gateway as an intermediary layer between users and Amazon Bedrock. This architecture helps enterprises control access, limit request quotas, track costs, and enhance security when deploying Generative AI applications.

This model utilizes Amazon API Gateway as the front-end access layer for Amazon Bedrock. The solution supports key features such as user authentication and authorization through existing identity systems (e.g., JWT), usage limit management, request throttling, API lifecycle management, canary releases, and enhanced security via AWS WAF. In addition, API Gateway supports real-time streaming responses, allowing results from the AI model to be sent directly to the user as they are generated rather than waiting for the entire process to complete.

Thanks to these capabilities, the AI Gateway not only acts as an access portal to Amazon Bedrock but also helps enterprises control costs, enhance security, and manage AI usage more effectively at scale. This reference architecture provides detailed control over LLM access using fully managed AWS services, operating transparently to client applications and integrating seamlessly into existing enterprise environments.

## Core Components of the Solution

The solution consists of five core components:

*   **Amazon Route 53 (Custom Domain Routing Management):** Responsible for allowing users to access the AI Gateway via the enterprise's private domain name instead of using the default Amazon API Gateway domain. This makes the system more professional and easier to integrate into the organization's existing infrastructure.
*   **Amazon API Gateway (Unified Access Portal):** Serves as the Entry Point for all requests sent to the AI system. This service provides crucial features such as Authorization, Request Throttling, Lifecycle Management, Rate Limiting, and Monitoring, helping enterprises control access, manage request traffic, monitor system activity, and ensure stability and security.
*   **AWS Lambda Authorizer (Flexible Authentication and Authorization):** Handles authorization for incoming requests (e.g., validating JWT tokens against existing authentication systems). For specific deployment needs, you can build custom authorization logic within the Lambda Authorizer, integrate with Amazon Cognito User Pools, or use other API Gateway authorization mechanisms.
*   **Lambda Integration (Dynamic Request Routing and Signing):** Acts as a Dynamic Request Forwarder that signs incoming requests with AWS credentials and routes them to the appropriate Amazon Bedrock endpoints. This component preserves all original request information (including API actions and parameters) to support current and future Amazon Bedrock APIs without requiring client source code changes.
*   **Amazon Bedrock (AI Service Platform):** Provides direct access to Foundation Models and other powerful AI capabilities.

## Advantages and Conclusion

The main advantage of this architecture is its transparency to client applications and its future-proof design. Client applications can continue to use AWS SDKs (such as Boto3) to access Amazon Bedrock features (like LLMs and Knowledge Bases) just as they would when calling the API directly, while the AI Gateway silently handles authentication, quota management, and other administrative tasks in the background.

This model provides a scalable way to manage access to foundation models through Amazon Bedrock. Originally developed and successfully deployed by Dynatrace to serve their global user base, the solution has proven its effectiveness at an enterprise scale. By leveraging the robust features of Amazon API Gateway, organizations can establish the necessary controls while maintaining all the benefits of a serverless architecture.

---

*Original post:* [Building an AI Gateway to Amazon Bedrock with Amazon API Gateway](https://aws.amazon.com/blogs/architecture/building-an-ai-gateway-to-amazon-bedrock-with-amazon-api-gateway/)