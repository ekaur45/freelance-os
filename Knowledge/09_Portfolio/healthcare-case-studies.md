# Healthcare Case Studies

## Healthcare SaaS
Focus areas:
- Patient management
- Clinical workflows
- HL7/FHIR integrations
- Secure healthcare platforms

## Telemedicine
Focus areas:
- Video consultation
- Scheduling
- Provider dashboards
- Remote care workflows

## Proposal Matching
Use for healthcare, healthtech, FHIR, EMR, EHR and telehealth opportunities.

---

## Case Study: Repose Healthcare — Order Automation & HL7 Lab Integration

### Overview
Repose Healthcare sells home testing kits through a WooCommerce storefront: a customer orders a test, a kit ships to them, they collect and return a sample, a lab processes it, and the result is routed back through the website to the customer — with status notifications (dispatch, kit received, result ready) at each step along the way.

### Client Problem
The storefront itself — the test catalog and checkout — already worked well. Everything downstream of checkout didn't: order handling, coordinating with the lab, and keeping the customer informed were all manual. Staff were re-keying order details for the lab and chasing status updates by hand, which slowed order turnaround and capped how much volume the business could take on.

### Solution
Designed and built the HL7 integration layer that lets lab results flow straight into the platform, and took ownership of the WooCommerce plugin that ties the whole pipeline together — order validation, lab transmission, result intake, and patient notification — turning a manual, staff-driven process into a largely automated one.

Concretely, the plugin now:
- Validates required patient and test fields at checkout, then either auto-transmits the order to the lab or routes it to a manual authorisation queue when a case needs a human look (anomalies, duplicate samples, or auto-transmit turned off)
- Generates a structured order payload for the lab and delivers it by whichever method the lab supports — email attachment or direct upload to cloud storage
- Accepts lab results back in two ways: a token-authenticated REST endpoint for labs that can integrate directly, and a secure browser-based upload portal for labs that can't
- Parses incoming HL7 result data (patients, visits, orders, reports, observations, notes) into structured records, auto-generates a branded PDF report, and queues it for review
- Runs results through a review workflow — pending review → approved → released — before the patient can see them, with approved PDFs stamped with the client's branding
- Notifies the patient by email with a secure link the moment their result is released, and logs every meaningful action (transmission, upload, approval, rejection, download) to an audit trail

### Architecture
- WordPress/WooCommerce storefront as the order entry point and patient-facing portal (results surface under "My Test Results" in the customer's account)
- Plugin-layer automation coordinating order state, lab transmission, and notification triggers, backed by dedicated database tables for queues, results, audit history, and the parsed HL7 segments
- A companion HL7 API service (NestJS/TypeScript) handling inbound lab result parsing
- Dual transmission paths so the integration works whether a given lab wants API access or a manual upload flow — a practical fit for the reality that not every diagnostic lab has integration infrastructure

### Technology Stack
- PHP, WordPress, WooCommerce (plugin)
- NestJS, TypeScript (HL7 parser service)
- HL7 messaging standard (ORU result segments — PID, PV1, ORC, OBR, OBX, NTE)
- Cloud blob storage for lab file transmission

### Implementation Highlights
- Built and deployed the HL7 result parser independently
- Took over and delivered substantial ongoing development on the WooCommerce plugin after the initial build was outsourced elsewhere — meaning working inside an existing codebase and conventions rather than starting clean
- Automated the full order → lab → result → notification pipeline that was previously handled by hand
- Built for labs with varying technical capability: a REST/token integration for labs that can call an API, and a portal upload option for labs that can't

### Business Impact
Order and result processing went from manual to largely automated, and the client saw increased sales following the automation work — faster turnaround and less staff overhead made it possible to handle more orders without a proportional increase in manual effort.

### Lessons Learned
Lock integration scope with the lab before building, not during. Message formats and field naming conventions need to be agreed early with each lab partner — mismatches discovered mid-integration caused rework that upfront alignment would have avoided.

### Proposal Usage
- Keywords: HL7 integration, HL7 ORU parsing, WooCommerce automation, healthcare order processing, lab integration, WordPress plugin development, home testing kits, diagnostic result delivery
- Related services: Healthcare Software Development, API Integration, Backend Development
- Related industries: Healthcare, Diagnostics/Lab Services, E-commerce

---

## Case Study: AchieveMSO — HIPAA-Compliant Medical Records Request Platform

### Overview
AchieveMSO is a HIPAA-compliant platform for managing healthcare data requests — the process of requesting, authorizing, and securely delivering medical records between the parties who need them. It's built as a management service organization (MSO) model: a single platform that serves multiple contracted healthcare provider clients, with distinct portals for each stakeholder type — patients, healthcare providers, representatives acting on a patient's behalf, and data requesters (e.g. researchers, health plans) submitting bulk requests.

Live at [achievemso.com](https://achievemso.com).

### Client Problem
Before this platform, getting a patient's medical records together for something like a court case, a school requirement, or any other formal request meant manually contacting every EMR/EHR provider that held a piece of that patient's history and requesting records from each one individually — a slow, fragmented process repeated from scratch for every request. Medical records requests also sit at the intersection of four different parties (patient, provider, representative, requester) who each need a different view of the same request, under strict HIPAA rules on who can authorize release of what data to whom. The client needed a single platform built from scratch that could centralize that whole lifecycle — request submission, provider verification, patient authorization, secure delivery — across multiple contracted healthcare organizations at once, without compromising on compliance.

### Solution
Built the entire platform from the ground up: requirements gathered directly with the client, then designed and delivered the frontend, backend, database, and deployment. The result is a four-step request flow — submission, provider review and record preparation, patient authorization, and secure delivery with a full audit trail — wrapped in role-specific portals:

- **Patients** — view request status, review and sign authorizations, download their own records
- **Healthcare providers** — review and process incoming data requests, manage their team, work through the platform as an extension of their own records-request workflow
- **Representatives** — request and manage records on a patient's behalf under proper legal authorization
- **Data requesters** — submit and track requests (including bulk requests) with an analytics dashboard

Underlying all four portals: HIPAA authorization workflows, identity verification, MFA/OTP verification for sensitive actions, and a separate representative-verification flow so records only ever release to someone with proper authority to receive them. Billing runs through Stripe.

### Architecture
- Laravel application with role-scoped controllers per stakeholder type (patient, provider, representative, requester) plus a "contracted client" layer reflecting the MSO model — the platform manages records requests on behalf of multiple contracted healthcare organizations, not just one
- Dedicated verification pipeline: identity verification, MFA/OTP, HIPAA authorization, and representative verification as distinct steps rather than a single generic "auth" flow — necessary given how differently HIPAA treats a patient acting for themselves versus a representative acting for them
- Stripe integration for billing/payments alongside the compliance workflow
- Notification and email-verification systems to keep every party informed as a request moves through review, authorization, and delivery

### Technology Stack
- Laravel (PHP), MySQL/relational database
- Stripe (payments, PCI DSS-compliant processing)
- Role-based access control with MFA/OTP verification

### Implementation Highlights
- Full-cycle delivery: client requirements gathering, frontend, backend, database design, and deployment — no team handoff, single point of ownership end to end
- Four distinct user roles (patient, provider, representative, requester) built on one shared platform rather than four separate apps, with permissions and data visibility scoped per role
- Compliance treated as a first-class part of the architecture rather than bolted on: HIPAA authorization, identity verification, and audit trails built into the request lifecycle itself, with every access, modification, and transfer logged for compliance review
- AES-256 encryption for data at rest and in transit, per the platform's published security posture

### Business Impact
Per AchieveMSO's own published figures, the platform now serves 500+ healthcare providers and has processed 10,000+ data requests, with a typical request turnaround of 7–10 business days, 99.9% uptime, and SOC 2 Type II certification — built on the foundation delivered in this engagement.

### Lessons Learned
Building a multi-role compliance platform from scratch means the identity and authorization model has to be right before anything else is built on top of it — patient, provider, and representative each need a genuinely different verification path (not a shared login with role flags), since HIPAA's rules on who can authorize release of what data don't map cleanly onto a single generic permissions system.

### Proposal Usage
- Keywords: HIPAA compliance, medical records request platform, healthcare data management, MSO software, identity verification, MFA, Stripe billing integration, role-based access control, patient portal, provider portal
- Related services: Healthcare Software Development, Full Stack Development, Backend Development, Database Design
- Related industries: Healthcare, Health IT, Medical Records/Compliance, MSO (Management Service Organizations)

---

## Case Study: SMART on FHIR Provider-Launch Integration (client confidential)

### Overview
Built a SMART on FHIR integration for a client's booking platform (internal codename "dbooker"), letting the platform launch directly from within a provider's EHR system — either embedded inside the EHR or as a standalone launch — and pull that patient's data in on demand rather than requiring it to be entered manually.

### Client Problem
The client was an experienced developer building the platform himself, but SMART on FHIR / EHR integration was outside his own expertise — the OAuth2 launch handshake, FHIR resource scopes, and the provider/patient/encounter context model that SMART on FHIR launches carry are a fairly specialized corner of healthcare software. He brought in FHIR-specific expertise to build that one piece rather than build it himself.

### Solution
Delivered a complete SMART on FHIR provider-launch integration supporting both launch modes an EHR might use:
- **Standalone launch** — the platform initiates the OAuth2 flow directly against the FHIR server
- **Embedded launch** — the platform launches from inside the EHR's own UI, picking up the `iss` and `launch` context parameters the EHR provides

Once launched, the integration completes the full OAuth 2.0 authorization flow, captures the provider's identity and maps them to the correct tenant (multi-tenant aware), and captures patient and encounter context when available. An "Import Current Patient" action then pulls in patient demographics, encounter details, and care plan data from the FHIR server, with deduplication logic to avoid re-importing data already on file.

Security was treated as core to the design rather than an add-on: no PHI or access/refresh tokens are ever written to logs, tokens are encrypted at rest, and every import is recorded in an audit trail (who imported, when, and from which FHIR server) without the underlying PHI itself touching the log.

### Architecture
- Express.js / TypeScript service with a MySQL database for imported data and audit logs
- OAuth 2.0 / SMART on FHIR launch handling for both standalone and embedded modes
- JWT-based session/token handling, with FHIR access and refresh tokens stored encrypted and excluded from all logging
- Multi-tenant provider mapping so the same integration serves multiple provider organizations with proper isolation

### Technology Stack
- Node.js, Express.js, TypeScript
- MySQL
- OAuth 2.0, SMART on FHIR, JWT
- FHIR resource scopes: Patient, Observation, CarePlan, Encounter

### Implementation Highlights
- Supported both SMART on FHIR launch modes (standalone and embedded) rather than just one, covering how different EHR systems trigger a launch
- Built a working sandbox demo environment against common FHIR sandbox providers, so the client could validate the integration without a live EHR connection
- Designed logging and audit trails to be compliance-safe by construction — audit entries capture provider ID, timestamp, and source FHIR server, deliberately excluding PHI and tokens
- Delivered as a clean code handover: the client's own team owned deployment and integration into the rest of the platform, so this engagement was scoped purely to building and handing off the FHIR integration itself

### Business Impact
Delivered as a code handover with no deployment or production involvement, so downstream business metrics from this engagement aren't available.

### Lessons Learned
None captured for this engagement.

### Proposal Usage
- Keywords: SMART on FHIR, FHIR integration, EHR integration, OAuth 2.0, provider launch, embedded launch, standalone launch, patient data import, healthcare interoperability
- Related services: Healthcare Software Development, API Integration, Backend Development
- Related industries: Healthcare, Health IT, EHR/EMR Systems

---

## Case Study: Demo Epic EMR Integrations (two clients, confidential)

### Overview
Built a demo Epic EMR integration twice, for two separate clients (one sourced via Upwork, one via Fiverr) who came in independently with the same request: a working demonstration of pulling data out of Epic's EHR system through its API.

### Client Problem
Both clients needed a working proof-of-concept Epic EMR integration rather than a production system — someone who could show, concretely, that a connection to Epic's API could be built and used to retrieve real data (patient and appointment information) from the EHR.

### Solution
Delivered a Node.js/Express REST API that authenticates against Epic's EHR API and exposes an endpoint to pull patient appointment data, with a modular, database-backed structure so the demo could plausibly extend into a real integration rather than being a throwaway script.

### Architecture
- Node.js, Express.js REST API
- TypeORM data layer supporting either MySQL or MongoDB
- Modular controller/route/service/model structure for maintainability beyond a one-off demo
- Centralized error-handling middleware and structured logging

### Technology Stack
- Node.js, Express.js, TypeScript/JavaScript
- TypeORM (MySQL / MongoDB)
- Epic EHR API (OAuth-based EMR integration)

### Implementation Highlights
- `POST /api/epic/get-patient-appointments` — the core demo endpoint proving the Epic connection and data retrieval worked end to end
- Built with production-style structure (separated controllers, services, models, middleware) rather than a quick script, so the client had something extensible, not just a proof it was possible
- Delivered the same category of demo independently for two different clients, each sourced through a different freelance platform

### Business Impact
Both engagements were code handovers with no deployment or ongoing involvement, so downstream business outcomes aren't available.

### Lessons Learned
None captured for this engagement.

### Proposal Usage
- Keywords: Epic EMR integration, Epic EHR API, healthcare API demo, proof of concept, patient appointment data, EMR integration demo
- Related services: Healthcare Software Development, API Integration, Backend Development
- Related industries: Healthcare, Health IT, EHR/EMR Systems

---

## Case Study: Multi-EMR Integration for a SOAP Notes Application (client confidential)

### Overview
Built OAuth-based integrations with multiple EMR systems — Athena Health, AdvancedMD, and Practice Fusion — for a client whose product is a SOAP notes application, delivered directly to the client's own developer for them to integrate into their app, alongside a consultation walkthrough of the code.

### Client Problem
The client's SOAP notes application needed to connect to multiple external EMR systems to pull patient and encounter data rather than have clinicians re-enter it. The original scope was four EMR vendors, but the client could only obtain developer/sandbox accounts for three (Athena Health, AdvancedMD, Practice Fusion) in time, so the fourth was dropped from scope.

### Solution
Built OAuth authentication flows per EMR vendor (each system has its own auth endpoints and quirks) on top of a shared, generic data-access layer for the operations the SOAP notes app actually needed — looking up a patient by ID and pulling their encounter history — so adding a vendor meant plugging in its auth flow rather than rebuilding data access each time.

Delivery went beyond a code drop: it included a consultation session with the client's developer walking through what the code did and how it worked, so their team could take over integration into the SOAP notes app with a clear understanding of the implementation, not just the source.

### Architecture
- Node.js / Express REST API
- Per-vendor OAuth controllers and routes for Athena Health, AdvancedMD, and Practice Fusion, each with its own `/auth` and `/callback` endpoints
- A shared generic EMR controller/service exposing vendor-agnostic patient and encounter lookups (`patient-by-id`, `encounters`) on top of the vendor-specific auth layer

### Technology Stack
- Node.js, Express.js
- OAuth 2.0 (per-EMR-vendor authentication)
- Athena Health, AdvancedMD, and Practice Fusion EMR APIs

### Implementation Highlights
- Three separate EMR vendor integrations built to a shared interface, rather than three disconnected one-off scripts
- Scope adjusted mid-engagement from four EMR systems down to three when developer account access for the fourth wasn't available in time
- Delivery included a live code walkthrough/consultation with the client's developer, not just a repository handover

### Business Impact
Delivered to the client's developer for integration into their SOAP notes application; no visibility into downstream business outcomes after handover.

### Lessons Learned
Always confirm upfront that the client can actually fulfill what a project requires (in this case, developer/sandbox account access for every EMR vendor in scope) before committing to that scope — this engagement had to drop one of four planned EMR integrations when that access didn't come through in time.

### Proposal Usage
- Keywords: Athena Health integration, AdvancedMD integration, Practice Fusion integration, multi-EMR integration, OAuth EMR authentication, SOAP notes application, healthcare interoperability
- Related services: Healthcare Software Development, API Integration, Backend Development
- Related industries: Healthcare, Health IT, EHR/EMR Systems, Clinical Documentation

---

## Case Study: Serverless HL7 Lab Result Pipeline (client confidential)

### Overview
Built and deployed a serverless HL7 parsing pipeline for a client's first-ever lab integration: incoming HL7 files landing in AWS S3 trigger a Lambda function, which passes the file to the parser, which delivers the structured result into the client's web application.

### Client Problem
This was the client's first integration with a lab — they had no existing pipeline for receiving and processing HL7 result files, and needed one built from the ground up, including the infrastructure to receive files reliably and get parsed data into their application.

### Solution
Built the parser first in Express.js, then converted it to NestJS. Delivered as a close collaboration with the client's own developer to integrate it into their application, and — unlike the EMR demo engagements above — this one included handling the actual deployment, not just a code handover.

### Architecture
- AWS S3 as the file landing point for incoming HL7 files from the lab
- AWS Lambda (Serverless Application Model / SAM) triggered on file arrival, invoking the parser
- HL7 parsing service (Express.js initially, later rebuilt in NestJS)
- Parsed output delivered into the client's web application

### Technology Stack
- Node.js — Express.js (first version), NestJS (rebuilt version)
- AWS Lambda, AWS S3, AWS SAM
- HL7 messaging standard

### Implementation Highlights
- Event-driven pipeline: no polling or manual file handling — an S3 upload directly triggers parsing via a Lambda function
- Migrated the parser from an initial Express.js implementation to NestJS as the project matured
- Worked directly with the client's developer on integration, and handled deployment personally rather than handing off a repository only

### Business Impact
Not captured for this engagement.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: HL7 parsing, serverless healthcare integration, AWS Lambda, AWS S3, lab result pipeline, event-driven architecture, HL7 to web application integration
- Related services: Healthcare Software Development, API Integration, Cloud Deployment, Backend Development
- Related industries: Healthcare, Diagnostics/Lab Services
