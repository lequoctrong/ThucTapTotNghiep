---
title: "Week 4 Worklog"
date: 2026-05-11
weight: 4
chapter: false
pre: "<b>1.4.</b> "
---

### Week 4 Objectives:

* Familiarize with modern system design paradigms focusing on abstract computing frameworks (Serverless) and automation.
* Master the core computational mechanics of AWS Lambda functions and the conceptual foundations of Event-driven Architecture.
* Gain hands-on experience building and deploying Serverless APIs by integrating AWS Lambda with Amazon API Gateway.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | ---------- | --------------- | ------------------ |
| Mon | - Explore the overall concepts of **Introduction to Serverless** models and its operational benefits over traditional servers.<br>- Study the technical papers on **AWS Lambda Fundamentals** (Lifecycle, Execution Roles, Timeout, Memory limitations). | 11/05/2026 | 11/05/2026 | <https://docs.aws.amazon.com/lambda/> |
| Tue | - Deep dive into the architectural principles of **Event-driven Architecture** within cloud eco-systems.<br>- Understand the internal mechanics of Event Triggers from various AWS computational sources (such as S3, CloudWatch, or API payloads). | 12/05/2026 | 12/05/2026 | <https://aws.amazon.com/event-driven-architecture/> |
| Wed | - Study the foundational engineering concepts behind managed endpoints with **API Gateway Basics**.<br>- Research distinctions between HTTP APIs and REST APIs, alongside standard client Routing and backend Integration logic. | 13/05/2026 | 13/05/2026 | <https://docs.aws.amazon.com/apigateway/> |
| Thu | - **Hands-on Function Provisioning & Triggers:**<br>&emsp; + Create a basic AWS Lambda function (utilizing Node.js or Python templates) within the AWS Console.<br>&emsp; + Configure and mock automated Event Payloads to evaluate operational trigger behaviors of the functional code. | 14/05/2026 | 14/05/2026 | AWS Management Console |
| Fri | - **Hands-on Serverless API Integration:**<br>&emsp; + Initialize a clean HTTP/REST API endpoint utilizing Amazon API Gateway.<br>&emsp; + Construct a secure Integration backend configuration linking the API Gateway directly to the target AWS Lambda function.<br>&emsp; + Deploy the managed API and utilize native tooling (Web Browser/Postman) to validate end-to-end cloud traffic streams. | 15/05/2026 | 16/05/2026 | AWS Console / API Client |

### Week 4 Achievements:

* **Serverless Engineering Mindset:**
  * Comprehended Serverless system designs, acknowledging micro-billing efficiencies (Pay-as-you-go) and the absolute minimization of routine hardware operations.
  * Achieved precise execution knowledge regarding AWS Lambda configurations, safely specifying execution memory, lifecycle timeouts, and mandatory IAM Execution Roles.
* **Event-driven Automation Proficiency:**
  * Mastered asynchronous architecture flows, demonstrating an ability to align distinct Event Sources to run standalone compute code gracefully when state changes happen.
* **Serverless API Delivery Capabilities:**
  * Grasped the architectural significance of Amazon API Gateway as a highly available reverse-proxy entry point for public HTTP requests.
  * Successfully engineered and delivered a fully decoupled Serverless API cluster: Mapping client API Gateway interactions -> Triggering targeted AWS Lambda compute runtime -> Streaming processed telemetry back to external consumers.