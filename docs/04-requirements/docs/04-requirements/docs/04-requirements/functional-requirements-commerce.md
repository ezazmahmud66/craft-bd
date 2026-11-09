# Craft BD — Functional Requirements Baseline Part 2

## 1. Purpose

This document defines the formal functional requirements for Craft BD's standard commerce workflow.

Covered modules:

- Cart
- Checkout
- Standard Order
- Simulated Payment
- Order Tracking
- Reviews

These requirements support a complete standard-purchase journey while keeping real payment-gateway integration outside the mandatory academic MVP.

---

# 2. Commerce Workflow Overview

The intended standard commerce workflow is:

```text
Browse Product
      ↓
Add to Cart
      ↓
Review Cart
      ↓
Checkout
      ↓
Confirm Order
      ↓
Simulated Payment
      ↓
Order Created
      ↓
Status Tracking
      ↓
Delivered
      ↓
Review
```

---

# 3. Cart Requirements

## FR-CART-001 — View Cart

**Statement**

The system shall allow an authenticated customer to view the products currently stored in their cart.

**Source:** STK-01 Customer  
**Priority:** Must  
**Evidence:** DERIVED / Standard Commerce Requirement  
**Status:** DRAFT

**Acceptance Criteria**

The customer shall be able to view:

- Product
- Unit price
- Quantity
- Line total
- Current cart total

for items currently stored in their own cart.

---

## FR-CART-002 — Add Product to Cart

**Statement**

The system shall allow an authenticated customer to add an available standard product to their cart.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

Given an eligible available product, when the customer selects a valid quantity and adds the product to the cart, the system shall store the item in that customer's cart.

Invalid or unavailable products shall not be added successfully.

---

## FR-CART-003 — Update Cart Quantity

**Statement**

The system shall allow an authenticated customer to modify the quantity of an item in their own cart within permitted availability limits.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

A valid quantity update shall change the cart quantity and recalculate the related totals.

Invalid quantities shall be rejected.

---

## FR-CART-004 — Remove Cart Item

**Statement**

The system shall allow an authenticated customer to remove an item from their own cart.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

After successful removal, the item shall no longer appear in the customer's cart and cart totals shall be recalculated.

---

## FR-CART-005 — Calculate Cart Total

**Statement**

The system shall calculate the current cart total using the valid price and quantity of each cart item.

**Source:** STK-01 / Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

The displayed cart total shall equal the sum of eligible cart-item line totals.

---

# 4. Checkout Requirements

## FR-ORDER-001 — Initiate Checkout

**Statement**

The system shall allow an authenticated customer with at least one eligible cart item to initiate checkout.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

Checkout shall not proceed when the cart contains no eligible order items.

---

## FR-ORDER-002 — Provide Delivery Information

**Statement**

The system shall allow the customer to provide the delivery information required for the order.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

The system shall validate required delivery fields before allowing the order to be confirmed.

---

## FR-ORDER-003 — Review Checkout Summary

**Statement**

The system shall allow the customer to review the order summary before confirming the order.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

The summary should include applicable information such as:

- Product
- Quantity
- Price
- Total
- Delivery information
- Selected payment option

**Acceptance Criteria**

The order shall not be finalized merely by viewing the checkout page; an explicit confirmation action shall be required.

---

## FR-ORDER-004 — Confirm Standard Order

**Statement**

The system shall allow the customer to confirm a valid standard order from the checkout workflow.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

A successful confirmation shall create a persistent order associated with the authenticated customer.

---

# 5. Order Record Requirements

## FR-ORDER-005 — Create Order Record

**Statement**

The system shall create a unique order record when a valid standard order is successfully confirmed.

**Source:** STK-01 / Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

The order shall contain a unique identifier and remain retrievable after creation.

---

## FR-ORDER-006 — Store Order Items

**Statement**

The system shall store the products and quantities included in a confirmed order as order items.

**Source:** Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

Each confirmed product and quantity shall remain associated with the relevant order even if the customer's cart later changes.

---

## FR-ORDER-007 — Store Order Price Snapshot

**Statement**

The system shall preserve the applicable order-item price used when the order was confirmed.

**Source:** Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

A later product-price change shall not silently change the price already stored for a previously confirmed order.

---

## FR-ORDER-008 — Clear Purchased Cart Items

**Statement**

The system shall remove successfully purchased cart items from the customer's active cart after order creation.

**Source:** Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

After successful order creation, purchased items shall not remain as active duplicate cart items unless intentionally re-added by the customer.

---

# 6. Standard Order Status Requirements

## FR-ORDER-009 — Assign Initial Order Status

**Statement**

The system shall assign an approved initial status to a newly created order.

**Source:** Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

Possible initial state:

```text
PENDING
```

or another approved state defined by the final order-state model.

---

## FR-ORDER-010 — Update Order Status

**Statement**

The system shall allow an authorized actor to update a standard order status according to permitted order-state transitions.

**Source:** STK-02 Artisan / STK-03 Admin  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

Only valid transitions performed by an authorized actor shall be stored.

Invalid status transitions shall be rejected.

---

## FR-ORDER-011 — View Own Order History

**Statement**

The system shall allow an authenticated customer to view their own standard-order history.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

The customer shall only receive order-history information belonging to their own account.

---

## FR-ORDER-012 — View Order Details

**Statement**

The system shall allow an authenticated customer to view permitted details of an order they own.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

Order details may include:

- Order ID
- Items
- Quantity
- Price
- Total
- Delivery information
- Payment status
- Order status

---

## FR-ORDER-013 — Track Current Order Status

**Statement**

The system shall display the current approved status of an order to its authorized customer.

**Source:** STK-01 Customer  
**Priority:** Must  
**Evidence:** SECONDARY_SUPPORTED / DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

When an authorized customer opens an eligible order, the current stored status shall be displayed.

---

# 7. Simulated Payment Requirements

## FR-ORDER-014 — Select Supported Payment Method

**Statement**

The system shall allow a customer to select from the payment methods supported by the academic MVP.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

The initial MVP may use simulated payment methods rather than real financial processing.

---

## FR-ORDER-015 — Record Simulated Payment Status

**Statement**

The system shall record the simulated payment status associated with an order.

**Source:** Business Logic  
**Priority:** Should  
**Evidence:** TECHNICAL / ACADEMIC  
**Status:** DRAFT

Possible status values may include:

```text
PENDING
PAID_SIMULATED
FAILED_SIMULATED
```

The exact model will be finalized during design.

---

## FR-ORDER-016 — Display Payment Status

**Statement**

The system shall allow an authorized customer to view the payment status recorded for their order.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

---

# 8. Real Payment Gateway Requirement

## IR-PAY-001 — Real Payment Integration

**Status:** DEFERRED

**Priority:** Won't Have Now

Real payment gateway integration shall not be a mandatory dependency of the academic MVP.

A future approved integration may support providers such as a payment gateway or mobile financial service through appropriate APIs.

No real payment-provider requirement shall be treated as implemented until the integration is explicitly approved.

---

# 9. Review Requirements

## FR-REV-001 — View Product Reviews

**Statement**

The system shall allow users to view eligible published reviews associated with a product.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** SECONDARY_SUPPORTED  
**Status:** DRAFT

**Acceptance Criteria**

The product-review view shall display eligible reviews without exposing private customer data beyond approved public reviewer information.

---

## FR-REV-002 — Submit Product Rating

**Statement**

The system shall allow an eligible authenticated customer to submit a rating for a product associated with an eligible completed purchase.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

**Related Business Rule:** BR-REV-001

**Acceptance Criteria**

A customer who satisfies the approved review-eligibility rule shall be able to submit a valid rating.

An ineligible user shall not be allowed to submit the review successfully.

---

## FR-REV-003 — Submit Product Review

**Statement**

The system shall allow an eligible authenticated customer to submit review text for a product associated with an eligible purchase.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

**Related Business Rule:** BR-REV-001

---

## FR-REV-004 — Prevent Unauthorized Review Modification

**Statement**

The system shall prevent an artisan from editing or deleting a legitimate customer review through normal artisan functionality.

**Source:** STK-01 / Platform Governance  
**Priority:** Must  
**Evidence:** SECURITY / BUSINESS  
**Status:** DRAFT

---

## FR-REV-005 — Moderate Review

**Statement**

The system shall allow an authorized administrator to take approved moderation actions on reviews that violate platform rules.

**Source:** STK-03 Administrator  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

Normal customers and artisans shall not receive administrator-level review moderation functionality.

---

# 10. Related Business Rules

The following rules will be formalized in the Business Rule Register.

## BR-CART-001

A cart item quantity must be valid and must not violate the approved availability rule.

## BR-ORDER-001

A confirmed standard order must belong to exactly one customer account.

## BR-ORDER-002

Order items must preserve the applicable transaction-time product information needed for historical consistency.

## BR-ORDER-003

An order may transition only through permitted standard-order states.

## BR-ORDER-004

Only authorized actors may perform an order-state transition.

## BR-REV-001

A customer may submit a product review only when the customer satisfies the approved purchase-eligibility condition.

## BR-REV-002

An artisan shall not remove a legitimate review merely because the review is unfavorable.

---

# 11. Order Status Direction

The exact standard-order state model will be finalized during workflow design.

A provisional example is:

```text
PENDING
   ↓
CONFIRMED
   ↓
PROCESSING
   ↓
READY_TO_SHIP
   ↓
SHIPPED
   ↓
DELIVERED
```

Possible terminal states:

```text
CANCELLED
```

The project should avoid unnecessary status complexity.

---

# 12. Standard Order vs Custom Order

These two workflows must remain conceptually separate.

## Standard Order

```text
Existing Product
→ Cart
→ Checkout
→ Order
```

## Custom Order

```text
Requirements
→ Artisan Review
→ Quote
→ Customer Approval
→ Production
```

A custom-order request should not be forced through the normal cart workflow before its quotation and approval conditions are satisfied.

---

# 13. Commerce Security Dependencies

These functional requirements depend on security controls for:

- Cart ownership
- Order ownership
- Authorization
- Price manipulation prevention
- Input validation
- Review eligibility
- Admin moderation
- Customer-data privacy

Example:

A customer-visible total should not be trusted as the authoritative order total merely because it came from the browser.

The server must enforce approved business rules.

---

# 14. Traceability Examples

| Stakeholder / Need | Requirement |
|---|---|
| Customer needs cart | FR-CART-001 through FR-CART-005 |
| Customer needs checkout | FR-ORDER-001 through FR-ORDER-004 |
| Customer needs stable order record | FR-ORDER-005 through FR-ORDER-008 |
| Customer needs tracking | FR-ORDER-012, FR-ORDER-013 |
| Academic MVP needs payment flow without real transaction risk | FR-ORDER-014 through FR-ORDER-016 |
| Customer needs trustworthy reviews | FR-REV-001 through FR-REV-005 |

---

# 15. Acceptance Test Direction

Future test IDs may include:

```text
TC-CART-001
TC-CART-002

TC-ORDER-001
TC-ORDER-002

TC-REV-001
TC-REV-002
```

Examples:

### TC-ORDER Example

Customer A attempts to access Customer B's order.

Expected:

```text
ACCESS DENIED
```

### TC-REV Example

Customer without an eligible completed purchase attempts to review a product.

Expected:

```text
REVIEW REJECTED
```

---

# 16. Part 2 Requirement Count

| Module | Current Requirements |
|---|---:|
| Cart | 5 |
| Standard Order / Checkout / Payment | 16 |
| Review | 5 |
| Deferred Integration | 1 |
| **Functional Total** | **26** |

Requirement count may change after detailed review.

---

# 17. Current MVP Decision

## Must

- Cart
- Checkout
- Order creation
- Order ownership
- Order status
- Price snapshot
- Authorization

## Should

- Order history
- Simulated payment
- Product reviews
- Review moderation

## Deferred

- Real payment gateway

---

# 18. Requirement Quality Boundary

The commerce module should not be described as complete merely because:

```text
Cart Page exists
+
Checkout Page exists
```

A complete commerce feature also requires:

```text
Data
+
Backend Logic
+
Business Rules
+
Authorization
+
Validation
+
UI
+
Testing
```

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Functional Requirements Baseline Part 2  
**Modules:** CART, ORDER, REV  
**Status:** Draft v0.1  
**Real Payment:** Deferred  
**Next Step:** Structured Custom-Order Functional Requirements
