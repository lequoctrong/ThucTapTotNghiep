---
title: "Week 11 Worklog"
date: 2026-07-17
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* **Automate Database Migration via AWS Lambda:** Deploy a Serverless architecture (AWS Lambda) operating entirely within a Private VPC to execute DDL/DML scripts, initializing the PostgreSQL database schema for the **PharmaCare AI** ecosystem without manual external intervention.
* **Integrate Secrets Management & Execution Security:** Enforce the principle of least privilege through an IAM Role, enabling the Lambda function to dynamically decrypt and fetch the Master DB credentials from AWS Secrets Manager, completely eliminating hardcoded sensitive data in the application codebase.
* **Build a Centralized Identity Management System:** Provision **Amazon Cognito User Pool** as the primary identity verification provider to govern user registration, authentication challenges, account verification, and JSON Web Token (JWT) issuance workflows.
* **Configure Role-Based Access Control (RBAC):** Structure dedicated authorization groups (`Admin` and `Customer`) within Cognito, establishing the baseline to gate API Gateway endpoints and secure granular application modules.

---

### Tasks to be carried out this week:

| Day | Task | Assigned To | Start Date | Completion Date |
| :--- | :--- | :--- | :--- | :--- |
| Mon | **IAM Role Provisioning & Lambda Execution Permissions:** <br> - Create the IAM Role `pharmacare-lambda-role`. <br> - Attach core execution policies: `AWSLambdaBasicExecutionRole`, `AWSLambdaVPCAccessExecutionRole`, and a custom inline policy `pharmacare-read-rds-secret-policy`. | You | 13/07/2026 | 13/07/2026 |
| Tue | **Lambda Migration Function Initialization & Tuning:** <br> - Initialize the Lambda function `pharmacare-db-migration` (Node.js 22.x, x86_64) bound to 2 Private Subnets within the `pharmacare-vpc`. <br> - Adjust runtime resources: Memory `256 MB`, Timeout `60 seconds` to prevent connection drops. | You | 14/07/2026 | 14/07/2026 |
| Wed | **Source Code Packaging & RDS Migration Execution:** <br> - Develop the `index.mjs` entry point utilizing `pg` and `@aws-sdk/client-secrets-manager` libraries. <br> - Compress the source into `function.zip`, upload it to Lambda, and trigger automated schema migration on Amazon RDS PostgreSQL. | You | 15/07/2026 | 15/07/2026 |
| Thu | **Amazon Cognito User Pool & App Client Deployment:** <br> - Provision `pharmacare-user-pool` to manage the complete user account lifecycle. <br> - Configure the App Client (Client ID) to prepare for decoupled ReactJS Frontend integration. | Huỳnh Minh Phú | 16/07/2026 | 16/07/2026 |
| Fri | **User Group Configuration & Token Flow Verification:** <br> - Create the strategic `Admin` and `Customer` authorization groups inside Cognito. <br> - Test the sign-up/sign-in flows, validate JWT cryptographic signatures, and audit runtime outputs via Amazon CloudWatch Logs. | Huỳnh Minh Phú | 17/07/2026 | 17/07/2026 |

---

### Detailed Implementation:

During this sprint, the engineering team took a major step forward in maturing the core Infrastructure as a Platform (IaaS) layer by automating database mutations and deploying the centralized identity security perimeter:

#### 1. Designing IAM Role Execution Boundaries for Lambda
* Opened the AWS IAM Console to create a secure service execution policy named `pharmacare-lambda-role`.
* Enforced tight security baselines using the least privilege principle by attaching 3 distinct operational permissions policies: CloudWatch emission rights (`AWSLambdaBasicExecutionRole`), Elastic Network Interface (ENI) attachment permissions inside isolated networks (`AWSLambdaVPCAccessExecutionRole`), and dynamic decryption policies targeting database secrets (`pharmacare-read-rds-secret-policy`).

![Configuring IAM Role for Lambda](/ThucTapAWS/images/lam1.png)

#### 2. Initializing the VPC-Bound Lambda Migration Endpoint
* Provisioned the `pharmacare-db-migration` serverless runner configured against a Node.js 22.x runtime environment (x86_64 architecture).
* Explicitly mapped the execution engine into 2 Private Subnets managed under the `pharmacare-vpc` boundary, isolating the container within a tailored Security Group that permits secure relational queries directly into the Amazon RDS PostgreSQL cluster.

![Lambda Migration Initial Provisioning Setup](/ThucTapAWS/images/lam2.png)

#### 3. Optimizing Computational Allocations & Connection Boundaries (Timeout/Memory)
* Processing robust transactional DDL/DML scripts (initializing schemas for users, products, carts, and specialized vector embeddings tailored for the GenAI Chatbot modules) requires uninterrupted network I/O lifecycles.
* Consequently, the deployment profile was scaled up to **256 MB** of allocated memory, while adjusting the default execution boundary up to a robust **60 seconds (1 minute)** limit, completely eliminating premature socket failures and Timeout Exceptions.

![Tuning Lambda Code Source Workspace](/ThucTapAWS/images/lam3.png)

![Tuning Lambda General Settings Allocation](/ThucTapAWS/images/lam4.png)

#### 4. Hardening Infrastructure State Management via Environment Variables
* Separated infrastructure topology configurations from static application code layers by defining key-value application properties: `DB_HOST`, `DB_NAME` (`pharmacare_ai`), `DB_PORT` (`5432`), and `RDS_SECRET_ARN`.
* This dynamic layout instructs the Lambda middleware to perform real-time authenticated lookups targeting Secrets Manager API microservices without storing hardcoded plain-text credentials.

![Configuring Lambda Environment Variables](/ThucTapAWS/images/lam5.png)

#### 5. Code Bundling & Cloud Deployment Continuous Integration
* Working out of the local Visual Studio Code environment, engineered the `index.mjs` orchestrator script alongside active node dependencies (`pg`, `@aws-sdk/client-secrets-manager`). Utilized the native PowerShell command block `Compress-Archive` to pack the working node tree and dependency modules into a `function.zip` bundle.

![Initializing and Archiving Lambda Build in VS Code](/ThucTapAWS/images/lam6.png)

* Performed a direct filesystem upload pushing the compiled `function.zip` archive layer into the live AWS Lambda Console deployment view.

![AWS Lambda Console Package Upload Workspace](/ThucTapAWS/images/lam7.png)

* Audited and verified the underlying structure of the SQL script compilation directly via the live integrated editor layout on the AWS Lambda management console to ensure structural harmony.

![Validating Lambda Source Files Post Initial Upload](/ThucTapAWS/images/lam8.png)

#### 6. Deploking Centralized Identity Security Layers via Amazon Cognito User Pool
* **Provisioning User Pool & App Client Configurations:** Deployed `pharmacare-user-pool` to act as the core secure system catalog, embedding self-service mechanisms governing Email/SMS verification alongside workflow password resets. Generated an active App Client asset to supply the Frontend ReactJS tier with its corresponding Client ID parameters.

![Amazon Cognito User Pool Overview and Parameters Interface](/ThucTapAWS/images/cog1.png)

* **Enforcing Role-Based Access Control (RBAC):** Successfully configured 2 vital systemic authorization frameworks mapping custom business segments:
  * `Admin`: The administrator group designated with elevated credentials targeting product listings, operational logistics, and reporting matrix views (assigned Precedence 1).
  * `Customer`: The standard consumer segment holding specific tokens to orchestrate store purchases and trigger interactive AI Chatbot pipelines (assigned Precedence 2).

![Configuring User Groups Layout Within Amazon Cognito](/ThucTapAWS/images/cog2.png)

---

### Week 11 Achievements:
* **Automated Data Deployment Lifecycle:** Completely replaced risk-prone manual table mutations with an isolated Serverless Lambda routine running inside private VPC spaces, guaranteeing data consistency and zero perimeter exposure.
* **Enterprise Identity Perimeter Alignment:** Successfully finalized the Amazon Cognito authentication baseline under engineer Huỳnh Minh Phú's jurisdiction, providing immediate security token services (JWT) ready for downstream ReactJS Frontend and API Gateway enforcement.
* **Unified Observability Architecture:** Entire execution paths, schema mutations logs, and identity workflows are tracked in real-time via **Amazon CloudWatch Logs**, ensuring complete system visibility and debugging insights for the engineering squad.