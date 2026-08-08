# Estimation Rules

## Purpose

Consistent estimation rules prevent both underpricing (which erodes margin and creates resentment toward the client) and overpricing (which loses winnable, well-qualified work). Estimates should be defensible, not guessed.

> **[TODO: This file defines the process. Actual rate figures live in `HourlyRates.md` and `FixedPrice.md` — fill those in with real numbers before relying on this file for live quotes.]**

---

# Before Estimating — Required Inputs

Per `CLAUDE.md`, identify before estimating:

* Features
* User roles
* APIs / third-party integrations
* AI requirements
* Authentication
* Notifications
* Reporting
* Deployment
* Maintenance expectations

If any of these are unclear, generate discovery questions first (see `Knowledge/08_Sales/DiscoveryQuestions.md`) rather than estimating blind.

---

# Estimation Process

1. **Break the project into components** (auth, core features, integrations, admin panel, deployment, etc.) rather than estimating the whole project as one block.
2. **Estimate each component in hours or complexity tiers** (see below).
3. **Add a risk buffer** for unknowns — larger buffer for vaguer requirements.
4. **Convert to price** using current hourly rate or a fixed-price multiplier (see `HourlyRates.md` / `FixedPrice.md`).
5. **Sanity-check against past similar projects** (see `PricingExamples.md`).

---

# Complexity Tiers

Use these as a starting classification before detailed estimation:

* **Simple** — single feature, no new integrations, minimal UI, well-defined scope.
* **Moderate** — multiple features, 1-2 integrations, standard auth, moderate UI complexity.
* **Complex** — multiple integrations, custom business logic, multi-role permissions, real-time or AI components.
* **Enterprise** — high compliance/security requirements, multiple systems integration, scalability requirements, healthcare/finance domain constraints.

---

# Risk Buffer Guidelines

Add buffer time/cost based on:

* **Unclear requirements** → larger buffer, or push to hourly/discovery-phase pricing instead of a fixed quote.
* **New/unfamiliar third-party API** → buffer for integration surprises.
* **Client history unknown (new client, no reviews)** → moderate buffer or milestone-based payment to reduce risk.
* **Fixed deadline with fixed scope** → buffer explicitly, or clearly flag that scope must flex if the deadline can't.

Never quote a fixed price on unclear scope — convert to a paid discovery phase first, then quote the build.

---

# When to Use Hourly vs. Fixed Price

Use **Fixed Price** when:

* Scope is well-defined and unlikely to change significantly.
* The client wants budget certainty.
* The project is short-to-medium in duration.

Use **Hourly** when:

* Scope is open-ended, exploratory, or likely to evolve.
* The engagement is ongoing (maintenance, retainer).
* The client needs flexibility to reprioritize as they learn.

See `FixedPrice.md` and `HourlyRates.md` for specifics.

---

# Re-Estimating Mid-Project

When scope changes materially after an estimate is agreed:

* Document what changed and why.
* Re-estimate only the delta, not the whole project.
* Communicate the change and get agreement in writing before proceeding (see `Knowledge/08_Sales/Negotiation.md`).

---

# Guiding Principle

An estimate should be something you'd be comfortable defending line by line — not a number picked to sound competitive.
