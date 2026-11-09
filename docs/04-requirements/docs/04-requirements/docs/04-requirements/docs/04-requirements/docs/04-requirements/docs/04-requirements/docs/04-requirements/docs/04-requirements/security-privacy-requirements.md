# Craft BD — Security & Privacy Requirements Baseline

## 1. Purpose

This document defines the formal security and privacy requirements for Craft BD.

The requirements protect:

- User accounts
- Customer information
- Artisan information
- Products
- Orders
- Custom-order requests
- Uploaded files
- Administrative functionality
- Application credentials and secrets

Security requirements use the prefix `SR`.

Privacy requirements use the prefix `PR`.

---

# 2. Security Design Principle

Craft BD shall follow the principle:

```text
Authenticate
     ↓
Authorize Role
     ↓
Validate Ownership
     ↓
Validate Business Rule
     ↓
Validate Input
     ↓
Perform Action
```

Frontend restrictions alone shall not be treated as security enforcement.

---

# 3. Authentication Security

## SR-AUTH-001 — Secure Password Storage

**Statement**

The system shall store user passwords using an approved one-way password-hashing mechanism and shall not store passwords in readable plain text.

**Source:** Security Requirement  
**Priority:** Must  
**Evidence:** SECURITY  
**Status:** DRAFT

**Acceptance Criteria**

Inspection of stored authentication data shall not reveal the user's original password.

---

## SR-AUTH-002 — Credential Validation

**Statement**

The system shall authenticate a user only when submitted credentials satisfy the approved authentication process.

**Priority:** Must  
**Status:** DRAFT

Invalid credentials shall not create an authenticated session.

---

## SR-AUTH-003 — Generic Login Failure

**Statement**

Authentication failures should avoid unnecessarily revealing whether a specific account identifier exists.

**Priority:** Should  
**Status:** DRAFT

Example acceptable message:

```text
Invalid email or password.
```

rather than exposing excessive account-discovery information.

---

## SR-AUTH-004 — Protected Session / Token Handling

**Statement**

Authentication sessions or tokens shall be handled according to the security practices supported by the selected authentication architecture.

**Priority:** Must  
**Status:** DRAFT

Authentication tokens shall not be intentionally exposed through public application content.

---

## SR-AUTH-005 — Logout Invalidates Active Access

**Statement**

After a successful logout, the terminated authentication context shall no longer authorize protected application actions.

**Priority:** Must  
**Status:** DRAFT

Related:

`FR-AUTH-004`

---

# 4. Authorization Requirements

## SR-AUTHZ-001 — Server-Side Authorization

**Statement**

The system shall enforce access-control decisions on the trusted server or authoritative backend layer.

**Priority:** Must  
**Status:** DRAFT

Hiding a button in the frontend shall not be considered sufficient authorization.

---

## SR-AUTHZ-002 — Role-Based Access

**Statement**

The system shall restrict protected functionality according to the authenticated user's approved role and permissions.

**Priority:** Must  
**Status:** DRAFT

Current roles:

- CUSTOMER
- ARTISAN
- ADMIN

---

## SR-AUTHZ-003 — Customer Administrative Restriction

**Statement**

A customer shall not access administrator-only functionality.

**Priority:** Must  
**Status:** DRAFT

---

## SR-AUTHZ-004 — Artisan Administrative Restriction

**Statement**

An artisan shall not access administrator-only functionality unless an explicit authorized permission model later provides such access.

**Priority:** Must  
**Status:** DRAFT

---

## SR-AUTHZ-005 — Unauthorized Access Failure

**Statement**

When a user attempts an operation for which they lack authorization, the system shall deny the operation and shall not perform the protected action.

**Priority:** Must  
**Status:** DRAFT

---

# 5. Ownership Requirements

## SR-OWN-001 — Product Ownership

**Statement**

The system shall verify product ownership before allowing an artisan to modify or deactivate a product.

**Priority:** Must  
**Status:** DRAFT

Related:

- BR-PROD-001
- FR-PROD-002
- FR-PROD-003

---

## SR-OWN-002 — Customer Order Ownership

**Statement**

The system shall prevent a customer from accessing private order details belonging to another customer.

**Priority:** Must  
**Status:** DRAFT

---

## SR-OWN-003 — Customer Custom-Request Ownership

**Statement**

The system shall prevent a customer from viewing, approving, rejecting, or modifying protected custom-order information belonging to another customer.

**Priority:** Must  
**Status:** DRAFT

---

## SR-OWN-004 — Artisan Custom-Request Assignment

**Statement**

The system shall verify that an artisan is assigned to a custom request before permitting artisan-side quotation or workflow actions.

**Priority:** Must  
**Status:** DRAFT

---

## SR-OWN-005 — Notification Ownership

**Statement**

The system shall prevent a normal user from accessing notifications belonging to another user's account.

**Priority:** Must  
**Status:** DRAFT

---

# 6. Business-Rule Enforcement

## SR-AUTHZ-006 — Custom Production Guard

**Statement**

The system shall prevent a custom order from entering production unless the required customer quotation approval exists.

**Priority:** Must  
**Status:** PROVISIONAL

Related:

`BR-CUSTOM-001`

---

## SR-AUTHZ-007 — Quotation Approval Ownership

**Statement**

The system shall verify that the authenticated customer owns the corresponding custom request before allowing quotation approval or rejection.

**Priority:** Must  
**Status:** PROVISIONAL

---

## SR-AUTHZ-008 — Review Eligibility Enforcement

**Statement**

The system shall verify approved purchase eligibility before allowing a customer to submit a product review where purchase-linked reviews are required.

**Priority:** Must  
**Status:** DRAFT

---

# 7. Input Validation Requirements

## SR-INPUT-001 — Backend Input Validation

**Statement**

The system shall validate externally supplied application data on the backend before using it in protected business operations or persistent storage.

**Priority:** Must  
**Status:** DRAFT

---

## SR-INPUT-002 — Required Field Validation

**Statement**

The system shall reject submissions that omit mandatory fields required by the relevant business workflow.

**Priority:** Must  
**Status:** DRAFT

---

## SR-INPUT-003 — Numeric Validation

**Statement**

The system shall validate numeric business data such as:

- Product price
- Product stock
- Cart quantity
- Custom-order quantity
- Quotation price

before persistence.

**Priority:** Must  
**Status:** DRAFT

Invalid negative or otherwise prohibited values shall be rejected.

---

## SR-INPUT-004 — Identifier Validation

**Statement**

The system shall validate identifiers supplied for protected resources and shall not assume that a client-provided identifier grants access to the associated resource.

**Priority:** Must  
**Status:** DRAFT

Example:

```text
/order/123
```

does not imply that the requesting user owns order `123`.

---

## SR-INPUT-005 — Search and Filter Validation

**Statement**

The system shall validate supported search, filter, sorting, and pagination parameters before applying them to application queries.

**Priority:** Should  
**Status:** DRAFT

---

# 8. File Upload Security

## SR-FILE-001 — Allowed File Types

**Statement**

The system shall accept only approved file types for image-upload functionality.

**Priority:** Must  
**Status:** DRAFT

Possible use cases:

- Product image
- Artisan profile image
- Custom-order reference image

The final allowed formats shall be defined during implementation planning.

---

## SR-FILE-002 — File Size Limit

**Statement**

The system shall enforce an approved maximum file size for uploaded files.

**Priority:** Must  
**Status:** DRAFT

The exact limit will be selected during architecture and storage planning.

---

## SR-FILE-003 — File Validation

**Statement**

The system shall validate uploaded files before treating them as approved user content.

**Priority:** Must  
**Status:** DRAFT

---

## SR-FILE-004 — Safe File Naming / Storage

**Statement**

The system shall not rely on untrusted client-provided filenames as authoritative storage paths.

**Priority:** Must  
**Status:** DRAFT

The storage design shall prevent a user-provided filename from controlling sensitive server filesystem paths.

---

## SR-FILE-005 — Upload Authorization

**Statement**

The system shall verify that the authenticated user is permitted to upload or associate a file with the requested resource.

**Priority:** Must  
**Status:** DRAFT

---

## SR-FILE-006 — Private Custom Reference Images

**Statement**

Custom-order reference images that are classified as private shall not be publicly exposed through normal public-product functionality.

**Priority:** Must  
**Status:** DRAFT

---

# 9. Secret Management

## SR-SECRET-001 — Secrets Outside Source Code

**Statement**

Production secrets shall not be hard-coded into normal application source code.

**Priority:** Must  
**Status:** DRAFT

Examples:

- Database password
- Authentication secret
- API secret
- Storage credential

---

## SR-SECRET-002 — Source-Control Protection

**Statement**

Sensitive environment configuration files and credentials shall not be committed to the public project repository.

**Priority:** Must  
**Status:** DRAFT

---

## SR-SECRET-003 — Example Environment Configuration

**Statement**

Where environment variables are required, the repository may provide a non-sensitive example configuration that documents required variable names without exposing real secrets.

**Priority:** Should  
**Status:** DRAFT

Example:

```text
.env.example
```

---

# 10. Logging Requirements

## SR-LOG-001 — No Password Logging

**Statement**

The system shall not intentionally record user passwords in application logs.

**Priority:** Must  
**Status:** DRAFT

---

## SR-LOG-002 — No Secret Logging

**Statement**

The system shall avoid logging API keys, authentication secrets, private keys, or equivalent sensitive credentials.

**Priority:** Must  
**Status:** DRAFT

---

## SR-LOG-003 — Administrative Action Logging

**Statement**

Important administrative actions should be recorded with sufficient information to support audit and troubleshooting.

**Priority:** Should  
**Status:** DRAFT

Candidate actions include:

- Account deactivation
- Content moderation
- Certificate revocation
- Verification-record deactivation
- Exceptional order action

---

## SR-LOG-004 — Safe Error Logging

**Statement**

Application errors may be recorded for debugging, but user-facing responses shall not expose unnecessary internal stack traces or secrets.

**Priority:** Must  
**Status:** DRAFT

---

# 11. Transport Security

## SR-TRANSPORT-001 — HTTPS Deployment

**Statement**

The deployed Craft BD application shall use HTTPS for communication between normal users and the deployed application endpoint.

**Priority:** Must  
**Status:** DRAFT

---

## SR-TRANSPORT-002 — No Production Credential Transmission Through Plain HTTP

**Statement**

Production authentication credentials shall not intentionally be transmitted through an unsecured plain-HTTP application flow.

**Priority:** Must  
**Status:** DRAFT

---

# 12. Administrative Security

## SR-ADMIN-001 — Admin Authentication

**Statement**

Administrator functionality shall require authentication.

**Priority:** Must  
**Status:** DRAFT

---

## SR-ADMIN-002 — Admin Authorization

**Statement**

Administrative actions shall require explicit administrator authorization or another approved privileged permission.

**Priority:** Must  
**Status:** DRAFT

---

## SR-ADMIN-003 — Sensitive Admin Action Protection

**Statement**

High-impact administrator actions should require clear confirmation where accidental execution could significantly affect user or platform data.

**Priority:** Should  
**Status:** DRAFT

---

## SR-ADMIN-004 — Admin Action Auditability

**Statement**

High-impact administrative operations should be traceable through approved logging or audit records where practical.

**Priority:** Should  
**Status:** DRAFT

---

# 13. Verification Security

## SR-VERIFY-001 — Verification Identifier Protection

**Statement**

Verification identifiers shall be designed so that requesting one record does not authorize access to unrelated private records.

**Priority:** Must if verification module is implemented  
**Status:** PROVISIONAL

---

## SR-VERIFY-002 — Invalid Verification Request

**Statement**

An invalid verification identifier shall not expose unrelated product or certificate information.

**Priority:** Must  
**Status:** PROVISIONAL

---

## SR-VERIFY-003 — Verification Management Authorization

**Statement**

Only an authorized administrative role shall be permitted to perform protected management actions on verification records.

**Priority:** Must  
**Status:** PROVISIONAL

---

# 14. Privacy Requirements

Privacy requirements use:

```text
PR-DATA-NNN
```

---

## PR-DATA-001 — Data Minimization

**Statement**

Craft BD shall collect only personal information required for approved application purposes.

**Source:** Privacy / Product Constraint  
**Priority:** Must  
**Status:** DRAFT

The system shall not collect unnecessary sensitive personal information merely because it might be useful later.

---

## PR-DATA-002 — Public and Private Data Separation

**Statement**

The system shall distinguish data intended for public display from private operational data.

**Priority:** Must  
**Status:** DRAFT

Example public information:

- Product description
- Artisan public biography
- Public craft information

Example private information:

- Customer delivery address
- Authentication information
- Private custom-order data

---

## PR-DATA-003 — Customer Delivery Privacy

**Statement**

Customer delivery information shall be accessible only to authorized actors who require that information for an approved transaction or administrative purpose.

**Priority:** Must  
**Status:** DRAFT

---

## PR-DATA-004 — Custom-Order Privacy

**Statement**

Private custom-order information shall normally be accessible only to:

- Request owner
- Assigned artisan
- Authorized administrator where required

**Priority:** Must  
**Status:** DRAFT

---

## PR-DATA-005 — Reference-Image Privacy

**Statement**

A custom-order reference image shall follow the access-control classification of the associated custom request unless explicitly approved for public use.

**Priority:** Must  
**Status:** DRAFT

---

## PR-DATA-006 — Public Artisan Data

**Statement**

The system shall expose only artisan-profile fields approved for public display through public artisan pages.

**Priority:** Must  
**Status:** DRAFT

Private account and authentication information shall remain excluded.

---

# 15. Account and Data Transparency

## PR-DATA-007 — Purpose Awareness

**Statement**

Before production use, Craft BD shall provide users with appropriate information describing why relevant personal information is collected and how it is used.

**Priority:** Must for commercial deployment  
**Status:** DRAFT

The final legal wording is outside the software requirement team's authority and may require formal review.

---

## PR-DATA-008 — Data Retention Direction

**Statement**

Personal data shall not be intentionally retained indefinitely without an approved operational, legal, historical, or security purpose.

**Priority:** Should  
**Status:** DRAFT

Detailed retention periods shall be finalized before commercial deployment.

---

# 16. Academic Demo Privacy

## PR-DATA-009 — Synthetic Demo Data

**Statement**

The public academic or portfolio demonstration should use synthetic or appropriately authorized customer information instead of exposing unnecessary real-user personal data.

**Priority:** Must  
**Status:** DRAFT

---

## PR-DATA-010 — Research Participant Privacy

**Statement**

Private information collected from research participants shall not be published in the public Craft BD source repository without appropriate authorization.

**Priority:** Must  
**Status:** DRAFT

---

# 17. Sensitive Information Boundary

The academic MVP does not require collection of:

- National identity numbers
- Bank passwords
- Payment PINs
- Card PINs
- Security-question answers
- Unnecessary identity documents

If a future feature requires additional sensitive information:

```text
New Requirement
      ↓
Privacy Review
      ↓
Security Review
      ↓
Legal Review
      ↓
Approval
```

must occur before implementation.

---

# 18. Simulated Payment Privacy

Because the academic MVP uses simulated payment:

Craft BD shall not request or store actual:

- Mobile financial service PIN
- Card PIN
- Bank password

The simulation should demonstrate the workflow rather than collect real financial credentials.

---

# 19. Security Test Scenarios

Future security testing should include scenarios such as:

### ST-01 — Customer Order Isolation

Customer A requests Customer B's private order.

Expected:

```text
ACCESS DENIED
```

---

### ST-02 — Artisan Product Ownership

Artisan A attempts to edit Artisan B's product.

Expected:

```text
ACCESS DENIED
```

---

### ST-03 — Custom Request Ownership

Customer A attempts to approve Customer B's quotation.

Expected:

```text
ACCESS DENIED
```

---

### ST-04 — Artisan Assignment

Artisan B attempts to quote Artisan A's assigned request.

Expected:

```text
ACCESS DENIED
```

---

### ST-05 — Admin Endpoint

Normal customer requests administrator functionality.

Expected:

```text
ACCESS DENIED
```

---

### ST-06 — Invalid Upload

Unsupported or invalid file is uploaded.

Expected:

```text
UPLOAD REJECTED
```

---

### ST-07 — Production Guard

Artisan attempts:

```text
QUOTED
→ IN_PRODUCTION
```

before customer approval.

Expected:

```text
TRANSITION REJECTED
```

---

### ST-08 — Invalid Verification Identifier

Unknown verification reference requested.

Expected:

```text
INVALID / NOT FOUND
```

No unrelated record shall be exposed.

---

# 20. Security Requirement Traceability

Examples:

| Requirement | Related Functional / Business Rule |
|---|---|
| SR-OWN-001 | FR-PROD-002, BR-PROD-001 |
| SR-OWN-002 | FR-ORDER-012, BR-ORDER-008 |
| SR-OWN-004 | FR-CUSTOM-014, BR-CUSTOM-003 |
| SR-AUTHZ-006 | FR-CUSTOM-028, BR-CUSTOM-001 |
| SR-AUTHZ-008 | FR-REV-002, BR-REV-001 |
| SR-FILE-006 | FR-CUSTOM-008 |
| SR-ADMIN-002 | FR-ADMIN-* |
| SR-VERIFY-002 | BR-VERIFY-004 |

---

# 21. Privacy Requirement Traceability

| Requirement | Related Area |
|---|---|
| PR-DATA-001 | Registration/Profile/Data Model |
| PR-DATA-002 | Public API / UI Design |
| PR-DATA-003 | Standard Order |
| PR-DATA-004 | Custom Order |
| PR-DATA-005 | Custom Reference Upload |
| PR-DATA-006 | Artisan Profile |
| PR-DATA-009 | Public Portfolio Deployment |
| PR-DATA-010 | User Research |

---

# 22. Security Verification Methods

Different requirements may require different verification methods.

| Security Area | Verification |
|---|---|
| Authentication | Integration / negative testing |
| Authorization | Access-control testing |
| Ownership | Cross-account tests |
| Input Validation | Invalid-input tests |
| File Security | Upload tests |
| Secrets | Repository/configuration review |
| Logging | Log inspection |
| HTTPS | Deployment inspection |
| Privacy | Access and data-flow review |

---

# 23. Security Priority

The following are non-negotiable MVP requirements:

```text
Password Protection
+
Backend Authorization
+
Ownership Validation
+
Input Validation
+
Safe File Handling
+
Secret Protection
+
HTTPS Deployment
+
Private Data Boundaries
```

Optional features may be removed before these controls are sacrificed.

---

# 24. Security Philosophy

Craft BD shall not follow:

```text
Build Everything
      ↓
Add Security Later
```

Instead:

```text
Requirement
      ↓
Security Rule
      ↓
Design
      ↓
Implementation
      ↓
Security Test
```

Security is part of the workflow, not a final decoration.

---

# 25. Current Requirement Count

Current draft:

| Category | Count |
|---|---:|
| Authentication Security | 5 |
| Authorization | 8 |
| Ownership | 5 |
| Input Validation | 5 |
| File Security | 6 |
| Secret Management | 3 |
| Logging | 4 |
| Transport Security | 2 |
| Admin Security | 4 |
| Verification Security | 3 |
| Privacy | 10 |
| **Total** | **55** |

The count may change after architecture and testing review.

---

# 26. Current Decision

Craft BD security and privacy requirements are:

**Feasible and mandatory for the MVP.**

No optional product capability should justify weakening:

- Authentication
- Authorization
- Ownership
- Input validation
- Secret management
- Privacy boundaries

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Security & Privacy Requirements Baseline  
**Status:** Draft v0.1  
**Primary Research Dependency:** Low  
**Next Step:** Data, Constraint & Integration Requirements
