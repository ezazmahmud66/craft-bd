# Craft BD — Requirement ID & Classification Standard

## 1. Purpose

This document defines the identification and classification standard for Craft BD requirements.

The standard will be used across:

- Requirement baseline
- SRS
- UML
- Business rules
- Acceptance criteria
- Requirement Traceability Matrix
- Test cases
- Change requests

The goal is to ensure every important requirement has a unique and meaningful identifier.

---

# 2. Requirement ID Structure

Craft BD will use the following format:

```text
TYPE-MODULE-NNN
```

Where:

- `TYPE` = requirement category
- `MODULE` = functional or quality area
- `NNN` = sequential number beginning at `001`

Example:

```text
FR-AUTH-001
```

Meaning:

```text
FR      = Functional Requirement
AUTH    = Authentication Module
001     = Requirement Number
```

---

# 3. Main Requirement Types

The following prefixes will be used:

| Prefix | Meaning |
|---|---|
| FR | Functional Requirement |
| NFR | Non-Functional Requirement |
| BR | Business Rule |
| SR | Security Requirement |
| PR | Privacy Requirement |
| DR | Data Requirement |
| IR | Integration Requirement |
| CR | Constraint Requirement |

---

# 4. Functional Requirement Modules

## Authentication

Prefix:

```text
FR-AUTH
```

Examples:

```text
FR-AUTH-001
FR-AUTH-002
FR-AUTH-003
```

Possible areas:

- Registration
- Login
- Logout
- Account access

---

## User / Profile

Prefix:

```text
FR-USER
```

Possible areas:

- Customer profile
- Profile update
- Account information

---

## Artisan

Prefix:

```text
FR-ART
```

Possible areas:

- Artisan profile
- Expertise
- Experience
- Artisan product relationship

---

## Product

Prefix:

```text
FR-PROD
```

Possible areas:

- Create product
- Edit product
- Product details
- Product images
- Product categories

---

## Discovery

Prefix:

```text
FR-DISC
```

Possible areas:

- Browse products
- Search
- Filtering
- Category browsing

---

## Cart

Prefix:

```text
FR-CART
```

Possible areas:

- Add item
- Update quantity
- Remove item
- View cart

---

## Standard Order

Prefix:

```text
FR-ORDER
```

Possible areas:

- Checkout
- Order creation
- Order history
- Order details
- Order status

---

## Custom Order

Prefix:

```text
FR-CUSTOM
```

Possible areas:

- Submit custom request
- Structured specifications
- Artisan review
- Quotation
- Approval
- Production status

---

## Review

Prefix:

```text
FR-REV
```

Possible areas:

- Submit review
- Rating
- View reviews

---

## Craft Context

Prefix:

```text
FR-CRAFT
```

Possible areas:

- Craft story
- Origin
- Technique
- Materials
- Cultural information

---

## Verification / QR

Prefix:

```text
FR-VERIFY
```

Possible areas:

- QR-linked product record
- Verification page
- Record lookup

---

## Certificate

Prefix:

```text
FR-CERT
```

Possible areas:

- Platform certificate record
- Certificate ID
- Verification information

---

## Notification

Prefix:

```text
FR-NOTIF
```

Possible areas:

- New custom request
- Quote available
- Order-status change

---

## Administration

Prefix:

```text
FR-ADMIN
```

Possible areas:

- User management
- Category management
- Moderation
- Exceptional operations

---

# 5. Non-Functional Requirement Categories

Non-functional requirements will use:

```text
NFR-CATEGORY-NNN
```

---

## Performance

```text
NFR-PERF-001
```

Examples may relate to:

- Page response
- Search response
- API performance

---

## Usability

```text
NFR-USE-001
```

Possible areas:

- Responsive interface
- Clear navigation
- Error messages
- Usability testing

---

## Reliability

```text
NFR-REL-001
```

Possible areas:

- Data consistency
- Error recovery
- State integrity

---

## Availability

```text
NFR-AVL-001
```

Used only where realistic and measurable.

---

## Maintainability

```text
NFR-MNT-001
```

Possible areas:

- Modular structure
- Documentation
- Testing
- Coding standards

---

## Scalability

```text
NFR-SCL-001
```

Only realistic academic-scale requirements should be defined.

---

## Compatibility / Responsiveness

```text
NFR-COMP-001
```

Possible areas:

- Supported browsers
- Desktop/mobile browser layouts

---

# 6. Security Requirement IDs

Security requirements will be separated from general NFRs.

Format:

```text
SR-CATEGORY-NNN
```

Examples:

```text
SR-AUTH-001
SR-AUTHZ-001
SR-FILE-001
SR-SECRET-001
```

Possible security categories:

| Code | Area |
|---|---|
| AUTH | Authentication security |
| AUTHZ | Authorization |
| OWN | Ownership validation |
| INPUT | Input validation |
| FILE | File-upload security |
| SECRET | Secret management |
| LOG | Secure logging |
| TRANSPORT | HTTPS / secure transport |

---

# 7. Privacy Requirement IDs

Format:

```text
PR-DATA-001
```

Possible areas:

- Data minimization
- Private data access
- Customer address protection
- Custom-image privacy
- Data retention
- Demo-data handling

---

# 8. Business Rule IDs

Format:

```text
BR-MODULE-NNN
```

Examples:

```text
BR-CUSTOM-001
BR-ORDER-001
BR-REV-001
BR-PROD-001
```

Business rules define constraints on system behavior.

Example:

```text
BR-CUSTOM-001
Production must not begin before the customer approves the quotation.
```

This is different from a functional requirement.

---

# 9. Functional Requirement vs Business Rule

Example:

## Functional Requirement

```text
FR-CUSTOM-006
The system shall allow the customer to approve a quotation associated with their custom request.
```

## Business Rule

```text
BR-CUSTOM-001
A custom order may transition to production only after quotation approval.
```

The functional requirement describes:

**What the system allows.**

The business rule describes:

**What condition must be enforced.**

---

# 10. Data Requirement IDs

Format:

```text
DR-MODULE-NNN
```

Examples:

```text
DR-USER-001
DR-PROD-001
DR-ORDER-001
DR-CUSTOM-001
```

Possible use:

```text
DR-PROD-001
A product record shall store a unique product identifier.
```

Data requirements may later be reflected in the database model.

---

# 11. Integration Requirement IDs

Format:

```text
IR-SERVICE-NNN
```

Examples:

```text
IR-EMAIL-001
IR-PAY-001
IR-STORAGE-001
```

Important:

Only approved integrations should receive formal MVP requirements.

Example:

Real payment remains future scope, so payment-provider integration should not automatically enter the MVP baseline.

---

# 12. Constraint Requirement IDs

Format:

```text
CR-AREA-NNN
```

Examples:

```text
CR-PLATFORM-001
CR-BUDGET-001
CR-TIME-001
```

Example:

```text
CR-PLATFORM-001
The initial Craft BD release shall be implemented as a responsive web application.
```

---

# 13. Requirement Statement Standard

Functional requirements should normally use:

> The system shall...

Example:

```text
FR-DISC-001

The system shall allow users to browse available products.
```

Avoid vague wording such as:

> The system should provide good searching.

Prefer:

> The system shall allow users to search products using supported product attributes.

---

# 14. Requirement Record Structure

Each formal requirement should contain:

| Field | Description |
|---|---|
| ID | Unique requirement identifier |
| Title | Short requirement name |
| Statement | Clear requirement |
| Actor / Source | Stakeholder or source |
| Priority | Must / Should / Could |
| Evidence | Validation classification |
| Related Business Rule | BR reference if applicable |
| Acceptance Criteria | Testable completion condition |
| Status | Draft / Approved / Provisional / Deferred |

---

# 15. Example Functional Requirement

```text
ID:
FR-PROD-001

Title:
Create Product

Statement:
The system shall allow an authenticated artisan to create a product associated with their artisan account.

Source:
STK-02 Artisan

Priority:
Must

Evidence:
Derived / User Requirement

Related Business Rule:
BR-PROD-001

Status:
Draft
```

---

# 16. Example Custom Requirement

```text
ID:
FR-CUSTOM-001

Title:
Submit Custom Order Request

Statement:
The system shall allow an authenticated customer to submit a custom-order request containing the required customization information.

Source:
STK-01 Customer
STK-02 Artisan

Priority:
Must — Provisional

Evidence:
Provisional

Status:
Pending Primary Validation
```

---

# 17. Example Security Requirement

```text
ID:
SR-OWN-001

Title:
Product Ownership Validation

Statement:
The system shall prevent an artisan from modifying a product owned by another artisan.

Source:
Security Design
STK-02 Artisan

Priority:
Must

Evidence:
Derived Security Requirement
```

---

# 18. Example Non-Functional Requirement

Instead of:

> The system should be user friendly.

Use:

```text
ID:
NFR-USE-001

Title:
Responsive Interface

Statement:
The Craft BD user interface shall support both desktop and mobile browser layouts without loss of access to core workflows.
```

This is more testable.

---

# 19. Requirement Numbering Rule

Numbers are sequential **within each module**.

Example:

```text
FR-AUTH-001
FR-AUTH-002
FR-AUTH-003

FR-PROD-001
FR-PROD-002

FR-CUSTOM-001
FR-CUSTOM-002
```

Do not use:

```text
FR-1
FR-6
FR-14
FR-21
```

with unexplained gaps.

---

# 20. Deleted Requirement Rule

Once a formal requirement ID has been used in an approved baseline, the ID should not be reused for another requirement.

Example:

If:

```text
FR-CUSTOM-004
```

is removed later, do not rename another requirement to `FR-CUSTOM-004`.

Instead mark:

```text
FR-CUSTOM-004 — Removed / Deprecated
```

This preserves traceability.

---

# 21. Draft-Stage Rule

Before the first approved formal baseline, requirement IDs may still be reorganized.

After baseline approval:

```text
ID Stability
=
Required
```

Changes should occur through requirement change control.

---

# 22. Requirement Priority Standard

Use MoSCoW:

```text
Must
Should
Could
Won't / Deferred
```

Example:

```text
FR-CUSTOM-001
Priority: Must — Provisional
```

For a validated mandatory feature:

```text
Priority: Must
```

---

# 23. Evidence Classification Standard

Each requirement should use one of:

```text
PRIMARY_VALIDATED
SECONDARY_SUPPORTED
DERIVED
TECHNICAL
SECURITY
LEGAL
ACADEMIC
PROVISIONAL
```

Example:

```text
FR-CUSTOM-001
Evidence: PROVISIONAL
```

---

# 24. Requirement Status Standard

Use:

```text
DRAFT
PROVISIONAL
APPROVED
DEFERRED
REJECTED
DEPRECATED
```

Examples:

```text
FR-PROD-001
Status: DRAFT
```

```text
FR-CUSTOM-001
Status: PROVISIONAL
```

```text
FR-RECOMMEND-001
Status: DEFERRED
```

---

# 25. Acceptance Criteria Rule

A requirement should eventually have at least one verifiable acceptance criterion.

Example:

Requirement:

```text
FR-CART-001
The system shall allow a customer to add an available product to the cart.
```

Acceptance criteria:

```text
Given an authenticated customer
and an available product,

when the customer selects Add to Cart,

then the product shall appear in the customer's cart
with the selected quantity.
```

---

# 26. Traceability Standard

Future traceability should use identifiers such as:

```text
STK-01
↓
PP-01
↓
FR-CUSTOM-001
↓
UC-CUSTOM-01
↓
BR-CUSTOM-001
↓
TC-CUSTOM-001
```

Meaning:

```text
Stakeholder
→ Pain Point
→ Requirement
→ Use Case
→ Business Rule
→ Test Case
```

---

# 27. Future Test Case Naming

To maintain consistency, test cases may later use:

```text
TC-MODULE-NNN
```

Examples:

```text
TC-AUTH-001
TC-PROD-001
TC-CUSTOM-001
```

This allows direct requirement-to-test mapping.

---

# 28. Future Use Case Naming

Use cases may later use:

```text
UC-MODULE-NNN
```

Examples:

```text
UC-AUTH-001
UC-ORDER-001
UC-CUSTOM-001
```

---

# 29. Naming Consistency Example

A custom-order requirement may eventually be traced as:

```text
STK-01
Customer
      ↓

PP-01
Requirement Ambiguity
      ↓

FR-CUSTOM-001
Submit Custom Request
      ↓

UC-CUSTOM-001
Submit Custom Order
      ↓

BR-CUSTOM-001
Approval Required Before Production
      ↓

TC-CUSTOM-001
Verify Custom Request Submission
```

---

# 30. Module Code Standard

Current approved module codes:

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

New module codes should be added only when necessary.

---

# 31. Classification Decision

Craft BD will use:

```text
FR    Functional Requirement
NFR   Non-Functional Requirement
BR    Business Rule
SR    Security Requirement
PR    Privacy Requirement
DR    Data Requirement
IR    Integration Requirement
CR    Constraint Requirement
```

with module-based IDs.

---

# 32. Final Naming Examples

```text
FR-AUTH-001
FR-PROD-001
FR-DISC-001
FR-CART-001
FR-ORDER-001
FR-CUSTOM-001
FR-REV-001

BR-CUSTOM-001
BR-REV-001

SR-AUTHZ-001
SR-OWN-001

PR-DATA-001

NFR-PERF-001
NFR-USE-001
NFR-MNT-001
```

---

# 33. Engineering Decision

The module-based naming convention is preferred because it provides:

- Clear ownership
- Easier navigation
- Better traceability
- Easier testing
- Easier SRS maintenance
- Better support for requirement changes

This replaces the inconsistent numbering found in the original Requirement Analysis.

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Requirement ID & Classification Standard  
**Status:** Approved for Phase 04 Drafting  
**Naming Convention:** `TYPE-MODULE-NNN`  
**Next Step:** Functional Requirement Baseline
