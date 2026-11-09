# Craft BD — Stakeholder Register

## 1. Purpose

This document identifies the major stakeholders related to Craft BD and distinguishes them from external technical dependencies.

The stakeholder register supports:

- Requirement elicitation
- Requirement prioritization
- UML actor identification
- UI/UX decisions
- Role-based access control
- Risk management
- Communication planning
- Project governance

The register is provisional because primary user interviews are still pending.

---

# 2. Stakeholder Definition

A stakeholder is any person, group, or organization that:

- Uses the system
- Is affected by the system
- Influences system requirements
- Makes project decisions
- Operates or governs the platform
- Has academic, legal, or business interest in the project

---

# 3. Stakeholder Categories

Craft BD stakeholders are grouped into:

## Primary Stakeholders

Directly use the system and receive direct value from it.

## Secondary Stakeholders

Support, manage, govern, or influence the system but are not the main value recipients.

## External / Regulatory Stakeholders

May influence legal, compliance, or business constraints.

## External Technical Dependencies

Provide infrastructure or integrations but are not treated as core product stakeholders.

---

# 4. Primary Stakeholders

## STK-01 — Customer

### Role

Primary platform user.

### Main Goals

- Discover handicraft products
- Understand product information
- View artisan identity
- Purchase products
- Submit custom-order requests
- Review quotations
- Track orders
- Submit reviews

### Main Needs

- Easy product discovery
- Clear information
- Trust
- Simple ordering
- Clear custom-order communication
- Status visibility

### Influence

Medium

### Interest

High

### Requirement Contribution

High

### Current Validation Status

Partially validated through secondary evidence.

Primary interview validation pending.

---

## STK-02 — Artisan / Craft Seller

### Role

Primary platform user and product provider.

### Main Goals

- Present professional profile
- Showcase products
- Receive customer orders
- Manage custom-order requests
- Provide quotations
- Update order progress
- Improve customer communication

### Main Needs

- Simple dashboard
- Easy product management
- Mobile-friendly workflow
- Clear customer requirements
- Reduced communication confusion
- Manageable administrative workload

### Influence

High

### Interest

High

### Requirement Contribution

Very High

### Current Validation Status

Partially supported by secondary evidence.

Primary artisan interviews pending.

---

# 5. Secondary Stakeholders

## STK-03 — Platform Administrator

### Role

Operational and governance stakeholder.

### Main Responsibilities

- Manage users
- Manage categories
- Moderate content
- Handle exceptional platform issues
- Manage platform verification records where applicable
- Monitor system activity

### Main Goals

- Maintain platform quality
- Prevent misuse
- Resolve administrative issues
- Maintain correct data

### Influence

High

### Interest

High

### Requirement Contribution

High

### Important Note

Administrator is primarily a system-operational role rather than the main beneficiary of the product.

---

## STK-04 — Project Development Team

### Role

Designs, develops, tests, documents, and deploys Craft BD.

### Main Responsibilities

- Requirement engineering
- Architecture
- UI/UX
- Development
- Testing
- Security
- Deployment
- Documentation

### Main Goals

- Deliver a functional project
- Meet course requirements
- Maintain code quality
- Produce portfolio-quality engineering evidence

### Influence

Very High

### Interest

Very High

### Requirement Contribution

Technical and implementation requirements.

---

## STK-05 — Academic Supervisor / Faculty

### Role

Academic evaluator and project advisor.

### Main Responsibilities

- Review project direction
- Evaluate academic quality
- Provide feedback
- Assess whether course outcomes are met

### Main Goals

- Correct Software Engineering process
- Clear requirement analysis
- Appropriate design decisions
- Testing evidence
- Academic rigor
- Realistic project scope

### Influence

Very High

### Interest

High

### Requirement Contribution

Academic and process constraints.

---

# 6. Potential Business Stakeholders

## STK-06 — Craft Business / Small Workshop Owner

### Role

Possible seller stakeholder where products are managed by a small craft business rather than an individual artisan.

### Main Goals

- Manage product catalog
- Reach customers
- Receive custom-order requests
- Present business/artisan identity

### Influence

Medium

### Interest

High

### Requirement Contribution

Potential seller-side requirements.

### Status

Secondary target segment.

---

## STK-07 — Social-Media-Based Craft Seller

### Role

Potential seller currently using platforms such as Facebook or Messenger for customer communication.

### Main Goals

- Reduce repetitive messaging
- Organize customer requests
- Manage quotations
- Track order progress
- Present products professionally

### Influence

Medium

### Interest

High

### Requirement Contribution

Important for custom-order workflow validation.

### Status

Priority research target.

---

# 7. External / Regulatory Stakeholders

## STK-08 — Relevant Government / Regulatory Authorities

### Role

Provide laws, regulations, guidelines, and compliance requirements relevant to digital commerce and personal data.

### Possible Areas of Influence

- Personal-data processing
- Cybersecurity
- Consumer protection
- Digital commerce

### Influence

High

### Direct System Usage

None

### Requirement Contribution

Legal and compliance constraints.

### Important Note

These authorities are not normal application users.

---

## STK-09 — Consumer Protection Authorities

### Role

Relevant to customer rights and digital-commerce conduct.

### Possible Interests

- Accurate product information
- Fair transactions
- Appropriate customer communication
- Complaint handling

### Influence

Medium–High

### Direct System Usage

Normally none.

---

# 8. Optional Future Stakeholders

The following may become stakeholders if future integrations are introduced.

## STK-10 — Payment Service Provider

Potential role:

- Process real transactions
- Provide payment status

Current MVP:

Real payment integration is not mandatory.

Therefore this is not currently a core operational stakeholder.

---

## STK-11 — Logistics / Courier Partner

Potential role:

- Deliver products
- Provide shipment updates

Current MVP:

No mandatory logistics API integration.

Therefore courier companies are not current core system actors.

---

## STK-12 — External Certification Organization

Potential future role:

- Verify product/craft authenticity
- Issue recognized certification

Current MVP:

Craft BD does not depend on an external certification authority.

Therefore this stakeholder remains future scope.

---

# 9. External Technical Dependencies

The following should not automatically be treated as product stakeholders.

## DEP-01 — GitHub

Purpose:

- Source control
- Issues
- Pull Requests
- Collaboration

Classification:

External Technical Dependency

---

## DEP-02 — Hosting Provider

Purpose:

- Application deployment

Classification:

External Technical Dependency

---

## DEP-03 — Database Provider

Purpose:

- Managed data storage if cloud database is used

Classification:

External Technical Dependency

---

## DEP-04 — File Storage Provider

Purpose:

- Store product/reference images

Classification:

External Technical Dependency

---

## DEP-05 — Email Provider

Purpose:

- Optional email notification

Classification:

External Technical Dependency

---

# 10. Stakeholder Summary Table

| ID | Stakeholder | Category | Interest | Influence | Priority |
|---|---|---|---|---|---|
| STK-01 | Customer | Primary | High | Medium | High |
| STK-02 | Artisan / Seller | Primary | High | High | Critical |
| STK-03 | Administrator | Secondary | High | High | High |
| STK-04 | Project Team | Secondary | Very High | Very High | Critical |
| STK-05 | Academic Supervisor | Secondary | High | Very High | Critical |
| STK-06 | Small Craft Business | Potential Primary | High | Medium | Medium |
| STK-07 | Social-Media Seller | Potential Primary | High | Medium | High |
| STK-08 | Regulatory Authorities | External | Medium | High | High |
| STK-09 | Consumer Protection Authority | External | Medium | Medium–High | Medium |
| STK-10 | Payment Provider | Future | Medium | Medium | Low for MVP |
| STK-11 | Logistics Partner | Future | Medium | Medium | Low for MVP |
| STK-12 | Certification Organization | Future | Medium | High | Low for MVP |

---

# 11. Core Stakeholder Set

For the current MVP, the most important stakeholders are:

```text
Customer
   +
Artisan / Seller
   +
Administrator
   +
Project Team
   +
Academic Supervisor
```

The strongest product-requirement input should come primarily from:

```text
Customer
   +
Artisan / Seller
```

because they are the primary value recipients.

---

# 12. Stakeholder vs System Actor

Not every stakeholder becomes a UML actor.

For example:

Academic Supervisor  
→ Stakeholder  
→ Not necessarily a system actor

Regulatory Authority  
→ Stakeholder  
→ Not necessarily a system actor

Customer  
→ Stakeholder  
→ System Actor

Artisan  
→ Stakeholder  
→ System Actor

Administrator  
→ Stakeholder  
→ System Actor

This distinction will be important during UML modeling.

---

# 13. Stakeholder vs External Dependency

Example:

Payment Gateway

If real payment is added:

Craft BD  
→ Sends transaction request  
→ Payment Provider

The provider may influence implementation, but it does not necessarily represent a normal end-user stakeholder.

Similarly:

Hosting Provider  
Database Provider  
GitHub

are infrastructure dependencies, not core product users.

---

# 14. Requirement Ownership

Initial mapping:

## Customer Requirements

Primary source:

STK-01

Examples:

- Product discovery
- Cart
- Order
- Custom request
- Review
- Status tracking

---

## Artisan Requirements

Primary source:

STK-02 / STK-07

Examples:

- Artisan profile
- Product management
- Custom-request management
- Quotation
- Status updates

---

## Administration Requirements

Primary source:

STK-03

Examples:

- User management
- Category management
- Moderation

---

## Technical Requirements

Primary source:

STK-04

Examples:

- Architecture
- Security
- Database
- Deployment
- Testing

---

## Academic Requirements

Primary source:

STK-05

Examples:

- UML
- SRS
- Software process
- Complexity analysis
- Testing evidence
- Cost estimation

---

# 15. Current Stakeholder Risk

The biggest stakeholder-analysis risk is:

> Product requirements may be influenced more by the project team than by actual customers and artisans.

Mitigation:

Primary research  
→ Validate Needs  
→ Revise Requirements  
→ Record Evidence

The team should avoid assuming that a technically interesting feature is automatically valuable to users.

---

# 16. Stakeholder Register Decision

The current stakeholder structure is suitable for continuing Phase 03.

However:

- Customer needs remain partially validated
- Artisan needs remain partially validated
- Custom-order assumptions remain open
- Future external actors should not be added to the MVP without scope review

---

## Document Status

**Phase:** 03 — Stakeholder & User Analysis  
**Document:** Stakeholder Register  
**Status:** Provisional v0.1  
**Primary Research Dependency:** Open  
**Next Step:** Stakeholder Power–Interest Analysis
