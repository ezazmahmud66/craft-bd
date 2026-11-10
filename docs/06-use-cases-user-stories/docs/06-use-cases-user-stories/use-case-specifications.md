# Craft BD — Core Use Case Specifications

**Phase:** 06 — Use Cases & User Stories  
**Version:** 0.1  
**Source:** Craft BD SRS v0.1  
**Status:** Draft Baseline

---

# UC-AUTH-003 — Login

**Primary Actor:** Visitor  
**Goal:** Authenticate and access authorized Craft BD functionality.

**Preconditions**
- User account exists.
- Account is eligible for login.

**Trigger**
User submits login credentials.

**Main Flow**
1. User enters credentials.
2. System validates input.
3. System verifies credentials.
4. System authenticates the user.
5. System identifies the user's role.
6. System provides authorized access.

**Alternative / Failure Flow**
- Invalid credentials → login rejected.
- Invalid input → validation message displayed.
- Unauthorized/inactive account → access denied.

**Postcondition**
Authenticated session exists for a valid user.

**Related Requirements:** `FR-AUTH-003`, `FR-AUTH-005`

---

# UC-DISC-001 — Browse and Search Products

**Primary Actor:** Visitor / Customer  
**Goal:** Discover available Craft BD products.

**Preconditions**
- Public catalog is available.

**Main Flow**
1. User opens product catalog.
2. System displays eligible products.
3. User enters search or supported filter criteria.
4. System validates criteria.
5. System returns matching eligible products.
6. User may select a product.

**Alternative Flow**
- No results → system displays an appropriate empty-result message.
- Invalid filter → request rejected or normalized safely.

**Postcondition**
User receives eligible discovery results.

**Related Requirements:** `FR-DISC-001`, `FR-DISC-003–008`

---

# UC-PROD-001 — Create Product

**Primary Actor:** Artisan  
**Goal:** Add a new product to the artisan's catalog.

**Preconditions**
- Artisan is authenticated.
- Artisan has authorization to create products.

**Main Flow**
1. Artisan opens product creation form.
2. Artisan enters required product information.
3. Artisan uploads supported images where required.
4. System validates data.
5. System verifies category and artisan relationship.
6. Product is stored.
7. System confirms successful creation.

**Failure Flow**
- Invalid price/stock/category → product rejected.
- Invalid image → upload rejected.
- Unauthorized user → access denied.

**Postcondition**
A valid product record exists and belongs to the artisan.

**Related Requirements:** `FR-PROD-001`, `FR-PROD-004–010`

---

# UC-CART-001 — Manage Shopping Cart

**Primary Actor:** Customer  
**Goal:** Prepare products for standard checkout.

**Preconditions**
- Customer is authenticated.
- Product is eligible for normal ordering.

**Main Flow**
1. Customer adds product to cart.
2. System validates product and quantity.
3. System stores cart item.
4. Customer may update quantity.
5. Customer may remove items.
6. System recalculates authoritative totals.
7. Customer views updated cart.

**Failure Flow**
- Invalid quantity → rejected.
- Unavailable product → rejected.
- Another customer's cart → access denied.

**Postcondition**
Customer's active cart contains valid selected items.

**Related Requirements:** `FR-CART-001–005`

---

# UC-ORDER-001 — Place Standard Order

**Primary Actor:** Customer  
**Goal:** Confirm purchase of eligible cart products.

**Preconditions**
- Customer is authenticated.
- Cart contains eligible products.

**Main Flow**
1. Customer initiates checkout.
2. System validates cart.
3. Customer enters delivery information.
4. Customer reviews order summary.
5. Customer selects supported payment option.
6. Customer explicitly confirms order.
7. System creates Order and Order Items.
8. System stores transaction-time prices.
9. System assigns initial order status.
10. Purchased cart items are cleared.
11. Confirmation is displayed.

**Failure Flow**
- Empty cart → checkout denied.
- Invalid delivery data → confirmation blocked.
- Invalid/unavailable product → order blocked.
- Server failure → order shall not be falsely shown as successful.

**Postcondition**
Persistent confirmed Order exists.

**Related Requirements:** `FR-ORDER-001–010`, `BR-ORDER-*`

---

# UC-ORDER-002 — Track Standard Order

**Primary Actor:** Customer  
**Goal:** View own order details and current status.

**Preconditions**
- Customer is authenticated.
- Order belongs to Customer.

**Main Flow**
1. Customer opens order history.
2. System returns Customer-owned orders.
3. Customer selects an order.
4. System validates ownership.
5. System displays order details and current status.

**Failure Flow**
- Unknown order → not found.
- Another customer's order → access denied.

**Postcondition**
No transaction data is modified.

**Related Requirements:** `FR-ORDER-011–013`

---

# UC-CUSTOM-001 — Submit Custom Request

**Primary Actor:** Customer  
**Status:** PROVISIONAL  
**Goal:** Submit structured customization requirements to an artisan.

**Preconditions**
- Customer is authenticated.
- Target artisan/product context is eligible.

**Main Flow**
1. Customer starts a custom request.
2. Customer provides required customization information.
3. Customer may upload reference image.
4. Customer submits request.
5. System validates fields and file.
6. System creates Custom Request.
7. System associates Customer and Artisan.
8. Initial status becomes `REQUESTED`.
9. Artisan is made aware of the request.

**Failure Flow**
- Invalid quantity/data → rejected.
- Invalid upload → rejected.
- Unauthorized access → denied.

**Postcondition**
Valid Custom Request exists.

**Related Requirements:** `FR-CUSTOM-001–013`

---

# UC-CUSTOM-003 — Create and Submit Quotation

**Primary Actor:** Artisan  
**Status:** PROVISIONAL  
**Goal:** Provide a commercial proposal for a Custom Request.

**Preconditions**
- Artisan is authenticated.
- Request is assigned to Artisan.
- Request is eligible for quotation.

**Main Flow**
1. Artisan opens assigned request.
2. Artisan reviews Customer requirements.
3. Artisan enters quoted price.
4. Artisan enters completion estimate and notes where applicable.
5. System validates quotation.
6. Artisan submits quotation.
7. Quotation is linked to Custom Request.
8. Request becomes `QUOTED`.
9. Customer is notified where notification functionality exists.

**Failure Flow**
- Wrong artisan → access denied.
- Invalid quotation price → rejected.
- Invalid workflow state → rejected.

**Postcondition**
Valid quotation is available to Customer.

**Related Requirements:** `FR-CUSTOM-018–023`

---

# UC-CUSTOM-004 — Approve or Reject Quotation

**Primary Actor:** Customer  
**Status:** PROVISIONAL  
**Goal:** Decide whether the proposed custom work should proceed.

**Preconditions**
- Customer owns the Custom Request.
- Valid quotation exists.

**Main Flow**
1. Customer opens quotation.
2. System verifies request ownership.
3. Customer reviews price, estimate, and notes.
4. Customer selects Approve or Reject.
5. System validates current workflow state.
6. Decision is stored.
7. Decision timestamp is recorded.
8. Artisan is made aware of the decision.

**Approval Result**
Request becomes eligible for production.

**Rejection Result**
Request shall not enter production.

**Failure Flow**
- Wrong Customer → access denied.
- Already finalized quotation → invalid action rejected.

**Related Requirements:** `FR-CUSTOM-024–028`

---

# UC-CUSTOM-005 — Update Custom Order Status

**Primary Actor:** Artisan  
**Status:** PROVISIONAL  
**Goal:** Maintain progress of an approved Custom Order.

**Preconditions**
- Artisan is assigned to the request.
- Customer approved a valid quotation.

**Main Flow**
1. Artisan opens active Custom Order.
2. System verifies assignment and current state.
3. Artisan selects an allowed next state.
4. System validates transition.
5. System updates authoritative state.
6. Customer-facing status is updated.
7. Relevant notification may be generated.

**Possible States**
- `IN_PRODUCTION`
- `QUALITY_CHECK`
- `READY_TO_SHIP`
- `SHIPPED`
- `DELIVERED`

**Failure Flow**
- Production before approval → rejected.
- Invalid transition → rejected.
- Wrong artisan → access denied.

**Postcondition**
Custom Order remains in a valid workflow state.

**Related Requirements:** `FR-CUSTOM-028–033`

---

# UC-REV-001 — Submit Eligible Product Review

**Primary Actor:** Customer  
**Goal:** Submit feedback for an eligible purchase.

**Preconditions**
- Customer is authenticated.
- Customer satisfies review eligibility rule.

**Main Flow**
1. Customer selects eligible product/order.
2. System validates review eligibility.
3. Customer enters rating/review.
4. System validates input.
5. Review is stored.
6. Review is associated with Customer and Product.

**Failure Flow**
- Ineligible Customer → rejected.
- Invalid rating → rejected.

**Postcondition**
Eligible Review exists.

**Related Requirements:** `FR-REV-002`, `FR-REV-003`, `BR-REV-001`

---

# UC-ADMIN-002 — Manage Product Categories

**Primary Actor:** Administrator  
**Goal:** Maintain valid Product Categories.

**Preconditions**
- Administrator is authenticated and authorized.

**Main Flow**
1. Administrator opens category management.
2. Administrator creates, edits, or deactivates a category.
3. System validates action.
4. System stores approved change.
5. Existing historical relationships remain preserved.

**Failure Flow**
- Unauthorized actor → access denied.
- Invalid category data → rejected.
- Destructive action would violate integrity → blocked.

**Postcondition**
Category data remains valid and consistent.

**Related Requirements:** `FR-ADMIN-003–005`, `BR-ADMIN-005`

---

# Common Security Rule

All protected use cases follow:

```text
Authentication
→ Authorization
→ Ownership / Assignment
→ Business Rule
→ Validation
→ Action
```

---

# Common Failure Conditions

Across relevant use cases, the system shall safely handle:

- Invalid input
- Authentication failure
- Authorization failure
- Ownership violation
- Missing resource
- Invalid workflow transition
- Invalid file upload
- Server failure

Sensitive implementation information shall not be exposed to normal users.

---

# Use Case Traceability Summary

| Use Case | Main Requirement Range |
|---|---|
| UC-AUTH-003 | FR-AUTH-003–005 |
| UC-DISC-001 | FR-DISC-001–008 |
| UC-PROD-001 | FR-PROD-001–010 |
| UC-CART-001 | FR-CART-001–005 |
| UC-ORDER-001 | FR-ORDER-001–010 |
| UC-ORDER-002 | FR-ORDER-011–013 |
| UC-CUSTOM-001 | FR-CUSTOM-001–013 |
| UC-CUSTOM-003 | FR-CUSTOM-018–023 |
| UC-CUSTOM-004 | FR-CUSTOM-024–028 |
| UC-CUSTOM-005 | FR-CUSTOM-028–033 |
| UC-REV-001 | FR-REV-002–003 |
| UC-ADMIN-002 | FR-ADMIN-003–005 |

---

# Research Boundary

Custom-order use cases remain provisional until primary Customer and Artisan validation is completed.

Their specification describes intended system behavior, not confirmed user demand.

---

## Document Status

**Detailed Use Cases:** 12  
**Core Commerce Covered:** Yes  
**Custom Workflow Covered:** Yes  
**Administration Covered:** Yes  
**Alternative/Failure Flows:** Included  
**Requirement Traceability:** Included  
**Status:** Draft v0.1 Complete
