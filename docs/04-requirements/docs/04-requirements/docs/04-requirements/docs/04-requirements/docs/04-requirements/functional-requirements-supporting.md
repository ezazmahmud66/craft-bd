# Craft BD — Functional Requirements Baseline Part 4

## 1. Purpose

This document defines the formal functional requirements for the supporting Craft BD modules:

- QR-linked Product Verification
- Platform Certificate Records
- Notifications
- Administration

These modules support trust, workflow visibility, and platform governance.

Some capabilities remain optional or provisional and must not delay the core MVP workflow.

---

# 2. Verification Scope

Craft BD verification functionality is intended to provide access to a platform-maintained product record.

The intended model is:

```text
QR Code
   ↓
Verification URL
   ↓
Craft BD Product Record
```

The QR code itself does not prove the physical authenticity of a product.

Therefore, the system shall use terminology such as:

- QR-linked Product Record
- Platform Verification Record

and shall avoid unsupported claims such as:

- Guaranteed Authentic Product
- Government Verified Product

unless an approved external verification process exists.

---

# 3. QR / Verification Requirements

## FR-VERIFY-001 — Generate Verification Identifier

**Statement**

The system shall allow an authorized process to assign a unique verification identifier to an eligible product record.

**Source:** STK-03 Administrator / Platform Requirement  
**Priority:** Should  
**Evidence:** PROVISIONAL / DERIVED  
**Status:** PROVISIONAL

**Acceptance Criteria**

Each active verification record shall contain an identifier that uniquely identifies the relevant Craft BD verification record.

---

## FR-VERIFY-002 — Generate QR-Linked Verification Reference

**Statement**

The system shall allow an authorized process to generate a QR code or equivalent scannable reference that links to the relevant Craft BD verification record.

**Source:** STK-01 Customer, STK-03 Administrator  
**Priority:** Should  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

**Acceptance Criteria**

Scanning or opening a valid generated reference shall direct the user to the corresponding verification record.

---

## FR-VERIFY-003 — View Verification Record

**Statement**

The system shall allow a user to view the permitted public information associated with a valid verification identifier.

**Source:** STK-01 Customer  
**Priority:** Should  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

Possible public information may include:

- Product identifier
- Product name
- Artisan
- Region
- Craft type
- Materials
- Supported production information
- Certificate record where applicable

---

## FR-VERIFY-004 — Handle Invalid Verification Identifier

**Statement**

The system shall clearly indicate when a requested verification identifier does not correspond to an active valid Craft BD verification record.

**Source:** Platform Trust Requirement  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

An invalid identifier shall not expose unrelated records and shall return an appropriate not-found or invalid-record response.

---

## FR-VERIFY-005 — Manage Verification Record Status

**Statement**

The system shall allow an authorized administrator to activate, deactivate, or otherwise manage the approved status of a verification record.

**Source:** STK-03 Administrator  
**Priority:** Could / Should if verification module is implemented  
**Evidence:** DERIVED  
**Status:** PROVISIONAL

---

# 4. Verification Business Boundary

The following must remain explicit:

```text
Craft BD Record
        ≠
Independent Proof of Physical Authenticity
```

A valid QR record proves only that:

> Craft BD contains a corresponding platform record.

It does not automatically prove that the physical object being scanned is the exact original product represented by that record.

---

# 5. Certificate Requirements

The certificate module is currently classified as:

**Optional / Could Have**

If implemented, the certificate represents a Craft BD platform record.

---

## FR-CERT-001 — Create Platform Certificate Record

**Statement**

The system shall allow an authorized administrator to create a Craft BD certificate record for an eligible product.

**Source:** STK-03 Administrator  
**Priority:** Could  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

Possible certificate information may include:

- Certificate ID
- Product ID
- Artisan
- Region
- Materials
- Issue date
- Verification reference

---

## FR-CERT-002 — Assign Unique Certificate Identifier

**Statement**

The system shall assign a unique certificate identifier to each valid Craft BD certificate record.

**Source:** Business Logic  
**Priority:** Could  
**Evidence:** DERIVED  
**Status:** PROVISIONAL

---

## FR-CERT-003 — View Certificate Record

**Statement**

The system shall allow permitted users to view the public information associated with an active Craft BD certificate record.

**Source:** STK-01 Customer  
**Priority:** Could  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

## FR-CERT-004 — Link Certificate to Product Record

**Statement**

The system shall associate a valid certificate record with the relevant Craft BD product record.

**Source:** Platform Requirement  
**Priority:** Could  
**Evidence:** DERIVED  
**Status:** PROVISIONAL

---

## FR-CERT-005 — Revoke / Deactivate Certificate Record

**Statement**

The system shall allow an authorized administrator to deactivate or revoke a Craft BD certificate record when required by approved platform rules.

**Source:** STK-03  
**Priority:** Could  
**Evidence:** DERIVED  
**Status:** PROVISIONAL

---

# 6. Certificate Terminology Rule

Craft BD should use:

```text
Craft BD Certificate Record
```

or:

```text
Platform Certificate
```

unless an authorized external certification organization is integrated.

The system must not describe the record as:

- Government certificate
- Legal authenticity certificate
- National certification

without supporting authority.

---

# 7. Notification Module Scope

The notification module supports user awareness of important workflow events.

The academic MVP does not require:

- Real-time push notifications
- SMS
- Mobile app notifications

A basic implementation may use:

- In-app notifications
- Dashboard alerts
- Email where practical

---

# 8. Notification Requirements

## FR-NOTIF-001 — Notify Artisan of New Custom Request

**Statement**

The system shall make the assigned artisan aware when a new custom-order request requiring artisan review is created.

**Source:** STK-02 Artisan  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

---

## FR-NOTIF-002 — Notify Customer of Available Quotation

**Statement**

The system shall make the request owner aware when a quotation has been submitted for their custom-order request.

**Source:** STK-01 Customer  
**Priority:** Should  
**Evidence:** PROVISIONAL / DERIVED  
**Status:** PROVISIONAL

---

## FR-NOTIF-003 — Notify Artisan of Quotation Approval

**Statement**

The system shall make the assigned artisan aware when the customer approves a quotation.

**Source:** STK-02  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

---

## FR-NOTIF-004 — Notify Artisan of Quotation Rejection

**Statement**

The system shall make the assigned artisan aware when the customer rejects a quotation.

**Source:** STK-02  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

---

## FR-NOTIF-005 — Notify Customer of Relevant Status Change

**Statement**

The system shall make the customer aware when an important custom-order or standard-order status relevant to them changes.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** PROVISIONAL / DERIVED  
**Status:** PROVISIONAL

Important notification events may include:

- Production started
- Product ready
- Order shipped
- Order delivered

---

## FR-NOTIF-006 — View Notifications

**Statement**

The system shall allow an authenticated user to view notifications associated with their own account.

**Source:** STK-01, STK-02  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

---

## FR-NOTIF-007 — Mark Notification as Read

**Statement**

The system shall allow an authenticated user to mark an owned notification as read.

**Source:** User Experience Requirement  
**Priority:** Could / Should  
**Evidence:** DERIVED  
**Status:** DRAFT

---

# 9. Notification Design Rule

Notifications should focus on:

```text
Action Required
or
Meaningful Status Change
```

Avoid excessive notifications such as:

- Every page view
- Every minor internal state change
- Repeated duplicate alerts

The goal is useful awareness rather than notification overload.

---

# 10. Administration Requirements

The administrator supports governance and exceptional operations.

Administration should follow:

```text
Normal User Workflow
        ↓
Customer / Artisan

Exceptional or Governance Action
        ↓
Administrator
```

The administrator should not approve every routine action.

---

# 11. User Administration

## FR-ADMIN-001 — View User Accounts

**Statement**

The system shall allow an authorized administrator to view permitted user-account information required for platform administration.

**Source:** STK-03 Administrator  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

Private or sensitive information shall remain subject to privacy rules.

---

## FR-ADMIN-002 — Manage User Status

**Statement**

The system shall allow an authorized administrator to perform approved account-status actions such as activation or deactivation.

**Source:** STK-03  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

Unauthorized users shall not be able to perform administrative account-status actions.

---

# 12. Category Administration

## FR-ADMIN-003 — Create Category

**Statement**

The system shall allow an authorized administrator to create a valid product category.

**Source:** STK-03  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

---

## FR-ADMIN-004 — Update Category

**Statement**

The system shall allow an authorized administrator to modify supported information for an existing category.

**Source:** STK-03  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

---

## FR-ADMIN-005 — Deactivate Category

**Statement**

The system shall allow an authorized administrator to deactivate a category according to approved data-integrity rules.

**Source:** STK-03  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

Historical product references shall not be silently corrupted because a category becomes inactive.

---

# 13. Content Moderation Requirements

## FR-ADMIN-006 — Moderate Product Content

**Statement**

The system shall allow an authorized administrator to take approved moderation actions on product content that violates platform rules.

**Source:** STK-03  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

---

## FR-ADMIN-007 — Moderate Artisan Profile Content

**Statement**

The system shall allow an authorized administrator to take approved moderation actions on artisan-profile content that violates platform rules.

**Source:** STK-03  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

---

## FR-ADMIN-008 — Moderate Reviews

**Statement**

The system shall allow an authorized administrator to moderate reviews according to approved platform rules.

**Source:** STK-03  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

This requirement complements:

`FR-REV-005`

and should later be reconciled to avoid duplicate implementation requirements.

---

# 14. Verification Administration Requirements

## FR-ADMIN-009 — Manage Verification Records

**Statement**

The system shall allow an authorized administrator to manage Craft BD verification records where the verification module is implemented.

**Source:** STK-03  
**Priority:** Should / Conditional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

## FR-ADMIN-010 — Manage Certificate Records

**Statement**

The system shall allow an authorized administrator to manage Craft BD certificate records where the certificate module is implemented.

**Source:** STK-03  
**Priority:** Could / Conditional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

# 15. Exceptional Order Administration

## FR-ADMIN-011 — View Order for Authorized Support

**Statement**

The system shall allow an authorized administrator to view permitted order information when required for approved administrative or support purposes.

**Source:** STK-03  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

---

## FR-ADMIN-012 — Perform Approved Exceptional Order Action

**Statement**

The system shall allow an authorized administrator to perform only approved exceptional order actions where normal customer/artisan workflow cannot resolve the issue.

**Source:** STK-03  
**Priority:** Could / Should  
**Evidence:** DERIVED  
**Status:** DRAFT

Important:

This does not grant unrestricted order manipulation.

Specific exceptional actions must later be defined.

---

# 16. Administration Security Boundary

Admin functionality must satisfy:

```text
Authenticated
+
ADMIN Role
+
Approved Permission
+
Business Rule
```

Admin routes must not be protected only by:

```text
Hidden Button
```

Frontend visibility is not authorization.

---

# 17. Auditability Direction

High-impact administrative actions should later support logging or auditability.

Examples:

- User deactivation
- Verification deactivation
- Certificate revocation
- Content moderation
- Exceptional order override

This requirement will be formalized in security/logging requirements.

---

# 18. Admin by Exception Principle

Avoid this:

```text
Product Created
→ Admin Approval

Order Created
→ Admin Approval

Status Updated
→ Admin Approval
```

unless a specific validated requirement requires it.

Prefer:

```text
Normal Action
→ User Workflow

Violation / Exceptional Case
→ Admin
```

This protects usability and scalability.

---

# 19. Supporting Module Priority

| Module | Priority | MVP Position |
|---|---|---|
| Basic Notifications | Should | Supporting |
| Admin User Management | Must | Core Governance |
| Category Management | Must | Core Governance |
| Review Moderation | Should | Supporting |
| QR Product Record | Should | Scope Dependent |
| Verification Management | Should | Conditional |
| Digital Certificate | Could | Optional |
| Certificate Administration | Could | Optional |

---

# 20. Related Business Rules

The supporting modules require business rules such as:

## BR-VERIFY-001

A QR-linked record shall represent a Craft BD platform record and shall not automatically imply independent proof of physical authenticity.

## BR-VERIFY-002

Only authorized roles may create or manage verification records.

## BR-CERT-001

Only an authorized administrator may issue a Craft BD platform certificate record.

## BR-CERT-002

A Craft BD certificate record shall not be represented as government or external certification unless such authority exists.

## BR-NOTIF-001

A user may view only notifications associated with their own account unless an explicit administrative rule applies.

## BR-ADMIN-001

Administrative functionality shall require approved administrator authorization.

## BR-ADMIN-002

Administrator intervention shall not be required for normal user workflow unless a specific business rule requires it.

---

# 21. Security Dependencies

This requirement group depends on:

- Administrator authorization
- Resource ownership
- Secure verification identifiers
- Input validation
- Privacy controls
- Administrative action logging
- Secure file handling where certificate/product assets are involved

---

# 22. Verification Security Example

Potential risk:

```text
/verify/1
/verify/2
/verify/3
```

may make records trivially enumerable if implemented poorly.

Therefore, verification identifiers should be designed with appropriate security and data-exposure considerations.

The exact identifier mechanism will be decided during technical design.

---

# 23. Notification Privacy Example

A notification must not expose private order information to the wrong user.

Example:

Customer A notification:

```text
Your quotation is ready.
```

must never appear in Customer B's account.

Therefore notification access requires ownership validation.

---

# 24. Administration Failure Scenarios

Future testing should include:

### Scenario 1

Customer attempts to access administrator user management.

Expected:

```text
ACCESS DENIED
```

### Scenario 2

Artisan attempts to issue a platform certificate without authorization.

Expected:

```text
ACCESS DENIED
```

### Scenario 3

Invalid verification identifier is requested.

Expected:

```text
INVALID / NOT FOUND
```

without exposing unrelated records.

### Scenario 4

Customer attempts to read another user's notification.

Expected:

```text
ACCESS DENIED
```

---

# 25. Future Use Case Direction

Possible use cases include:

```text
UC-VERIFY-001
View Product Verification Record

UC-CERT-001
Issue Platform Certificate

UC-NOTIF-001
View Notifications

UC-ADMIN-001
Manage User

UC-ADMIN-002
Manage Category

UC-ADMIN-003
Moderate Content
```

Only implemented capabilities should become final UML use cases.

---

# 26. Traceability Examples

| Need / Source | Requirement |
|---|---|
| Customer seeks product record | FR-VERIFY-003 |
| Platform needs safe invalid lookup handling | FR-VERIFY-004 |
| Customer needs quotation awareness | FR-NOTIF-002 |
| Artisan needs approval awareness | FR-NOTIF-003 |
| Admin needs user governance | FR-ADMIN-001, FR-ADMIN-002 |
| Platform needs categories | FR-ADMIN-003 through FR-ADMIN-005 |
| Trust claim boundary | BR-VERIFY-001 |
| Certificate boundary | BR-CERT-002 |

---

# 27. Part 4 Requirement Count

| Module | Requirements |
|---|---:|
| Verification | 5 |
| Certificate | 5 |
| Notification | 7 |
| Administration | 12 |
| **Total** | **29** |

Several requirements are conditional because optional modules may later be removed from MVP.

---

# 28. Scope Protection Rule

If schedule becomes constrained:

Remove or defer in this order:

```text
Certificate
↓
Advanced Verification Management
↓
Non-essential Notifications
```

Protect:

```text
Admin Authorization
Category Management
Essential Governance
Core Customer/Artisan Workflow
```

QR/certificate features must not delay testing of core ordering and custom-order workflows.

---

# 29. Current Supporting Module Decision

## Core Governance

- Admin authorization
- User management
- Category management

## Supporting MVP

- Basic notifications
- Review moderation

## Scope Dependent

- QR-linked product record

## Optional

- Digital certificate

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Functional Requirements Baseline Part 4  
**Modules:** VERIFY, CERT, NOTIF, ADMIN  
**Status:** Draft / Provisional v0.1  
**Next Step:** Business Rule Register
