# Craft BD — Sequence Diagrams

**Phase:** 07 — UML & System Analysis  
**Version:** 0.1  
**Source:** SRS v0.1 + Phase 06 Use Cases

---

# 1. Login Sequence Diagram

```mermaid
sequenceDiagram
    actor U as User
    participant UI as Web UI
    participant API as Backend/API
    participant DB as Database

    U->>UI: Enter email and password
    UI->>API: Submit login request
    API->>API: Validate input
    API->>DB: Find user account
    DB-->>API: User + password hash + role

    alt Valid credentials
        API->>API: Verify password
        API->>API: Create authenticated session/token
        API-->>UI: Login success + authorized role
        UI-->>U: Show authorized dashboard
    else Invalid credentials
        API-->>UI: Authentication failed
        UI-->>U: Show safe error message
    end
```

## Main Rules

- Password shall not be stored as readable plain text.
- Invalid credentials shall not create a session.
- Role controls protected functionality.
- Login errors shall not expose sensitive internal information.

**Traceability:**  
`FR-AUTH-003–005 → UC-AUTH-003 → US-001`

---

# 2. Standard Order Sequence Diagram

```mermaid
sequenceDiagram
    actor C as Customer
    participant UI as Web UI
    participant API as Backend/API
    participant DB as Database

    C->>UI: Open cart
    UI->>API: Request customer cart
    API->>DB: Load owned cart and items
    DB-->>API: Cart data
    API-->>UI: Cart + authoritative totals

    C->>UI: Proceed to checkout
    C->>UI: Enter delivery information
    UI->>API: Submit checkout data

    API->>API: Validate customer and checkout
    API->>DB: Validate products, prices and availability
    DB-->>API: Valid product data

    alt Checkout valid
        API->>DB: Create Order
        API->>DB: Create OrderItems
        API->>DB: Store transaction-time prices
        API->>DB: Assign initial order status
        API->>DB: Clear purchased cart items
        DB-->>API: Order created
        API-->>UI: Order confirmation
        UI-->>C: Display order ID and status
    else Checkout invalid
        API-->>UI: Validation/business-rule error
        UI-->>C: Show correction message
    end
```

## Important Rules

```text
Browser-submitted total
≠
Authoritative order total
```

Backend shall verify:

- Product availability
- Quantity
- Current authoritative price
- Customer ownership
- Required delivery information

Historical order prices shall remain unchanged if the current Product price changes later.

**Traceability:**  
`FR-CART-* + FR-ORDER-001–010 → UC-ORDER-001 → US-004/005`

---

# 3. Custom Request → Quotation → Approval Sequence Diagram

**Status:** PROVISIONAL

```mermaid
sequenceDiagram
    actor C as Customer
    actor A as Artisan
    participant UI as Web UI
    participant API as Backend/API
    participant DB as Database

    C->>UI: Enter custom requirements
    UI->>API: Submit custom request
    API->>API: Validate request and ownership
    API->>DB: Create CustomRequest
    API->>DB: Set status = REQUESTED
    DB-->>API: Request created
    API-->>UI: Submission success

    A->>UI: Open assigned requests
    UI->>API: Request assigned custom requests
    API->>DB: Load requests assigned to artisan
    DB-->>API: Assigned request data
    API-->>UI: Display request

    A->>UI: Enter quotation
    UI->>API: Submit quoted price, estimate, notes
    API->>API: Validate artisan assignment
    API->>DB: Create Quotation
    API->>DB: Set request status = QUOTED
    DB-->>API: Quotation saved
    API-->>UI: Quotation submitted

    C->>UI: Open quotation
    UI->>API: Request quotation
    API->>API: Verify request ownership
    API->>DB: Load quotation
    DB-->>API: Quotation data
    API-->>UI: Display quotation

    alt Customer approves
        C->>UI: Approve quotation
        UI->>API: Submit approval
        API->>API: Verify ownership and current state
        API->>DB: Record APPROVED decision
        API->>DB: Set status = CUSTOMER_APPROVED
        DB-->>API: State updated
        API-->>UI: Approval successful

        A->>UI: Start production
        UI->>API: Request IN_PRODUCTION
        API->>API: Verify approval + artisan assignment
        API->>DB: Set status = IN_PRODUCTION
        DB-->>API: State updated
        API-->>UI: Production status updated

    else Customer rejects
        C->>UI: Reject quotation
        UI->>API: Submit rejection
        API->>DB: Record REJECTED decision
        DB-->>API: Decision stored
        API-->>UI: Rejection confirmed
    end
```

## Critical Rule

Production requires:

```text
Valid Quotation
      +
Customer Approval
      +
Assigned Artisan
```

Therefore this must be rejected:

```text
QUOTED
→ IN_PRODUCTION
```

without approval.

## Security Checks

Before protected actions:

```text
Authentication
→ Role
→ Ownership / Assignment
→ Current State
→ Business Rule
→ Action
```

**Traceability:**  
`FR-CUSTOM-001–033 → UC-CUSTOM-001/003/004/005 → US-007–010`

---

# 4. Sequence Diagram Summary

| Diagram | Primary Actors | Main Purpose |
|---|---|---|
| Login | User | Authentication and role recognition |
| Standard Order | Customer | Cart-to-order transaction |
| Custom Workflow | Customer + Artisan | Request, quotation, approval, production guard |

---

# 5. System Analysis Observation

The three diagrams expose three important backend responsibilities:

```text
Authentication Flow
→ Identity + Authorization
```

```text
Commerce Flow
→ Data + Transaction Integrity
```

```text
Custom Flow
→ Ownership + State-Machine Integrity
```

These responsibilities will later influence:

- Architecture
- API design
- Database design
- Security
- Integration testing

---

# Research Boundary

The Custom Order sequence remains **PROVISIONAL** until primary Customer and Artisan validation is completed.

The diagram represents current intended system behavior only.

---

## Document Status

**Sequence Diagrams:** Complete v0.1  
**Login:** Included  
**Standard Order:** Included  
**Custom Workflow:** Included  
**Security/Business Rules:** Represented  
**Research Boundary:** Preserved
