---
title: "Week 10 Worklog"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* **Build Backend Architecture:** Initialize the backend project using a multi-tiered pattern (Controller, Service, Repository) and establish connectivity with PostgreSQL.
* **Develop RESTful APIs:** Build core APIs for User, Product, and Medicine Category management to serve the Frontend application.
* **Integrate User Authentication:** Implement registration, login, and authorization mechanisms leveraging JWT Authentication.
* **Test APIs and Standardize Documentation:** Test all endpoints using Postman and generate clean Swagger/OpenAPI documentation.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date |
| :--- | :--- | :--- | :--- |
| Mon | **Backend Project Initialization:** <br> - Initialize the Spring Boot/Node.js project. <br> - Configure PostgreSQL connection strings and establish the Controller - Service - Repository architecture. | 22/06/2026 | 22/06/2026 |
| Tue | **User Management API Development:** <br> - Develop Registration and Login endpoints. <br> - Implement JWT Authentication workflows and secure Password Hashing. | 23/06/2026 | 23/06/2026 |
| Wed | **Product Management API Development:** <br> - Build comprehensive CRUD operations for products, categories, and inventory. <br> - Bind data models with the PostgreSQL persistence layer. | 24/06/2026 | 24/06/2026 |
| Thu | **Cart & Order API Engineering:** <br> - Build functional endpoints to manage cart items. <br> - Implement order creation pipelines and order payment status telemetry updates. | 25/06/2026 | 25/06/2026 |
| Fri | **API Testing & Swagger Finalization:** <br> - Execute automated endpoint validation using Postman. <br> - Generate declarative Swagger/OpenAPI documentation and optimize global exception handling filters. | 26/06/2026 | 26/06/2026 |

---

### Detailed Implementation:

During this sprint, the engineering team focused on building the Backend layer of the Pharmacare AI ecosystem, which serves as the core intermediary orchestration layer linking the front-facing client interfaces with the PostgreSQL relational database.

#### System Architecture Overview
Below is the comprehensive AWS cloud infrastructure layout deployed to handle secure API routing, compute execution layers, generative AI orchestration, and relational/vector storage synchronization:

![Pharmacare AI System Architecture Diagram](/ThucTapAWS/images/kientruc.jpg)

#### 1. Backend Project Initialization

* Initialized the backend codebase using a clean decoupled design pattern separating Controller, Service, Repository, and Entity components.
* Configured the PostgreSQL database connection pool utilizing standard Object-Relational Mapping (ORM) tools (Spring Data JPA / Prisma / Sequelize).
* Established centralized environment variables configuration management rules and structured application logging handlers.

#### 2. User API Development

* Engineered standalone endpoints governing account registration, authentication challenges, and user profile delivery.
* Enforced security regulations by encrypting passwords via BCrypt algorithms prior to persistence layer synchronization.
* Deployed stateless JWT Authentication filters to manage cross-origin request validations and role-based access controls.

#### 3. Product Management API Engineering

* Developed modular endpoints handling product mutations including create, read, update, delete, and advanced criteria filtering.
* Structured data schemas handling specialized medicine categorizations alongside inventory stock balance calculations.
* Implemented payload data validation constraints and designed global business exception handlers.

#### 4. Cart and Order API Integration

* Engineered endpoints governing real-time cart mutations, supporting safe additions, mutations, and item drops.
* Coded transaction pipelines transforming pending user cart entities into finalized billing orders.
* Synchronized downstream order fulfillment updates seamlessly within the relational database schemas.

#### 5. Verification and Interactive API Specification

* Conducted rigorous end-to-end integration testing across all endpoint endpoints leveraging Postman suites.
* Assessed edge-case exceptions, minimizing unexpected runtime payloads while refining informative validation error response streams.
* Generated live interactive Swagger/OpenAPI specifications, enabling decoupled frontend engineering integrations in upcoming operational sprints.

---

### Week 10 Achievements:

* Successfully established the multi-tiered Backend engineering architecture.
* Built and validated resilient RESTful APIs supporting core User, Product, and Order management services.
* Deployed stateless JWT security layers to minimize perimeter exposure and enforce robust resource authentication.
* Finalized compliant Swagger schemas and cleared integration benchmarks via Postman validation, securing readiness for Frontend component integration in upcoming workflows.