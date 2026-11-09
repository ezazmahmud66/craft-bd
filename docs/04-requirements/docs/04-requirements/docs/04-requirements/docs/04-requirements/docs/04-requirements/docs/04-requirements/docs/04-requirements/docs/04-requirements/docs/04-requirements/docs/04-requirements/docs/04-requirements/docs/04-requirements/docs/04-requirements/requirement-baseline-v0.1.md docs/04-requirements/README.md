# Craft BD — Requirement Baseline v0.1

## 1. Purpose

This document consolidates the Phase 04 requirement analysis for Craft BD into the first controlled requirement baseline.

The baseline establishes the current:

- Functional scope
- Business rules
- Quality requirements
- Security and privacy requirements
- Data requirements
- Project constraints
- External integration boundaries
- Requirement priorities
- Dependencies
- Traceability direction
- Change-control policy

This document should be treated as the primary Phase 04 requirement summary.

---

# 2. Baseline Version

**Baseline:** v0.1  
**Phase:** 04 — Requirement Finalization  
**Status:** Controlled Draft Baseline  
**Primary User Validation:** Pending

This baseline contains both:

### Controlled Requirements

Requirements sufficiently defined for further analysis and design.

### Provisional Requirements

Requirements that are technically defined but still depend on primary customer or artisan research.

---

# 3. Product Requirement Direction

Craft BD is currently defined as a digital platform supporting:

- Bangladeshi handicraft discovery
- Artisan identity and profile information
- Product information
- Standard purchasing workflow
- Structured custom-order workflow
- Craft/cultural context
- Product-record traceability
- Platform governance

The project shall not be positioned merely as a generic handicraft e-commerce website.

---

# 4. Primary System Actors

The current system actors are:

## Customer

Primary capabilities include:

- Browse products
- Search/filter products
- View artisan information
- Place standard orders
- Submit custom requests
- Review quotations
- Track orders
- Submit eligible reviews

---

## Artisan / Seller

Primary capabilities include:

- Maintain artisan profile
- Manage owned products
- Review assigned custom requests
- Create quotations
- Manage approved custom-order progress

---

## Administrator

Primary responsibilities include:

- User governance
- Category management
- Content moderation
- Exceptional platform operations
- Conditional verification/certificate management

Administration follows the principle:

**Admin by Exception**

rather than requiring administrator approval for every normal workflow.

---

# 5. Core Functional Modules

The current functional requirement modules are:

| Module | Code |
|---|---|
| Authentication | AUTH |
| User/Profile | USER |
| Artisan | ART |
| Product | PROD |
| Discovery | DISC |
| Cart | CART |
| Standard Order | ORDER |
| Custom Order | CUSTOM |
| Review | REV |
| Craft Context | CRAFT |
| Verification | VERIFY |
| Certificate | CERT |
| Notification | NOTIF |
| Administration | ADMIN |

---

# 6. Functional Requirement Baseline

## Core MVP

The current core functional baseline includes:

### Identity

- Registration
- Login
- Logout
- Role recognition

### Artisan

- Artisan profile
- Artisan public information
- Artisan profile management
- Artisan-product relationship

### Product

- Product creation
- Product editing
- Product deactivation
- Price
- Stock
- Product images
- Categories
- Product description

### Discovery

- Browse products
- Product details
- Category browsing
- Search

### Standard Commerce

- Cart
- Checkout
- Order creation
- Order items
- Price snapshot
- Delivery information
- Status tracking

### Administration

- User-status management
- Category management
- Core authorization and governance

---

# 7. Provisional Core Workflow

The structured custom-order workflow is currently classified as:

**Provisional Must Have**

because it represents the strongest current product-differentiation hypothesis but still requires primary user validation.

Current workflow:

```text
Customer
   ↓
Custom Request
   ↓
Artisan Review
   ↓
Quotation
   ↓
Customer Approval
   ↓
Production
   ↓
Status Tracking
   ↓
Completion
```

Important rule:

```text
Request
≠
Confirmed Production Order
```

Production must not begin before approved quotation acceptance.

---

# 8. Standard Order Workflow

The current standard-order model is:

```text
Product
   ↓
Cart
   ↓
Checkout
   ↓
Order Confirmation
   ↓
Simulated Payment
   ↓
Order Status
   ↓
Delivery
   ↓
Eligible Review
```

Real payment processing is not required for the academic MVP.

---

# 9. Business Rule Baseline

Business rules are maintained independently from functional requirements.

Examples include:

- Artisan may modify only owned products.
- Orders belong to one customer.
- Historical order prices must remain stable.
- Custom production requires quotation approval.
- Only request owners may approve quotations.
- Invalid workflow transitions must be rejected.
- Review submission requires approved eligibility.
- QR records do not guarantee physical authenticity.
- Admin actions require authorization.

Business-rule identifiers use:

`BR-MODULE-NNN`

---

# 10. Non-Functional Requirement Baseline

Quality requirements are defined for:

- Performance
- Usability
- Reliability
- Maintainability
- Compatibility
- Availability
- Scalability
- Data quality
- Error handling
- Practical accessibility

The project shall avoid unsupported statements such as:

- Highly scalable
- Extremely fast
- Perfectly secure
- 99.99% available

unless those claims are measurable and demonstrated.

---

# 11. Performance Direction

Current academic targets include:

- Common server-dependent interactions should generally complete within acceptable demonstration-time limits.
- Product search should remain responsive for the expected MVP dataset.
- Performance must be verified through testing rather than marketing claims.

Exact targets remain subject to final implementation and test-environment review.

---

# 12. Usability Direction

Core workflows should:

- Work on desktop and mobile browser layouts
- Provide clear validation messages
- Provide visible action feedback
- Avoid unnecessary artisan administration effort
- Be tested with representative task scenarios

---

# 13. Reliability Direction

The system shall preserve:

- Confirmed order records
- Custom-order workflow integrity
- Valid entity relationships
- Historical transaction prices

Invalid business-state transitions shall be rejected.

---

# 14. Maintainability Direction

The implementation should provide:

- Modular organization
- Git-based change history
- Externalized environment configuration
- Setup documentation
- Automated testing support
- Consistent naming and coding conventions

---

# 15. Security Baseline

Security is a mandatory cross-cutting requirement.

Protected workflows follow:

```text
Authenticate
      ↓
Authorize
      ↓
Validate Ownership
      ↓
Validate Business Rule
      ↓
Validate Input
      ↓
Perform Action
```

Core security areas include:

- Password protection
- Authentication
- Role authorization
- Resource ownership
- Input validation
- File-upload validation
- Secret management
- Safe logging
- HTTPS
- Administrative authorization

---

# 16. Security Boundary

Frontend restrictions are not sufficient security controls.

Example:

```text
Hide Edit Button
```

does not replace:

```text
Backend Ownership Validation
```

The authoritative backend must enforce protected business actions.

---

# 17. Privacy Baseline

Privacy requirements include:

- Data minimization
- Public/private data separation
- Delivery-information protection
- Custom-order privacy
- Reference-image privacy
- Public artisan-field controls
- Synthetic public demo data
- Research participant privacy

The project should not collect unnecessary sensitive information.

---

# 18. Payment Privacy Boundary

The academic MVP shall not require or store actual:

- Card PIN
- Banking password
- Mobile financial service PIN

Simulated payment exists to demonstrate system workflow rather than process real funds.

---

# 19. Data Requirement Baseline

Current core data areas include:

- User
- Customer profile
- Artisan profile
- Category
- Product
- Product image
- Cart
- Cart item
- Order
- Order item
- Custom request
- Quotation
- Review
- Notification
- Verification record
- Certificate record

Verification and certificate entities remain conditional.

The final database schema will be created during the database-design phase.

---

# 20. Current Entity Direction

The current high-level relationship direction includes:

```text
User
 ├── Customer
 └── Artisan
        ↓
      Product
```

```text
Customer
   ↓
Cart
   ↓
Order
   ↓
OrderItem
```

```text
Customer
   +
Artisan
   ↓
CustomRequest
   ↓
Quotation
   ↓
Custom Workflow
```

This is not yet the formal ERD.

---

# 21. Constraint Baseline

Current project constraints include:

- Responsive web application
- No mandatory native mobile application
- Small-team-manageable architecture
- No required microservices
- Low-cost academic infrastructure
- Controlled academic schedule
- Simulated payment permitted
- Real financial credentials excluded
- No blockchain dependency
- No live-chat dependency
- No courier API dependency
- No government-certification claim
- No automatic physical-authenticity claim

---

# 22. Integration Baseline

## Required Infrastructure Capability

- Database
- Deployment environment
- File/image storage where required

## Optional

- Email notifications

## Deferred

- Real payment gateway
- Courier integration
- Government/external certification integration
- Advanced analytics integration

The core application should avoid unnecessary external-service dependence.

---

# 23. QR Verification Boundary

Craft BD may provide:

```text
QR
↓
Craft BD Verification Record
```

This means:

> A corresponding Craft BD platform record exists.

It does not automatically mean:

> The physical product has been independently authenticated.

This distinction must remain explicit in UI, documentation, and testing.

---

# 24. Certificate Boundary

If implemented, Craft BD may provide:

**Platform Certificate Record**

It shall not automatically be described as:

- Government certificate
- Legal authenticity certificate
- Independent external certification

without supporting authority.

---

# 25. Current MoSCoW Baseline

## Must

- Authentication
- Role authorization
- Artisan profile
- Product management
- Product discovery
- Cart
- Checkout
- Standard ordering
- Order tracking
- Core administration
- Security
- Privacy
- Validation
- Testing
- Deployment

## Provisional Must

- Structured custom-order workflow

## Should

- Customer profile
- Product filters
- Basic craft context
- Simulated payment
- Reviews
- Notifications
- Moderation
- QR-linked product records

## Could

- Wishlist
- Product journey
- Platform certificate
- Simple future recommendation

## Deferred

- Real payment
- Advanced AI recommendation
- Gift recommendation
- Events/workshops
- Live chat
- Blockchain
- Courier API
- Native application
- Advanced analytics

---

# 26. Requirement Dependency Baseline

Core dependency direction:

```text
Authentication
      ↓
Authorization
      ↓
Ownership
      ↓
Business Workflow
```

Product dependency:

```text
Artisan
   ↓
Product
   ↓
Discovery
   ↓
Commerce
```

Custom-order dependency:

```text
Customer + Artisan
       ↓
Custom Request
       ↓
Quotation
       ↓
Approval
       ↓
Production
```

---

# 27. Requirement Conflict Decisions

Key decisions include:

### Custom Flexibility vs Artisan Simplicity

Use structured required fields plus optional notes/reference images.

### Information Richness vs Data Entry Burden

Separate essential fields from optional enrichment.

### Customer Speed vs Production Control

Require quotation and approval before production.

### Status Visibility vs Artisan Burden

Use a limited meaningful status model.

### Admin Control vs Usability

Use admin by exception.

### Trust vs Authenticity Claims

Use transparent platform-record terminology.

### Feature Quantity vs Quality

Prefer fewer fully engineered features.

---

# 28. Traceability Baseline

The project now supports:

```text
Stakeholder
→ Pain Point / Goal
→ Requirement
→ Business / Security Rule
→ Acceptance Criteria
→ Future Use Case
→ Future Test Case
```

Current status:

| Mapping | Status |
|---|---|
| Stakeholder → Requirement | Established |
| Pain Point → Requirement | Established for core flows |
| Requirement → Business Rule | Established |
| Requirement → Security Rule | Established for protected workflows |
| Requirement → Acceptance Criteria | Established |
| Requirement → Use Case | Pending |
| Requirement → UML | Pending |
| Requirement → Architecture | Pending |
| Requirement → Code | Pending |
| Requirement → Tests | Planned |
| Requirement → UAT | Pending |

---

# 29. Requirement ID Standard

Craft BD uses:

`TYPE-MODULE-NNN`

Examples:

```text
FR-PROD-001
FR-CUSTOM-001
BR-CUSTOM-001
NFR-USE-001
SR-OWN-001
PR-DATA-001
DR-ORDER-001
IR-PAY-001
CR-SCOPE-001
```

Once an approved baseline uses an ID, that ID should not later be reused for unrelated behavior.

---

# 30. Acceptance Criteria Principle

Important requirements should define observable results.

Preferred pattern:

```text
Given
<starting state>

When
<action>

Then
<expected system behavior>
```

Both positive and negative paths should be tested where meaningful.

---

# 31. Change-Control Baseline

After Phase 04:

```text
New Idea
   ↓
Change Request
   ↓
Impact Analysis
   ↓
Approve / Reject / Defer
   ↓
Update Requirements
   ↓
Update Traceability
```

Material requirement changes shall not be introduced silently.

---

# 32. Change Request Identifier

Requirement change requests use:

```text
CRQ-NNN
```

Example:

`CRQ-001`

This remains separate from:

`CR-*`

which represents constraint requirements.

---

# 33. Baseline Version Direction

Recommended future baseline progression:

```text
v0.1
Controlled requirement baseline

↓ Primary research

v0.2
Research-informed requirement revision

↓ Design / validation

v1.0
Approved implementation baseline
```

This progression may be adjusted if project evidence requires it.

---

# 34. Primary Research Dependency

The largest unresolved product risk remains:

> Whether customers and artisans gain enough value from the structured custom-order workflow compared with existing informal communication methods.

Therefore several requirements remain:

`PROVISIONAL`

Primary research may result in:

```text
Approve
Rewrite
Reduce
Defer
Reject
```

Existing documentation effort shall not override evidence.

---

# 35. Phase 04 Deliverables

The requirement-finalization phase currently includes:

- Existing requirement audit
- Requirement ID standard
- Functional requirements — identity/product/discovery
- Functional requirements — commerce
- Functional requirements — custom order
- Functional requirements — supporting modules
- Business-rule register
- Non-functional requirements
- Security/privacy requirements
- Data/constraint/integration requirements
- Traceability matrix
- Priority/dependency/conflict review
- Change-control policy
- Consolidated Requirement Baseline v0.1

---

# 36. Quality Review

The requirement set now provides:

- Unique IDs
- Actor/source identification
- Clear functional boundaries
- MoSCoW priority
- Evidence status
- Business rules
- Security constraints
- Acceptance criteria
- Dependency mapping
- Traceability
- Change control

This is substantially stronger than the project's original unstructured feature-oriented requirement analysis.

---

# 37. Known Remaining Gaps

The following remain intentionally unresolved:

- Real primary customer interviews
- Real artisan/seller interviews
- Final custom-order validation
- Final craft-context validation
- Final QR-value validation
- Final technology stack
- Formal SRS
- Use-case specifications
- UML diagrams
- Architecture
- Database schema
- API contract
- Final test cases

These belong to later phases or pending research.

---

# 38. Phase 04 Baseline Decision

Craft BD Requirement Baseline v0.1 is suitable to proceed into detailed SRS and system-analysis work with one important condition:

> Provisional research-dependent requirements must remain visibly provisional until primary research supports their approval.

Therefore:

```text
Engineering Definition
        ✅ Established

Requirement Structure
        ✅ Established

Scope Control
        ✅ Established

Traceability
        ✅ Established

Primary User Validation
        🟡 Pending
```

---

## Document Status

**Project:** Craft BD  
**Phase:** 04 — Requirement Finalization  
**Baseline:** v0.1  
**Status:** Controlled Draft Baseline  
**Primary Research Dependency:** Open  
**Next Major Phase:** SRS Preparation
