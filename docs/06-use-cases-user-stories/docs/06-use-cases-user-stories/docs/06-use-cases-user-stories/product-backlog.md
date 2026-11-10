# Craft BD — Product Backlog

**Phase:** 06 — Use Cases & User Stories  
**Version:** 0.1  
**Source:** Craft BD SRS v0.1 + Use Case Model  
**Status:** Draft Baseline

---

# 1. User Story Format

Craft BD user stories follow:

> As a **[actor]**, I want **[goal]**, so that **[value]**.

Acceptance Criteria use:

```text
Given
When
Then
```

Traceability:

```text
Requirement
→ Use Case
→ User Story
→ Acceptance Criteria
→ Test Case
```

---

# 2. Product Backlog

| ID | User Story | Actor | Priority | Related Use Case |
|---|---|---|---|---|
| US-001 | Login securely | Customer / Artisan / Admin | Must | UC-AUTH-003 |
| US-002 | Browse and search products | Visitor / Customer | Must | UC-DISC-001 |
| US-003 | Create and manage products | Artisan | Must | UC-PROD-001 |
| US-004 | Manage shopping cart | Customer | Must | UC-CART-001 |
| US-005 | Place standard order | Customer | Must | UC-ORDER-001 |
| US-006 | Track standard order | Customer | Must | UC-ORDER-002 |
| US-007 | Submit custom request | Customer | Provisional Must | UC-CUSTOM-001 |
| US-008 | Review custom request and send quotation | Artisan | Provisional Must | UC-CUSTOM-002 / 003 |
| US-009 | Approve or reject quotation | Customer | Provisional Must | UC-CUSTOM-004 |
| US-010 | Update and track custom-order progress | Artisan / Customer | Provisional Must | UC-CUSTOM-005 / 006 |
| US-011 | Submit eligible product review | Customer | Should | UC-REV-001 |
| US-012 | Manage categories | Administrator | Must | UC-ADMIN-002 |

---

# 3. Detailed User Stories

## US-001 — Secure Login

**User Story**

As a registered user, I want to log in securely so that I can access functionality permitted for my role.

**Priority:** Must

**Acceptance Criteria**

### AC-001
**Given** valid credentials  
**When** the user submits login  
**Then** the system authenticates the user.

### AC-002
**Given** invalid credentials  
**When** login is attempted  
**Then** authentication is rejected.

### AC-003
**Given** successful login  
**When** the session is created  
**Then** access shall follow the user's authorized role.

**Traceability:** `FR-AUTH-003–005` → `UC-AUTH-003`

---

# US-002 — Browse and Search Products

**User Story**

As a visitor or customer, I want to browse and search available handicraft products so that I can discover products relevant to me.

**Priority:** Must

**Acceptance Criteria**

- **Given** available products, **when** the catalog is opened, **then** eligible products are displayed.
- **Given** a supported search term, **when** search is performed, **then** relevant eligible products are returned.
- **Given** no matching products, **when** search completes, **then** an appropriate no-results message is displayed.

**Traceability:** `FR-DISC-001–008` → `UC-DISC-001`

---

# US-003 — Create and Manage Products

**User Story**

As an artisan, I want to create and manage my products so that customers can discover and purchase my available crafts.

**Priority:** Must

**Acceptance Criteria**

- **Given** an authenticated artisan, **when** valid product information is submitted, **then** the product is created.
- **Given** an artisan owns a product, **when** valid updates are submitted, **then** the product is updated.
- **Given** Artisan A does not own Product B, **when** Artisan A attempts modification, **then** access is denied.
- Invalid price, stock, category, or unsupported files shall be rejected.

**Traceability:** `FR-PROD-*` → `UC-PROD-001/002`

---

# US-004 — Manage Shopping Cart

**User Story**

As a customer, I want to manage products in my cart so that I can prepare the items I intend to purchase.

**Priority:** Must

**Acceptance Criteria**

- Customer can add an eligible product.
- Customer can update valid quantity.
- Customer can remove an item.
- Cart total is recalculated using authoritative values.
- Customer cannot access another customer's cart.

**Traceability:** `FR-CART-001–005` → `UC-CART-001`

---

# US-005 — Place Standard Order

**User Story**

As a customer, I want to complete checkout and place an order so that I can purchase selected handicraft products.

**Priority:** Must

**Acceptance Criteria**

### AC-001
**Given** a valid non-empty cart  
**When** the customer provides valid checkout information and confirms  
**Then** the system creates an Order.

### AC-002
**Given** an empty cart  
**When** checkout is attempted  
**Then** order creation is rejected.

### AC-003
**Given** an order is confirmed  
**When** product price later changes  
**Then** the historical Order Item price remains unchanged.

### AC-004
A successful order shall receive an approved initial state.

**Traceability:** `FR-ORDER-001–010` → `UC-ORDER-001`

---

# US-006 — Track Standard Order

**User Story**

As a customer, I want to view my order history and current order status so that I know the progress of my purchase.

**Priority:** Must

**Acceptance Criteria**

- Customer can view their own orders.
- Customer can view permitted order details.
- Current status is displayed.
- Another customer's private order shall not be accessible.

**Traceability:** `FR-ORDER-011–013` → `UC-ORDER-002`

---

# US-007 — Submit Custom Request

**User Story**

As a customer, I want to submit structured customization requirements so that an artisan can understand what custom product I want.

**Priority:** Provisional Must  
**Status:** PROVISIONAL

**Acceptance Criteria**

The customer can provide supported information including:

- Product type
- Design
- Color
- Size
- Material
- Quantity
- Reference image
- Additional instructions

A valid submission shall:

1. Create a Custom Request.
2. Associate the correct Customer.
3. Associate the intended Artisan.
4. Assign initial status `REQUESTED`.

Invalid required information or unsupported files shall be rejected.

**Traceability:** `FR-CUSTOM-001–013` → `UC-CUSTOM-001`

---

# US-008 — Review Request and Send Quotation

**User Story**

As an artisan, I want to review assigned custom requests and send quotations so that customers can decide whether to proceed.

**Priority:** Provisional Must  
**Status:** PROVISIONAL

**Acceptance Criteria**

- Artisan can access requests assigned to them.
- Artisan can view authorized customer requirements.
- Artisan can provide a valid quoted price.
- Artisan may provide completion estimate and notes.
- Submitted quotation is linked to the correct request.
- Wrong artisan access is denied.
- Valid submission moves the request to `QUOTED`.

**Traceability:** `FR-CUSTOM-014–023` → `UC-CUSTOM-002/003`

---

# US-009 — Approve or Reject Quotation

**User Story**

As a customer, I want to review and approve or reject an artisan quotation so that custom production begins only with my agreement.

**Priority:** Provisional Must  
**Status:** PROVISIONAL

**Acceptance Criteria**

### Approval

**Given** a valid quotation owned by the customer  
**When** the customer approves it  
**Then** the decision is stored and the request becomes eligible for production.

### Rejection

**Given** a valid quotation  
**When** the customer rejects it  
**Then** the request shall not enter production.

### Ownership

Another customer shall not be able to decide on the quotation.

**Traceability:** `FR-CUSTOM-024–028` → `UC-CUSTOM-004`

---

# US-010 — Update and Track Custom Order

**User Story**

As an artisan, I want to update the progress of an approved custom order, and as a customer, I want to track that progress so that both parties understand the current state.

**Priority:** Provisional Must  
**Status:** PROVISIONAL

**Acceptance Criteria**

- Production-related state cannot begin before valid quotation approval.
- Only assigned/authorized Artisan may perform protected updates.
- Invalid state transitions shall be rejected.
- Customer can view the current authorized status.

Current provisional flow:

```text
CUSTOMER_APPROVED
→ IN_PRODUCTION
→ QUALITY_CHECK
→ READY_TO_SHIP
→ SHIPPED
→ DELIVERED
```

**Traceability:** `FR-CUSTOM-028–036` → `UC-CUSTOM-005/006`

---

# US-011 — Submit Product Review

**User Story**

As an eligible customer, I want to rate and review a purchased product so that I can share my experience.

**Priority:** Should

**Acceptance Criteria**

- Eligible customer can submit rating/review.
- Ineligible customer is rejected.
- Review remains associated with Customer and Product.
- Artisan cannot remove a legitimate negative review through normal artisan functionality.

**Traceability:** `FR-REV-002–005` → `UC-REV-001`

---

# US-012 — Manage Product Categories

**User Story**

As an administrator, I want to manage product categories so that products can remain consistently organized.

**Priority:** Must

**Acceptance Criteria**

- Authorized Admin can create a valid category.
- Authorized Admin can update a category.
- Authorized Admin can deactivate a category where allowed.
- Unauthorized users are denied.
- Deactivation shall not destroy required historical relationships.

**Traceability:** `FR-ADMIN-003–005` → `UC-ADMIN-002`

---

# 4. Backlog Priority

## Priority 1 — Core Foundation

```text
US-001 Login
US-003 Product Management
US-002 Product Discovery
```

## Priority 2 — Standard Commerce

```text
US-004 Cart
US-005 Place Order
US-006 Track Order
```

## Priority 3 — Structured Custom Workflow

```text
US-007 Custom Request
US-008 Artisan Quotation
US-009 Customer Decision
US-010 Custom Status
```

These remain subject to primary validation.

## Priority 4 — Supporting

```text
US-011 Review
US-012 Category Administration
```

---

# 5. Suggested Implementation Sequence

```text
US-001
Login
 ↓
US-003
Product
 ↓
US-002
Discovery
 ↓
US-004
Cart
 ↓
US-005
Order
 ↓
US-006
Tracking
```

Then, if the custom workflow remains approved:

```text
US-007
→ US-008
→ US-009
→ US-010
```

Followed by:

```text
US-011
US-012
```

---

# 6. Definition of Ready

A User Story is ready for implementation when:

- Actor is identified
- Goal is clear
- Requirement traceability exists
- Acceptance Criteria exist
- Major dependencies are understood
- No unresolved blocker prevents development

---

# 7. Definition of Done

A User Story is complete when:

- Required behavior is implemented
- Relevant acceptance criteria pass
- Authorization/business rules are enforced
- Relevant tests pass
- Documentation is updated where needed
- Code review is complete
- Work is merged into `main`

---

# 8. Research Boundary

Stories:

```text
US-007
US-008
US-009
US-010
```

remain provisional.

They shall not be described as validated Customer/Artisan requirements until primary research supports them.

---

# 9. Backlog Traceability Summary

```text
SRS
 ↓
Use Case Model
 ↓
Use Case Specification
 ↓
User Story
 ↓
Acceptance Criteria
 ↓
GitHub Issue
 ↓
Implementation
 ↓
Test Case
```

---

## Document Status

**Product Backlog:** Complete v0.1  
**User Stories:** 12  
**Acceptance Criteria:** Included  
**Priorities:** Included  
**Use Case Traceability:** Included  
**Definition of Ready:** Included  
**Definition of Done:** Included  
**Research Boundary:** Preserved
