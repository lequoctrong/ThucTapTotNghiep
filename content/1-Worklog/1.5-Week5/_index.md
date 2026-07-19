---
title: "Week 5 Worklog"
date: 2026-05-18
weight: 5
chapter: false
pre: "<b>1.5.</b> "
---

### Week 5 Objectives:

* Audit, review, and optimize security configurations for all previously provisioned cloud resources (EC2, S3, IAM).
* Elevate administrative capabilities by utilizing the AWS CLI command-line interface instead of graphical interfaces (Console).
* Consolidate practical insights and standardize operational workflows to update internal technical documentation.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | ---------- | --------------- | ------------------ |
| Mon | - Execute an **AWS EC2 Review**: Audit instance health statuses and optimize compute sizing.<br>- Review **Security Group** architectures, inspecting and tightening open Inbound paths (restricting insecure `0.0.0.0/0` exposure). | 18/05/2026 | 19/05/2026 | AWS Management Console |
| Tue | - Perform an **Amazon S3 Basics Review** & **IAM Fundamentals** audit: Evaluate object data safety and flag accidental Public Access exposure.<br>- Audit existing IAM User accounts, revoking deprecated or unused Access Keys to eliminate lingering access risks. | 19/05/2026 | 19/05/2026 | <https://docs.aws.amazon.com/iam/> |
| Wed | - Investigate **AWS CLI Introduction** documentation (Syntax standards, structured JSON Outputs, and advanced data filtering attributes like `--query` and `--filter`).<br>- Learn to navigate terminal help manuals natively using the `aws help` module. | 20/05/2026 | 20/05/2026 | <https://docs.aws.amazon.com/cli/> |
| Thu | - **Hands-on Operations with AWS CLI:**<br>&emsp; + Utilize the terminal to poll remote resource status lists (`aws ec2 describe-instances`, `aws s3 ls`, `aws iam list-users`).<br>&emsp; + Practice initializing and configuring a complete Security Group firewall architecture purely via CLI commands. | 21/05/2026 | 21/05/2026 | Terminal / AWS CLI |
| Fri | - **Technical Synthesis & Internal Documentation:**<br>&emsp; + Compile operational log histories, documenting key engineering errors and troubleshooting runbooks faced during the labs.<br>&emsp; + Author, update, and standardize internal technical reference guides for team deployment. | 22/05/2026 | 23/05/2026 | Internal Knowledge Base / Markdown Editor |

### Week 5 Achievements:

* **Security Governance & Asset Audit Mindset:**
  * Successfully audited and re-aligned security baselines for active EC2 instances, S3 Buckets, and IAM accounts; terminated unnecessary open ports and restricted untrusted IP boundaries.
  * Cultivated a systematic security auditing methodology applicable to production-grade Cloud architectures.
* **Command-Line Administrative Proficiency (AWS CLI):**
  * Transitioned comfortably from visual console workflows (Click-ops) toward programmatic command-line automation (CLI-ops).
  * Mastered core retrieval syntax, demonstrating the ability to parse JSON terminal payloads to extract explicit configuration attributes quickly.
  * Programmatically initialized and configured functional network security firewalls without calling the web UI.
* **Technical Asset Packing (Documentation & Knowledge Sharing):**
  * Successfully engineered and updated standard internal onboarding knowledge bases, documenting explicit procedural execution paths alongside historical error resolutions.
  * Refined core Technical Writing capabilities, improving collaborative knowledge hand-offs and asset-sharing readiness within the engineering division.