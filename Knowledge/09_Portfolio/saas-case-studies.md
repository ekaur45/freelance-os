# SaaS Case Studies

## Multi-Tenant SaaS
Focus areas:
- Tenant isolation
- Role-based access
- Subscription billing
- Scalable architecture

## Business Applications
Examples:
- CRM
- ERP
- Workflow automation
- Admin platforms

Use for SaaS product development proposals.

---

## Case Study: RoleGenius — AI-Powered Career Mentoring Platform

### Overview
RoleGenius ([rolegenius.com](https://rolegenius.com)) is an AI-powered career mentoring and development platform aimed at immigrants identifying transferable skills, recent graduates entering the workforce, and job seekers navigating a career transition. It combines human mentoring with AI-driven career tools — offering free discovery sessions, career assessment and goal-setting, resume and cover letter development, LinkedIn profile optimization, mock-interview preparation, job search strategy, and skill-gap identification tied to learning resources.

### Client Problem
The client needed the platform built entirely from scratch — there was no existing system, just the idea of pairing AI-driven career tools with human mentoring to help people navigate career uncertainty and job transitions. The engagement came through an informal referral (a friend, over WhatsApp), not a marketplace listing.

### Solution
Built the platform end-to-end as the sole full-stack developer, across backend, frontend, and landing page. On the AI side, the backend integrates OpenAI to generate a "Career Pulse" assessment, job descriptions, job roles, and role-specific skill breakdowns from user input — directly powering the platform's skill-gap identification and career-guidance features. Generated job descriptions can be exported as branded PDFs and delivered by email.

Beyond the AI layer, the platform includes a learning-management module (tying skill gaps to learning resources), a video module (supporting the mock-interview/mentoring-session side of the product), payments (for mentoring sessions/subscriptions), and account/user management — the full set of pieces a mentoring-plus-AI-tools product needs, not just a chatbot bolted onto a form.

The frontend went through more than one iteration as the product evolved — an initial Angular build, then a rebuilt frontend and landing page as the platform matured.

### Architecture
- Node.js / Express / TypeScript backend with dedicated modules for OpenAI integration, learning management, video, payments, accounts, and users
- Angular frontend, rebuilt over the course of the engagement as the product's needs evolved
- OpenAI API for career-pulse generation, job description generation, job role generation, and role-skill generation
- PDF generation and email delivery for AI-generated job description output

### Technology Stack
- Node.js, Express.js, TypeScript
- Angular
- OpenAI API
- PDF generation, email delivery

### Implementation Highlights
- Built the full stack solo: backend API, AI integration, frontend application, and landing page
- Structured the OpenAI integration around specific career-focused generation tasks (career pulse, job descriptions, job roles, role skills) rather than a generic chat interface, keeping the AI output directly tied to the product's mentoring and skill-gap use case
- Delivered AI-generated job description output as branded, emailable PDFs, not just on-screen text
- Rebuilt the frontend as the product matured, rather than treating the first version as final

### Business Impact
No metrics available — this was an informal referral engagement outside the usual marketplace/tracked channels, so usage or outcome numbers weren't captured.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: AI career platform, OpenAI integration, career mentoring SaaS, AI-generated job descriptions, skill gap analysis, learning management, full stack AI product development
- Related services: AI Development, Full Stack Development, Backend Development, Frontend Development
- Related industries: HR Tech, EdTech, Career Services, SaaS

---

## Case Study: Taleemiyat — Self-Built Online Tutoring Platform (personal product)

### Overview
Taleemiyat (taleemiyat.com; "hamari-product" was the internal working/repo name — Urdu for "our product") is a self-initiated, self-funded online tutoring platform in the spirit of Preply — connecting students and teachers for live lessons, with its own AI assistant, an in-house real-time educational whiteboard, class booking, and payments. Currently paused, but the core product is functional: booking, payments, AI chat, and the whiteboard's core drawing functionality all work.

### Client Problem
Not client work — this is a founder-led personal product. The vision was to make high-quality education accessible at a lower price point than existing platforms, while offering more advanced features (an integrated AI assistant and a purpose-built collaborative whiteboard) rather than a bare-bones booking-and-video-call product.

### Solution
Built the full platform from scratch: a NestJS backend covering the actual mechanics of a tutoring marketplace — academies, teachers, students, parent/parent-child accounts, subjects, class scheduling, enrollment, assignments, reviews, invitations, currency handling, and payments — plus an AI module (built on Groq for fast inference) and a websocket layer for real-time features.

On the frontend, alongside the standard student/teacher/parent experience, a custom educational whiteboard was built specifically for live tutoring sessions: drawing tools, shapes, text, image upload, color/line controls, undo/redo, zoom, page management, and PNG/PDF export are all working. Real-time multi-user collaboration on the whiteboard (live cursors, simultaneous editing) was scoped and partially built but not completed before the project was paused.

### Architecture
- NestJS backend with domain-scoped modules: academy, teacher, student, parent, parent-child, class, subject, enrollment, assignment, reviews, invitation, currency, payment, discover, chat, performance, admin, plus a dedicated AI module
- Websocket layer for real-time features (chat, and the in-progress whiteboard collaboration)
- Angular frontend with a custom-built canvas-based whiteboard component, independent of any third-party whiteboard SDK
- Email templating system for platform notifications

### Technology Stack
- NestJS, TypeScript (backend)
- Angular (frontend, including a custom canvas whiteboard)
- Groq (AI inference provider for the in-app AI assistant)
- WebSockets (real-time chat and whiteboard groundwork)
- Payment processing integration

### Implementation Highlights
- Built a genuinely multi-role marketplace (student, teacher, parent, parent-child, admin, academy) rather than a simple two-sided booking app
- Custom-built whiteboard rather than embedding a third-party tool — core drawing/annotation features fully working, with real-time collaboration scoped and tracked but not finished
- AI assistant integrated via Groq for fast inference
- End-to-end booking and payments both functional

### Business Impact
Not applicable — self-funded personal product, currently paused before public launch. No user/revenue metrics to report; value here is as a demonstration of shipped, working functionality (booking, payments, AI chat, core whiteboard) across a full multi-sided platform.

### Lessons Learned
Not captured for this project.

### Proposal Usage
- Keywords: online tutoring platform, EdTech marketplace, real-time whiteboard, AI tutoring assistant, NestJS, Angular, multi-sided marketplace, class booking and payments
- Related services: Full Stack Development, AI Development, Backend Development, Frontend Development
- Related industries: EdTech, Online Learning, Marketplace/Multi-sided Platforms

---

## Case Study: Plickee — Shoppable OTT Streaming Platform (client confidential)

### Overview
Plickee was a startup concept for an OTT streaming platform — think Netflix or Amazon Prime as the viewing experience — but built around a fundamentally different monetization idea: instead of interrupting the video with traditional pre-roll or mid-roll ads, items visible within a video (say, a diamond ring a character is wearing) could be tagged as clickable segments. If that item existed in the platform's linked store, a viewer could click the segment during playback and buy it directly — advertising embedded natively in the content itself rather than breaking it up.

### Client Problem
The client had the product idea and needed the entire technical build — backend, web app, and mobile app — to bring it to life as a working platform. The project ultimately didn't move forward because the client wasn't able to secure investor funding to take it further; that side of the business (fundraising) was outside the scope of this engagement, which was purely the technical build.

### Solution
Built and owned the full technical stack solo — backend API, Angular web application, and a mobile app — effectively acting as the client's entire technical team. The core mechanic: videos are broken into time-based segments, each of which can carry a title, description, and a linked item; when a segment's linked item is available in the connected store, viewers can click through from that exact moment in the video to view and buy it. Standard streaming-platform pieces — accounts, an activity feed, content/age-confirmation gating, and an admin layer for managing content — were built around that core mechanic.

### Architecture
- Node.js / Express / TypeScript backend with dedicated services for video content, video segments/intervals (the clickable-ad mechanic), user accounts, and activity tracking
- MySQL data model built specifically around time-interval-linked video segments (a segment has a title, description, a linked URL, and a start/end interval tied to a specific video)
- Angular web application with account, admin, landing, and main viewing modules, plus content-gating (age/censor confirmation) before video playback
- A companion native mobile app delivering the same viewing and shoppable-segment experience

### Technology Stack
- Node.js, Express.js, TypeScript, MySQL (backend)
- Angular (web)
- Native mobile app
- CI/CD pipeline (AWS CodeBuild/CodeDeploy configuration present in the backend)

### Implementation Highlights
- Designed a segment/interval data model expressive enough to tie an arbitrary clickable link to a specific time range within a specific video — the core IP of the product
- Delivered across three platforms (backend, web, mobile) as the sole developer
- Built content-gating (age/censorship confirmation) into the viewing flow alongside the core streaming experience
- Set up CI/CD deployment tooling for the backend rather than leaving deployment manual

### Business Impact
The platform reached working-build stage across all three components but didn't proceed to launch — the client wasn't able to secure investor funding to take it further, which was outside this engagement's scope.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: OTT streaming platform, shoppable video, interactive video advertising, video segment tagging, native mobile app, full stack startup MVP, video commerce
- Related services: Full Stack Development, Backend Development, Frontend Development, Mobile Development
- Related industries: Media/Streaming, E-commerce, AdTech, Startups

---

## Case Study: GoStudy.ae — Personalised Online Tutoring Platform

### Overview
GoStudy.ae ([gostudy.ae](https://gostudy.ae)) is a personalised online tutoring platform serving students in the UAE, with distinct onboarding flows for teachers, students, and parents, and a fixed, structured subject catalog. Alongside the core platform, it runs a content-marketing blog built on Next.js with a Laravel-based CMS backend (using the open-source "Canvas" blogging package) for SEO and content publishing.

### Client Problem
The client wanted a new educational website/platform built from scratch, serving UAE students seeking personalised tutoring.

### Solution
Delivered as the full-stack developer for the entire application — not just the blog. The platform gives teachers, students, and parents each their own onboarding path into the system, built around a fixed list of subjects rather than open-ended subject creation, reflecting a more curated, structured tutoring offering. The supporting blog runs on its own Next.js frontend backed by a Laravel API wrapping the Canvas blogging package, giving the marketing/content side of the platform its own independently deployable stack from the core application.

### Architecture
- Full-stack educational platform with role-based onboarding for teachers, students, and parents, and a fixed subject catalog
- Next.js blog frontend for content marketing and SEO
- Laravel backend (using the `austintoddj/canvas` blogging package) exposing a custom API layer for the blog frontend to consume

### Technology Stack
- Next.js, TypeScript (blog frontend)
- Laravel, PHP (blog CMS backend, Canvas blogging package)
- (Core platform stack as delivered to the client; blog/CMS stack is the portion directly reflected in this account's repositories)

### Implementation Highlights
- Built the entire platform end-to-end, including role-specific onboarding for three distinct user types (teacher, student, parent)
- Kept the content-marketing blog architecturally separate from the core application — a Next.js site backed by its own Laravel/Canvas CMS — so content publishing doesn't depend on the main platform's release cycle
- Wrapped the open-source Canvas blogging package with a custom API layer rather than exposing it directly, keeping the frontend decoupled from the CMS internals

### Business Impact
Not captured for this engagement.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: online tutoring platform, EdTech website development, role-based onboarding, Next.js blog, Laravel CMS, content marketing platform, UAE education
- Related services: Full Stack Development, Frontend Development, Backend Development
- Related industries: EdTech, Online Learning, Education (UAE market)

---

## Case Study: Taiz Kaam — Services Marketplace API (client confidential)

### Overview
Built the backend API for a services marketplace mobile app ("Taiz Kaam" — roughly "fast work") connecting service providers with customers who can browse services, place orders, and rate providers afterward.

### Client Problem
The client needed a backend API to power their mobile app — a marketplace where customers could find and order services from providers, with a ratings system to build trust between the two sides.

### Solution
Scoped purely as backend work: API, database, and deployment. Built the full API first in Node.js/TypeScript, covering authentication, provider profiles, service listings, orders, and ratings. After that build was ready, it turned out the client's hosting was a shared cPanel plan that couldn't run a Node application — so the same API had to be rebuilt in PHP/Laravel to run on the infrastructure the client actually had, rather than the infrastructure the project had been built for.

### Architecture
- Two functionally-equivalent backend implementations of the same API: Node.js/Express/TypeScript (original) and PHP/Laravel (rebuilt for cPanel compatibility)
- Domain structure shared across both: authentication, provider management, service listings, order management, and ratings
- Deployed to the client's cPanel hosting environment (the constraint that drove the PHP rebuild)

### Technology Stack
- Node.js, Express.js, TypeScript (original build)
- PHP, Laravel (rebuilt version, cPanel-compatible)
- Relational database (MySQL)

### Implementation Highlights
- Delivered the same marketplace domain model — providers, services, orders, ratings, auth — in two different stacks when infrastructure constraints demanded it
- Owned the full backend lifecycle: API development, database design, and deployment
- Handled deployment onto a shared cPanel environment, which is a materially different (and more constrained) target than a typical Node deployment

### Business Impact
Not captured for this engagement.

### Lessons Learned
Confirm the client's actual hosting budget and infrastructure upfront, before committing to a tech stack — this project had to be rebuilt from Node to PHP after the fact because the client's hosting couldn't run Node and wasn't going to be upgraded. Asking early whether the client can afford infrastructure that matches the proposed stack would have avoided the rework.

### Proposal Usage
- Keywords: services marketplace API, gig marketplace backend, mobile app backend, Node to PHP migration, cPanel deployment, provider/order/rating system
- Related services: Backend Development, API Integration, Cloud Deployment, Database Design
- Related industries: Services Marketplace, On-demand Services, Mobile Apps
