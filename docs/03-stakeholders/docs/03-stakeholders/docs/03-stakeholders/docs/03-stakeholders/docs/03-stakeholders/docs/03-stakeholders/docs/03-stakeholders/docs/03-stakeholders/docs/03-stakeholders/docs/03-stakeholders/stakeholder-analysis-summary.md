# Craft BD — Consolidated Stakeholder & User Analysis

## 1. Purpose

This document consolidates the major findings from Phase 03 — Stakeholder & User Analysis.

The purpose of this phase is to establish a clear understanding of:

- Who influences Craft BD
- Who directly uses Craft BD
- What different stakeholders need
- Which user segments should be prioritized
- Where stakeholder conflicts may occur
- Which requirement areas originate from which stakeholders
- Which assumptions still require primary validation

The analysis remains provisional because real customer and artisan interviews are still pending.

---

# 2. Core Stakeholder Structure

The current stakeholder structure contains:

## Primary Product Stakeholders

- Customer
- Artisan / Craft Seller

These stakeholders are the main recipients of product value.

---

## Operational Stakeholder

- Administrator

The administrator supports governance, moderation, and exceptional operational tasks.

---

## Project Stakeholders

- Project Development Team
- Academic Supervisor / Faculty

These stakeholders strongly influence project quality, scope, implementation, and academic evaluation.

---

## External / Regulatory Stakeholders

- Relevant regulatory authorities
- Consumer-protection authorities

These influence privacy, security, commerce, and compliance constraints.

---

## Future / Integration-Dependent Stakeholders

- Payment Service Provider
- Logistics / Courier Provider
- External Certification Organization

These are not current core MVP actors.

---

# 3. Stakeholder vs System Actor

Not every stakeholder becomes a system actor.

Current likely application actors are:

```text
Customer
Artisan
Administrator
```

Other stakeholders such as:

```text
Faculty
Regulatory Authorities
Project Team
```

influence the project but do not necessarily interact directly with the Craft BD application.

---

# 4. External Technical Dependencies

The following are primarily technical dependencies rather than product stakeholders:

- GitHub
- Hosting provider
- Database provider
- File-storage provider
- Email provider

Future integrations may introduce additional dependencies.

---

# 5. Stakeholder Priority

## Manage Closely

- Artisan / Seller
- Administrator
- Project Team
- Academic Supervisor

## Keep Informed

- Customer
- Social-Media-Based Craft Seller
- Small Craft Business Owner

## Keep Satisfied

- Regulatory authorities
- Consumer-protection stakeholders
- Future certification authority where relevant

## Monitor

- Payment provider
- Logistics provider

---

# 6. Important Stakeholder Interpretation

Power and product importance are not the same.

Example:

```text
Faculty
→ Very High Project Influence
→ Not Primary Product User
```

while:

```text
Customer
→ Medium Formal Project Power
→ Very High Product Importance
```

Therefore product requirements should not be prioritized using stakeholder power alone.

---

# 7. Current Customer Segments

The current customer segmentation contains:

## C1 — Cultural Craft Explorer

Interested in:

- Product discovery
- Artisan identity
- Craft origin
- Materials
- Cultural context

Priority:

High

Validation:

Partially supported.

---

## C2 — Custom Craft Buyer

Interested in:

- Structured customization
- Reference images
- Quotations
- Approval
- Order progress

Priority:

Very High

Validation:

High-priority hypothesis.

---

## C3 — Gift Buyer

Interested in:

- Occasion-based discovery
- Budget
- Gift selection

Priority:

Low / Future.

---

## C4 — Trust-Conscious Buyer

Interested in:

- Seller information
- Reviews
- Detailed product information
- Platform records

Priority:

Medium.

---

# 8. Current Artisan Segments

## A1 — Individual Artisan

Primary needs may include:

- Simple profile
- Product management
- Custom-request handling
- Quotation
- Status update

Priority:

Very High.

---

## A2 — Small Craft Business / Workshop

May require:

- Product management
- Order organization
- Business identity

Priority:

Medium.

---

## A3 — Social-Media-Based Craft Seller

Potential needs include:

- Centralized custom requests
- Structured requirements
- Quotation
- Approval records
- Status management

Priority:

Very High.

This is a particularly important research segment because Craft BD must demonstrate meaningful improvement over existing Messenger-based workflows.

---

# 9. Priority User Pairing

The strongest current provisional product relationship is:

```text
Custom Craft Buyer
        ↕
Structured Custom Order Workflow
        ↕
Individual Artisan /
Social-Media Seller
```

Secondary experience:

```text
Cultural Craft Explorer
        ↓
Product + Artisan + Craft Context
```

---

# 10. Provisional Personas

Current synthetic personas include:

- P01 — Custom Craft Buyer
- P02 — Cultural Craft Explorer
- P03 — Individual Artisan
- P04 — Social-Media-Based Seller

These personas are design and research tools.

They must not be represented as real interview findings.

---

# 11. High-Priority User Goals

## Customer

Customers may need to:

- Discover products
- Understand product information
- Understand artisan information
- Purchase standard products
- Communicate customization requirements
- Review quotation
- Approve custom order
- Track progress
- Provide review

---

## Artisan

Artisans may need to:

- Showcase identity
- Manage products
- Receive clear customer requirements
- Provide quotation
- Receive approval
- Manage order progress
- Reduce repetitive communication

---

# 12. High-Priority Pain Points

The current strongest provisional pain points are:

## PP-01 — Custom Requirement Ambiguity

Customer may struggle to explain requirements.

Artisan may receive incomplete requirements.

---

## PP-02 — Informal Quotation / Approval

Customer and artisan may not have a clear record of agreed terms.

---

## PP-03 — Status Communication

Customer may repeatedly request updates.

Artisan may need to manually respond repeatedly.

---

## PP-04 — Product Information Fragmentation

Product, artisan, and craft information may be spread across different locations.

---

## PP-05 — Adoption Friction

Artisans may reject Craft BD if it requires more effort than their current workflow.

---

# 13. Current Product Opportunity

The current strongest two-sided opportunity is:

```text
Customer
Needs clearer requirements
        ↓
Structured Request
        ↑
Artisan
Needs complete specifications
```

followed by:

```text
Customer
Needs clear agreement
        ↓
Quotation + Approval
        ↑
Artisan
Needs confirmed order
```

and:

```text
Customer
Needs progress visibility
        ↓
Status Workflow
        ↑
Artisan
Needs fewer repeated questions
```

These remain hypotheses until primary research confirms them.

---

# 14. Customer Journey Baseline

The customer journey currently follows:

```text
Discover
→ Evaluate
→ Select
→ Order / Customize
→ Confirm
→ Track
→ Receive
→ Review
```

Two important customer paths exist.

## Standard Product

```text
Product
→ Cart
→ Checkout
→ Order
→ Delivery
→ Review
```

## Custom Product

```text
Product / Idea
→ Custom Request
→ Artisan Review
→ Quotation
→ Approval
→ Production
→ Delivery
→ Review
```

---

# 15. Artisan Journey Baseline

The artisan journey currently follows:

```text
Join
→ Create Profile
→ Add Products
→ Receive Request
→ Review
→ Quote
→ Receive Approval
→ Produce
→ Update Status
→ Complete
```

The main UX condition is:

> Craft BD should reduce organizational difficulty rather than increase administrative work.

---

# 16. Core Responsibility Model

## Customer

```text
Discover
Order
Customize
Approve
Track
Review
```

## Artisan

```text
Present
Manage Product
Review Request
Quote
Produce
Update
```

## Administrator

```text
Govern
Moderate
Manage Exceptions
```

---

# 17. Access-Control Baseline

Future authorization should consider:

```text
Authentication
        ↓
Role
        ↓
Ownership
        ↓
Business Rule
        ↓
Allow / Deny
```

Examples:

- Customer A cannot access Customer B's private order
- Artisan A cannot edit Artisan B's product
- Artisan cannot approve customer quotation
- Customer cannot access admin operations

---

# 18. Major Stakeholder Conflicts

Important identified conflicts include:

## Customer Flexibility vs Artisan Simplicity

Resolution:

Structured required information + optional notes.

---

## Detailed Product Information vs Fast Product Entry

Resolution:

Required essential fields + optional enrichment.

---

## Customer Progress Visibility vs Artisan Administrative Work

Resolution:

Small number of meaningful statuses.

---

## Admin Control vs Workflow Speed

Resolution:

Admin by exception rather than approval of every action.

---

## Academic Feature Richness vs Feasibility

Resolution:

Prioritize engineering depth over feature count.

---

## Faculty / Team Preference vs User Evidence

Resolution:

Major suggestions require evidence and impact analysis before scope inclusion.

---

# 19. Current Requirement Sources

## Customer

Primary source for:

- Product discovery
- Product information
- Cart
- Checkout
- Ordering
- Custom requests
- Quote approval
- Tracking
- Reviews

---

## Artisan

Primary source for:

- Artisan profile
- Product management
- Request review
- Quotation
- Production/status management

---

## Administrator

Primary source for:

- Governance
- Moderation
- User/category administration

---

## Project Team

Primary source for:

- Architecture
- Security
- Testing
- Database integrity
- Deployment
- Technical constraints

---

## Academic Supervisor

Primary source for:

- Software Engineering deliverables
- SRS
- UML
- Testing evidence
- Cost estimation
- Complexity analysis
- Documentation quality

---

## Regulatory Context

Primary source for:

- Privacy constraints
- Security constraints
- Data-handling rules
- Consumer-facing compliance considerations

---

# 20. Requirement Traceability Direction

The project should later support:

```text
Stakeholder
↓
Goal / Pain Point
↓
Requirement
↓
Use Case
↓
Design
↓
Implementation
↓
Test Case
```

This will form the future Requirement Traceability Matrix.

---

# 21. Requirements That Remain Provisional

The following requirement areas should not yet be treated as permanently validated:

- Structured custom-order importance
- Artisan preference for structured custom-order management
- Craft-story importance
- Product-journey value
- QR-linked product-record value
- Digital certificate value
- Personalized recommendation requirement

---

# 22. Stronger Requirement Areas

The following areas can continue into detailed requirement analysis with relatively strong justification:

- Authentication
- Authorization
- Product management
- Product discovery
- Standard order workflow
- Data protection
- Security
- Testing
- Deployment
- Academic documentation

This does not mean their detailed requirements are already finalized.

---

# 23. Main Phase 03 Risk

The largest stakeholder-analysis risk remains:

> The project team may create detailed assumptions about customers and artisans and later treat those assumptions as real evidence.

Mitigation:

```text
Provisional Model
      ↓
Real Interviews
      ↓
Compare
      ↓
Confirm / Modify / Reject
```

---

# 24. Phase 03 Decision

The current stakeholder and user-analysis baseline is sufficiently structured to support:

- Requirement Finalization
- Use Case Analysis
- UML
- UI/UX
- Security
- Access Control
- Testing Planning

However:

**Primary customer and artisan research remains an open dependency.**

---

# 25. Current Product Model

The current product relationship can be summarized as:

```text
CUSTOMER
│
├── Discover
├── Understand
├── Order
├── Customize
├── Approve
└── Track
        ↕
      CRAFT BD
        ↕
ARTISAN
│
├── Present
├── Manage
├── Review
├── Quote
├── Produce
└── Update
```

with:

```text
ADMIN
↓
Governance + Moderation + Exceptions
```

---

## Final Phase 03 Assessment

**Stakeholder Identification:** COMPLETE  
**Stakeholder Classification:** COMPLETE  
**User Segmentation:** PROVISIONAL COMPLETE  
**Persona Baseline:** PROVISIONAL COMPLETE  
**Journey Baseline:** PROVISIONAL COMPLETE  
**Role / Responsibility Mapping:** COMPLETE  
**Conflict Analysis:** COMPLETE  
**Requirement Source Mapping:** COMPLETE  
**Primary User Validation:** PENDING

---

## Document Status

**Phase:** 03 — Stakeholder & User Analysis  
**Document:** Consolidated Stakeholder Review  
**Version:** 0.1  
**Status:** PROVISIONAL  
**Primary Research Dependency:** OPEN
