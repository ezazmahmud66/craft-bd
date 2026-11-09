# Craft BD — Existing Requirement Audit

## 1. Purpose

This document audits the existing Craft BD Requirement Analysis before creating the formal requirement baseline.

The objective is to identify requirements that should be:

- Kept
- Rewritten
- Merged
- Moved
- Deferred
- Removed

This audit prevents ambiguous, duplicated, weakly justified, or out-of-scope requirements from entering the formal SRS.

---

# 2. Audit Decision Types

## KEEP

The requirement concept is appropriate and can continue with minor wording improvement.

## REWRITE

The requirement concept is useful, but the current wording is ambiguous, incomplete, or not testable.

## MERGE

Two or more requirements represent the same or strongly overlapping behavior.

## MOVE

The item is valid but belongs in another category such as:

- Business Rule
- Non-Functional Requirement
- Security Requirement
- Future Scope

## DEFER

The capability may be useful later but should not be part of the initial MVP baseline.

## REMOVE

The capability should not continue in the current scope because it has insufficient value or creates unnecessary complexity.

---

# 3. General Audit Findings

The existing Requirement Analysis provides a useful functional starting point, but several issues must be corrected before formal SRS preparation.

Current major issues include:

1. Requirement numbering contains gaps.
2. Some requirements mix system behavior with business rules.
3. Several non-functional requirements are too broad to test.
4. Recommendation functionality is insufficiently defined.
5. Real payment scope is unclear.
6. Event/workshop functionality is not clearly bounded.
7. QR-related wording may imply stronger authenticity verification than the system can actually provide.
8. Certificate functionality needs a clear platform-level boundary.
9. Several requirements remain dependent on primary user validation.
10. Admin responsibilities require tighter scope control.

---

# 4. Authentication & Account Requirements

## Existing Capability

- User registration
- Login
- User account
- Role-related functionality

## Audit Decision

**KEEP + REWRITE**

## Reason

Authentication is required, but formal requirements must distinguish:

- Authentication
- Role assignment
- Authorization
- Ownership

## Future Requirement Direction

Separate into requirements such as:

- User registration
- User login
- User logout
- Role assignment
- Protected operations
- Profile management

---

# 5. Product Browsing

## Existing Capability

Customers can browse products.

## Decision

**KEEP**

## Reason

Core product-discovery capability.

## Required Refinement

Specify:

- What information appears in listing
- Pagination or result handling if required
- Access without login where appropriate

---

# 6. Product Search

## Existing Capability

Search products.

## Decision

**KEEP + REWRITE**

## Reason

"Search products" alone is not sufficiently precise.

## Future Direction

Define searchable fields such as:

- Product name
- Category
- Craft type
- Artisan where appropriate

Detailed search behavior will be finalized later.

---

# 7. Product Filtering

## Existing Capability

Filter products.

## Decision

**KEEP + REWRITE**

Potential filter criteria may include:

- Category
- Price range
- Material
- Craft type

Only filters supported by the final data model should be included.

---

# 8. Product Comparison

## Existing Capability

Customers can compare products.

## Decision

**DEFER / REQUIRE VALIDATION**

## Reason

Product comparison is useful but not currently essential to Craft BD's core MVP.

It also introduces additional UI complexity.

## Current Status

**Should / Could Have**

Not required for the first baseline unless later evidence supports it.

---

# 9. Product Details

## Existing Capability

View detailed product information.

## Decision

**KEEP**

Potential information includes:

- Name
- Price
- Description
- Images
- Stock
- Category
- Material
- Artisan
- Craft information

Detailed required fields will be normalized during formal requirement writing.

---

# 10. Artisan Profile

## Existing Capability

View artisan details such as:

- Name
- Location
- Experience
- Expertise
- Biography
- Products

## Decision

**KEEP**

## Reason

This capability is aligned with the current Craft BD product direction.

## Validation Status

Partially supported.

---

# 11. Craft Story

## Existing Capability

Product/craft information may include:

- Origin
- History
- Materials
- Techniques
- Traditional uses

## Decision

**KEEP AS PROVISIONAL / REWRITE**

## Reason

The capability supports Craft BD's contextual positioning, but user value is not fully validated.

## Scope Boundary

The MVP should contain lightweight contextual information rather than a large cultural encyclopedia.

---

# 12. Product Journey

## Existing Capability

Show stages such as:

Raw Material  
→ Design  
→ Making  
→ Finishing  
→ Quality Check  
→ Final Product

## Decision

**DEFER / OPTIONAL**

## Reason

Technically feasible but not essential to the core workflow.

## Current Priority

Could Have.

This feature must not delay:

- Custom-order workflow
- Testing
- Deployment

---

# 13. Wishlist

## Existing Capability

Customer can save products.

## Decision

**DEFER / OPTIONAL**

## Reason

Useful standard commerce functionality but not central to Craft BD differentiation.

---

# 14. Shopping Cart

## Existing Capability

Customer can:

- Add items
- Modify quantities
- Remove items

## Decision

**KEEP**

## Required Refinement

Formal requirements should separately define:

- Add to cart
- Update quantity
- Remove item
- View cart
- Quantity validation

---

# 15. Checkout

## Existing Capability

Customer can checkout.

## Decision

**KEEP + REWRITE**

## Reason

"Checkout" contains multiple behaviors and should not remain one vague requirement.

Potential future requirements:

- Provide delivery information
- Review order
- Select supported payment method
- Confirm order

---

# 16. Payment

## Existing Capability

Payment functionality is proposed.

## Decision

**REWRITE + REDUCE SCOPE**

## MVP Decision

Use:

**Simulated Payment**

Real payment gateway:

**DEFER**

## Reason

Real payment creates external, security, provider, and compliance dependencies without being necessary for demonstrating the core academic workflow.

---

# 17. Standard Order Placement

## Existing Capability

Customer places product order.

## Decision

**KEEP**

Formal requirements should define:

- Order creation
- Order items
- Price snapshot
- Quantity
- Order owner
- Initial order state

---

# 18. Standard Order Tracking

## Existing Capability

Customer tracks orders.

## Decision

**KEEP + REWRITE**

## Reason

Order tracking should define permitted statuses rather than using vague "track order" wording.

---

# 19. Reviews and Ratings

## Existing Capability

Customers can review products.

## Decision

**KEEP + REWRITE**

## Required Business Rule

Only an eligible customer associated with a valid purchase should normally be able to submit a product review.

The eligibility rule should be moved into the Business Rule register.

---

# 20. Custom Order Request

## Existing Capability

Customer can provide:

- Product type
- Design
- Color
- Size
- Material
- Quantity
- Reference image
- Instructions

## Decision

**KEEP AS PROVISIONAL CORE**

## Reason

This represents the strongest current differentiating workflow.

## Important Status

Primary customer/artisan validation remains pending.

Therefore it must be marked:

**Provisional Must Have**

rather than falsely validated.

---

# 21. Custom Order Review by Artisan

## Existing Capability

Artisan reviews submitted custom requirements.

## Decision

**KEEP**

## Refinement Required

Artisan should be able to determine whether a request is suitable for quotation.

Potential outcomes:

- Proceed to quotation
- Reject request

---

# 22. Custom Order Quotation

## Existing Capability

Artisan provides a price estimate.

## Decision

**KEEP + REWRITE**

## Formal quotation should include:

- Quoted price
- Estimated completion date
- Notes

Quotation must belong to a specific custom request.

---

# 23. Customer Quotation Approval

## Existing Capability

Customer approves artisan estimate.

## Decision

**KEEP**

## Related Business Rule

Production must not begin before customer approval.

This rule should not remain buried inside a functional requirement.

---

# 24. Custom Production Workflow

## Existing Capability

Production / quality / delivery stages are represented.

## Decision

**KEEP + REWRITE**

## Important Boundary

Craft BD records workflow status.

Craft BD does not physically:

- Manufacture
- Perform quality inspection
- Ship the item

Formal requirements should describe:

**status recording and transition**

rather than claiming that the software performs physical activities.

---

# 25. Custom Order Status

## Existing Capability

Track custom order progress.

## Decision

**KEEP**

Possible internal states may include:

```text
REQUESTED
UNDER_REVIEW
QUOTED
CUSTOMER_APPROVED
IN_PRODUCTION
QUALITY_CHECK
READY_TO_SHIP
SHIPPED
DELIVERED
```

Possible terminal states:

```text
REJECTED
CANCELLED
```

Exact state-transition rules will be documented separately.

---

# 26. QR Functionality

## Existing Capability

QR code may provide:

- Product ID
- Artisan
- Location
- Craft type
- Materials
- Production information
- Certificate

## Decision

**REWRITE**

## Major Issue

QR functionality must not be described as automatically verifying physical authenticity.

## Correct Scope

Use:

**QR-linked Product Record**

Possible flow:

```text
QR Code
→ Craft BD URL
→ Product Record
```

## Priority

Should Have / Scope Dependent.

---

# 27. Digital Certificate

## Existing Capability

Certificate-related information.

## Decision

**REWRITE + OPTIONAL**

## Correct Boundary

Craft BD may maintain:

**Platform Certificate Record**

It must not automatically be described as:

- Government certificate
- Legally recognized authenticity certificate
- Independent third-party certification

unless such integration actually exists.

---

# 28. Recommendation System

## Existing Capability

Personalized recommendations based on:

- Search history
- Views
- Purchases
- Wishlist
- Category
- Price
- Preferences

## Decision

**DEFER + REDUCE SCOPE**

## Issue

The initial system is unlikely to have sufficient behavioral data for a meaningful advanced personalized recommendation model.

## Future Direction

Possible simple content-based recommendation using:

- Category
- Material
- Craft type
- Region
- Price range

## MVP Status

Not Core.

---

# 29. Gift Recommendation

## Existing Capability

Gift-oriented recommendation/discovery.

## Decision

**DEFER**

## Reason

Currently weak evidence and low relevance to the core MVP problem.

---

# 30. Events / Workshops

## Existing Capability

Events/workshops are included in the initial analysis.

## Decision

**DEFER**

## Reason

Scope is currently unclear.

It is not defined whether the system would support:

- Information only
- Registration
- Capacity
- Payment
- Attendance

Adding these creates a separate business module.

## MVP Status

Future Scope.

---

# 31. Administrator Requirements

## Existing Capability

Admin manages platform data and users.

## Decision

**KEEP + REWRITE**

## Issue

Admin responsibilities must not become unlimited.

## Formal Requirement Areas

Potential admin functions:

- Manage users
- Manage categories
- Moderate content
- Moderate reviews
- Manage exceptional platform actions
- Manage platform verification records where included

Admin should not manually approve every normal user transaction.

---

# 32. Notification Requirements

## Existing Status

Notification behavior is not sufficiently defined.

## Decision

**ADD / DERIVE**

Possible requirement areas:

Customer:

- Quotation available
- Order status change

Artisan:

- New custom request
- Quote approved

## MVP Scope

Basic in-app notification or clear pending-action indicators.

Real-time push notifications are not required.

---

# 33. File Upload Requirements

## Existing Status

Reference/product images imply upload capability, but upload rules are not sufficiently separated.

## Decision

**ADD / DERIVE**

Formal requirements should define controlled uploads for:

- Product images
- Artisan images
- Custom reference images

Security restrictions will be documented separately.

---

# 34. Profile Management

## Existing Status

Profile information exists, but profile-management behavior should be explicitly separated.

## Decision

**ADD / REWRITE**

Future requirements should distinguish:

- Customer profile management
- Artisan profile management

---

# 35. Existing Non-Functional Requirements

Current areas include:

- Usability
- Performance
- Security
- Reliability
- Availability
- Maintainability
- Scalability

## Decision

**KEEP CATEGORIES — REWRITE REQUIREMENTS**

## Main Issue

Statements such as:

> The system should be fast.

or:

> The system should be secure.

are not testable.

NFRs must eventually contain measurable or verifiable criteria.

---

# 36. Usability NFR

## Decision

**REWRITE**

Instead of:

> System should be user friendly.

define verifiable expectations such as:

- Responsive interfaces
- Consistent navigation
- Clear error messages
- Core workflows understandable during usability testing

Exact metrics will be defined later.

---

# 37. Performance NFR

## Decision

**REWRITE**

Performance requirements must specify:

- Which operation
- Under what condition
- Expected response target

Avoid arbitrary performance numbers without justification.

---

# 38. Security NFR

## Decision

**EXPAND**

Security should be separated into explicit requirements such as:

- Password protection
- Authentication
- Authorization
- Ownership validation
- Input validation
- Secure file handling
- Secret management
- HTTPS deployment

---

# 39. Reliability NFR

## Decision

**REWRITE**

Reliability should describe specific system behaviors such as:

- Prevent invalid state transitions
- Preserve completed transaction records
- Handle failed operations predictably

rather than vague "high reliability."

---

# 40. Availability NFR

## Decision

**REWRITE / LOWER PRIORITY FOR ACADEMIC MVP**

An academic free-tier deployment should not make enterprise availability guarantees.

Avoid unsupported claims such as:

> 99.99% uptime

unless infrastructure and measurement support them.

---

# 41. Maintainability NFR

## Decision

**KEEP + REWRITE**

Potential verifiable areas:

- Modular organization
- Documentation
- Environment configuration
- Automated tests
- Consistent coding standards

---

# 42. Scalability NFR

## Decision

**REWRITE**

Do not claim enterprise-scale capability without evidence.

For the academic project, design should avoid obvious architectural barriers while remaining appropriate for current scale.

---

# 43. Business Rules Missing From Formal Analysis

The existing requirements contain several business rules that should be extracted into a dedicated register.

Examples:

### BR-01

Production cannot begin before quotation approval.

### BR-02

Only the owner of a custom request may approve its quotation.

### BR-03

An artisan may edit only their own products unless an administrator performs an authorized action.

### BR-04

Only eligible customers may review purchased products.

### BR-05

A submitted custom request must belong to a customer.

### BR-06

A quotation must belong to a valid custom request.

### BR-07

Order-status changes must follow permitted transitions.

### BR-08

QR lookup represents a Craft BD platform record and not automatic proof of physical authenticity.

---

# 44. Requirement Numbering Problem

The original requirement set contains numbering gaps.

## Decision

**RENUMBER FORMAL BASELINE**

Do not try to preserve broken numbering merely for consistency.

The new requirement baseline should use clean IDs.

Possible structure:

```text
FR-AUTH-001
FR-AUTH-002

FR-PROD-001
FR-PROD-002

FR-ORDER-001

FR-CUSTOM-001

FR-ADMIN-001
```

or a simpler sequential scheme.

The exact ID convention will be selected in the next step.

---

# 45. Requirements to Keep in Core MVP

Current provisional core:

- Registration
- Login
- Role authorization
- Artisan profile
- Product management
- Product browsing
- Search
- Basic filtering
- Product details
- Cart
- Checkout
- Standard orders
- Order tracking
- Structured custom request
- Artisan quotation
- Customer approval
- Custom-order state management
- Eligible product reviews
- Basic admin governance

---

# 46. Requirements to Keep as Supporting / Conditional

- Craft story
- Reference-image upload
- Basic notification
- QR-linked product record

---

# 47. Requirements to Keep Optional

- Wishlist
- Product journey
- Platform certificate record
- Simple recommendation

---

# 48. Requirements to Defer

- Real payment gateway
- Advanced personalized recommendation
- Gift recommendation
- Event/workshop management
- Live chat
- Logistics integration
- Native mobile application
- Advanced analytics

---

# 49. Requirements to Reject for Initial MVP

- Blockchain verification
- Advanced AI recommendation dependency
- Automatic physical-product authenticity detection
- Enterprise ERP functionality
- Full warehouse management

---

# 50. Validation Classification

Requirements in the final baseline should receive one of the following evidence states:

- Primary Validated
- Secondary Supported
- Derived
- Technical
- Academic
- Provisional

Example:

```text
Custom Order Requirement
Evidence Status:
PROVISIONAL
```

until real customer/artisan research confirms it.

---

# 51. Audit Summary Table

| Requirement Area | Decision | MVP Status |
|---|---|---|
| Authentication | Keep / Rewrite | Core |
| Authorization | Expand | Core |
| Product Catalog | Keep | Core |
| Search | Rewrite | Core |
| Filtering | Rewrite | Core |
| Product Comparison | Defer | Future |
| Artisan Profile | Keep | Core |
| Craft Story | Provisional | Supporting |
| Product Journey | Defer | Optional |
| Wishlist | Defer | Optional |
| Cart | Keep | Core |
| Checkout | Rewrite | Core |
| Standard Order | Keep | Core |
| Order Tracking | Rewrite | Core |
| Real Payment | Defer | Future |
| Simulated Payment | Add | Supporting |
| Reviews | Rewrite | Core/Supporting |
| Custom Request | Provisional Keep | Core* |
| Artisan Review | Keep | Core* |
| Quotation | Rewrite | Core* |
| Customer Approval | Keep | Core* |
| Custom Status | Rewrite | Core* |
| QR Product Record | Rewrite | Supporting |
| Certificate | Rewrite / Optional | Optional |
| Recommendation | Defer / Simplify | Future |
| Gift Recommendation | Defer | Future |
| Events/Workshops | Defer | Future |
| Admin | Rewrite | Core |
| Notifications | Add | Supporting |
| File Upload | Add | Supporting |
| NFRs | Rewrite | Required |

`*` Primary user validation remains pending.

---

# 52. Audit Decision

The existing Requirement Analysis should **not** be discarded.

It should be treated as:

> An initial requirement source that now requires normalization, prioritization, traceability, and validation.

The formal Phase 04 requirement baseline will therefore:

```text
Existing Requirements
        ↓
Audit
        ↓
Normalize
        ↓
Prioritize
        ↓
Add Source / Evidence
        ↓
Add Acceptance Criteria
        ↓
Create Formal Baseline
```

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Existing Requirement Audit  
**Status:** Complete v0.1  
**Primary Research Dependency:** Open  
**Next Step:** Requirement ID & Classification Standard
