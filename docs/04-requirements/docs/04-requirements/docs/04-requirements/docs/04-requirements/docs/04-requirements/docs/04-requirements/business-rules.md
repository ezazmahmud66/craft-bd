# Craft BD — Business Rule Register

## 1. Purpose

This document defines the formal business rules that govern Craft BD workflows.

Business rules describe conditions, restrictions, ownership rules, state-transition rules, eligibility rules, and governance policies that must be enforced by the system.

They support:

- Functional requirements
- Database design
- API validation
- Authorization
- UML state/activity modeling
- Testing
- Requirement traceability

---

# 2. Business Rule Standard

Business rules use:

`BR-MODULE-NNN`

Examples:

- BR-PROD-001
- BR-CART-001
- BR-ORDER-001
- BR-CUSTOM-001
- BR-REV-001
- BR-VERIFY-001
- BR-CERT-001
- BR-ADMIN-001

---

# 3. Business Rule Classification

Business rules may control:

## Ownership

Who owns or controls a resource.

## Eligibility

Who may perform an action.

## Validation

What data is valid.

## State Transition

Which workflow changes are permitted.

## Integrity

How historical/system data must remain consistent.

## Governance

How platform-level administrative actions operate.

---

# 4. Product Business Rules

## BR-PROD-001 — Product Ownership

An artisan may modify or deactivate only products associated with that artisan account through normal artisan functionality.

**Priority:** Must  
**Status:** DRAFT

Related:

- FR-PROD-002
- FR-PROD-003

---

## BR-PROD-002 — Valid Product Category

A product must reference an available valid category according to the approved category model.

**Priority:** Must  
**Status:** DRAFT

Related:

- FR-PROD-007

---

## BR-PROD-003 — Valid Product Price

A product price must satisfy the approved numeric and business validation rules.

Negative prices shall not be permitted.

**Priority:** Must  
**Status:** DRAFT

---

## BR-PROD-004 — Valid Product Stock

Where stock tracking applies, stock quantity shall not be negative.

**Priority:** Must  
**Status:** DRAFT

---

## BR-PROD-005 — Product Visibility

Only products satisfying approved visibility rules may appear in public product discovery.

Examples may include:

- Active product
- Valid artisan association
- Valid category
- Approved visibility status

**Priority:** Must  
**Status:** DRAFT

---

## BR-PROD-006 — Historical Product Preservation

Deactivating a product shall not automatically delete historical order records that reference that product.

**Priority:** Must  
**Status:** DRAFT

---

# 5. Cart Business Rules

## BR-CART-001 — Cart Ownership

A customer's active cart belongs only to that customer account.

**Priority:** Must  
**Status:** DRAFT

---

## BR-CART-002 — Valid Cart Quantity

Cart quantity must be a valid positive quantity and must satisfy the approved availability rule.

**Priority:** Must  
**Status:** DRAFT

---

## BR-CART-003 — Available Product Requirement

A product may be added to the active cart only when it is eligible for normal ordering.

**Priority:** Must  
**Status:** DRAFT

---

## BR-CART-004 — Cart Total Calculation

Cart total shall be calculated from the authoritative product price and approved cart quantity rather than from a customer-supplied total value.

**Priority:** Must  
**Status:** DRAFT

---

# 6. Standard Order Business Rules

## BR-ORDER-001 — Order Ownership

Each standard order shall belong to exactly one customer account.

**Priority:** Must  
**Status:** DRAFT

---

## BR-ORDER-002 — Order Item Persistence

A confirmed order shall preserve the relevant purchased product information required for historical transaction consistency.

This includes the applicable transaction-time price.

**Priority:** Must  
**Status:** DRAFT

Related:

- FR-ORDER-006
- FR-ORDER-007

---

## BR-ORDER-003 — Valid Checkout

A standard order may be confirmed only when all mandatory checkout information is valid.

**Priority:** Must  
**Status:** DRAFT

---

## BR-ORDER-004 — Empty Cart Restriction

A customer shall not confirm a standard order when no eligible items exist in the checkout.

**Priority:** Must  
**Status:** DRAFT

---

## BR-ORDER-005 — Standard Order State Integrity

A standard order may transition only through an approved state transition.

**Priority:** Must  
**Status:** DRAFT

---

## BR-ORDER-006 — Authorized Status Update

Only an authorized actor may change a standard order's status.

**Priority:** Must  
**Status:** DRAFT

---

## BR-ORDER-007 — Historical Price Integrity

A later change to the current product price shall not alter the stored price of a previously confirmed order.

**Priority:** Must  
**Status:** DRAFT

---

## BR-ORDER-008 — Order Access

A customer may access private order details only for orders owned by that customer unless an approved administrative rule applies.

**Priority:** Must  
**Status:** DRAFT

---

# 7. Simulated Payment Business Rules

## BR-ORDER-009 — Academic Payment Boundary

The academic MVP may simulate payment status without processing real financial credentials or transferring real funds.

**Priority:** Should  
**Status:** DRAFT

---

## BR-ORDER-010 — Payment Credential Restriction

Craft BD shall not require or store:

- Card PINs
- Mobile financial service PINs
- Bank passwords
- Payment-provider passwords

**Priority:** Must  
**Status:** DRAFT

---

# 8. Custom Order Business Rules

## BR-CUSTOM-001 — Approval Before Production

A custom order shall not enter the production workflow until the request owner has approved a valid artisan quotation.

**Priority:** Must  
**Status:** PROVISIONAL

Related:

- FR-CUSTOM-025
- FR-CUSTOM-028

---

## BR-CUSTOM-002 — Quotation Decision Ownership

Only the customer who owns the custom request may approve or reject its quotation through normal customer functionality.

**Priority:** Must  
**Status:** PROVISIONAL

---

## BR-CUSTOM-003 — Artisan Assignment

Only the assigned artisan or an explicitly authorized administrative role may perform artisan-side actions on a custom request.

**Priority:** Must  
**Status:** PROVISIONAL

---

## BR-CUSTOM-004 — Valid Quotation Relationship

A quotation must belong to a valid existing custom-order request.

**Priority:** Must  
**Status:** DRAFT

---

## BR-CUSTOM-005 — Valid Quotation Price

A quotation must contain a valid price according to approved pricing validation rules.

**Priority:** Must  
**Status:** DRAFT

---

## BR-CUSTOM-006 — Valid Custom Quantity

A custom-order request must contain a valid positive quantity.

**Priority:** Must  
**Status:** DRAFT

---

## BR-CUSTOM-007 — Custom State Integrity

A custom-order request or order may transition only through an approved custom-order state transition.

**Priority:** Must  
**Status:** PROVISIONAL

---

## BR-CUSTOM-008 — Rejected Request Restriction

A rejected custom-order request shall not proceed directly into quotation or production unless an approved reopening process exists.

**Priority:** Must  
**Status:** PROVISIONAL

---

## BR-CUSTOM-009 — Customer Requirement Integrity

An artisan shall not silently modify customer-submitted customization requirements.

**Priority:** Must  
**Status:** PROVISIONAL

---

## BR-CUSTOM-010 — Post-Approval Change Control

Changes to agreed custom-order requirements after quotation approval must follow an approved change process.

**Priority:** Should  
**Status:** PROVISIONAL

---

## BR-CUSTOM-011 — Private Custom-Order Access

Private custom-order data shall normally be accessible only to:

- Request owner
- Assigned artisan
- Authorized administrator where necessary

**Priority:** Must  
**Status:** DRAFT

---

## BR-CUSTOM-012 — Customer-Facing Status Accuracy

A simplified customer-facing status may combine internal states, but it shall not misrepresent the actual workflow state.

**Priority:** Must  
**Status:** DRAFT

---

## BR-CUSTOM-013 — Request Rejection

An artisan may reject a custom request before production when the request is not feasible or the artisan chooses not to proceed, according to approved platform rules.

**Priority:** Must  
**Status:** PROVISIONAL

---

## BR-CUSTOM-014 — Cancellation Eligibility

A customer may cancel a custom order only when the current state and approved cancellation policy permit cancellation.

**Priority:** Should  
**Status:** PROVISIONAL

---

# 9. Custom Order State Rules

The provisional valid flow is:

`REQUESTED`

→ `UNDER_REVIEW`

→ `QUOTED`

→ `CUSTOMER_APPROVED`

→ `IN_PRODUCTION`

→ `QUALITY_CHECK`

→ `READY_TO_SHIP`

→ `SHIPPED`

→ `DELIVERED`

Alternative terminal states:

- `REJECTED`
- `CANCELLED`

Exact transitions will be finalized during state-machine design.

---

# 10. Example Invalid Custom Transitions

The following should not normally be allowed:

`REQUESTED → SHIPPED`

`QUOTED → IN_PRODUCTION` without customer approval

`REJECTED → IN_PRODUCTION`

`DELIVERED → IN_PRODUCTION`

These cases should be rejected unless an explicit exceptional workflow exists.

---

# 11. Review Business Rules

## BR-REV-001 — Review Eligibility

A customer may submit a product rating or review only when the customer satisfies the approved purchase-eligibility condition for that product.

**Priority:** Must  
**Status:** DRAFT

Related:

- FR-REV-002
- FR-REV-003

---

## BR-REV-002 — Review Ownership

A review shall remain associated with the customer who submitted it.

**Priority:** Must  
**Status:** DRAFT

---

## BR-REV-003 — Seller Review Restriction

An artisan shall not edit or delete a legitimate customer review through normal artisan functionality.

**Priority:** Must  
**Status:** DRAFT

---

## BR-REV-004 — Review Moderation

An administrator may moderate a review only according to approved platform moderation rules.

**Priority:** Should  
**Status:** DRAFT

---

## BR-REV-005 — Review Privacy

Published reviews shall not expose private customer information beyond approved public reviewer information.

**Priority:** Must  
**Status:** DRAFT

---

# 12. Artisan Business Rules

## BR-ART-001 — Artisan Profile Ownership

An artisan may update only their own artisan profile through normal artisan functionality.

**Priority:** Must  
**Status:** DRAFT

---

## BR-ART-002 — Artisan Public Information

Only information classified as public profile information may be exposed through the public artisan profile.

**Priority:** Must  
**Status:** DRAFT

---

# 13. Verification Business Rules

## BR-VERIFY-001 — Platform Record Boundary

A QR-linked verification record represents information maintained by Craft BD.

It shall not automatically be treated as independent proof of physical-product authenticity.

**Priority:** Must if verification module exists  
**Status:** PROVISIONAL

---

## BR-VERIFY-002 — Authorized Verification Management

Only an authorized role may create, activate, deactivate, or modify verification records.

**Priority:** Must  
**Status:** PROVISIONAL

---

## BR-VERIFY-003 — Unique Verification Record

Each active verification record shall use an identifier that uniquely resolves to the intended record.

**Priority:** Must  
**Status:** PROVISIONAL

---

## BR-VERIFY-004 — Invalid Verification Lookup

An invalid verification identifier shall not return unrelated product or certificate data.

**Priority:** Must  
**Status:** PROVISIONAL

---

# 14. Certificate Business Rules

## BR-CERT-001 — Authorized Certificate Creation

Only an authorized administrator may create a Craft BD platform certificate record.

**Priority:** Must if certificate module exists  
**Status:** PROVISIONAL

---

## BR-CERT-002 — Certificate Claim Boundary

A Craft BD certificate record shall not be represented as:

- Government certification
- Legally recognized authenticity certification
- Independent external certification

unless an authorized external process actually exists.

**Priority:** Must  
**Status:** PROVISIONAL

---

## BR-CERT-003 — Unique Certificate Identifier

Each valid Craft BD certificate record shall contain a unique certificate identifier.

**Priority:** Must if certificate module exists  
**Status:** PROVISIONAL

---

## BR-CERT-004 — Certificate Product Relationship

A certificate record shall reference an eligible Craft BD product record.

**Priority:** Must if implemented  
**Status:** PROVISIONAL

---

## BR-CERT-005 — Certificate Deactivation Integrity

Deactivating or revoking a certificate shall not silently erase historical certificate information required for audit or historical display.

**Priority:** Should  
**Status:** PROVISIONAL

---

# 15. Notification Business Rules

## BR-NOTIF-001 — Notification Ownership

A normal user may view only notifications associated with their account.

**Priority:** Must  
**Status:** DRAFT

---

## BR-NOTIF-002 — Relevant Notification Events

Notifications should be created for meaningful user actions or status changes rather than every minor internal event.

**Priority:** Should  
**Status:** DRAFT

---

## BR-NOTIF-003 — Notification Privacy

A notification shall not expose private order or custom-order information to an unauthorized user.

**Priority:** Must  
**Status:** DRAFT

---

# 16. Administration Business Rules

## BR-ADMIN-001 — Administrator Authorization

Administrative functionality shall require authenticated administrator authorization.

**Priority:** Must  
**Status:** DRAFT

---

## BR-ADMIN-002 — Admin by Exception

Administrator intervention shall not be required for normal customer-artisan workflow unless a specific approved business rule requires administrative action.

**Priority:** Must  
**Status:** DRAFT

---

## BR-ADMIN-003 — Administrative Least Privilege

Administrator permissions should be limited to the functions required by the approved governance model.

**Priority:** Must  
**Status:** DRAFT

---

## BR-ADMIN-004 — Sensitive Administrative Actions

High-impact administrative actions should be traceable where practical.

Examples:

- User deactivation
- Certificate revocation
- Verification deactivation
- Content moderation
- Exceptional order override

**Priority:** Should  
**Status:** DRAFT

---

## BR-ADMIN-005 — Category Integrity

Deactivating a product category shall not silently invalidate or erase historical product/order information.

**Priority:** Must  
**Status:** DRAFT

---

# 17. Privacy Business Rules

## BR-PRIV-001 — Minimum Necessary Access

Users shall receive access only to personal or transaction information necessary for their authorized role and current workflow.

**Priority:** Must  
**Status:** DRAFT

---

## BR-PRIV-002 — Public / Private Separation

Craft BD shall distinguish public product/artisan information from private operational information.

**Priority:** Must  
**Status:** DRAFT

---

## BR-PRIV-003 — Demo Data

Public academic demonstrations should use synthetic or otherwise appropriately authorized data rather than exposing private real-user records.

**Priority:** Must  
**Status:** DRAFT

---

# 18. Business Rule Conflict Priority

Where business rules conflict, decisions should consider:

1. Legal / Privacy / Security constraints
2. Data integrity
3. Core workflow correctness
4. User value
5. Operational simplicity
6. Optional feature convenience

A convenience requirement shall not override a critical security or integrity rule.

---

# 19. Rule-to-Requirement Traceability Examples

| Business Rule | Related Requirement |
|---|---|
| BR-PROD-001 | FR-PROD-002, FR-PROD-003 |
| BR-CART-002 | FR-CART-003 |
| BR-ORDER-002 | FR-ORDER-006, FR-ORDER-007 |
| BR-CUSTOM-001 | FR-CUSTOM-025, FR-CUSTOM-028 |
| BR-CUSTOM-002 | FR-CUSTOM-025, FR-CUSTOM-026 |
| BR-CUSTOM-011 | FR-CUSTOM-012 through FR-CUSTOM-015 |
| BR-REV-001 | FR-REV-002, FR-REV-003 |
| BR-VERIFY-001 | FR-VERIFY-003 |
| BR-CERT-002 | FR-CERT-003 |
| BR-NOTIF-001 | FR-NOTIF-006 |
| BR-ADMIN-001 | FR-ADMIN-001 through FR-ADMIN-012 |

---

# 20. Rule-to-Test Direction

Business rules should later receive test coverage.

Examples:

`BR-CUSTOM-001`

Test:

Artisan attempts to move quotation directly into production without customer approval.

Expected:

**Rejected**

---

`BR-PROD-001`

Test:

Artisan A attempts to edit Artisan B's product.

Expected:

**Access Denied**

---

`BR-REV-001`

Test:

Customer without an eligible purchase attempts to review the product.

Expected:

**Review Rejected**

---

`BR-VERIFY-004`

Test:

Unknown verification identifier is submitted.

Expected:

**Invalid / Not Found**

and unrelated records remain protected.

---

# 21. Business Rule Summary

Current rule groups:

| Module | Rule Count |
|---|---:|
| Product | 6 |
| Cart | 4 |
| Standard Order | 10 |
| Custom Order | 14 |
| Review | 5 |
| Artisan | 2 |
| Verification | 4 |
| Certificate | 5 |
| Notification | 3 |
| Administration | 5 |
| Privacy | 3 |
| **Total** | **61** |

The count may change during formal review.

---

# 22. Provisional Rules

The following groups remain especially dependent on future user/product validation:

- Custom-order rules
- QR verification rules
- Certificate rules

Their workflow logic may be technically valid while the underlying product need remains provisional.

---

# 23. Rule Change Principle

After formal baseline approval, a business rule should not be silently changed.

Use:

Change Request  
→ Impact Analysis  
→ Requirement Review  
→ Rule Update  
→ Related Requirement Update  
→ Test Update

A rule change may affect:

- Database
- API
- UI
- State machine
- Security
- Test cases

---

# 24. Engineering Decision

Craft BD will keep business rules separate from functional requirements because this improves:

- Requirement clarity
- Workflow design
- Authorization
- State-machine modeling
- Testing
- Traceability
- Maintenance

The implementation must enforce relevant business rules on the trusted backend or appropriate authoritative system layer rather than relying only on frontend behavior.

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Business Rule Register  
**Status:** Draft / Provisional v0.1  
**Next Step:** Non-Functional Requirements Baseline
