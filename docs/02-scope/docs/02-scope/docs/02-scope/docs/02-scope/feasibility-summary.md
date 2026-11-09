# Craft BD — Consolidated Feasibility Review

## 1. Purpose

This document consolidates the feasibility analysis conducted for Craft BD during Phase 02.

The analysis evaluates whether the proposed product can realistically be:

- Designed
- Developed
- Tested
- Deployed
- Operated
- Maintained

within the constraints of an academic Software Engineering project.

---

# 2. Overall Feasibility Decision

## Overall Assessment

**FEASIBLE WITH CONTROLLED SCOPE**

Craft BD can realistically be developed as an academic and portfolio-grade web application if:

- The MVP remains focused
- Optional features do not delay core workflows
- Security and testing are included from the beginning
- Advanced integrations remain outside the initial release
- Primary user research later confirms or revises the current custom-order direction

---

# 3. Technical Feasibility

**Decision: FEASIBLE**

The project can be implemented using standard full-stack web technologies.

Recommended high-level direction:

Responsive Web Frontend  
→ REST API  
→ Modular Backend  
→ Relational Database

Technically feasible core capabilities include:

- Authentication
- Role-based authorization
- Artisan profiles
- Product catalog
- Search and filtering
- Shopping cart
- Orders
- Structured custom orders
- Quotations
- Status management
- Reviews
- QR-linked product records

High-complexity features such as advanced AI, blockchain, live chat, and complex logistics integration are not recommended for the initial MVP.

---

# 4. Operational Feasibility

**Decision: FEASIBLE**

Customers should be able to use the platform with minimal training.

Artisan workflows must remain:

- Simple
- Mobile-friendly
- Structured
- Easy to understand

Administrator responsibilities should focus on:

- Governance
- Moderation
- Exceptional actions
- Verification-related tasks

The system should avoid creating unnecessary administrative bottlenecks.

---

# 5. Economic Feasibility

## Academic MVP

**Decision: ECONOMICALLY FEASIBLE**

The project can potentially be developed and deployed using:

- Free/open-source development tools
- Free source-control infrastructure
- Free or low-cost hosting
- Free development database tiers
- Simulated payment

Direct infrastructure cost may remain close to zero for the academic prototype.

However, development time remains a real project cost.

---

## Future Commercial Product

Commercial deployment would require a separate production budget.

Possible future costs include:

- Hosting
- Database
- Storage
- Domain
- Monitoring
- Payment services
- Email/SMS
- Backups
- Support

---

# 6. Schedule Feasibility

**Decision: FEASIBLE WITH CONTROLLED MVP**

A provisional development schedule of approximately:

**12–14 working weeks**

is considered realistic.

Key conditions:

- Requirements stabilize early
- Optional features remain secondary
- Testing occurs continuously
- Integration is not postponed
- Deployment is attempted before the final deadline

If time becomes limited:

**Reduce Scope — Do Not Reduce Quality**

---

# 7. Privacy Feasibility

**Decision: FEASIBLE**

Craft BD can operate using data-minimization principles.

The project should avoid collecting unnecessary sensitive information.

Important areas include:

- User accounts
- Contact information
- Delivery information
- Custom-order records
- Uploaded reference images
- Authentication data

Public and private information should be clearly separated.

---

# 8. Security Feasibility

**Decision: FEASIBLE WITH REQUIRED CONTROLS**

Required controls include:

- Secure password storage
- Server-side authorization
- Role-based access control
- Ownership validation
- Input validation
- Secure file uploads
- Secret management
- HTTPS
- Safe logging

Security should be designed before implementation rather than added at the end.

---

# 9. Legal / Compliance Feasibility

**Academic MVP Decision: FEASIBLE**

The project must avoid unsupported claims relating to:

- Physical authenticity
- Government certification
- Legal certification
- Payment security

A future commercial release would require formal legal and compliance review.

---

# 10. Core MVP Direction

The current recommended MVP centers on:

## Identity

- Registration
- Login
- Roles
- Authorization

## Artisan

- Artisan profile
- Expertise
- Experience
- Product relationship

## Product

- Product catalog
- Product details
- Categories
- Search
- Filtering

## Commerce

- Cart
- Checkout
- Order
- Order status
- Simulated payment

## Custom Order

Customer Request  
→ Artisan Review  
→ Quotation  
→ Customer Approval  
→ Production  
→ Status Updates  
→ Delivery

## Trust / Context

- Reviews
- Basic craft information
- Optional QR-linked product record

---

# 11. Feature Priority

## Must Have

- Authentication
- Authorization
- Artisan profile
- Product catalog
- Product details
- Search
- Cart
- Checkout
- Order management
- Structured custom request
- Artisan quotation
- Customer approval
- Custom-order status

## Should Have

- Filtering
- Craft story
- Reviews
- Reference-image upload
- Simulated payment
- QR-linked product record

## Could Have

- Wishlist
- Product journey
- Digital certificate
- Simple content-based recommendation

## Won't Have in Initial MVP

- Advanced AI recommendation
- Blockchain
- Live chat
- Native mobile application
- Mandatory real payment gateway
- Logistics API integration
- Advanced analytics
- Full event-management system

---

# 12. Major Constraints

The primary project constraints are:

- Academic timeline
- Small development team
- Limited budget
- Limited production data
- Primary research still pending
- Limited access to commercial APIs

These constraints justify a controlled MVP.

---

# 13. Critical Dependency

The most important unresolved product dependency is:

> Whether real customers and artisans validate structured custom-order management as an important problem.

Therefore:

Custom Order  
= Provisional Core Feature

until primary research is completed.

---

# 14. Main Project Risks

Highest-priority risks include:

1. Feature overload
2. Generic e-commerce positioning
3. Unvalidated custom-order problem
4. Weak real-user validation
5. Academic schedule pressure
6. Artisan adoption difficulty
7. Authorization/security mistakes
8. Scope creep

---

# 15. Risk Response Strategy

Craft BD will follow:

Risk  
→ Impact Analysis  
→ Protect Core Workflow  
→ Reduce Optional Scope  
→ Review Decision

The team should protect:

- Security
- Correctness
- Testing
- Documentation

before protecting optional features.

---

# 16. Proposed MVP Boundary

## In Scope

Responsive Web App  
+ Customer  
+ Artisan  
+ Admin  
+ Authentication  
+ Authorization  
+ Artisan Profiles  
+ Product Discovery  
+ Standard Orders  
+ Structured Custom Orders  
+ Quotations  
+ Approval  
+ Status Management  
+ Reviews  
+ Basic Craft Context

## Optional

Product Journey  
+ QR Product Record  
+ Digital Certificate  
+ Wishlist  
+ Simple Recommendation

## Out of Scope

Advanced AI  
+ Blockchain  
+ Live Chat  
+ Native App  
+ Complex Logistics  
+ Enterprise ERP  
+ Mandatory Real Payment Gateway

---

# 17. Academic Suitability

Craft BD is suitable for the Software Engineering course because it can demonstrate:

- Software process selection
- Requirement engineering
- Stakeholder analysis
- UML modeling
- Business rules
- State-based workflows
- Database relationships
- Security
- Testing
- Cost estimation
- Complexity analysis
- Git collaboration
- Deployment
- Documentation

---

# 18. Portfolio Suitability

The project can provide strong portfolio evidence if implemented with:

- Requirement traceability
- Clean Git history
- Pull Requests
- Architecture decisions
- Role-based authorization
- Custom-order state machine
- REST API design
- Relational database design
- Testing
- Deployment
- Professional README and case study

Portfolio value should come from engineering quality rather than feature quantity.

---

# 19. Final Phase 02 Recommendation

Craft BD should proceed to requirement finalization and system design using the current provisional MVP.

However:

Real primary research must still be completed before the custom-order workflow and final problem statement are permanently locked.

---

## Final Feasibility Result

| Area | Decision |
|---|---|
| Technical | FEASIBLE |
| Operational | FEASIBLE |
| Economic — Academic | FEASIBLE |
| Schedule | FEASIBLE WITH CONTROLLED SCOPE |
| Privacy | FEASIBLE |
| Security | FEASIBLE WITH CONTROLS |
| Legal — Academic MVP | FEASIBLE |
| Overall | **FEASIBLE WITH CONTROLLED SCOPE** |

---

## Document Status

**Phase:** Phase 02 — Feasibility & Scope Analysis  
**Document:** Consolidated Feasibility Review  
**Version:** 0.1  
**Status:** PROVISIONAL  
**Primary Research Dependency:** Open
