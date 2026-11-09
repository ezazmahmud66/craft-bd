# Craft BD — Stakeholder to Requirement Source Mapping

## 1. Purpose

This document maps Craft BD stakeholder groups to the requirement areas they influence.

The objective is to ensure that future requirements can be traced back to:

- User needs
- Stakeholder expectations
- Business rules
- Academic constraints
- Security requirements
- Regulatory constraints

This document forms the foundation for the future Requirement Traceability Matrix.

---

# 2. Traceability Principle

A requirement should not exist without a justified source.

Recommended traceability chain:

```text
Stakeholder
    ↓
Goal / Need
    ↓
Requirement
    ↓
Design
    ↓
Implementation
    ↓
Test
```

Example:

```text
Customer
↓
Needs order-status visibility
↓
FR-XX: System shall display current order status
↓
Order Tracking UI + API
↓
Implemented Feature
↓
System Test
```

---

# 3. Requirement Source Types

Craft BD requirements may originate from different source categories.

## SRC-USER

Direct user needs.

Examples:

- Customer
- Artisan

## SRC-OPS

Operational needs.

Example:

- Administrator

## SRC-BUSINESS

Product and workflow rules.

Examples:

- Quote approval before production
- Review eligibility

## SRC-TECH

Technical and engineering requirements.

Examples:

- Authentication
- Architecture
- Database constraints
- Deployment

## SRC-SECURITY

Security and privacy requirements.

Examples:

- Authorization
- Password protection
- Ownership checks

## SRC-LEGAL

Legal and compliance constraints.

## SRC-ACADEMIC

Course and project-evaluation requirements.

---

# 4. Customer Requirement Sources

## Stakeholder

**STK-01 — Customer**

Customer is the primary source for requirements related to:

### Product Discovery

Potential requirements:

- Browse products
- Search products
- Filter products
- View categories
- View product details

Source type:

**SRC-USER**

---

## Product Information

Customer may require access to:

- Price
- Product description
- Materials
- Images
- Availability
- Artisan information
- Craft context

Source:

**STK-01**

Validation:

Partially supported.

---

## Standard Ordering

Customer is the source for:

- Cart
- Checkout
- Order creation
- Order history
- Order details
- Order tracking

Source type:

**SRC-USER + SRC-BUSINESS**

---

## Custom Ordering

Potential customer requirements include:

- Submit custom request
- Specify size
- Specify color
- Specify material
- Specify quantity
- Upload reference image
- Provide instructions

Source:

**STK-01 — Customer**

Validation:

**High-priority hypothesis**

---

## Quotation Review

Customer may require:

- View quoted price
- View estimated completion date
- View artisan notes
- Approve quotation
- Reject quotation

Source:

**STK-01**

Business-rule support:

**SRC-BUSINESS**

---

## Reviews

Customer is the primary source for:

- Submit rating
- Submit review
- View reviews

However:

Review eligibility rules originate from both:

```text
Customer Need
+
Platform Trust Rule
```

---

# 5. Artisan Requirement Sources

## Stakeholder

**STK-02 — Artisan / Seller**

Artisan is the primary source for seller-side requirements.

---

## Artisan Profile

Potential requirements include:

- Maintain profile
- Add biography
- Add expertise
- Add experience
- Add location
- Display products

Source:

**STK-02**

---

## Product Management

Artisan requires:

- Add product
- Edit own product
- Manage stock
- Manage price
- Upload product images
- Deactivate product

Source:

**STK-02**

---

## Custom Request Management

Artisan may require:

- View assigned custom requests
- Review structured requirements
- View reference images
- Accept request for quotation
- Reject unsuitable request

Source:

**STK-02**

Validation:

High-priority hypothesis.

---

## Quotation

Artisan may require:

- Create quotation
- Specify price
- Specify completion estimate
- Add quotation notes

Source:

**STK-02**

---

## Production Status

Artisan may require:

- Mark order as in production
- Mark order ready
- Mark order shipped
- Complete relevant workflow actions

Source:

**STK-02**

Business-rule constraints also apply.

---

# 6. Administrator Requirement Sources

## Stakeholder

**STK-03 — Administrator**

Administrator requirements primarily concern platform governance.

Potential requirements include:

- Manage users
- Manage categories
- Moderate content
- Moderate reviews
- Manage exceptional platform actions
- Manage verification/certificate records where approved

Source type:

**SRC-OPS**

---

# 7. Administrator Boundary

Not every system action should originate from administrator needs.

Example:

```text
Customer Order
→ Customer + Artisan Workflow
```

should not automatically become:

```text
Customer Order
→ Admin Approval
```

unless a real governance requirement exists.

Therefore admin requirements must remain controlled.

---

# 8. Development Team Requirement Sources

## Stakeholder

**STK-04 — Project Development Team**

The project team is a source of technical requirements, not primary business-user needs.

Examples:

- Maintainable architecture
- API structure
- Database integrity
- Error handling
- Testing
- Logging
- Deployment
- Environment configuration

Source type:

**SRC-TECH**

Important:

A developer preference should not be presented as a customer requirement.

---

# 9. Academic Supervisor Requirement Sources

## Stakeholder

**STK-05 — Academic Supervisor / Faculty**

Faculty is a source for academic and process requirements.

Examples:

- SRS
- UML diagrams
- Process model justification
- Complexity analysis
- Function Point / cost estimation
- Testing documentation
- Software Engineering methodology
- Final report

Source type:

**SRC-ACADEMIC**

These requirements influence the project deliverables but may not become Craft BD application features.

---

# 10. Regulatory Requirement Sources

## Stakeholder

**STK-08 — Regulatory Authorities**

Possible requirement areas include:

- Personal-data protection
- Cybersecurity
- Consumer-facing transaction practices

Source type:

**SRC-LEGAL**

These requirements normally become:

- Security requirements
- Privacy requirements
- Data-handling rules
- Operational constraints

rather than normal end-user features.

---

# 11. Consumer Protection Requirement Sources

## Stakeholder

**STK-09 — Consumer Protection Authorities**

Potential requirement implications include:

- Clear product information
- Transparent transaction information
- Seller information
- Appropriate customer support
- Accurate claims

Source type:

**SRC-LEGAL + SRC-BUSINESS**

---

# 12. Social-Media Seller as Requirement Source

## Stakeholder

**STK-07 — Social-Media-Based Craft Seller**

This segment is especially important for validating:

- Structured request management
- Quotation
- Order-status management
- Seller dashboard simplicity
- Mobile usability

Source:

**SRC-USER**

Validation:

Primary research pending.

---

# 13. Requirement Source Matrix

| Requirement Area | Primary Source | Secondary Source | Source Type |
|---|---|---|---|
| Registration/Login | Customer, Artisan | Project Team | USER + TECH |
| Role Authorization | Project Team | Admin | SECURITY + TECH |
| Product Catalog | Customer | Artisan | USER |
| Product Management | Artisan | Admin | USER + OPS |
| Search | Customer | — | USER |
| Filtering | Customer | — | USER |
| Artisan Profile | Customer, Artisan | — | USER |
| Craft Story | Customer | Project Team | USER / Provisional |
| Cart | Customer | — | USER |
| Checkout | Customer | Project Team | USER + BUSINESS |
| Order Management | Customer, Artisan | Admin | USER + BUSINESS |
| Custom Request | Customer | Artisan | USER |
| Structured Requirements | Customer, Artisan | — | USER |
| Quotation | Artisan | Customer | USER + BUSINESS |
| Quote Approval | Customer | Artisan | BUSINESS |
| Production Status | Artisan | Customer | USER + BUSINESS |
| Reviews | Customer | Admin | USER + OPS |
| Review Eligibility | Platform Rule | Customer | BUSINESS |
| QR Product Record | Customer | Admin | USER / Provisional |
| Digital Certificate | Admin | Customer | OPS / Provisional |
| File Upload | Customer, Artisan | Project Team | USER + SECURITY |
| Admin Management | Administrator | Project Team | OPS |
| Privacy | Regulatory / Users | Project Team | LEGAL + SECURITY |
| Security | Project Team | Users/Admin | SECURITY |
| Testing | Project Team / Faculty | — | TECH + ACADEMIC |
| Deployment | Project Team | Faculty | TECH + ACADEMIC |

---

# 14. Business Rule Sources

Some requirements do not come from one stakeholder alone.

They come from business logic.

Examples:

## BR-01

Production must not begin before quotation approval.

Sources:

```text
Customer Need
+
Artisan Need
+
Workflow Integrity
```

---

## BR-02

Only the request owner can approve a quotation.

Source:

**Security + Business Rule**

---

## BR-03

An artisan may edit only products they own.

Source:

**Security + Ownership Rule**

---

## BR-04

A customer should only review an eligible purchased product.

Source:

**Trust + Business Rule**

---

# 15. Security Requirement Sources

Security requirements may originate from:

- Customer privacy expectations
- Artisan ownership requirements
- Administrator privilege requirements
- Legal constraints
- Engineering standards

Example:

```text
Need:
Artisan A must not edit Artisan B's product

↓
Security Requirement:
System shall verify ownership before allowing product modification.
```

---

# 16. Requirement Evidence Levels

Each future requirement should also record its evidence strength.

Recommended values:

## Primary Validated

Supported by real user research.

## Secondary Supported

Supported by secondary research or credible proxy evidence.

## Derived

Required because of another validated requirement or business rule.

## Technical

Required for engineering/security operation.

## Academic

Required by course/project deliverables.

## Provisional

Still based mainly on assumptions.

---

# 17. Example Requirement Trace

## Example A — Search

```text
Stakeholder:
STK-01 Customer

Need:
Find suitable products efficiently

Requirement Area:
Product Search

Evidence:
Reasonable / secondary supported

Future Requirement:
FR-XX

Design:
Search UI + Product Query API

Testing:
Search returns matching products
```

---

# 18. Example Custom-Order Trace

```text
Stakeholders:
STK-01 Customer
STK-02 Artisan

Pain Point:
PP-01 Requirement ambiguity

Need:
Store customization requirements clearly

Potential Requirement:
System shall allow customers to submit
structured custom-product requirements.

Evidence:
Provisional

Future Requirement ID:
FR-XX

Implementation:
CustomOrder entity
+ API
+ Form

Test:
Submitted requirements are stored
and visible to assigned artisan.
```

---

# 19. Example Authorization Trace

```text
Stakeholder:
STK-02 Artisan

Need:
Manage own products safely

Security Need:
Prevent unauthorized modification

Requirement:
System shall prevent artisans from editing
products belonging to another artisan.

Source:
USER + SECURITY

Test:
Artisan A attempts to edit Artisan B's product
→ Access denied
```

---

# 20. Requirement Source Conflict

If two sources produce conflicting requirements:

```text
Requirement A
       ↕
Requirement B
```

the team should not silently choose one.

Use:

```text
Conflict
→ Evidence Review
→ Stakeholder Analysis
→ Impact Analysis
→ Decision
→ Documentation
```

Reference the Stakeholder Conflict Analysis where appropriate.

---

# 21. Requirement Source Priority

A practical priority model is:

```text
Validated User Need
        +
Security / Legal Requirement
        +
Core Business Rule
        ↓
Highest Requirement Importance
```

while:

```text
Developer Preference
or
Optional Feature Idea
```

should require additional justification.

---

# 22. Future Requirement Metadata

During requirement finalization, important requirements should ideally record:

- Requirement ID
- Requirement statement
- Stakeholder source
- Need / problem source
- Evidence status
- Priority
- Acceptance criteria
- Related business rule
- Related use case
- Test reference

Example:

| Field | Example |
|---|---|
| ID | FR-XX |
| Requirement | Submit custom request |
| Source | STK-01, STK-02 |
| Problem | PP-01 |
| Evidence | Provisional |
| Priority | Must |
| Use Case | UC-XX |
| Test | TC-XX |

---

# 23. Future Traceability Model

The project should eventually support:

```text
Stakeholder
   ↓
Need / Pain Point
   ↓
Requirement
   ↓
Use Case
   ↓
Design Component
   ↓
Code
   ↓
Test Case
```

This will provide strong academic and portfolio evidence.

---

# 24. Requirements That Remain Provisional

The following areas should retain provisional evidence status until primary research is completed:

- Structured custom-order importance
- Artisan preference for structured request management
- Craft-story importance
- Product-journey value
- QR product-record value
- Digital certificate value
- Personalized recommendation need

---

# 25. Requirement Sources That Are Already Strong

The following areas are sufficiently strong to continue planning:

- Authentication
- Authorization
- Product management
- Product discovery
- Basic commerce workflow
- Data protection
- Testing
- Deployment
- Academic documentation

Their detailed requirements still require formal review.

---

# 26. Traceability Risk

A major project risk is:

> Requirements may be written without remembering why they were added.

This causes:

- Feature creep
- Contradictory requirements
- Difficult prioritization
- Weak testing
- Poor academic justification

Mitigation:

Every important requirement should have a traceable source.

---

# 27. Current Mapping Decision

The strongest current requirement-source relationships are:

```text
CUSTOMER
→ Discovery
→ Ordering
→ Custom Request
→ Approval
→ Tracking

ARTISAN
→ Profile
→ Product Management
→ Request Review
→ Quotation
→ Status

ADMIN
→ Governance
→ Moderation

PROJECT TEAM
→ Technical / Security Requirements

FACULTY
→ Academic Deliverables

REGULATORY CONTEXT
→ Privacy / Legal Constraints
```

---

## Document Status

**Phase:** 03 — Stakeholder & User Analysis  
**Document:** Stakeholder → Requirement Source Mapping  
**Status:** Provisional v0.1  
**Primary Research Dependency:** Open  
**Future Output:** Requirement Traceability Matrix  
**Next Step:** Phase 03 Consolidated Stakeholder Review
