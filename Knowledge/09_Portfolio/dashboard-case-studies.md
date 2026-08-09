# Dashboard Case Studies

## Admin Dashboards

Focus:
- Data visualization
- User management
- Reporting
- Analytics
- Workflow control

Relevant for SaaS, ERP, CRM and internal tools.

---

## Case Study: Logistics & Parcel Tracking Platform (client not named)

### Overview
A full digital platform for a courier/logistics business, built across three parts: a public marketing and self-service website (quote requests, parcel tracking, company info), an internal admin operations panel, and the backend API tying both together. The engagement came through an informal referral (a friend), and no company/brand name was captured for this write-up.

### Client Problem
The client needed a complete digital presence and operations system for a parcel/courier business from the ground up: a public-facing site customers could use to request quotes and track shipments, and an internal system staff could use to actually run the business — creating and managing packages, recording sender/receiver details, tracking a shipment as it moves through multiple handling points, pricing each leg of that movement, and keeping on top of fleet/equipment maintenance.

### Solution
Built as the developer across the full stack: an Angular-based admin panel, a public marketing/tracking website, and an Express/TypeScript backend API.

The core of the system is a "logistic chain" model — a shipment isn't just "in transit" or "delivered," it moves through a defined chain of locations, each with its own price and status, giving staff granular visibility into exactly where a package is and what each leg of its journey costs. On top of that: sender/receiver management, role-based access (admin vs. regular staff see different scopes of data), maintenance reporting, and a reports module for operational visibility.

The public site covers the customer-facing side of the same business — service pages, a quote-request form, parcel tracking, and standard company/marketing pages (about, team, careers, FAQs, blog).

### Architecture
- Express.js / TypeScript backend with dedicated controllers for packages, sender/receiver records, accounts, and users; Swagger-documented API; localization support
- Domain models built around a logistic-chain concept: packages, logistic chain entries (per-leg location and pricing), location-change events, and maintenance reports, alongside standard order/shipping/user models
- Angular admin panel (built on the ngx-admin template) with dedicated pages for dashboard, packages, sender/receiver, tracking, users, maintenance, and profile — role-scoped by user type
- Static/public-facing marketing and tracking site as a separate frontend

### Technology Stack
- Node.js, Express.js, TypeScript (backend)
- Angular, ngx-admin (admin panel)
- HTML/CSS/JS (public marketing site)
- Swagger (API documentation), localization support

### Implementation Highlights
- Modeled shipments as a multi-leg "logistic chain" with per-location pricing and status, rather than a flat "package status" field — gives the business real operational granularity, not just a tracking number
- Role-based data scoping in the backend (admin sees everything; other staff see only what's relevant to them)
- Maintenance reporting built alongside the core shipment/package workflow, treating fleet/equipment upkeep as part of the same operational system rather than a separate tool
- Delivered all three pieces (backend, admin panel, public site) as one coherent platform

### Business Impact
No metrics captured — this was an informal referral engagement outside tracked marketplace channels.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: logistics platform, parcel tracking, courier management system, shipment tracking, admin operations dashboard, Angular admin panel, Express API, fleet maintenance reporting
- Related services: Full Stack Development, Admin Dashboard Development, Backend Development, API Integration
- Related industries: Logistics, Courier/Delivery Services, Transportation

---

## Case Study: Estate Hub — Property Listing & Management Platform

### Overview
Estate Hub is a real estate listing platform letting property buyers, renters, and agents browse listings by type and area, with a portal for adding and managing property listings. Live demo: [estatehubisb.develenza.com](https://estatehubisb.develenza.com).

### Client Problem
Estate Hub needed a platform to list and manage properties online — a public-facing site for browsing listings, and a way for their team/agents to add and manage those listings without needing a developer involved for every update.

### Solution
Built as the full-stack developer, covering the public listing site (home, property search/listings, individual property pages, about/contact) and a portal for adding and managing properties directly, with SEO handling built in for listing pages.

### Architecture
- PHP backend (framework-free, custom bootstrap/helpers structure) with dedicated modules for listings data, property uploads, and SEO
- Tailwind CSS for the frontend styling
- A separate portal area for property management (add/manage listings) alongside the public-facing site
- File/image upload handling for property listings

### Technology Stack
- PHP, MySQL
- Tailwind CSS
- Custom-built (no framework) — bootstrap/helpers/config structure built from scratch rather than relying on a framework's conventions

### Implementation Highlights
- Built both sides of the platform — public listings site and the internal property-management portal — as one cohesive system
- SEO handling built in specifically for listing pages, relevant given real estate listings live and die by search visibility
- Image/file upload pipeline for property photos as part of the listing-management flow

### Business Impact
Not captured for this engagement.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: real estate platform, property listing website, property management portal, PHP web development, Tailwind CSS, SEO-optimized listings
- Related services: Full Stack Development, Frontend Development, Backend Development
- Related industries: Real Estate, PropTech

---

## Case Study: Travel Booking Platform (details reconstructed from code)

### Overview
A Laravel-based travel booking system covering flights, hotels, and destinations — customers (or agency staff) can browse destinations, book hotel rooms and flights, and generate a PDF booking voucher/confirmation for each reservation. This was real client work from earlier in the freelance history that isn't fully recalled in detail — the description below is reconstructed from the codebase itself.

### Client Problem
Reconstructed from the code: a travel-agency-style business needed a system to manage bookings across flights, hotels, and destinations in one place, with the ability to generate a formal PDF voucher for each booking rather than handling confirmations manually.

### Solution
Built a booking management system with dedicated models for destinations, hotels (including room types and photos), flights, and the bookings that tie them together (a booking can include a hotel leg, a flight leg, and a destination). Full CRUD on bookings with search/filtering, plus one-click PDF voucher generation per booking and a "main voucher" view for consolidated confirmations.

### Architecture
- Laravel application with a relational model: Destination, Hotel, HotelPicture, RoomType, Flight, Location, and Booking (with BookingHotel, BookingFlight, and BookingDestination linking a booking to its component parts)
- Dashboard and account controllers for staff-side management alongside the booking/hotel/destination logic
- PDF generation built directly into the booking workflow rather than as a bolt-on export tool

### Technology Stack
- PHP, Laravel, MySQL
- PDF generation (voucher/confirmation documents)
- File upload handling (hotel/property images)

### Implementation Highlights
- Modeled bookings as composite records (a single booking can span hotel, flight, and destination legs) rather than one flat reservation type
- Search/filtering on bookings by term, alongside standard CRUD
- Dedicated PDF voucher generation per booking, plus a consolidated "main voucher" view

### Business Impact
Not available — this is older work and specific outcomes weren't recalled at the time of writing this case study.

### Lessons Learned
Not available for the same reason.

### Proposal Usage
- Keywords: travel booking system, hotel booking, flight booking, destination management, PDF voucher generation, Laravel booking platform
- Related services: Full Stack Development, Backend Development, Admin Dashboard Development
- Related industries: Travel & Hospitality, Tourism

---

## Case Study: Roof Survey London — Lead-Gen Marketing Website

### Overview
A custom-built, fully responsive marketing website for a London roof survey and inspection business, delivered as an Upwork engagement. Live demo: [niko.develenza.com](https://niko.develenza.com).

### Client Problem
The client needed a professional, conversion-focused marketing website to generate leads for roof inspection services across London — covering service areas, pricing, credibility content (case studies, reviews, FAQs), and a clear path to contact/booking, without needing a database or CMS to maintain it.

### Solution
Built a database-free PHP site where every piece of content — site name, contact details, reviews, service areas, FAQs, case studies, pricing plans, "why choose us" statistics — lives in a single centralized data file, so the client (or a non-developer) can update site content without touching markup or logic. On top of that: a full 8-color theme system (switchable via a selector or URL parameter), a mobile-first responsive layout with a slide-in drawer menu, sticky navigation, and a testimonials carousel.

### Architecture
- Framework-free PHP with modular, reusable components (header, footer, FAQ, pricing, service areas, case studies, contact) included per-page
- Centralized data file driving all dynamic content — reviews, service areas, FAQs, case studies, pricing, statistics — functioning as a lightweight content layer without a database
- CSS architecture split by concern: base styles, then separate responsive stylesheets per breakpoint (992px/768px/480px), plus one stylesheet per color theme
- jQuery + Owl Carousel for the testimonials/reviews carousel

### Technology Stack
- PHP (framework-free, modular components)
- HTML5, CSS3 (CSS custom properties for theming)
- JavaScript/jQuery, Owl Carousel 2
- Font Awesome, Google Fonts

### Implementation Highlights
- 8 switchable color themes built on CSS custom properties, selectable via UI or URL parameter — a genuinely reusable theming system, not just a single palette
- Content fully separated from markup via a single data file, so the client can update reviews, pricing, service areas, and FAQs without a CMS or database
- Full responsive breakpoint system with a dedicated stylesheet per breakpoint, plus a mobile slide-in drawer menu with keyboard (ESC) and overlay support
- Delivered as a complete, documented handover — the project's own README covers setup, customization, and troubleshooting in detail

### Business Impact
Not captured for this engagement.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: marketing website, lead generation website, responsive web design, PHP website (framework-free), multi-theme website, service business website, local SEO website
- Related services: Frontend Development, Full Stack Development
- Related industries: Home Services, Local Business, Marketing Websites

---

## Case Study: Multi-Tenant QR Code Menu Platform (client unknown, Fiverr)

### Overview
A multi-tenant, bilingual (German and English) platform letting restaurants and hospitality businesses put their menu online behind a scannable QR code — each business signs up as its own company/tenant, manages its own menu, and gets a QR code customers can scan to view it, rather than a physical printed menu.

### Client Problem
The client wanted their menu available online via QR code scanning, in both German and English, rather than a single hard-coded menu page — the resulting build supports multiple companies onboarding independently, each managing and publishing its own menu.

### Solution
Built as the full-stack developer: a multi-tenant system where each business registers a company account (with verification), logs in to manage its own menu, and generates a QR code that links to that business's live, publicly viewable menu page — with the whole customer-facing experience available in German and English.

### Architecture
- PHP backend with company-scoped accounts (registration, login, email verification) so each business's menu is isolated from others on the platform
- QR code generation (`phpqrcode`) tied to each company's menu, producing a scannable code that resolves to that business's public menu view
- Separate public menu-viewing pages from the authenticated company/admin menu-management pages
- Bilingual content support (German/English) throughout the customer-facing menu experience

### Technology Stack
- PHP, MySQL
- phpqrcode (QR code generation library)
- HTML/CSS/JS (public menu display)

### Implementation Highlights
- Multi-tenant from the ground up — company signup, verification, and login rather than a single hard-coded business
- QR generation wired directly to each company's own menu, so scanning a code takes a customer straight to that business's current menu
- Bilingual (German/English) menu experience, relevant for a platform likely targeting the German hospitality market

### Business Impact
Not captured for this engagement.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: QR code menu, digital menu platform, multi-tenant SaaS, restaurant technology, bilingual website, contactless menu, hospitality tech
- Related services: Full Stack Development, Backend Development
- Related industries: Restaurant/Hospitality, Food Tech, SaaS

---

## Case Study: Restaurant Discovery & Booking Platform (client details not recalled)

### Overview
A restaurant discovery, booking, and reviews platform — customers can browse restaurants, make bookings, and leave reviews. Real client work sourced via a friend's Fiverr connection; specific client and outcome details weren't recalled, so this write-up is reconstructed from the codebase.

### Client Problem
Reconstructed from the code: the client needed a platform where customers could discover restaurants, book a table, and leave reviews — an OpenTable-style booking and discovery system rather than a single restaurant's own site.

### Solution
Built as the full-stack developer: account management (registration/login), a restaurant listing/discovery system, a booking flow, and a reviews system where customers can rate and review restaurants after booking.

### Architecture
- PHP backend organized around action groups: account, booking, restaurant, reviews, and file handling
- Relational data model connecting restaurants, bookings, and reviews to user accounts
- RTL (right-to-left) layout support included, suggesting the platform needed to serve an RTL-language market alongside standard LTR

### Technology Stack
- PHP, MySQL
- RTL-aware frontend layout

### Implementation Highlights
- Full discovery-to-booking-to-review flow rather than just a listing site
- RTL layout support built in, not bolted on afterward
- Account-scoped bookings and reviews tying customer activity together

### Business Impact
Not available — client and outcome details weren't recalled at the time of writing this case study.

### Lessons Learned
Not available for the same reason.

### Proposal Usage
- Keywords: restaurant booking platform, restaurant discovery, table booking system, restaurant reviews, RTL website support
- Related services: Full Stack Development, Backend Development
- Related industries: Restaurant/Hospitality, Food Tech

---

## Case Study: Threads4u — Custom E-commerce Platform for a Fashion Brand

### Overview
A fully custom-built e-commerce website for Threads4u ([threads4u.com](https://threads4u.com)), a new South Asian and contemporary fashion brand (women's, men's, and kids' clothing plus accessories) based in Pakistan — built from scratch rather than on an off-the-shelf platform like Shopify.

### Client Problem
A new clothing brand needed a fully custom online store — product catalog, cart, checkout, payments, and the surrounding customer-facing and marketing features — built specifically for them rather than adapted from a generic e-commerce template.

### Solution
Built as the full-stack developer: a complete storefront covering product browsing (with categories, brands, product variants and attributes for size/color-style options, and product images), cart and checkout, dual payment processing via Stripe and PayPal, order management with status history, coupons, wishlists, and customer reviews. Beyond the core store, the platform includes a blog/CMS layer, newsletter signup, contact handling, sitemap generation for SEO, and analytics event tracking.

### Architecture
- Laravel application split into Storefront (customer-facing: home, shop, product, cart, checkout, orders, payments, reviews, wishlist, blog, newsletter, contact, sitemap) and Admin layers, with dedicated webhook controllers for Stripe and PayPal
- Rich product data model: Product, ProductVariant, ProductAttribute/ProductAttributeValue, ProductImage, Category, Brand — supporting real apparel variation (size, color) rather than flat SKUs
- Order lifecycle modeled explicitly (Order, OrderItem, OrderStatusHistory, Payment, PaymentMethod) rather than a single status field
- Marketing/content layer: Blog, BlogCategory, CmsPage, Banner, Testimonial, Coupon/CouponUsage, Newsletter
- Webhook-driven payment confirmation from both Stripe and PayPal rather than relying solely on client-side confirmation

### Technology Stack
- PHP, Laravel, MySQL
- Stripe and PayPal (payment processing, webhook-verified)
- SEO tooling (sitemap generation)

### Implementation Highlights
- Product variants and attributes modeled properly (size/color/style combinations), not flattened into separate products
- Dual payment gateway support (Stripe + PayPal) with dedicated webhook handlers for reliable order/payment reconciliation
- Full order lifecycle tracking with status history, not just a current-status field
- Marketing features (coupons, newsletter, blog, testimonials, banners) built alongside the core store rather than left for a future phase
- Analytics event tracking built into the platform itself

### Business Impact
Not captured for this engagement.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: custom e-commerce platform, Laravel e-commerce, Stripe integration, PayPal integration, product variants, fashion e-commerce, online store development
- Related services: Full Stack Development, Backend Development, API Integration
- Related industries: E-commerce, Fashion/Apparel, Retail

---

## Case Study: Taxi/Cab Fleet Management System (Dubai-based client, confidential)

### Overview
A web-based fleet management system for a Dubai-based taxi/cab operator, letting the business manage drivers, vehicles, sales recorded by drivers, spare parts inventory, bank transactions, worker and driver salaries, and workshop expenses from one system.

### Client Problem
The client needed to manage the day-to-day operations of a taxi/cab fleet — drivers, vehicles, daily sales, parts inventory, and payroll — in one system rather than scattered records, with different access levels for management versus front-line staff.

### Solution
Delivered as the full-stack developer, building on and customizing an existing open-source fleet-management codebase to move faster rather than starting from zero, then adapting and extending it for the client's specific needs. The system supports three role levels — SuperAdmin, Admin, and Worker/Attendant — with SuperAdmin/Admin able to manage drivers, workers, vehicles, inventory, bank transactions, salaries, and workshop expenses, while Worker/Attendant accounts are scoped to recording daily sales and adding drivers.

### Architecture
- PHP MVC structure (controllers/models/views) with AJAX-driven admin interactions
- Role-based access split across SuperAdmin, Admin, and Worker/Attendant
- MySQL-backed data model covering drivers, vehicles, sales, inventory, bank transactions, salaries, and workshop expenses

### Technology Stack
- PHP, MySQL
- HTML5, jQuery/AJAX, Bootstrap

### Implementation Highlights
- Three-tier role system separating management-level operations (fleet, inventory, payroll, bank transactions) from front-line staff actions (recording sales, adding drivers)
- Financial tracking built in alongside operations — bank transactions, salaries, and workshop expenses tracked in the same system as the fleet itself
- Customized and extended an open-source fleet-management base for the client's specific operation rather than building the entire domain model from scratch, delivering faster

### Business Impact
Not captured for this engagement.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: fleet management system, taxi/cab management, driver management, vehicle inventory tracking, payroll tracking, workshop expense management
- Related services: Full Stack Development, Backend Development, Admin Dashboard Development
- Related industries: Transportation, Fleet Management, Logistics

---

## Case Study: Custom Decision Tree / Business Rules Engine (client confidential)

### Overview
A backend service that lets a business define its own decision logic as data (a JSON-structured decision tree) and execute it via a single API call — rather than hard-coding business rules into the application, the client can define and change their own conditional logic without a code change.

### Client Problem
The client (sourced via Fiverr) needed customers to be able to define and execute custom business logic tailored to their own needs — effectively a configurable rules engine rather than a fixed, hard-coded set of conditions.

### Solution
Built as the backend developer: a decision-tree model that can be constructed from JSON and executed on demand via a `POST /execute` endpoint, so the "business logic" itself is data supplied to the service rather than code shipped with it. Delivered as a properly engineered service, not just a script — full unit test coverage (Jest, with coverage reporting), Swagger API documentation, and a real CI/CD pipeline (AWS CodeBuild/CodePipeline deploying to EC2, triggered from GitHub) rather than manual deployment.

### Architecture
- Node.js / Express / TypeScript service with a dedicated decision-tree model, controller, router, and service layer
- Decision tree structure defined and passed as JSON, parsed into a model, and executed on request
- Standardized custom response utilities (`Ok`, `BadRequest`, `NotFound`, `UnAuthorized`, `InternalServerError`) for consistent API responses across the service
- Full CI/CD: GitHub-triggered AWS CodePipeline, CodeBuild for test/build, automated deployment to EC2 via shell scripts

### Technology Stack
- Node.js, Express.js, TypeScript
- Jest (unit testing, coverage reporting)
- Swagger (API documentation)
- AWS CodeBuild, CodePipeline, EC2 (CI/CD and hosting)

### Implementation Highlights
- Business logic modeled as configurable data (a JSON decision tree) rather than hard-coded conditionals, so the client can define their own rules without code changes
- Full automated CI/CD pipeline from GitHub to EC2, not manual deployment
- Test coverage and API documentation (Swagger) built in as standard practice, not an afterthought
- Standardized response utilities for consistent API behavior across endpoints

### Business Impact
Not captured for this engagement.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: business rules engine, decision tree engine, configurable business logic, Node.js API, AWS CI/CD, CodeBuild CodePipeline, Swagger documentation, test-driven backend
- Related services: Backend Development, API Integration, Cloud Deployment
- Related industries: SaaS, B2B Software, Workflow Automation

---

## Case Study: Standalone OAuth 2.0 Authorization Server (reconstructed from code)

### Overview
A standalone OAuth 2.0 authorization server built with NestJS — client registration, token issuance, and JWT-based client authentication as a self-contained service rather than auth logic embedded inside a larger application. No client/engagement context was given for this write-up; it's reconstructed purely from the code.

### Client Problem
Not specified — this reads as reusable authentication infrastructure (a dedicated auth server other applications can delegate to) rather than a single client's business problem, but that context wasn't confirmed.

### Solution
Built a dedicated auth service exposing client registration (`POST /register`), OAuth2 token issuance (`POST /token`), and JWT retrieval (`GET /Jwt`). The token request flow supports JWT-based client assertion (`client_assertion_type` / `client_assertion` fields) — the same JWT-bearer client authentication pattern (RFC 7523) used in SMART on FHIR backend-service flows, notably consistent with the FHIR/EHR integration work elsewhere in this portfolio.

### Architecture
- NestJS application with dedicated `auth` and `account` modules, each with their own controllers, services, DTOs, entities, and repositories
- Guards for request handling (form-URL-encoded request parsing, session handling)
- Dockerized (Dockerfile included) for containerized deployment
- Swagger/OpenAPI decorators on DTOs for API documentation

### Technology Stack
- NestJS, TypeScript
- OAuth 2.0, JWT (including JWT-bearer client assertion)
- Docker

### Implementation Highlights
- Implements JWT-bearer client assertion for token requests, not just basic client-secret auth — a more advanced OAuth2 client authentication pattern aligned with SMART on FHIR-style backend service authentication
- Separated account management from the auth/token-issuance logic as distinct modules
- Containerized for deployment rather than assuming a specific host environment

### Business Impact
Not available — no engagement context was provided for this write-up.

### Lessons Learned
Not available for the same reason.

### Proposal Usage
- Keywords: OAuth 2.0 server, JWT authentication, client assertion authentication, NestJS auth service, SMART on FHIR authentication, standalone identity server
- Related services: Backend Development, API Integration
- Related industries: Healthcare (FHIR-adjacent), SaaS, B2B Software

---

## Case Study: Offer-Based Online Shop (Fiverr, client unknown)

### Overview
An online shop with an offer/negotiation mechanic — buyers can make offers on products rather than only buying at a fixed listed price — built with a Svelte frontend and a Spring Boot (Java) + MongoDB backend. Delivered as a Fiverr engagement for a client who was a student.

### Client Problem
Not fully recalled beyond the client being a student sourced via Fiverr; reconstructed from the code, the request was for a working online shop with buyer-initiated offers on products, not just standard fixed-price checkout.

### Solution
Built as the full-stack developer: a Spring Boot backend exposing account, product, and offer management (buyers can submit offers on listed products, tracked via dedicated offer/buyer data models), with JWT-based authentication and file upload support for product assets, backed by MongoDB. The Svelte frontend consumes this API for the shopping experience.

### Architecture
- Spring Boot (Java) backend: Account, Product, and Offer controllers, with JWT auth filtering and Spring Security configuration
- MongoDB data layer via Spring Data MongoDB, with a custom sequence generator service for ID handling
- Svelte frontend (rollup-based build) with its own auth store and routing, consuming the backend over a REST API
- API documentation via springdoc-openapi (Swagger UI)

### Technology Stack
- Java, Spring Boot, Spring Security, Spring Data MongoDB
- JWT (jjwt)
- Svelte, Rollup
- MongoDB

### Implementation Highlights
- Offer/negotiation model (BuyerDto, OfferModelDto, OfferController) layered on top of standard product management — a more involved data model than a flat add-to-cart flow
- JWT authentication implemented at the Spring Security filter level, not bolted on afterward
- OpenAPI/Swagger documentation generated directly from the Spring Boot API

### Business Impact
Not captured for this engagement.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: Spring Boot e-commerce, Java backend development, MongoDB, JWT authentication, offer-based marketplace, Svelte frontend, REST API
- Related services: Full Stack Development, Backend Development, API Integration
- Related industries: E-commerce, Marketplace

---

## Case Study: Allergy-Aware Recipe Platform (reconstructed from code)

### Overview
A recipe platform where every ingredient is tagged Allergic or Non-Allergic and carries nutritional data (energy, fat, unsaturated fat, carbohydrates, and related values) — letting users browse and manage recipes with allergy and nutrition information attached at the ingredient level, not just the recipe level. No client/engagement context was given for this write-up; it's reconstructed from the code.

### Client Problem
Not specified — reconstructed from the code, the platform solves for recipe management where allergy status and nutritional content need to be tracked per ingredient, not just described in recipe text.

### Solution
Built a PHP recipe platform with account login/signup, recipe creation and editing, an ingredient system where each ingredient is classified Allergic/Non-Allergic with nutritional fields, a comment system on recipes, an admin view for managing recipes, and a grocery list feature generated from recipe ingredients.

### Architecture
- PHP application organized around action handlers (account, recipe, comment) separated from presentation partials
- Ingredient model carrying allergy classification and nutritional data (energy, fat, unsaturated fat, carbohydrates) rather than treating ingredients as plain text
- Recipe CRUD (add/edit/delete) with a separate admin-facing recipe management view
- Comment system scoped to recipes
- Grocery list generation from recipe ingredients

### Technology Stack
- PHP, MySQL
- HTML/CSS/JS (Bootstrap-based forms and layout)

### Implementation Highlights
- Ingredient-level allergy tagging and nutrition data, rather than flat recipe descriptions — the platform's actual differentiator
- Grocery list generation tied directly to recipe ingredients
- Separate admin view for recipe management alongside the standard user-facing recipe CRUD
- Comment system for user engagement on individual recipes

### Business Impact
Not available — no engagement context was provided for this write-up.

### Lessons Learned
Not available for the same reason.

### Proposal Usage
- Keywords: recipe platform, allergy tracking, nutrition data, ingredient management, grocery list generation, food tech, PHP web application
- Related services: Full Stack Development, Backend Development
- Related industries: Food Tech, Health & Nutrition, Consumer Apps

---

## Case Study: SveltyCMS Marketplace (reconstructed from code, team project)

### Overview
A marketplace application (products, categories, orders, transactions, user accounts) built on SvelteKit and SveltyCMS (an open-source headless CMS). Commit history shows this was a small team effort rather than solo work — contributed some features to the project rather than building it end to end. Specific engagement/client context wasn't recalled for this write-up.

### Client Problem
Not specified — details of the engagement weren't recalled.

### Solution
Contributed features to a SvelteKit/SveltyCMS-based marketplace covering product listings, categories, orders, transactions, file uploads, and account management. Specific individual contributions within the broader team effort aren't itemized here since they weren't recalled at the time of writing.

### Architecture
- SvelteKit application (TypeScript) built on SveltyCMS as the underlying content/data layer
- Domain entities: Product, Category, Order, Transaction, User
- Route structure covering account, category, file (uploads), and product areas plus a supporting API layer

### Technology Stack
- SvelteKit, TypeScript
- SveltyCMS (open-source headless CMS foundation)
- Tailwind CSS

### Implementation Highlights
- Built on top of an existing open-source CMS (SveltyCMS) rather than a from-scratch data layer, extending it with marketplace-specific entities (products, categories, orders, transactions)
- Delivered as part of a small team rather than solo

### Business Impact
Not available — engagement details weren't recalled.

### Lessons Learned
Not available for the same reason.

### Proposal Usage
- Keywords: SvelteKit marketplace, headless CMS, SveltyCMS, e-commerce marketplace, TypeScript full stack
- Related services: Full Stack Development, Frontend Development
- Related industries: E-commerce, Marketplace

---

## Case Study: Event Vendor Marketplace (client confidential)

### Overview
An event-planning marketplace connecting three types of vendors — venue providers, car rental agencies, and event decorators — with customers planning an event, letting them browse, book, and pay a deposit across all three vendor types in one place instead of sourcing each separately.

### Client Problem
The client needed a marketplace where event vendors could register and get verified, and customers could find and book venues, rental cars, and decoration services for an event through a single platform rather than coordinating each vendor independently.

### Solution
Delivered as the full-stack developer, as a code delivery. Built a vendor onboarding flow where venue providers, car rental agencies, and decorators register through a vendor-specific form (including ID/CNIC upload), get verified (with a "verified" badge once approved), and then list their own services. On the customer side: search and filter across vendors, booking flows for venues, car rentals, and decorators, ratings/feedback, and a 10% advance payment system to secure a booking. Car listings included their own verification step tied to vehicle registration.

### Architecture
- Node.js/Express backend with dedicated controllers for auth, events, venues, car rental, users, and home/landing content
- Domain models covering venues, cars (with ratings), decorators (via booking models), events, and services, separate from the base user model
- Multiple frontend iterations (an initial landing page, a redesigned "landing-rewamp," and a separate admin interface) reflecting the product evolving over the engagement
- API documentation via Swagger, with test coverage under `__test__`

### Technology Stack
- Node.js, Express.js
- Swagger (API documentation), Jest (testing)
- Frontend: multiple iterations (landing, redesigned landing, admin panel)

### Implementation Highlights
- Three distinct vendor types (venue, car rental, decorator) modeled and onboarded through one shared registration/verification flow rather than three separate systems
- Verification built into both vendor onboarding (ID upload, "verified" badge) and specific listings (e.g., car verification via registration number) — trust signals baked into the marketplace rather than left implicit
- 10% advance payment mechanic to secure bookings, addressing the no-show/commitment problem multi-vendor booking marketplaces commonly face
- Delivered through multiple frontend iterations as the product direction evolved, rather than treating the first design as final

### Business Impact
Not captured for this engagement.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: event vendor marketplace, multi-vendor booking platform, vendor verification system, event planning platform, venue booking, car rental booking
- Related services: Full Stack Development, Backend Development, API Integration
- Related industries: Events & Hospitality, Marketplace, Booking Platforms

---

## Case Study: Leaflet Mapping Skills Demo (led to client engagement)

### Overview
An interactive map demo built with Leaflet.js — draggable/resizable area selection on an OpenStreetMap base layer, paired with real building-footprint GeoJSON data (including 3D properties like height and roof material) — built specifically to demonstrate mapping capability to a prospective client.

### Client Problem
The client needed to evaluate whether custom interactive mapping (area selection, building-level geodata) was something that could be delivered for their actual project before committing to the full engagement.

### Solution
Built a focused Leaflet.js demo: an interactive area-select tool over an OpenStreetMap base layer showing selection bounds and dimensions in real time, plus a working example of loading and rendering real building-footprint GeoJSON data with 3D attributes (height, roof material, building type). The demo did its job — it led directly to the client engagement, after which the actual project was built and delivered in the client's own source control, so it isn't reflected in this repo.

### Architecture
- Leaflet.js for the interactive map and area-selection interaction
- GeoJSON building-footprint data (OpenStreetMap-derived) demonstrating real-world geodata rendering, including 3D building attributes
- Lightweight PHP/HTML/JS demo page, no backend beyond serving static assets

### Technology Stack
- Leaflet.js, jQuery
- GeoJSON, OpenStreetMap data
- PHP (static demo hosting)

### Implementation Highlights
- Purpose-built as a capability demonstration rather than a production deliverable — scoped tightly to prove the specific mapping capability the client needed to see
- Used real building-footprint GeoJSON data (not synthetic placeholders) to make the demo credible
- Successfully converted into a paid engagement, with the actual project delivered through the client's own source control

### Business Impact
Directly led to securing the client engagement — the demo's purpose was to win the work, and it did.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: Leaflet.js, interactive mapping, GeoJSON, OpenStreetMap, building footprint data, mapping proof of concept, geospatial development
- Related services: Frontend Development, Full Stack Development
- Related industries: GIS/Mapping, PropTech, Any industry needing custom map interactions

---

## Case Study: Booking Invoice & Voucher Generator (Fiverr, reconstructed from code)

### Overview
A booking system with automated PDF invoice and voucher generation — bookings are managed through the backend, and multiple invoice/voucher templates (including a price-hidden invoice variant) are rendered to PDF. Fiverr client work; a `forfiverr.xlsx` file left in the repo confirms the platform, though the client and further details weren't recalled.

### Client Problem
Reconstructed from the code: the client needed bookings to generate proper PDF documentation automatically — invoices (including a variant that hides pricing, likely for internal/partner-facing copies) and vouchers — rather than creating these documents manually per booking.

### Solution
Built a Node.js backend handling accounts, bookings, and users, with a dedicated set of PDF templates for invoices (two versions, one without pricing shown) and vouchers, paired with an Angular frontend for the booking interface.

### Architecture
- Node.js/Express backend with account, booking, and user controllers/models
- HTML-based PDF templates (invoice, invoice v2, invoice v2 without price, voucher) rendered per booking
- MySQL data layer (`project.sql`, dedicated `mysql` model folder)
- Angular frontend for the booking-facing interface

### Technology Stack
- Node.js, Express.js, MySQL
- HTML-to-PDF templating
- Angular

### Implementation Highlights
- Multiple invoice variants for different audiences (standard invoice vs. a price-hidden version), not just a single fixed template
- Voucher generation alongside invoicing, covering both the payment-confirmation and the redeemable-document sides of a booking
- Full booking lifecycle (account, booking, user) backing the document generation rather than PDF generation being a standalone tool

### Business Impact
Not available — client and outcome details weren't recalled at the time of writing this case study.

### Lessons Learned
Not available for the same reason.

### Proposal Usage
- Keywords: PDF invoice generation, booking system, voucher generation, HTML to PDF, Angular booking interface, automated document generation
- Related services: Full Stack Development, Backend Development
- Related industries: Travel & Hospitality, Booking Platforms, Professional Services

---

## Case Study: Family Finance & Bill Tracking App

### Overview
A household finance tracker for families — despite the project's working name ("FamilyBankingSystem"), it's not a literal banking integration; it's budget and expense tracking scoped to a family unit. Members track shared bills (utilities like water and gas, with pending/partial/paid status per billing period), personal debits/installment loans with due dates, a debit/credit transaction ledger per member, and gift money exchanged between family members.

### Client Problem
Reconstructed from the code: a family needed a shared way to track household bills, debts, and money movement between members — who owes what, what's been paid, and gifts given — rather than tracking it informally.

### Solution
Built as the full-stack developer: member accounts, a bills module tracking utility-style bills by type/month/year with payment status and partial-payment amounts, a debits module for tracked loans/installments with due dates, a transactions ledger recording debit/credit entries per member, and a gifts feature for money given between family members. A chatbot feature was also included for interacting with the system.

### Architecture
- PHP application with dedicated pages per feature area (bills, debits, gifts, members, statements, chatbot) and a lightweight internal API
- MySQL schema with explicit tables for bills, debits, and transactions, each scoped to a `userId` (family member)
- Session-based access control (`sessioncheck`) gating the member-facing pages

### Technology Stack
- PHP, MySQL
- Session-based authentication

### Implementation Highlights
- Bill status modeled with real granularity (Not available / Pending / Partial paid / Paid) with a separate amount-paid field, not just a boolean paid flag
- Debits tracked with installment amounts and due dates, effectively a simple loan-tracking feature within the family context
- A unified transaction ledger (debit/credit, per member) tying bills, debits, and gifts together into one financial picture per family member
- Chatbot feature included for interacting with the system, beyond standard CRUD screens

### Business Impact
Not captured for this engagement.

### Lessons Learned
Not captured for this engagement.

### Proposal Usage
- Keywords: family finance tracker, household budgeting app, bill tracking, debt/installment tracking, transaction ledger, personal finance PHP application
- Related services: Full Stack Development, Backend Development
- Related industries: FinTech (personal/household finance), Consumer Apps

---

## Case Study: PrimeAtele — Meal Prep Customer & Order Management (Fiverr, reconstructed from code)

### Overview
A customer and order management tool for a meal prep / food delivery business — staff can add customers and track each customer's meal order and daily pickup, alongside standard account/admin management. Real Fiverr client work (a `forfiverr.xlsx` file is present in the repo); further client details weren't recalled.

### Client Problem
Reconstructed from the code: the business needed a simple internal tool to track customers, what they ordered (meals), and when they're picking up, rather than managing daily pickups informally.

### Solution
Delivered as the full-stack developer: a React frontend (login, dashboard, add-customer, profile views) backed by a Node.js API with account, admin, and customer modules. The customer record centers on the operational reality of the business — name, contact info, a note field, today's pickup, and meals — rather than a generic contact-list schema.

### Architecture
- Node.js/Express backend with account and admin controllers, and a dedicated customer model/edit-customer model
- MySQL data layer
- React frontend with dashboard, customer creation, login/forgot-password, and profile views

### Technology Stack
- Node.js, Express.js, MySQL
- React

### Implementation Highlights
- Customer schema built around the business's actual daily operation (today's pickup, meals) rather than a generic CRM contact model
- Separate create/edit customer models, supporting a clean add-vs-update flow
- Full account lifecycle on the frontend (login, forgot password, profile) alongside the core customer/order management

### Business Impact
Not available — client and outcome details weren't recalled at the time of writing this case study.

### Lessons Learned
Not available for the same reason.

### Proposal Usage
- Keywords: meal prep management system, food delivery customer tracking, order management tool, small business admin tool, React dashboard
- Related services: Full Stack Development, Admin Dashboard Development
- Related industries: Food & Beverage, Meal Delivery, Small Business Tools

---

## Case Study: Kris Kindle — Secret Santa Group Draw Tool (reconstructed from code)

### Overview
A "Kris Kindle" (Secret Santa) organizer — admins create groups, add participants, and run a randomized gift-exchange draw, with support for excluding specific participants from being matched with each other (e.g. couples or family members who shouldn't draw each other).

### Client Problem
Reconstructed from the code: whoever this was built for needed a way to organize a gift-exchange draw across a group of participants, with the ability to exclude certain pairings, rather than manually managing the draw and exclusion rules by hand.

### Solution
Built as the full-stack developer: an admin-managed system for creating groups, adding/removing/updating participants, marking specific participants as excluded from the draw pool, and running the randomized draw itself, with session-based login protecting the admin functions.

### Architecture
- PHP application with a clear separation between admin pages (create-admin, groups, group-participants) and the draw/participant-management actions under `pages/`
- MySQL-backed groups and group-participants data, with an `excluded` flag per participant supporting pairing exclusions
- Session-based authentication for admin access

### Technology Stack
- PHP, MySQL

### Implementation Highlights
- Exclusion logic built into the participant model (an `excluded` flag filtered out at draw time), not just a plain random shuffle
- Clear group/participant CRUD separated from the draw action itself
- Include/exclude toggle actions (`inlude-user.php` / `exlude-user.php`) letting admins adjust the eligible pool without deleting participants

### Business Impact
Not available — engagement details weren't recalled at the time of writing this case study.

### Lessons Learned
Not available for the same reason.

### Proposal Usage
- Keywords: gift exchange app, Secret Santa organizer, group draw tool, random matching with exclusions, event/group management
- Related services: Full Stack Development, Backend Development
- Related industries: Events, Consumer Apps

---

## Case Study: Personal Music Upload Platform (reconstructed from code)

### Overview
A login-protected music upload tool — users can add music tracks with an accompanying cover image, tied to their own account. Engagement/client context wasn't recalled for this write-up; details below are reconstructed from the code.

### Client Problem
Not specified — reconstructed from the code, the platform solves for users needing a simple, personal space to upload and manage their own music files with associated artwork.

### Solution
A PHP application with session-based login, a music upload flow (file plus cover image), and per-user music management (add/delete), backed by a `user_music` table scoped to each user's account.

### Architecture
- PHP with session-based authentication gating upload/management pages
- Dedicated service layer for music add/delete/create and file upload handling
- MySQL schema: `user_music` (name, file location, picture location, linked to `userid`) alongside a `users` table

### Technology Stack
- PHP, MySQL
- File upload handling (audio file + cover image)

### Implementation Highlights
- Per-user music library scoping — each upload tied to the owning account, not a shared/global list
- Separated file-upload handling from the music-record CRUD logic
- Cover image support alongside the audio file itself, not just a bare file list

### Business Impact
Not available — no engagement context was provided for this write-up.

### Lessons Learned
Not available for the same reason.

### Proposal Usage
- Keywords: music upload platform, file upload management, personal media library, PHP web application
- Related services: Full Stack Development, Backend Development
- Related industries: Media, Consumer Apps

---

## Case Study: Browser-Based Code Editor UI (reconstructed from code)

### Overview
A browser-based, multi-file code editor interface — a file sidebar for managing multiple files (add/delete, with confirmation modal), built on the CodeMirror editor component. Engagement/client context wasn't recalled for this write-up; details below are reconstructed from the code.

### Client Problem
Not specified — reconstructed from the code, the project solves for an in-browser code editing interface with multi-file management, the kind of UI needed for an online IDE, coding playground, or embedded code-editing feature within a larger product.

### Solution
Built a frontend-only code editor UI: a file-list sidebar backed by a data layer (`data.js`), CodeMirror as the underlying editing surface (with a Solarized theme), and file management interactions (add file, delete file with a confirmation modal) layered on top.

### Architecture
- CodeMirror as the core code-editing component
- Custom sidebar/file-list UI with jQuery-based interactions (including a multi-select component)
- Modal-based confirmation flow for destructive actions (file deletion)

### Technology Stack
- HTML/CSS/JavaScript
- CodeMirror
- jQuery, jQuery Multi-Select

### Implementation Highlights
- Multi-file management UI (not just a single-textarea code box) — sidebar file list with add/remove
- Confirmation modal on delete, guarding against accidental file loss
- Built on CodeMirror rather than a bare `<textarea>`, giving proper syntax highlighting and editing ergonomics

### Business Impact
Not available — no engagement context was provided for this write-up.

### Lessons Learned
Not available for the same reason.

### Proposal Usage
- Keywords: browser code editor, CodeMirror, online IDE, multi-file editor UI, developer tools
- Related services: Frontend Development
- Related industries: Developer Tools, EdTech (coding platforms), SaaS

---

## Case Study: Coffee Shop E-commerce Site (reconstructed from code)

### Overview
A small e-commerce site for a coffee shop — product browsing, cart, checkout, customer accounts, an admin area, plus a blog and contact page. Engagement/client context wasn't recalled for this write-up; details below are reconstructed from the code.

### Client Problem
Not specified — reconstructed from the code, a coffee business needed a standard online storefront: browse products, add to cart, check out, with an admin side for managing the shop and a blog/contact presence for marketing.

### Solution
A PHP e-commerce application covering the full customer journey (shop → cart → checkout → account) plus admin login and item management, alongside blog and contact pages for the storefront's marketing side.

### Architecture
- PHP application with action handlers separated by concern (cart, items, checkout, login/signup, admin login)
- Standard e-commerce page set: shop, cart, checkout, account, admin, blog, contact
- File upload support (product imagery)

### Technology Stack
- PHP, MySQL

### Implementation Highlights
- Full customer purchase flow (shop → cart → checkout) built alongside a separate admin area for shop/item management
- Blog and contact pages included, treating the site as a marketing presence, not just a checkout flow

### Business Impact
Not available — no engagement context was provided for this write-up.

### Lessons Learned
Not available for the same reason.

### Proposal Usage
- Keywords: coffee shop e-commerce, small business online store, PHP e-commerce, shopping cart, checkout flow
- Related services: Full Stack Development, Backend Development
- Related industries: E-commerce, Food & Beverage

---

## Case Study: Recipe Finder & Grocery List App (reconstructed from code)

### Overview
A recipe platform where users can add and browse recipes, comment on them, and generate a grocery list from recipe ingredients — similar in spirit to the allergy-aware recipe platform elsewhere in this portfolio, but a separate build with its own API layer. Engagement/client context wasn't recalled for this write-up; details below are reconstructed from the code.

### Client Problem
Not specified — reconstructed from the code, the project solves for recipe discovery and management with a practical grocery-shopping tie-in, letting users go from "recipes I like" to "what I need to buy" in one flow.

### Solution
A PHP application with recipe add/view functionality, a comment system on recipes, account login/signup, and grocery list generation from recipe ingredients, backed by its own dedicated API layer for these actions.

### Architecture
- PHP application with a dedicated `API` folder handling core actions, separate from the page-rendering logic
- Recipe, comment, and grocery-list features backed by their own action handlers
- Account login/signup flow

### Technology Stack
- PHP, MySQL

### Implementation Highlights
- Grocery list generation tied directly to recipe ingredients, turning recipe browsing into an actionable shopping list
- Comment system for user engagement on individual recipes
- Structured API layer separating data actions from page templates, rather than mixing logic directly into views

### Business Impact
Not available — no engagement context was provided for this write-up.

### Lessons Learned
Not available for the same reason.

### Proposal Usage
- Keywords: recipe app, grocery list generator, recipe discovery, PHP web application, food tech
- Related services: Full Stack Development, Backend Development
- Related industries: Food Tech, Consumer Apps
