# Craft BD — Constraints, Dependencies & Assumptions Register

## 1. Purpose

This document records the major constraints, dependencies, and assumptions that may influence Craft BD's scope, schedule, architecture, implementation, testing, and deployment.

The objective is to make important project limitations visible before detailed requirements and development begin.

---

# 2. Definitions

## Constraint

A condition that limits the project.

Example:

Limited academic development time.

## Dependency

Something Craft BD requires before another activity can proceed correctly.

Example:

Product management depends on authentication and artisan identity.

## Assumption

Something currently believed to be true but not yet fully verified.

Example:

A responsive web application will be sufficient for the MVP.

---

# 3. Project Constraints

## C-01 — Academic Timeline

Craft BD must be completed within the academic course schedule.

### Impact

High

### Response

- Maintain strict MVP
- Prioritize core workflows
- Avoid unnecessary advanced features
- Test continuously

---

## C-02 — Small Development Team

The project is being developed by a student team rather than a full software company.

### Impact

High

### Response

- Use modular architecture
- Avoid microservices
- Share project knowledge
- Use GitHub Issues and Pull Requests
- Keep module ownership clear

---

## C-03 — Limited Budget

The academic project has limited financial resources.

### Impact

Medium

### Response

Use:

- Open-source tools
- Free development tiers
- Simulated payment
- Low-cost deployment

---

## C-04 — Limited Primary Research

Real customer and artisan interviews are not yet complete.

### Impact

High

### Response

Keep:

- Problem statement provisional
- MVP scope provisional
- Custom-order assumptions open

Review the scope after primary research.

---

## C-05 — Limited Production Data

The project does not initially have:

- Large real customer datasets
- Large purchase-history datasets
- Large recommendation datasets
- Large artisan datasets

### Impact

High for advanced recommendation systems.

### Response

Avoid making advanced AI recommendation a core MVP requirement.

---

## C-06 — Academic Infrastructure

The project may rely on free or low-cost hosting.

### Impact

Medium

### Possible Limitations

- Sleep / cold starts
- Resource restrictions
- Database limits
- Storage limits
- Build limits

### Response

Use free infrastructure for academic demonstration only and document limitations.

---

## C-07 — Browser-Based MVP

The initial platform is limited to a responsive web application.

### Impact

Low–Medium

### Out of Scope

- Native Android
- Native iOS

---

## C-08 — External API Availability

The team may not have guaranteed access to:

- Commercial payment APIs
- Logistics APIs
- SMS services
- Government certification services

### Impact

Medium

### Response

Do not make these integrations mandatory dependencies.

---

# 4. Technical Constraints

| ID | Constraint | Impact |
|---|---|---|
| TC-01 | Relational data model required for strongly connected entities | Medium |
| TC-02 | Role authorization must be enforced server-side | High |
| TC-03 | Sensitive secrets cannot be stored in source control | High |
| TC-04 | File uploads must be validated | High |
| TC-05 | Application must support responsive browser usage | Medium |
| TC-06 | Core workflows must be testable | High |
| TC-07 | Production deployment must use secure transport | High |
| TC-08 | Architecture should remain manageable for a small team | High |

---

# 5. Product Dependencies

## D-01 — Authentication → Authorization

Role-based behavior depends on successful authentication.

```text
Authentication
      ↓
User Identity
      ↓
Role
      ↓
Authorization
```

---

## D-02 — Artisan Profile → Product

A product must be associated with an artisan or seller.

```text
Artisan
   ↓
Product
```

---

## D-03 — Product → Cart / Order

Commerce functionality depends on valid product records.

```text
Product
  ↓
Cart
  ↓
Order
```

---

## D-04 — Customer + Artisan → Custom Order

The custom-order workflow requires both actors.

```text
Customer
     +
Artisan
     ↓
Custom Order
```

---

## D-05 — Custom Request → Quotation

Quotation cannot exist without a valid custom request.

---

## D-06 — Quotation → Customer Approval

Production should not begin before the customer accepts the quotation.

---

## D-07 — Approved Custom Order → Production Status

Only approved requests should transition to production.

---

## D-08 — Completed Order → Review

A verified-purchase review depends on an eligible completed order.

---

## D-09 — Product Record → QR Record

QR-linked verification requires an existing product or certificate record.

---

# 6. Development Dependencies

Recommended development sequence:

```text
Requirements
      ↓
Architecture
      ↓
Database
      ↓
API Contract
      ↓
Authentication
      ↓
Core Modules
      ↓
Integration
      ↓
Testing
      ↓
Deployment
```

Skipping major dependencies increases rework risk.

---

# 7. Documentation Dependencies

## SRS

Depends on:

- Discovery
- Scope
- Stakeholders
- Requirement finalization

## UML

Depends on:

- Actors
- Requirements
- Business workflows

## Database Design

Depends on:

- Functional requirements
- Entity identification
- Business rules

## API Design

Depends on:

- Architecture
- Database
- Workflow definitions

---

# 8. External Dependencies

Potential external dependencies include:

- GitHub
- Hosting platform
- Managed database provider
- File-storage provider
- Email provider
- Payment provider if added later
- Domain registrar if a custom domain is purchased

The MVP should minimize dependence on external commercial services.

---

# 9. Security Dependencies

Security depends on multiple design decisions.

Examples:

Authentication  
→ secure password storage

Authorization  
→ role design

File security  
→ upload restrictions

Secrets  
→ environment configuration

Review integrity  
→ purchase verification

Therefore, security is not a standalone final-stage activity.

---

# 10. Current Product Assumptions

## A-01

Customers are comfortable using a responsive web application.

**Status:** Open

---

## A-02

Artisans can operate a simple mobile-friendly web dashboard.

**Status:** Open

---

## A-03

Customers value structured product and artisan information.

**Status:** Partially supported

---

## A-04

Custom-order communication is currently inefficient enough to justify a structured workflow.

**Status:** Open / High Priority

---

## A-05

Artisans will benefit from structured custom-order requirements.

**Status:** Open / High Priority

---

## A-06

Simulated payment is acceptable for the academic MVP.

**Status:** Accepted for project planning

---

## A-07

A real payment gateway is not required for demonstrating the core Software Engineering value.

**Status:** Accepted

---

## A-08

Free or low-cost hosting will support the academic demonstration.

**Status:** Reasonable but provider-dependent

---

## A-09

A relational database is suitable for Craft BD.

**Status:** Strong assumption; to be confirmed during architecture design

---

## A-10

The project does not require microservices.

**Status:** Strong assumption based on current scale

---

# 11. User Assumptions

| ID | Assumption | Status |
|---|---|---|
| UA-01 | Customers can perform standard e-commerce actions | Reasonable |
| UA-02 | Customers may care about artisan identity | Needs validation |
| UA-03 | Customers may value cultural information | Needs validation |
| UA-04 | Customers may need custom-order status | Needs validation |
| UA-05 | Artisans may prefer a structured workflow over chat-only management | Needs validation |
| UA-06 | Administrators can manage basic platform governance | Reasonable |

---

# 12. Business Assumptions

| ID | Assumption | Status |
|---|---|---|
| BA-01 | Craft BD should not compete mainly on marketplace size | Accepted |
| BA-02 | Generic e-commerce is insufficient differentiation | Supported |
| BA-03 | Custom-order workflow may provide differentiation | Provisional |
| BA-04 | Craft context may provide additional value | Provisional |
| BA-05 | QR records may improve information access | Provisional |

---

# 13. Schedule Dependencies

The schedule assumes:

- Team members contribute regularly
- Major scope changes are controlled
- Architecture is approved before major implementation
- Testing occurs during development
- Deployment begins before the final deadline

If these assumptions fail, the schedule must be revised.

---

# 14. Academic Dependencies

Craft BD should demonstrate the course outcomes through the project.

The project therefore depends on producing evidence of:

- Software process selection
- Requirement analysis
- UML modeling
- Complexity analysis
- Cost estimation
- Software testing
- Tool usage
- Documentation

Implementation alone is not sufficient.

---

# 15. Dependency Risk Matrix

| Dependency | Failure Impact | Mitigation |
|---|---|---|
| Requirements incomplete | High | Finalize before development |
| Database design unstable | High | Review schema before coding |
| API contract unclear | High | Document endpoints first |
| Team coordination poor | High | GitHub Issues + PR workflow |
| External service unavailable | Medium | Provide fallback |
| Primary research delayed | Medium–High | Keep scope provisional |
| Hosting failure | Medium | Maintain deployment alternatives |
| Payment API unavailable | Low for MVP | Simulated payment |

---

# 16. Constraint Priority

## Critical

- Academic timeline
- Requirement stability
- Security controls
- Team capacity
- Scope control

## Important

- Hosting limitations
- Research availability
- External service access

## Manageable

- Custom domain
- Optional advanced integrations

---

# 17. Constraint Response Principle

When a constraint creates conflict:

```text
Constraint
   ↓
Impact Analysis
   ↓
Protect Core Workflow
   ↓
Reduce Optional Scope
```

The team should not sacrifice:

- Security
- Testing
- Correctness

only to preserve optional features.

---

# 18. Assumption Validation Rule

Important assumptions should eventually become one of:

**Validated**  
Evidence supports the assumption.

**Rejected**  
Evidence contradicts the assumption.

**Accepted Risk**  
The assumption cannot be fully validated but is acceptable for the project.

**Revised**  
The assumption must be changed.

---

# 19. Current Critical Open Assumption

The most important unresolved assumption remains:

> Structured custom-order management solves a sufficiently important customer/artisan problem to justify being a core MVP workflow.

This must be reviewed after primary user research.

---

# 20. Current Constraint Summary

```text
Academic Time
      +
Small Team
      +
Limited Budget
      +
Limited Data
      +
Primary Research Pending
      ↓
Controlled MVP Required
```

---

# 21. Engineering Decision

Given the current constraints:

Craft BD should use:

- Responsive web application
- Modular monolithic architecture
- Relational database
- Controlled MVP scope
- Free/low-cost academic infrastructure
- Simulated payment
- Incremental delivery
- Continuous testing

subject to later architecture review.

---

## Document Status

**Phase:** 02 — Feasibility & Scope Analysis  
**Document:** Constraints, Dependencies & Assumptions Register  
**Status:** Provisional v0.1  
**Next Step:** Phase 02 Consolidated Feasibility Review
