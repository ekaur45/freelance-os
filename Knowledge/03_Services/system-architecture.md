---
id: service-system-architecture
title: System Architecture
category: Service
priority: High
skills:
  - Clean Architecture
  - Microservices
  - Domain-Driven Design
  - Scalability Planning
---

# System Architecture Service

## Service Summary

I design the structural foundation of software systems — how services, data, and boundaries are organized — so that applications stay maintainable and scalable as they grow. This covers greenfield architecture design, breaking apart monoliths that have become unmanageable, and planning for scale before it becomes an emergency.

---

# Service Overview

This service includes:

* System & Application Architecture Design
* Microservices vs. Modular Monolith Decisions
* Domain-Driven Design (DDD)
* API-First Architecture Planning
* Scalability & Load Planning
* Event-Driven Architecture Design
* Monolith-to-Microservices Migration Planning
* Multi-Tenant Architecture Design

---

# Business Problems Solved

Clients typically hire me to:

* Design the architecture for a new system before development starts
* Break apart a monolithic application that's become difficult to change safely
* Plan for scale ahead of expected growth (users, data volume, traffic)
* Design multi-tenant architecture for a SaaS product
* Resolve recurring architectural pain points (tight coupling, unclear boundaries)

---

# Typical Deliverables

* Architecture diagrams and documentation
* Service/module boundary definitions
* Data ownership and consistency strategy
* Technology and infrastructure recommendations
* Migration plan (for monolith-to-microservices or major restructuring)

---

# Architectural Approaches

* Clean Architecture / Layered Architecture
* Domain-Driven Design (DDD)
* CQRS
* Microservices
* Modular Monoliths
* Event-Driven Architecture
* API-First Design

---

# Common Use Cases

* New SaaS product architecture
* Multi-tenant platform design
* Breaking apart a monolith into services
* Designing for high-scale or high-availability requirements
* Establishing architectural standards across a growing engineering team

---

# Best Practices

* Start from business domains and data ownership, not technology preferences
* Prefer a well-structured modular monolith over premature microservices
* Define clear service/module boundaries before scaling out infrastructure
* Design for observability (logging, monitoring) from the start
* Document architectural decisions and the reasoning behind them (ADRs)

---

# Common Client Problems Solved

* Codebase has grown into a tightly coupled system that's risky to change
* No clear boundaries between features, making changes ripple unpredictably
* Team wants microservices but isn't sure if the complexity is justified yet
* System needs to support multiple tenants/customers but wasn't designed for it
* Scaling issues are architectural, not just infrastructure-related

---

# Industries Served

* SaaS
* Healthcare
* Enterprise Software
* Business Automation

---

# Proposal Positioning

Use this service when clients mention:

* System architecture
* Microservices
* Scalability
* Technical debt / tightly coupled system
* Multi-tenant
* Domain-driven design
* Monolith to microservices

---

# Discovery Questions

When appropriate, ask:

* Is this greenfield architecture or restructuring an existing system?
* What's driving the architecture need — current pain, expected growth, or both?
* What's the team size and structure that will build/maintain this?
* Is multi-tenancy a requirement?
* What are the critical scalability or availability requirements?

---

# Cross References

Related Skills

* Backend Development
* Microservices
* Database Design

Representative Projects

Reference:

`Knowledge/04_Projects/`

Related Services

* Backend Development
* Full Stack Development
* Technical Consulting

---

# Notes for AI

System Architecture is often paired with Technical Consulting (assessment) or Backend Development (implementation), depending on whether the client wants a design/recommendation or a built system. Avoid recommending microservices by default — only propose them when the client's actual scale or team structure justifies the added complexity; a modular monolith is usually the more honest recommendation for early-stage products.
