---
id: service-database-design
title: Database Design
category: Service
priority: High
skills:
  - SQL Server
  - PostgreSQL
  - MongoDB
---

# Database Design Service

## Service Summary

I design relational and document database schemas that stay correct and fast as data volume and business complexity grow. This includes new schema design, optimizing existing databases that have slowed down, and planning migrations between database systems or major schema changes without downtime.

---

# Service Overview

This service includes:

* Relational Schema Design
* Data Modeling for New Applications
* Query Optimization & Indexing
* Database Migration Planning
* ORM Configuration (Entity Framework Core, Prisma, TypeORM)
* Data Integrity & Constraint Design
* Reporting & Analytics Schema Design

---

# Business Problems Solved

Clients typically hire me to:

* Design a database schema for a new application
* Fix slow queries impacting application performance
* Plan a migration from one database engine to another
* Add proper indexing and constraints to a schema built without them
* Design reporting/analytics structures on top of transactional data

---

# Typical Deliverables

* Entity-relationship diagram (ERD)
* Normalized (or intentionally denormalized) schema
* Migration scripts
* Indexing strategy
* Query optimization recommendations
* ORM model/configuration

---

# Technology Stack

Relational

* SQL Server
* PostgreSQL
* MySQL

Document / NoSQL

* MongoDB

ORMs

* Entity Framework Core
* Prisma
* TypeORM

---

# Common Use Cases

* New application schema design
* Multi-tenant SaaS data modeling
* Performance tuning for slow-running queries
* Reporting/analytics data structures
* Database migrations (engine change or major version upgrade)

---

# Best Practices

* Normalize for integrity first, denormalize deliberately for known performance needs
* Index based on actual query patterns, not guesswork
* Use constraints (foreign keys, unique, not-null) to enforce data integrity at the database level
* Plan migrations with rollback strategies and zero/minimal downtime
* Document schema decisions so future developers understand the "why"

---

# Common Client Problems Solved

* Queries that used to be fast are now slow as data has grown
* Schema has no clear structure, with duplicated or inconsistent data
* No indexing strategy, causing full table scans on common queries
* Migration between database engines feels too risky to attempt

---

# Industries Served

* SaaS
* Healthcare
* E-commerce
* Enterprise Software

---

# Proposal Positioning

Use this service when clients mention:

* Database design
* Schema design
* Query performance / slow queries
* Data modeling
* Database migration
* Indexing

---

# Discovery Questions

When appropriate, ask:

* Is this a new schema or an existing database needing optimization?
* What's the current or expected data volume?
* What are the most frequent/critical queries the application runs?
* Is there a specific performance problem, or is this proactive design?
* Are there compliance or data residency requirements affecting design?

---

# Cross References

Primary Skills

* SQL Server
* PostgreSQL
* Entity Framework Core

Supporting Skills

* .NET / Node.js (application-side data access)
* MongoDB

Representative Projects

Reference:

`Knowledge/04_Projects/`

Related Services

* Backend Development
* System Architecture
* Full Stack Development

---

# Notes for AI

Database Design is usually a supporting service bundled into backend or full-stack engagements, but should be highlighted as a standalone offering when a client's job post is specifically about performance problems, schema design, or migrations. Reference specific database engines the client already uses when known.
