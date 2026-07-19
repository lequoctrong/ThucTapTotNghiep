---
title: "Week 9 Worklog"
date: 2026-06-15
weight: 9
chapter: false
pre: "<b>1.9.</b> "
---

### Week 9 Objectives:

* Learn and master centralized cloud repository management for container artifacts using Amazon ECR.
* Deep dive into advanced container orchestration concepts and lifecycles within Amazon ECS (Clusters, Task Definitions, Services).
* Successfully deploy containerized micro-applications on a Serverless infrastructure using AWS Fargate while embedding secure networking and identity policies.
* Practice cost-optimization procedures by conducting exhaustive resource cleanup after finishing the practical infrastructure assignments.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | ---------- | --------------- | ------------------ |
| Mon | - Research cloud registry capabilities utilizing **Amazon ECR** (Elastic Container Registry).<br>- **Hands-on with AWS CLI:** Practice authenticating the local terminal, tagging images via `docker tag`, and executing `docker push` pipelines to upload local Docker Images onto Amazon ECR. | 15/06/2026 | 16/06/2026 | <https://docs.aws.amazon.com/ecr/> |
| Tue | - Study the architectural abstractions governing **Amazon ECS** (Elastic Container Service).<br>- Differentiate the precise infrastructure boundaries between a **Cluster** (Resource Group), a **Task Definition** (Container Blueprint), and a **Service** (State Maintenance). | 16/06/2026 | 16/06/2026 | <https://docs.aws.amazon.com/ecs/> |
| Wed | - **Hands-on Secure Network & Identity Layout for ECS:**<br>&emsp; + Map secure isolated networking structures (VPC, Subnets) to house targeted ECS Tasks.<br>&emsp; + Enforce granular isolation layers using IAM Roles (Task Role vs. Task Execution Role) alongside restricted Security Group firewall policies. | 17/06/2026 | 17/06/2026 | AWS Management Console |
| Thu | - **Hands-on Serverless Container Deployment:**<br>&emsp; + Draft a standard Task Definition referencing the remote ECR image artifact, and spin up a mock sample container app running entirely under **AWS Fargate** (Serverless computational profiles without managing EC2 units).<br>&emsp; + Verify endpoint connectivity over the Internet. | 18/06/2026 | 18/06/2026 | AWS ECS Console |
| Fri | - **Auditing, Resource Cleanup & Worklog Synthesis:**<br>&emsp; + Inspect runtime logs, audit application footprints, and systematically wipe out (clean up) deployed ECR repositories, ECS clusters, and Fargate targets to mitigate automated billing expenses.<br>&emsp; + Author and format the technical **Week 9 Worklog**. | 19/06/2026 | 20/06/2026 | AWS Console / Markdown Editor |

### Week 9 Achievements:

* **Cloud Registry Operations Proficiency (Amazon ECR):**
  * Mastered programmatic AWS CLI logic to govern remote registries, executing secure repository logging, uniform tagging formats, and successful image distributions from a local workstation onto Amazon ECR.
* **Serverless Container Orchestration Mindset (ECS & AWS Fargate):**
  * Acquired solid foundational insights into Amazon ECS operations, clearly interpreting the step-by-step lifecycle from structural declarative design schemas (Task Definition) up to operational orchestration (Service maintenance).
  * Successfully initialized modular container micro-apps using AWS Fargate, acknowledging the technical advantages of abstract Serverless execution layers where host patching and OS maintenance are completely eliminated.
* **Advanced Network Security Hardening:**
  * Configured precise target networking blocks (VPCs/Subnets) and constructed strict Security Group rules to secure traffic pathways across running ECS Tasks.
  * Correctly applied least-privilege constraints separating IAM Task Roles (container internal permissions) from Task Execution Roles (ECS service agent image pulling capabilities).
* **Proactive Cost Governance Capabilities:**
  * Cultivated production-grade cost-awareness habits by verifying system status and executing comprehensive teardown routines (clean up) for cloud-based services post-lab, avoiding unnecessary or stray billing overages.