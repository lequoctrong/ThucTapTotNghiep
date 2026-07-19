---
title: "Week 11 Worklog"
date: 2026-07-17
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* **Automate Database Migration with AWS Lambda:** Deploy a Serverless architecture (AWS Lambda) running fully within an isolated private network (Private VPC) to execute DDL/DML scripts and initialize the PostgreSQL table schemas for the **PharmaCare AI** system without manual external intervention.
* **Integrate Secrets Management & Secure the Execution Pipeline:** Enforce the principle of least privilege using an IAM Role, allowing the Lambda function to dynamically decrypt and retrieve Master DB credentials from AWS Secrets Manager, completely eliminating hardcoded sensitive data within the application codebase.
* **Build a Centralized Identity Management System:** Deploy an **Amazon Cognito User Pool** as the primary identity governance service, managing user sign-up, sign-in, account verification workflows, and JSON Web Token (JWT) issuance.
* **Establish Role-Based Access Control (RBAC):** Configure distinct permission groups (`Admin` and `Customer`) within Cognito, laying the security groundwork for API Gateway access control and functional authorization rules across core modules.

---

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date |
| :--- | :--- | :--- | :--- |
| Mon | **Configure IAM Role & Lambda Execution Permissions:** <br> - Provision the `pharmacare-lambda-role` IAM role. <br> - Attach core policies: `AWSLambdaBasicExecutionRole`, `AWSLambdaVPCAccessExecutionRole`, and a custom inline policy `pharmacare-read-rds-secret-policy`. | 13/07/2026 | 13/07/2026 |
| Tue | **Initialize & Configure the Migration Lambda Function:** <br> - Provision the `pharmacare-db-migration` function (Node.js 22.x, x86_64) bound to two Private Subnets inside the `pharmacare-vpc`. <br> - Optimize runtime properties: Memory `256 MB`, Timeout `60 seconds` to prevent connection drops. | 14/07/2026 | 14/07/2026 |
| Wed | **Bundle Source Code & Execute Migration on RDS:** <br> - Author the `index.mjs` runtime logic integrating `pg` and `@aws-sdk/client-secrets-manager` libraries. <br> - Package dependencies into `function.zip`, upload to Lambda, and trigger automated schema migration on Amazon RDS PostgreSQL. | 15/07/2026 | 15/07/2026 |
| Thu | **Deploy Amazon Cognito User Pool & App Client:** <br> - Provision `pharmacare-user-pool` to govern user account lifecycles. <br> - Configure the App Client (Client ID) required for React frontend integration. | 16/07/2026 | 16/07/2026 |
| Fri | **Configure User Groups & Validate Token Signatures:** <br> - Establish administrative and consumer boundaries via `Admin` and `Customer` groups within Cognito. <br> - Test SignUp/SignIn authentication loops, verify JWT token signatures, and trace runtime outputs on Amazon CloudWatch Logs. | 17/07/2026 | 17/07/2026 |

---

### Detailed Implementation:

During this sprint cycle, the architecture advanced to an enterprise-grade Infrastructure as a Platform level by automating core data operations and integrating a secure centralized identity management tier:

#### 1. Setting Up IAM Role Execution Permissions for Lambda
* Opened the IAM Management Console to provision a new execution role named `pharmacare-lambda-role`.
* Enforced the principle of least privilege by attaching three key baseline policies: CloudWatch telemetry access (`AWSLambdaBasicExecutionRole`), ENI network interface attachment within a VPC (`AWSLambdaVPCAccessExecutionRole`), and dynamic runtime reading permissions for target secrets within AWS Secrets Manager (`pharmacare-read-rds-secret-policy`).

![Configuring IAM Role for Lambda](/ThucTapTotNghiep/images/lam1.png)

#### 2. Provisioning the Migration Lambda Function inside the VPC
* Created the `pharmacare-db-migration` backend function running an optimized Node.js 22.x engine (x86_64 architecture).
* Bound the function paths directly into two isolated Private Subnets of the `pharmacare-vpc` network and assigned a custom Lambda Security Group, allowing secure, firewalled data traffic to the target Amazon RDS PostgreSQL instance.

![Configuring Lambda Migration Function Settings](/ThucTapTotNghiep/images/lam2.png)

#### 3. Optimizing Runtime Resources & Timeouts
* Executing complex raw relational database migrations (including data definitions for accounts, products, baskets, and vector embedding extensions for the AI chatbot service) demands sustained network I/O operations.
* Therefore, the baseline compute profiles were expanded to **256 MB** of execution memory, and the default execution lifespan was extended from 3 seconds to **60 seconds (1 minute)**, fully neutralizing potential connection drop risks (`TimeoutException`).

![Reviewing Initial Lambda Code Source Sandbox](/ThucTapTotNghiep/images/lam3.png)

![Modifying Timeout and Memory Allocations for Lambda](/ThucTapTotNghiep/images/lam4.png)

#### 4. Decoupling Architectural Settings via Environment Variables
* Decoupled server targets from the runtime codebase by establishing static environment key-value configurations: `DB_HOST`, `DB_NAME` (`pharmacare_ai`), `DB_PORT` (`5432`), and `RDS_SECRET_ARN`.
* This setup empowers the serverless runtime to make dynamic API calls to AWS Secrets Manager to pull, parse, and decrypt the master database passwords on the fly.

![Injecting Environment Variables into Lambda](/ThucTapTotNghiep/images/lam5.png)

#### 5. Bundling Code Assets & Launching to Cloud Environments
* Within the local VS Code workspace, constructed the deployment engine `index.mjs` and installed standard driver dependencies (`pg`, `@aws-sdk/client-secrets-manager`). Utilized the PowerShell utility `Compress-Archive` to pack the source code assets alongside the `node_modules` directory into a deployable package named `function.zip`.

![Bundling and Compressing Code Assets inside VS Code](/ThucTapTotNghiep/images/lam6.png)

* Uploaded the resulting `function.zip` archive directly to the Code tab within the AWS Lambda Management Console.

![Uploading the ZIP Package via the Lambda Code Console](/ThucTapTotNghiep/images/lam7.png)

* Reviewed the deployment code layouts and verified the SQL Migration query structures directly in the integrated console editor to ensure structural alignment.

![Validating Lambda Source Files Post Update](/ThucTapTotNghiep/images/lam8.png)

#### 6. Deploying the Centralized Authentication Pipeline via Amazon Cognito User Pool
* **Provisioning User Pool & App Client:** Deployed `pharmacare-user-pool` as the single source of truth for user data, out-of-the-box supporting Email/SMS multi-factor verifications and automated recovery loops. Created the app interface target `pharmacare-web-client`, rendering the explicit Client ID string required for ReactJS application integration.

![Reviewing Amazon Cognito User Pool Status and Details Dashboard](/ThucTapTotNghiep/images/cog1.png)

* **Enforcing Role-Based Access Control (RBAC):** Successfully instantiated two operational groups: the administrative boundary `Admin` mapping to Precedence 1, and the general customer tier `Customer` mapping to Precedence 2, preparing the system for secure token evaluation downstream at the API Gateway level.

![Configuring User Group Precedence inside Amazon Cognito](/ThucTapTotNghiep/images/cog2.png)

---

### Week 11 Achievements:
* **Automated Data Deployment Ingestion:** Replaced error-prone, manual shell-driven table creation steps with an isolated Serverless Lambda function processing schemas internally inside the private VPC, achieving absolute database protection.
* **Production-Grade Identity Management Setup:** Successfully established the centralized Amazon Cognito authorization engine, preparing the ecosystem to deliver secure, signed JSON Web Tokens (JWT) for both the ReactJS UI layout and API Gateway filtering layers.
* **End-to-End System Observability:** All execution records, runtime schema generation processes, and client validation tasks emit structured traces in real time to **Amazon CloudWatch Logs**, keeping the operational baseline fully transparent.