# Craft BD — Use Case Model

**Phase:** 06 — Use Cases & User Stories  
**Version:** 0.1  
**Source:** `docs/05-srs/SRS.md`  
**Status:** Draft Baseline

---

# 1. Purpose

This document defines the actors and major use cases of Craft BD based on the approved SRS v0.1.

Traceability direction:

```text
SRS Requirement
      ↓
Use Case
      ↓
User Story
      ↓
Acceptance Criteria
      ↓
Test Case
```

No unsupported functionality is introduced in this model.

---

# 2. Actors

## ACT-01 — Visitor

A non-authenticated user who may:

- Browse products
- Search products
- View product details
- View public artisan information
- View public Craft BD verification records where implemented
- Register
- Login

---

## ACT-02 — Customer

An authenticated user who may:

- Manage own profile
- Discover products
- Manage cart
- Place standard orders
- Track own orders
- Submit custom requests
- Review quotations
- Track custom orders
- Submit eligible reviews
- View notifications

---

## ACT-03 — Artisan / Seller

An authenticated seller who may:

- Manage own artisan profile
- Manage own products
- Review assigned custom requests
- Create quotations
- Manage approved custom-order progress
- Perform authorized order-status operations

---

## ACT-04 — Administrator

An authorized governance user who may:

- Manage user status
- Manage categories
- Moderate platform content
- Moderate reviews
- Handle approved exceptional cases
- Manage verification records where implemented
- Manage certificate records where implemented

---

# 3. Use Case Inventory

## 3.1 Authentication & Public Discovery

| ID | Use Case | Primary Actor | Priority |
|---|---|---|---|
| UC-AUTH-001 | Register Customer Account | Visitor | Must |
| UC-AUTH-002 | Register Artisan Account | Visitor | Must |
| UC-AUTH-003 | Login | Visitor | Must |
| UC-AUTH-004 | Logout | Customer / Artisan / Admin | Must |
| UC-DISC-001 | Browse and Search Products | Visitor / Customer | Must |
| UC-DISC-002 | View Product Details | Visitor / Customer | Must |
| UC-ART-001 | View Artisan Profile | Visitor / Customer | Must |

---

## 3.2 Customer Profile & Standard Commerce

| ID | Use Case | Primary Actor | Priority |
|---|---|---|---|
| UC-USER-001 | Manage Own Profile | Customer | Should |
| UC-CART-001 | Manage Shopping Cart | Customer | Must |
| UC-ORDER-001 | Place Standard Order | Customer | Must |
| UC-ORDER-002 | View Order Details and Track Status | Customer | Must |
| UC-REV-001 | Submit Eligible Product Review | Customer | Should |
| UC-NOTIF-001 | View Notifications | Customer / Artisan | Should |

---

## 3.3 Artisan Product Management

| ID | Use Case | Primary Actor | Priority |
|---|---|---|---|
| UC-ART-002 | Manage Own Artisan Profile | Artisan | Must |
| UC-PROD-001 | Create Product | Artisan | Must |
| UC-PROD-002 | Update / Deactivate Own Product | Artisan | Must |
| UC-ORDER-003 | Update Authorized Order Status | Artisan | Must |

---

# 4. Structured Custom Order Use Cases

These use cases remain **PROVISIONAL** because primary Customer and Artisan validation is still pending.

| ID | Use Case | Primary Actor | Status |
|---|---|---|---|
| UC-CUSTOM-001 | Submit Custom Request | Customer | Provisional Must |
| UC-CUSTOM-002 | Review Assigned Custom Request | Artisan | Provisional Must |
| UC-CUSTOM-003 | Create and Submit Quotation | Artisan | Provisional Must |
| UC-CUSTOM-004 | Review and Approve/Reject Quotation | Customer | Provisional Must |
| UC-CUSTOM-005 | Update Custom Order Status | Artisan | Provisional Must |
| UC-CUSTOM-006 | Track Custom Order | Customer | Provisional Must |
| UC-CUSTOM-007 | Request Eligible Cancellation | Customer | Provisional Should |

---

# 5. Administration Use Cases

| ID | Use Case | Primary Actor | Priority |
|---|---|---|---|
| UC-ADMIN-001 | Manage User Status | Administrator | Must |
| UC-ADMIN-002 | Manage Product Categories | Administrator | Must |
| UC-ADMIN-003 | Moderate Platform Content | Administrator | Should |
| UC-ADMIN-004 | Moderate Reviews | Administrator | Should |
| UC-ADMIN-005 | Handle Exceptional Order Case | Administrator | Should |

---

# 6. Conditional Supporting Use Cases

## Verification

| ID | Use Case | Actor | Status |
|---|---|---|---|
| UC-VERIFY-001 | View QR-Linked Verification Record | Visitor / Customer | Conditional Should |
| UC-VERIFY-002 | Manage Verification Record | Administrator | Conditional Should |

A Craft BD verification record represents a platform-maintained record.

It does not independently guarantee physical-product authenticity.

---

## Certificate

| ID | Use Case | Actor | Status |
|---|---|---|---|
| UC-CERT-001 | View Platform Certificate Record | Visitor / Customer | Could |
| UC-CERT-002 | Manage Platform Certificate Record | Administrator | Could |

Craft BD platform certificates shall not be represented as government certification unless an approved external authority is integrated.

---

# 7. High-Level Use Case Model

```text
                         ┌────────────────────────────┐
                         │          Craft BD          │
                         │                            │
Visitor ────────────────►│ Register / Login           │
Visitor ────────────────►│ Browse / Search Products   │
Visitor ────────────────►│ View Product Details       │
Visitor ────────────────►│ View Artisan Profile       │
                         │                            │
Customer ───────────────►│ Manage Profile             │
Customer ───────────────►│ Manage Cart                │
Customer ───────────────►│ Place Standard Order       │
Customer ───────────────►│ Track Order                │
Customer ───────────────►│ Submit Review              │
                         │                            │
Customer ───────────────►│ Submit Custom Request      │
Customer ───────────────►│ Review Quotation           │
Customer ───────────────►│ Track Custom Order         │
                         │                            │
Artisan ────────────────►│ Manage Artisan Profile     │
Artisan ────────────────►│ Manage Products            │
Artisan ────────────────►│ Review Custom Request      │
Artisan ────────────────►│ Create Quotation           │
Artisan ────────────────►│ Update Order Status        │
                         │                            │
Administrator ─────────►│ Manage Users               │
Administrator ─────────►│ Manage Categories          │
Administrator ─────────►│ Moderate Content           │
Administrator ─────────►│ Handle Exceptions          │
                         └────────────────────────────┘
```

---

# 8. Core Standard Commerce Flow

```text
Customer
   ↓
UC-DISC-001
Browse / Search
   ↓
UC-DISC-002
View Product
   ↓
UC-CART-001
Manage Cart
   ↓
UC-ORDER-001
Place Order
   ↓
UC-ORDER-002
Track Order
   ↓
UC-REV-001
Submit Eligible Review
```

---

# 9. Custom Order Use Case Flow

```text
Customer
   ↓
UC-CUSTOM-001
Submit Custom Request
   ↓
Artisan
UC-CUSTOM-002
Review Request
   ↓
UC-CUSTOM-003
Create Quotation
   ↓
Customer
UC-CUSTOM-004
Approve / Reject
   ↓
[If Approved]
   ↓
Artisan
UC-CUSTOM-005
Update Production Status
   ↓
Customer
UC-CUSTOM-006
Track Custom Order
```

Important rule:

```text
Quotation Approval
      ↓
Required Before
      ↓
Production
```

---

# 10. Actor–Use Case Matrix

| Use Case Area | Visitor | Customer | Artisan | Admin |
|---|:---:|:---:|:---:|:---:|
| Register / Login | ✓ | ✓ | ✓ | ✓ |
| Browse Products | ✓ | ✓ | — | — |
| View Artisan | ✓ | ✓ | — | — |
| Manage Customer Profile | — | ✓ | — | — |
| Manage Artisan Profile | — | — | ✓ | — |
| Manage Products | — | — | ✓ | — |
| Cart | — | ✓ | — | — |
| Standard Order | — | ✓ | Limited | Exception |
| Custom Request | — | ✓ | Review | Exception |
| Quotation | — | Decision | Create | Exception |
| Custom Status | — | View | Update | Exception |
| Review | View | Submit | View | Moderate |
| Notifications | — | ✓ | ✓ | — |
| Verification | View | View | — | Manage |
| Certificate | View | View | — | Manage |
| Categories | — | — | — | Manage |

---

# 11. Important Use Case Relationships

## Standard Commerce

`UC-ORDER-001 — Place Standard Order`

requires:

- Authenticated Customer
- Eligible Product
- Valid Cart
- Valid Checkout Information

---

## Review

`UC-REV-001 — Submit Eligible Product Review`

requires:

```text
Eligible Purchase
→ Review Permission
```

---

## Custom Production

`UC-CUSTOM-005 — Update Custom Order Status`

for production-related states requires:

```text
Valid Quotation
+
Customer Approval
```

---

## Ownership

Protected use cases require:

```text
Authentication
→ Authorization
→ Ownership / Assignment
→ Business Rule Validation
```

---

# 12. Out-of-Scope Actors

The following are not current mandatory MVP actors:

- Payment Gateway
- Courier Provider
- External Certification Authority
- Analytics Provider
- Blockchain Network

They shall only become formal system actors if their integrations are approved later.

---

# 13. Traceability Examples

| Requirement | Use Case |
|---|---|
| FR-AUTH-001 | UC-AUTH-001 |
| FR-PROD-001 | UC-PROD-001 |
| FR-CART-001–005 | UC-CART-001 |
| FR-ORDER-001–009 | UC-ORDER-001 |
| FR-ORDER-011–013 | UC-ORDER-002 |
| FR-REV-002–003 | UC-REV-001 |
| FR-CUSTOM-001–013 | UC-CUSTOM-001 |
| FR-CUSTOM-014–017 | UC-CUSTOM-002 |
| FR-CUSTOM-018–023 | UC-CUSTOM-003 |
| FR-CUSTOM-024–028 | UC-CUSTOM-004 |
| FR-CUSTOM-029–033 | UC-CUSTOM-005 |
| FR-CUSTOM-034–036 | UC-CUSTOM-006 |
| FR-ADMIN-001–002 | UC-ADMIN-001 |
| FR-ADMIN-003–005 | UC-ADMIN-002 |

---

# 14. Use Cases Selected for Detailed Specification

To keep Phase 06 manageable, detailed specifications will focus on the most important workflows:

1. `UC-AUTH-003` — Login
2. `UC-DISC-001` — Browse and Search Products
3. `UC-PROD-001` — Create Product
4. `UC-CART-001` — Manage Shopping Cart
5. `UC-ORDER-001` — Place Standard Order
6. `UC-ORDER-002` — Track Standard Order
7. `UC-CUSTOM-001` — Submit Custom Request
8. `UC-CUSTOM-003` — Create Quotation
9. `UC-CUSTOM-004` — Approve / Reject Quotation
10. `UC-CUSTOM-005` — Update Custom Order Status
11. `UC-REV-001` — Submit Eligible Review
12. `UC-ADMIN-002` — Manage Product Categories

Other use cases remain represented in the overall Use Case Model and may be expanded later if required.

---

# 15. Research Boundary

The following use cases remain provisional:

- UC-CUSTOM-001
- UC-CUSTOM-002
- UC-CUSTOM-003
- UC-CUSTOM-004
- UC-CUSTOM-005
- UC-CUSTOM-006
- UC-CUSTOM-007

Documenting these use cases does not mean primary user validation has been completed.

---

## Document Status

**Use Case Model:** Complete v0.1  
**Actors Defined:** Yes  
**Use Case Inventory:** Complete  
**Actor Mapping:** Complete  
**Requirement Mapping:** Included  
**Unsupported External Actors:** Excluded  
**Custom Order Research Boundary:** Preserved
