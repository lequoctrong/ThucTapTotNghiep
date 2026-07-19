---
title: "Week 12 Worklog"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

* **Deploy Static Frontend Web Architecture via Amazon S3:** Provision a highly available and secure Amazon S3 bucket instance optimized to store, host, and serve static production assets (`index.html`, Javascript bundles, asset structures) for the **PharmaCare AI** client-side dashboard.
* **Accelerate Global Content Delivery Network (CDN) via Amazon CloudFront:** Set up an edge-cached Amazon CloudFront distribution mapping to the S3 static origin, providing HTTPS security enforcement, low-latency client handshakes, and strict edge-level caching strategies.
* **Resolve Client-Side SPA Routing & Custom Cache Management:** Address single-page application (SPA) client-side entry faults by structuring custom `403` and `404` error handling to cleanly fallback to `/index.html`. Handle distribution cache management using targeted system invalidation workflows.
* **Unify Distributed Identity Integrations & Domain Management:** Synchronize production distribution endpoints directly inside the Amazon Cognito User Pool redirect boundaries, while leveraging Amazon Route 53 management portals to orchestrate custom domain resource planning.

---

### Tasks to be carried out this week:

| Day | Task | Assigned To | Start Date | Completion Date |
| :--- | :--- | :--- | :--- | :--- |
| Mon | **S3 Static Bucket Architecture Initialization:** <br> - Provision the unique static host target `pharmacare-frontend-web-phu-2026` inside the `ap-southeast-1` region. | Huỳnh Minh Phú | 20/07/2026 | 20/07/2026 |
| Tue | **Frontend Production Compiling & Object Deployment:** <br> - Build React production static files locally and synchronize raw bundles (`assets/`, `index.html`, `favicon.svg`) directly into the target S3 asset directory. | Huỳnh Minh Phú | 21/07/2026 | 21/07/2026 |
| Wed | **CDN CloudFront Distribution Setup:** <br> - Deploy `pharmacare-frontend-distribution` utilizing the global edge cluster framework. <br> - Assign default root configurations mapping safely to `/index.html`. | You | 22/07/2026 | 22/07/2026 |
| Thu | **SPA Client Error Responses & Cache Invalidations:** <br> - Configure CloudFront custom error pages mapping `403`/`404` anomalies back to HTTP `200` under `/index.html`. <br> - Fire asset cache invalidation operations targeting `/*`. | You | 23/07/2026 | 23/07/2026 |
| Fri | **Cognito Identity Integration & Route 53 Domain Planning:** <br> - Bind the active CloudFront CDN production domain into the allowed Callback and Sign-out parameters inside Cognito. <br> - Map availability checks for the `pharmacare.ai` domain zone. | You | 24/07/2026 | 24/07/2026 |

---

### Detailed Implementation:

During this implementation cycle, the engineering core structured the public delivery layer of the ecosystem, taking the web architecture from a localized development environment into an enterprise-grade cloud production delivery path:

#### 1. Provisioning the Cloud Storage Sandbox via Amazon S3
* Initiated setup procedures via the Amazon S3 Storage console interface to deploy an decoupled asset container named `pharmacare-frontend-web-phu-2026`.
* Mapped the storage cluster into the local APAC node structure (`ap-southeast-1` Singapore Region) running a standard Global Namespace general-purpose storage tier to maintain strict asset synchronization.

![Configuring S3 Bucket Parameters](/ThucTapTotNghiep/images/deploy1.jpg)

![Verifying Empty S3 Bucket Instance Allocation](/ThucTapTotNghiep/images/deploy2.jpg)

#### 2. Compiling and Synchronizing Static Application Artifacts
* Ran local deployment scripts on the project tree to render optimized production chunks.
* Synchronized and pushed the structural layers (including the system `assets/` directories, `index.html`, `favicon.svg`, and custom vector representations `icons.svg`) straight into the S3 asset storage engine with full timestamp synchronization.

![Reviewing Uploaded Static Objects in S3 Bucket](/ThucTapTotNghiep/images/deploy3.jpg)

#### 3. Provisioning the Global Amazon CloudFront Distribution Network
* Deployed a production CDN cluster layer under the deployment naming scheme `pharmacare-frontend-distribution`.
* The newly established edge engine successfully configured its dynamic URL profile (`d3tm5364zrtmpq.cloudfront.net`), ensuring optimized global caching parameters and setting up the Default Root Object to intercept requests straight at `index.html`.

![Reviewing Active CloudFront General Settings Dashboard](/ThucTapTotNghiep/images/deploy4.jpg)

#### 4. Hardening Client-Side SPA Routes & Performing Cache Invalidation
* Since React utilizes a Virtual DOM routing model (client-side routing), direct deep-linking attempts frequently lead to standard AWS object lookup failures.
* Resolved this design quirk by constructing distinct Error Pages custom interception strategies: mapping code `403` and `404` anomalies to redirect straight into `/index.html` with an overridden HTTP response structure of `200 OK`.

![Configuring Custom Error Pages Responses for SPA Compatibility](/ThucTapTotNghiep/images/deploy5.jpg)

* Triggered an infrastructure cache wipe request (`Invalidation ID: I22BWFD9RT2N26X729DOHWEPR9`) pointing explicitly at path pattern `/*`. This forces CloudFront to drop old cache layers across all global edge nodes and fetch the freshly deployed code from the S3 origin.

![Executing Asset Cache Invalidation Tracking](/ThucTapTotNghiep/images/deploy6.png)

#### 5. Binding Identity Callback Zones & Auditing Domain Availability
* Opened the Amazon Cognito Identity Management workspace to extend configurations for the `pharmacare-web-client` App Client.
* Bound the verified production URL path configurations (`https://d3tm5364zrtmpq.cloudfront.net/`) directly alongside the development paths (`http://localhost:5173/`) under the **Allowed callback URLs** and **Allowed sign-out URLs** parameters, empowering the cloud UI layer to execute OAuth2 authorization routines securely.

![Updating Amazon Cognito App Client Redirect Target Boundaries](/ThucTapTotNghiep/images/deploy7.png)

* Navigated to Amazon Route 53 Domain Registry portals to plan domain mapping targets for the target corporate site profile (`pharmacare.ai`). The system detected an active registration lock on the primary domain and recommended fallback records to structure production DNS maps next week.

![Auditing Domain Zone Registry Configurations inside Route 53](/ThucTapTotNghiep/images/deploy8.jpg)

---

### Week 12 Achievements:
* **Zero-Server Static Production Delivery:** Successfully migrated from localized local runners into a scalable serverless CDN structure combining Amazon S3 hosting parameters with Amazon CloudFront distribution edges.
* **Unified OAuth2 Identity Routing:** Allowed callback interfaces inside the Amazon Cognito directory have been safely updated by the engineering team to accept security handshakes coming from the public CloudFront URL.
* **Perfected Single-Page Application Behaviors:** Achieved native browser routing flexibility across all React dynamic pages via CloudFront error redirection overrides, while ensuring real-time code deployments via targeted invalidations.