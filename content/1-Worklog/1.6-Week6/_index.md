---
title: "Week 6 Worklog"
date: 2026-05-25
weight: 6
chapter: false
pre: "<b>1.6.</b> "
---

### Week 6 Objectives:

* Practice deploying and managing advanced Amazon EC2 instances following professional standards under direct mentorship.
* Master credential-less cloud authorization mechanisms by successfully applying secure IAM Roles to infrastructure components.
* Build an end-to-end cloud infrastructure integration: Enabling EC2 instances to programmatically interact with Amazon S3 while tracking server health metrics via CloudWatch.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | ---------- | --------------- | ------------------ |
| Mon | - Receive technical requirements and standards for **Amazon EC2 Management** workflows.<br>- Launch and optimize performance metrics of an EC2 instance following real-world engineering blueprints. | 25/05/2026 | 25/05/2026 | Mentor Guidance / AWS Console |
| Tue | - Deep dive into secure programmatic access concepts using **IAM Roles and Policies**.<br>- Differentiate the secure framework of IAM Roles (Temporary Tokens) versus IAM Users (Static Access Keys) to reduce credential leakage risks. | 26/05/2026 | 26/05/2026 | <https://docs.aws.amazon.com/iam/> |
| Wed | - Investigate advanced principles of **Amazon S3 Storage Management** (Data access boundaries, server-side encryption, and advanced object handling).<br>- Architect a secure access topology for upcoming compute-to-storage server integration. | 27/05/2026 | 27/05/2026 | <https://docs.aws.amazon.com/s3/> |
| Thu | - **Hands-on Secure System Integration Lab:**<br>&emsp; + Author a custom JSON IAM Policy with targeted S3 permissions, and attach it to an operational IAM Role designed for EC2 resources.<br>&emsp; + Associate the IAM Role with the active EC2 instance and run file management commands to verify access to S3 without configuring local keys. | 28/05/2026 | 29/05/2026 | AWS Management Console / Terminal |
| Fri | - **Hands-on Cloud Observability Engineering:**<br>&emsp; + Leverage **AWS CloudWatch Basics** to engineer personalized, performance-driven tracking Dashboards for active EC2 workloads.<br>&emsp; + Set up centralized system log aggregations, trace live computational metrics, and submit the engineering progress report to the Mentor. | 29/05/2026 | 30/05/2026 | <https://docs.aws.amazon.com/cloudwatch/> |

### Week 6 Achievements:

* **Enterprise Server Provisioning (EC2 Management):**
  * Successfully initialized and optimized high-performance EC2 environments adhering to industry production patterns and specific blueprints outlined by the Mentor.
* **Credential-less Security Framework Mastery (IAM):**
  * Mastered the architecture of IAM Roles, gaining a practical understanding of granting granular permissions to code running inside EC2 using Temporary Security Credentials, removing insecure static assets from the infrastructure.
* **Functional Cloud Architecture Integration:**
  * Engineered a fully automated cloud integration flow: Authorizing a Linux EC2 instance via IAM Roles to dynamically perform data mutations and file streams onto Amazon S3 buckets safely.
* **Infrastructure Observability & Visual Monitoring (CloudWatch):**
  * Gained control over the AWS CloudWatch suite, successfully building real-time visual system performance Dashboards to manage infrastructure, ensuring instant alerting availability for operational issues.