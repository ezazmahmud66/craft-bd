# Craft BD — Activity Diagrams

**Phase:** 07 — UML & System Analysis  
**Version:** 0.1

This document contains activity models for the three main Craft BD workflows.

---

# 1. Standard Order Activity Diagram

```mermaid
flowchart TD

    A([Start]) --> B[Browse / Search Products]
    B --> C[View Product]
    C --> D{Add to Cart?}

    D -- No --> B
    D -- Yes --> E[Add Product to Cart]

    E --> F[View / Update Cart]
    F --> G{Proceed to Checkout?}

    G -- No --> F
    G -- Yes --> H[Enter Delivery Information]

    H --> I[Review Order Summary]
    I --> J{Valid Checkout Data?}

    J -- No --> K[Show Validation Error]
    K --> H

    J -- Yes --> L[Confirm Order]
    L --> M[Create Order + Order Items]
    M --> N[Store Transaction Price]
    N --> O[Assign Initial Status]
    O --> P[Clear Purchased Cart Items]
    P --> Q[Show Order Confirmation]
    Q --> R([End])
```

## Main Rules

- Empty cart cannot proceed to valid order creation.
- Transaction-time price shall be preserved.
- Order belongs to authenticated Customer.
- Invalid checkout data prevents confirmation.

---

# 2. Structured Custom Order Activity Diagram

**Status:** PROVISIONAL

```mermaid
flowchart TD

    A([Start]) --> B[Customer Creates Custom Request]
    B --> C[Enter Custom Requirements]
    C --> D[Optional Reference Image]
    D --> E[Submit Request]

    E --> F{Valid Request?}

    F -- No --> G[Show Validation Error]
    G --> C

    F -- Yes --> H[Create Request: REQUESTED]
    H --> I[Artisan Reviews Request]

    I --> J{Artisan Accepts for Quotation?}

    J -- No --> K[Set REJECTED]
    K --> Z([End])

    J -- Yes --> L[Create Quotation]
    L --> M[Set QUOTED]
    M --> N[Customer Reviews Quotation]

    N --> O{Customer Approves?}

    O -- No --> P[Record Rejection]
    P --> Z

    O -- Yes --> Q[Set CUSTOMER_APPROVED]
    Q --> R[Set IN_PRODUCTION]
    R --> S[QUALITY_CHECK]
    S --> T[READY_TO_SHIP]
    T --> U[SHIPPED]
    U --> V[DELIVERED]
    V --> Z
```

## Critical Business Rule

```text
Quotation Approved
        ↓
Required Before
        ↓
Production
```

Invalid example:

```text
QUOTED → IN_PRODUCTION
```

without Customer approval.

---

# 3. Artisan Product Creation Activity Diagram

```mermaid
flowchart TD

    A([Start]) --> B[Artisan Login]
    B --> C[Open Product Management]
    C --> D[Select Create Product]
    D --> E[Enter Product Information]
    E --> F[Upload Supported Product Images]
    F --> G[Select Valid Category]

    G --> H{Input Valid?}

    H -- No --> I[Show Validation Error]
    I --> E

    H -- Yes --> J{Authorized Artisan?}

    J -- No --> K[Access Denied]
    K --> Z([End])

    J -- Yes --> L[Create Product Record]
    L --> M[Associate Product with Artisan]
    M --> N[Store Image References]
    N --> O[Confirm Product Creation]
    O --> Z
```

## Important Rules

- Product must belong to the authenticated Artisan.
- Product price and stock must be valid.
- Category must be valid.
- Unsupported files must be rejected.
- Another Artisan cannot manage the Product.

---

# 4. Workflow Comparison

| Workflow | Main Actor | Main Decision |
|---|---|---|
| Standard Order | Customer | Checkout valid? |
| Custom Order | Customer + Artisan | Quotation approved? |
| Product Creation | Artisan | Product data valid and authorized? |

---

# 5. System Analysis Observation

The activity models show three different workflow styles:

### Transaction Workflow

```text
Product → Cart → Checkout → Order
```

### Negotiation Workflow

```text
Request → Quote → Approval → Production
```

### Resource Management Workflow

```text
Artisan → Product Data → Validation → Product Record
```

This distinction will guide later Sequence, Class, API, and testing design.

---

## Status

**Activity Diagrams:** Complete v0.1  
**Standard Order:** Included  
**Structured Custom Order:** Included  
**Product Creation:** Included  
**Research Boundary:** Preserved
