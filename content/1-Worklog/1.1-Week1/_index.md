---
title: "Week 1 Worklog"
date: 2026-04-20
weight: 1
chapter: false
pre: "<b>1.1.</b> "
---

### Week 1 Objectives:
* Complete onboarding, integrate with the working environment, and get to know the team members.
* Study the foundational concepts of AWS Global Infrastructure and the identity management framework (IAM).
* Establish a secure local development environment, configure account security, and install essential development tools (Dev Tools).

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | ------------ | --------------- | ------------------ |
| Mon | - Attend the onboarding program and get familiar with internal regulations.<br>- Study the fundamentals of **AWS Global Infrastructure** (Regions, Availability Zones, Edge Locations). | 17/04/2026 | 17/04/2026 | <https://aws.amazon.com/about-aws/global-infrastructure/> |
| Tue | - Create and configure an AWS account dedicated for interns.<br>- Explore and navigate the **AWS Management Console** interface.<br>- **Practice:** Set up Multi-Factor Authentication (MFA) to secure the root account. | 18/04/2026 | 21/04/2026 | <https://aws.amazon.com/free/> |
| Wed | - Deep dive into **AWS IAM** (Identity and Access Management): Define and distinguish Users, Groups, Roles, and Policies.<br>- **Practice:** Create custom JSON policies adhering strictly to the **"Least Privilege"** principle. | 22/04/2026 | 22/04/2026 | <https://docs.aws.amazon.com/iam/> |
| Thu | - Begin local development environment setup:<br>&emsp; + Install **AWS CLI** and configure credentials (Access Key / Secret Key).<br>&emsp; + Set up **Visual Studio Code** along with essential extensions for Cloud/DevOps. | 23/04/2026 | 23/04/2026 | <https://docs.aws.amazon.com/cli/> |
| Fri | - Continue local environment setup and version control configuration:<br>&emsp; + Install **Git / GitHub** and configure secure SSH Keys.<br>&emsp; + Install **Docker Desktop** and enable virtualization backend (WSL2/Hyper-V).<br>- Test basic CLI commands and troubleshoot setup issues. | 24/04/2026 | 24/04/2026 | <https://docs.docker.com/desktop/> |

### Week 1 Achievements:

* **Environment & Processes:** Successfully completed the onboarding process, established smooth communication with team members, and fully understood internal workflows.
* **Cloud Infrastructure Mindset:** Gained a solid understanding of how AWS physically distributes infrastructure into Regions and Availability Zones (AZs) to design systems with High Availability (HA).
* **Account Management & Security:**
  * Successfully initialized the intern AWS account and activated Multi-Factor Authentication (MFA) to prevent basic security risks.
  * Mastered identity management concepts in IAM, successfully wrote basic JSON policies, and correctly distinguished when to use IAM Users, Groups, or Roles.
* **Development Tools Setup (Dev Tools):** Allocated sufficient time to perfectly configure local environments and fully resolve local configuration conflicts:
  * **AWS CLI:** Successfully linked local machines to the AWS account using Access Keys/Secret Keys, setting default regions and formatting output to `json`.
  * **Visual Studio Code:** Standardized the coding environment with proper configurations.
  * **Git / GitHub:** Established secure source control synchronization via SSH Keys authentication.
  * **Docker Desktop:** Successfully configured the virtualization layer (WSL2/Hyper-V), fully ready for upcoming containerized application deployments.