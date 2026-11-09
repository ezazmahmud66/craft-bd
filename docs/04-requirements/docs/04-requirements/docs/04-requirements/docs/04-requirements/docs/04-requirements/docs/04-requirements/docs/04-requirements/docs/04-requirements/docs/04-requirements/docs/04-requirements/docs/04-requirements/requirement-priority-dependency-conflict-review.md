# Craft BD — Requirement Priority, Dependency & Conflict Review

## 1. Purpose

This document reviews Craft BD requirements according to:

- MVP priority
- Requirement dependencies
- Conflicting requirements
- Scope risk
- Validation status
- Implementation sequence

The goal is to prevent optional features from competing with core workflows and to identify requirements that cannot be implemented independently.

---

# 2. Priority Standard

Craft BD uses MoSCoW prioritization:

| Priority | Meaning |
|---|---|
| Must | Required for MVP success |
| Should | Important but MVP can still operate without it |
| Could | Implement only when time and quality permit |
| Won't / Deferred | Excluded from current MVP |

A high number of `Must` requirements reduces the usefulness of prioritization.

Therefore only genuinely essential capabilities should remain `Must`.

---

# 3. MVP Priority Principles

Requirements are prioritized using:

1. Core user workflow value
2. Security and privacy necessity
3. Data integrity
4. Academic Software Engineering value
5. Dependency on other requirements
6. Research evidence
7. Technical feasibility
8. Schedule impact
9. Portfolio value

Optional visual or convenience features shall not outrank core workflow correctness.

---

# 4. Authentication Priority

## Must

- FR-AUTH-001 — Customer Registration
- FR-AUTH-002 — Artisan Registration
- FR-AUTH-003 — Login
- FR-AUTH-004 — Logout
- FR-AUTH-005 — Role Recognition

Reason:

All protected Customer, Artisan, and Administrator workflows depend on identity and authorization.

---

# 5. Customer Profile Priority

## Should

- FR-USER-001 — View Own Profile
- FR-USER-002 — Update Own Profile

These improve usability but are not more important than ordering or security.

---

# 6. Artisan Priority

## Must

- FR-ART-001 — Artisan Profile
- FR-ART-002 — Public Artisan Profile
- FR-ART-003 — Update Own Profile
- FR-ART-004 — Artisan Products

Reason:

Artisan identity is part of the current Craft BD product positioning.

---

# 7. Product Management Priority

## Must

- Create product
- Edit own product
- Deactivate own product
- Maintain price
- Maintain stock
- Product images
- Category assignment
- Product description

## Should

- Material information
- Craft type / region information

Core catalog functionality must exist before advanced discovery or contextual features.

---

# 8. Product Discovery Priority

## Must

- Browse products
- View product details
- Browse category
- Search products

## Should

- Filter by category
- Filter by price

## Should — Provisional

- Filter by material
- Filter by craft type

---

# 9. Craft Context Priority

## Should — Provisional

- Basic craft context

## Could / Should — Provisional

- Craft-context management

This module supports differentiation but must remain smaller than the core commerce and custom-order workflows.

---

# 10. Cart Priority

## Must

- View cart
- Add product
- Update quantity
- Remove product
- Calculate total

The cart is required for the selected standard-commerce workflow.

---

# 11. Standard Order Priority

## Must

- Initiate checkout
- Delivery information
- Checkout review
- Confirm order
- Create order
- Store order items
- Store price snapshot
- Initial order status
- Authorized status updates
- View order details
- Track status

## Should

- Order history
- Simulated payment method
- Simulated payment status display

---

# 12. Payment Priority

## Should

Simulated payment.

## Deferred

Real payment gateway.

Reason:

Real payment introduces external security, compliance, provider, and integration dependencies that do not improve the academic MVP enough to justify current risk.

---

# 13. Review Priority

## Should

- View reviews
- Submit rating
- Submit review
- Admin moderation

## Must Rule

If reviews are implemented, review eligibility and authorization must be enforced.

A feature may be `Should`, while the security rule governing an implemented feature remains `Must`.

---

# 14. Custom Order Priority

The custom-order workflow currently remains:

**Provisional Must**

because it is central to the current product hypothesis but still requires real user validation.

Protected provisional requirements include:

- Create request
- Structured customization data
- Artisan review
- Quotation
- Customer approval/rejection
- Production guard
- Status management
- Customer tracking
- Artisan active-work view

If validated, these become core Must requirements.

If rejected by primary research, they must be revised rather than protected by sunk effort.

---

# 15. Custom Order Supporting Priority

## Should

- Reference image
- Additional instructions
- Quotation notes
- Quality-check state
- Cancellation workflow
- Completed custom-order history

These may be simplified if schedule pressure occurs.

---

# 16. Notification Priority

## Should

- New custom request
- Quotation available
- Quote approval/rejection
- Important order-status change
- View notifications

## Could

- Mark notification as read

Real-time push, SMS, and complex notification infrastructure remain outside MVP.

---

# 17. Administration Priority

## Must

- Administrator authorization
- User-status management
- Category management

## Should

- Review moderation
- Product/profile moderation
- Exceptional order support

## Conditional

- Verification management
- Certificate management

---

# 18. QR / Verification Priority

## Should — Conditional

- Verification identifier
- QR-linked product record
- Public verification view
- Invalid lookup handling

This module supports the product-information/traceability direction but shall not delay the core system.

---

# 19. Certificate Priority

## Could

All platform-certificate functionality.

Reason:

It adds complexity and trust-related terminology risk without being necessary for the main MVP workflow.

If schedule becomes constrained, certificate functionality should be removed before core requirements.

---

# 20. Explicitly Deferred Capabilities

The following are outside the current MVP:

- Real payment gateway
- Advanced AI recommendation
- Gift recommendation engine
- Events/workshops platform
- Live chat
- Courier API integration
- Blockchain verification
- External certification integration
- Native mobile application
- Advanced analytics platform

These items should not quietly return during implementation without requirement change review.

---

# 21. Core Requirement Dependency Model

Major dependencies include:

```text
Authentication
      ↓
Role Authorization
      ↓
Ownership
      ↓
Protected User Workflows
```

---

# 22. Artisan / Product Dependency

```text
Artisan Account
      ↓
Artisan Profile
      ↓
Product
      ↓
Product Discovery
```

A product cannot safely exist without a valid approved ownership relationship.

---

# 23. Standard Commerce Dependency

```text
Product
   ↓
Availability / Price
   ↓
Cart
   ↓
Checkout
   ↓
Order
   ↓
Order Status
   ↓
Review
```

Reviews therefore depend indirectly on:

```text
Product + Customer + Completed Eligible Purchase
```

---

# 24. Custom Order Dependency

```text
Customer
      +
Artisan
      ↓
Custom Request
      ↓
Artisan Review
      ↓
Quotation
      ↓
Customer Decision
      ↓
Production
      ↓
Status Tracking
```

Production must never be implemented as an independent starting action.

---

# 25. QR Dependency

```text
Product Record
      ↓
Verification Record
      ↓
Verification Identifier
      ↓
QR Reference
```

Therefore QR generation should not be implemented before a stable product-record model exists.

---

# 26. Certificate Dependency

```text
Product
      ↓
Certificate Record
      ↓
Verification / Display
```

Certificate is dependent on Product and authorized administration.

---

# 27. Notification Dependency

Notifications are event-dependent.

Example:

```text
Quotation Submitted
      ↓
Notification Event
      ↓
Customer Notification
```

Therefore the notification system should not become the source of business state.

Business state must exist first.

---

# 28. Security Dependency

Every protected workflow depends on:

```text
Authentication
      ↓
Authorization
      ↓
Ownership
      ↓
Business Rule
      ↓
Input Validation
```

Security is therefore a cross-cutting dependency rather than an optional later module.

---

# 29. Requirement Conflict — Flexibility vs Simplicity

## Conflict

Customer wants flexible customization.

Artisan needs structured, manageable requests.

## Decision

Use:

- Required structured fields
- Optional notes
- Optional reference image

Avoid an unrestricted free-text-only workflow.

---

# 30. Requirement Conflict — Information Richness vs Seller Effort

## Conflict

Customers may value:

- Craft context
- Material
- Region
- Product story

But artisans may find excessive product-data entry burdensome.

## Decision

Separate:

### Essential fields

Required for product listing.

### Enrichment fields

Optional or progressively added.

---

# 31. Requirement Conflict — Customer Speed vs Quotation Control

## Conflict

Customer may want quick confirmation.

Custom products require artisan feasibility and price review.

## Decision

Custom request shall not automatically become a confirmed production order.

Use:

```text
Request
→ Artisan Review
→ Quote
→ Customer Approval
```

---

# 32. Requirement Conflict — Status Visibility vs Artisan Burden

## Conflict

Customer wants frequent status visibility.

Artisan should not perform excessive administrative updates.

## Decision

Use a small meaningful status set.

Do not model every physical production activity as a separate mandatory status.

---

# 33. Requirement Conflict — Admin Control vs Workflow Efficiency

## Conflict

Strong platform governance may suggest admin approval.

But approval of every routine action would create delays.

## Decision

Follow:

**Admin by Exception**

Routine valid workflows should remain Customer ↔ Artisan.

---

# 34. Requirement Conflict — Trust vs Authenticity Claim

## Conflict

Users may value authenticity information.

The system cannot prove physical authenticity solely through a QR record.

## Decision

Use transparent terminology:

```text
Craft BD Product Record
```

not:

```text
Guaranteed Authentic Product
```

---

# 35. Requirement Conflict — Feature Richness vs Schedule

## Conflict

Academic projects may appear impressive with many features.

But excessive scope reduces:

- Testing quality
- Architecture quality
- Documentation quality
- Deployment stability

## Decision

Prefer:

```text
Fewer Features
+
Complete Engineering
```

over:

```text
Many Features
+
Incomplete Engineering
```

---

# 36. Requirement Conflict — Recommendation vs Data Availability

## Conflict

Personalized recommendation appears advanced.

The initial system has limited behavioral data.

## Decision

Advanced recommendation remains deferred.

If implemented later, begin with a simple explainable method such as content-based matching.

---

# 37. Requirement Conflict — Real Payment vs Academic Safety

## Conflict

Real payment improves realism.

It also increases integration, security, provider, and compliance complexity.

## Decision

Use simulated payment for MVP.

---

# 38. Requirement Conflict — Product Comparison vs Core Workflow

## Conflict

Product comparison is useful but adds additional UI/data behavior.

## Decision

Defer unless future research establishes strong need.

---

# 39. Requirement Conflict — Events vs Product Focus

## Conflict

Events/workshops may support cultural engagement.

However they introduce a largely separate module involving:

- Event creation
- Registration
- Capacity
- Scheduling
- Possible payment

## Decision

Defer from MVP.

---

# 40. Must-Have MVP Baseline

Subject to primary validation of the custom-order hypothesis, the current recommended MVP is:

```text
Authentication
      ↓
Role Authorization

Artisan Profile
      ↓
Product Management
      ↓
Product Discovery

Product
      ↓
Cart
      ↓
Checkout
      ↓
Standard Order
      ↓
Status Tracking

Customer + Artisan
      ↓
Structured Custom Request
      ↓
Quotation
      ↓
Approval
      ↓
Status Tracking

Admin
      ↓
Core Governance

Across Everything:
Security + Privacy + Validation + Testing
```

---

# 41. Should-Have Baseline

Current Should features:

- Customer profile
- Product filters
- Basic craft context
- Simulated payment
- Reviews
- Basic notifications
- Moderation
- QR-linked product record where schedule allows

---

# 42. Could-Have Baseline

Current Could features:

- Wishlist
- Product journey
- Platform certificate
- Additional notification convenience
- Simple recommendation after core completion

---

# 43. Scope Cut Order

If project schedule becomes constrained, cut features approximately in this order:

```text
Certificate
↓
Wishlist
↓
Product Journey
↓
Advanced Filters
↓
QR Verification
↓
Non-essential Notifications
↓
Craft Context Depth
```

Protect:

```text
Security
Authentication
Authorization
Product
Order
Custom Workflow*
Testing
Deployment
```

`*` subject to primary validation.

---

# 44. Dependency-Based Implementation Direction

A practical development sequence should respect dependencies:

```text
1. Authentication / Roles
2. Profiles
3. Artisan
4. Product / Category
5. Discovery
6. Cart
7. Standard Order
8. Custom Request
9. Quotation / Approval
10. Status Workflows
11. Reviews
12. Notifications
13. Verification
14. Certificate
```

This is not yet the final sprint plan, but it prevents implementation in the wrong dependency order.

---

# 45. Requirement Conflict Resolution Criteria

When a new conflict appears, evaluate:

1. Security / legal impact
2. Data integrity
3. Evidence
4. Core user value
5. Dependency impact
6. Technical feasibility
7. Schedule impact
8. Maintainability
9. Academic value
10. Portfolio value

Stakeholder power alone shall not automatically determine priority.

---

# 46. Provisional Requirement Rule

Any requirement marked:

`PROVISIONAL`

shall remain subject to:

```text
Research Evidence
      ↓
Review
      ↓
Approve
or
Rewrite
or
Defer
or
Reject
```

It shall not silently become approved merely because implementation has begun.

---

# 47. Requirement Freeze Direction

The project is approaching the first formal requirement baseline.

However, requirements dependent on primary customer/artisan validation should not yet be treated as permanently frozen.

The recommended baseline status is:

```text
v0.1
Controlled Baseline
```

rather than:

```text
Final Forever
```

Changes after baseline shall use documented change control.

---

# 48. Current Core Risk

The largest unresolved product-level risk remains:

> Is the structured custom-order workflow sufficiently valuable to both customers and artisans compared with their existing informal workflow?

This is primarily a research question, not a coding question.

Until primary research is completed, the workflow remains technically well-defined but product-validation status remains provisional.

---

# 49. Phase 04 Priority Review Decision

The current requirement set is suitable to proceed toward a controlled requirement baseline because:

- Core functional areas are identified
- Priority is defined
- Business rules are separated
- Security/privacy requirements exist
- Data requirements exist
- Dependencies are mapped
- Major conflicts are documented
- Deferred scope is explicit
- Traceability has begun

Remaining major requirement work includes:

- Controlled baseline summary
- Requirement-change process
- Documentation index/review
- Final Phase 04 Pull Request

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Requirement Priority, Dependency & Conflict Review  
**Status:** Draft v0.1  
**Primary Research Dependency:** Open  
**Next Step:** Requirement Change Control & Baseline Policy
