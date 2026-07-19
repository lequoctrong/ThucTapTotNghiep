---
title: "Week 2 Worklog"
date: 2026-04-27
weight: 2
chapter: false
pre: "<b>1.2.</b> "
---

### Week 2 Objectives:
* Deep dive into and master the core AWS services: Compute (EC2), Storage (S3), and Networking (VPC).
* Grasp foundational cloud security concepts (Security Groups & NACLs) and public-key cryptography mechanisms (Key Pairs).
* Gain hands-on experience in building cloud environments: Launching virtual servers, provisioning static IPs, uploading/downloading data, and establishing secure remote access.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | ---------- | --------------- | ------------------ |
| Mon | - Learn the computing concepts of **Amazon EC2 Basics** (Instance Types, Public/Private/Elastic IPs).<br>- Study the fundamentals of object storage with **Amazon S3 Storage** (Buckets, Objects, S3 Storage Classes). | 27/04/2026 | 27/04/2026 | <https://docs.aws.amazon.com/ec2/> <br> <https://docs.aws.amazon.com/s3/> |
| Tue | - **Hands-on Amazon S3:**<br>&emsp; + Initialize a personal Amazon S3 Bucket.<br>&emsp; + Practice uploading, downloading, managing objects, and configuring basic access permissions. | 28/04/2026 | 28/04/2026 | AWS Management Console |
| Wed | - Study the **Introduction to Networking on AWS** whitepaper (Understand VPC, Subnets, and Internet Gateways).<br>- Distinguish network security mechanisms between **Security Groups** (Stateful) and **NACLs** (Stateless). | 29/04/2026 | 29/04/2026 | <https://docs.aws.amazon.com/vpc/> |
| Thu | - **Hands-on Network & Server Provisioning:**<br>&emsp; + Generate a new Key Pair and configure secure Security Groups/NACLs regulations.<br>&emsp; + Successfully launch an Amazon EC2 instance running Linux OS. | 30/04/2026 | 30/04/2026 | AWS Management Console |
| Fri | - **Hands-on IP & Routing Configurations:**<br>&emsp; + Allocate and associate an Elastic IP (EIP) to the newly created EC2 instance.<br>&emsp; + Verify Route Tables to guarantee proper inbound/outbound internet routing. | 01/05/2026 | 01/05/2026 | AWS Management Console |


### Week 2 Achievements:

* **Compute & Storage Management (EC2 & S3):**
  * Fully understood Amazon EC2 core mechanics, distinguished Public, Private, and Elastic IPs, and learned how to select optimal Instance Types.
  * Mastered storage operations on Amazon S3, including bucket creation, secure object manipulation, and data lifecycle optimization using S3 storage classes.
* **Cloud Networking & Firewall Mindset (VPC, SG, NACL):**
  * Acquired solid foundational knowledge of VPC architecture and essential cloud internet routing components.
  * Clearly differentiated the security boundaries of Security Groups (instance-level firewall) and NACLs (subnet-level firewall) to write precise Inbound/Outbound rules.
* **Production Environment Deployment:**
  * Successfully launched a Linux EC2 instance and attached an Elastic IP to maintain a static entry point upon instance reboots.
  * Leveraged standard cryptographic Key Pairs to securely connect from the local workstation into the remote cloud server via SSH.
  * Developed strong troubleshooting skills by independently resolving standard Network Timeout bugs using fundamental firewall and routing verification mindsets.