# Craft BD — Data, Constraint & Integration Requirements

## 1. Purpose

This document defines the formal Data Requirements, Constraint Requirements, and Integration Requirements for Craft BD.

These requirements support:

- Database design
- API design
- Architecture
- Deployment
- Security
- Requirement traceability
- Scope control

The three requirement categories use the following prefixes:

- `DR` — Data Requirement
- `CR` — Constraint Requirement
- `IR` — Integration Requirement

---

# 2. Data Requirement Standard

Data requirements use:

`DR-MODULE-NNN`

Example:

`DR-PROD-001`

A data requirement defines information that Craft BD must store, relate, preserve, or validate.

---

# 3. User Data Requirements

## DR-USER-001 — Unique User Identifier

**Statement**

Each user account shall have a unique system identifier.

**Priority:** Must  
**Status:** DRAFT

---

## DR-USER-002 — User Role

**Statement**

Each active user account shall be associated with an approved Craft BD role or permission model.

Initial roles include:

- Customer
- Artisan
- Administrator

**Priority:** Must  
**Status:** DRAFT

---

## DR-USER-003 — Authentication Data

**Statement**

The system shall maintain the authentication information required to identify registered users without storing readable plain-text passwords.

**Priority:** Must  
**Related Security Requirement:** SR-AUTH-001  
**Status:** DRAFT

---

## DR-USER-004 — Customer Profile Data

**Statement**

The system shall store the approved customer-profile information required for customer workflows.

**Priority:** Should  
**Status:** DRAFT

The final field list will be defined during data-model design.

---

# 4. Artisan Data Requirements

## DR-ART-001 — Artisan Profile Record

**Statement**

Each artisan account shall be associated with an artisan-profile record containing approved artisan information.

Possible data includes:

- Name
- Region/location
- Expertise
- Experience
- Biography
- Profile image reference

**Priority:** Must  
**Status:** DRAFT

---

## DR-ART-002 — Artisan–Product Relationship

**Statement**

Each artisan-managed product shall be associated with the artisan responsible for that product.

**Priority:** Must  
**Status:** DRAFT

---

# 5. Product Data Requirements

## DR-PROD-001 — Unique Product Identifier

**Statement**

Each product shall have a unique product identifier.

**Priority:** Must  
**Status:** DRAFT

---

## DR-PROD-002 — Required Product Information

**Statement**

Each active standard product shall contain the approved mandatory product information.

Possible mandatory information includes:

- Product name
- Category
- Price
- Stock where applicable
- Description
- Artisan association

**Priority:** Must  
**Status:** DRAFT

---

## DR-PROD-003 — Product Category Relationship

**Statement**

Each product requiring categorization shall reference a valid category record.

**Priority:** Must  
**Status:** DRAFT

---

## DR-PROD-004 — Product Image References

**Statement**

The system shall store the metadata or storage references required to associate approved product images with the correct product.

**Priority:** Must  
**Status:** DRAFT

---

## DR-PROD-005 — Product Status

**Statement**

The system shall store the information required to determine whether a product is active, inactive, or otherwise eligible for public display and ordering.

**Priority:** Must  
**Status:** DRAFT

---

## DR-PROD-006 — Optional Context Information

**Statement**

Where supported, the system may store approved product-context information such as:

- Material
- Craft type
- Region
- Craft context

**Priority:** Should  
**Status:** DRAFT

---

# 6. Category Data Requirements

## DR-PROD-007 — Unique Category Identifier

Each product category shall have a unique identifier.

**Priority:** Must  
**Status:** DRAFT

---

## DR-PROD-008 — Category Status

The system shall maintain sufficient category-state information to distinguish currently usable categories from inactive categories where category deactivation is supported.

**Priority:** Should  
**Status:** DRAFT

---

# 7. Cart Data Requirements

## DR-CART-001 — Customer Cart Ownership

Each persistent customer cart shall be associated with the relevant customer account.

**Priority:** Must  
**Status:** DRAFT

---

## DR-CART-002 — Cart Item Relationship

Each cart item shall reference:

- Cart
- Product
- Quantity

and other approved data required for the cart workflow.

**Priority:** Must  
**Status:** DRAFT

---

# 8. Standard Order Data Requirements

## DR-ORDER-001 — Unique Order Identifier

Each standard order shall have a unique identifier.

**Priority:** Must  
**Status:** DRAFT

---

## DR-ORDER-002 — Order Customer Relationship

Each standard order shall belong to exactly one customer account.

**Priority:** Must  
**Related Rule:** BR-ORDER-001  
**Status:** DRAFT

---

## DR-ORDER-003 — Order Item Records

Each confirmed order shall maintain one or more order-item records describing the products included in the transaction.

**Priority:** Must  
**Status:** DRAFT

---

## DR-ORDER-004 — Transaction-Time Price

Each order item shall preserve the applicable transaction-time price required for historical consistency.

**Priority:** Must  
**Related Rule:** BR-ORDER-007  
**Status:** DRAFT

---

## DR-ORDER-005 — Order Status

Each order shall store its current approved workflow status.

**Priority:** Must  
**Status:** DRAFT

---

## DR-ORDER-006 — Order Timestamps

The system shall store relevant timestamps for important order events.

Examples may include:

- Created at
- Updated at
- Delivered at where applicable

**Priority:** Should  
**Status:** DRAFT

---

## DR-ORDER-007 — Delivery Information

The system shall store the approved delivery information required to fulfill an order.

**Priority:** Must  
**Privacy Dependency:** PR-DATA-003  
**Status:** DRAFT

---

## DR-ORDER-008 — Payment Status

Where simulated or real payment status is supported, the order shall store the approved payment-state information.

**Priority:** Should  
**Status:** DRAFT

---

# 9. Custom-Order Data Requirements

## DR-CUSTOM-001 — Unique Custom Request Identifier

Each custom-order request shall have a unique identifier.

**Priority:** Must — Provisional  
**Status:** PROVISIONAL

---

## DR-CUSTOM-002 — Customer Relationship

Each custom request shall be associated with the customer who submitted it.

**Priority:** Must  
**Status:** PROVISIONAL

---

## DR-CUSTOM-003 — Assigned Artisan Relationship

Each active custom request shall identify the artisan responsible for reviewing or fulfilling the request.

**Priority:** Must  
**Status:** PROVISIONAL

---

## DR-CUSTOM-004 — Custom Requirement Data

The system shall store the submitted customization information required by the approved custom-order workflow.

Possible fields include:

- Product type
- Design
- Color
- Size
- Material
- Quantity
- Instructions

**Priority:** Must — Provisional  
**Status:** PROVISIONAL

---

## DR-CUSTOM-005 — Reference Image Relationship

Where a reference image is submitted, the system shall associate the approved file/storage reference with the relevant custom request.

**Priority:** Should  
**Status:** PROVISIONAL

---

## DR-CUSTOM-006 — Custom Request Status

Each custom request shall store its current approved workflow state.

**Priority:** Must  
**Status:** PROVISIONAL

---

# 10. Quotation Data Requirements

## DR-CUSTOM-007 — Quotation Relationship

Each quotation shall reference the custom request for which it was created.

**Priority:** Must  
**Status:** PROVISIONAL

---

## DR-CUSTOM-008 — Quoted Price

Each submitted quotation shall store a valid quoted price.

**Priority:** Must  
**Status:** PROVISIONAL

---

## DR-CUSTOM-009 — Completion Estimate

Where required by the approved workflow, the quotation shall store an estimated completion date or approved equivalent completion estimate.

**Priority:** Must — Provisional  
**Status:** PROVISIONAL

---

## DR-CUSTOM-010 — Quotation Decision

The system shall store the approved customer decision associated with an eligible quotation.

Possible values may include:

- Pending
- Approved
- Rejected

**Priority:** Must  
**Status:** PROVISIONAL

---

## DR-CUSTOM-011 — Quotation Decision Timestamp

The system should store when the customer approved or rejected a quotation.

**Priority:** Should  
**Status:** PROVISIONAL

---

# 11. Review Data Requirements

## DR-REV-001 — Review Identifier

Each review shall have a unique identifier.

**Priority:** Must  
**Status:** DRAFT

---

## DR-REV-002 — Review Customer Relationship

Each review shall remain associated with the customer who submitted it.

**Priority:** Must  
**Status:** DRAFT

---

## DR-REV-003 — Review Product Relationship

Each product review shall reference the product being reviewed.

**Priority:** Must  
**Status:** DRAFT

---

## DR-REV-004 — Rating Data

Where ratings are supported, the review shall store a rating within the approved rating range.

**Priority:** Should  
**Status:** DRAFT

---

## DR-REV-005 — Review Content

The system may store review text associated with an eligible review.

**Priority:** Should  
**Status:** DRAFT

---

# 12. Notification Data Requirements

## DR-NOTIF-001 — Notification Ownership

Each user notification shall be associated with the account that is permitted to view it.

**Priority:** Must  
**Status:** DRAFT

---

## DR-NOTIF-002 — Notification State

The system should maintain sufficient information to distinguish unread and read notifications where this feature is implemented.

**Priority:** Should  
**Status:** DRAFT

---

## DR-NOTIF-003 — Notification Event Context

A notification should contain sufficient approved context for the user to understand the related event without exposing unnecessary private information.

**Priority:** Should  
**Status:** DRAFT

---

# 13. Verification Data Requirements

## DR-VERIFY-001 — Verification Identifier

Each active verification record shall contain a unique verification identifier.

**Priority:** Should / Conditional  
**Status:** PROVISIONAL

---

## DR-VERIFY-002 — Verification Product Relationship

Each verification record shall reference the relevant Craft BD product record.

**Priority:** Should / Conditional  
**Status:** PROVISIONAL

---

## DR-VERIFY-003 — Verification Status

The system shall maintain sufficient information to determine whether a verification record is active or inactive where the module is implemented.

**Priority:** Should  
**Status:** PROVISIONAL

---

# 14. Certificate Data Requirements

## DR-CERT-001 — Unique Certificate Identifier

Each Craft BD platform certificate shall contain a unique certificate identifier.

**Priority:** Could  
**Status:** PROVISIONAL

---

## DR-CERT-002 — Certificate Product Relationship

Each certificate record shall reference the relevant eligible product.

**Priority:** Could  
**Status:** PROVISIONAL

---

## DR-CERT-003 — Certificate Metadata

Where implemented, a certificate record may store approved information such as:

- Artisan
- Region
- Material
- Issue date
- Verification reference

**Priority:** Could  
**Status:** PROVISIONAL

---

## DR-CERT-004 — Certificate Status

The system shall store enough information to distinguish valid and inactive/revoked certificate records where certificate management is implemented.

**Priority:** Could  
**Status:** PROVISIONAL

---

# 15. Audit / Administrative Data Direction

## DR-ADMIN-001 — Administrative Action Record

For selected high-impact administrative actions, the system should store approved audit information sufficient to identify:

- Action
- Authorized actor
- Affected resource
- Relevant timestamp

**Priority:** Should  
**Status:** DRAFT

The exact audit schema will be defined during security and database design.

---

# 16. Data Integrity Principle

Core relational data should maintain valid relationships.

Examples:

```text
User
↓
ArtisanProfile
↓
Product
```

```text
Customer
↓
Order
↓
OrderItem
↓
Product
```

```text
Customer
↓
CustomRequest
↓
Quotation
↓
Workflow State
```

Invalid orphan relationships should be prevented or appropriately handled.

---

# 17. Data Deletion Direction

Permanent deletion must be considered carefully for records involved in historical transactions.

Example:

A product that appears in a completed order should not be removed in a way that destroys the historical order record.

Where practical, business records may use:

- Deactivation
- Archived status
- Soft-delete strategy

instead of destructive deletion.

The exact strategy will be decided during database design.

---

# 18. Constraint Requirement Standard

Constraint requirements use:

`CR-AREA-NNN`

Constraints define boundaries within which the system and project must operate.

---

# 19. Platform Constraints

## CR-PLATFORM-001 — Responsive Web Application

**Statement**

The initial Craft BD release shall be implemented as a responsive web application.

**Priority:** Must  
**Status:** APPROVED FOR CURRENT MVP

---

## CR-PLATFORM-002 — No Mandatory Native Application

**Statement**

A native Android or iOS application shall not be required for the initial MVP.

**Priority:** Must  
**Status:** APPROVED

---

# 20. Architecture Constraints

## CR-ARCH-001 — Manageable Small-Team Architecture

**Statement**

The initial architecture shall remain manageable for a small academic development team.

**Priority:** Must  
**Status:** DRAFT

Current preferred direction:

- Modular monolith
- Relational database
- REST-style API

Final architecture will be approved in the architecture phase.

---

## CR-ARCH-002 — Microservices Not Required

**Statement**

The initial Craft BD MVP shall not require a microservice architecture unless later evidence demonstrates a clear technical need.

**Priority:** Must  
**Status:** DRAFT

---

# 21. Budget Constraints

## CR-BUDGET-001 — Low-Cost Academic Infrastructure

**Statement**

The academic MVP should use free or low-cost development and deployment infrastructure where practical.

**Priority:** Must  
**Status:** DRAFT

---

## CR-BUDGET-002 — Paid Integration Not Mandatory

**Statement**

The MVP shall not depend on paid commercial integrations unless specifically approved.

**Priority:** Must  
**Status:** DRAFT

---

# 22. Time Constraints

## CR-TIME-001 — Academic Schedule

**Statement**

The project scope shall remain achievable within the approved academic project schedule.

**Priority:** Must  
**Status:** DRAFT

---

## CR-TIME-002 — Optional Feature Reduction

**Statement**

If schedule pressure threatens core quality, optional functionality shall be reduced before mandatory security, testing, or core workflow quality is reduced.

**Priority:** Must  
**Status:** DRAFT

---

# 23. Scope Constraints

## CR-SCOPE-001 — Core MVP Protection

The MVP shall prioritize:

- Authentication
- Authorization
- Artisan
- Product
- Standard Order
- Structured Custom Order
- Testing
- Deployment

subject to final user-validation results.

**Priority:** Must  
**Status:** PROVISIONAL

---

## CR-SCOPE-002 — Advanced AI Exclusion

Advanced AI recommendation shall not be a mandatory dependency of the initial MVP.

**Priority:** Must  
**Status:** APPROVED

---

## CR-SCOPE-003 — Blockchain Exclusion

Blockchain-based product verification or certification shall not be required for the initial MVP.

**Priority:** Must  
**Status:** APPROVED

---

## CR-SCOPE-004 — Live Chat Exclusion

Real-time customer-artisan live chat shall not be required for the initial MVP.

**Priority:** Must  
**Status:** APPROVED

---

## CR-SCOPE-005 — Logistics Integration Exclusion

Courier/logistics API integration shall not be required for MVP completion.

**Priority:** Must  
**Status:** APPROVED

---

# 24. Payment Constraints

## CR-PAY-001 — Simulated Payment Allowed

The academic MVP may demonstrate payment workflow through simulated payment states.

**Priority:** Should  
**Status:** APPROVED

---

## CR-PAY-002 — Real Financial Credentials Excluded

The academic MVP shall not require storage of real card PINs, banking passwords, or mobile financial service PINs.

**Priority:** Must  
**Status:** APPROVED

---

# 25. Certification Constraints

## CR-CERT-001 — No Government Certification Claim

Craft BD shall not represent an internal platform certificate as government certification without an authorized external certification process.

**Priority:** Must  
**Status:** APPROVED

---

## CR-VERIFY-001 — No Automatic Authenticity Claim

QR-linked product records shall not be described as automatic proof of physical authenticity.

**Priority:** Must  
**Status:** APPROVED

---

# 26. Research Constraint

## CR-RESEARCH-001 — Provisional User Hypotheses

Requirements based primarily on unresolved user assumptions shall remain explicitly marked as provisional until appropriate primary validation occurs.

**Priority:** Must  
**Status:** APPROVED

This applies particularly to:

- Structured custom-order importance
- Craft-context value
- QR product-record value
- Recommendation need

---

# 27. Integration Requirement Standard

Integration requirements use:

`IR-SERVICE-NNN`

An integration requirement should be added only when the project genuinely interacts with an external system.

---

# 28. Current Integration Philosophy

The MVP should minimize hard external dependencies.

Preferred approach:

```text
Core Craft BD
works independently
        ↓
External Integration
added only where justified
```

This reduces schedule and deployment risk.

---

# 29. File Storage Integration

## IR-STORAGE-001 — Image Storage Capability

**Statement**

The deployed system shall provide a supported storage mechanism for approved application images where persistent file storage is required.

**Priority:** Must  
**Status:** DRAFT

Possible files include:

- Product images
- Artisan profile images
- Custom reference images

The final provider has not yet been selected.

---

## IR-STORAGE-002 — Storage Reference

The application shall maintain the approved reference or metadata required to retrieve an authorized stored file.

**Priority:** Must  
**Status:** DRAFT

---

# 30. Email Integration

## IR-EMAIL-001 — Email Notification Integration

**Statement**

Email notification integration may be implemented to deliver selected system notifications if the final architecture and schedule support it.

**Priority:** Could  
**Status:** DEFERRED / OPTIONAL

The core MVP shall not fail solely because an email provider is unavailable.

---

# 31. Payment Integration

## IR-PAY-001 — Real Payment Gateway

**Statement**

Real payment-gateway integration is deferred from the mandatory academic MVP.

**Priority:** Won't Have Now  
**Status:** DEFERRED

If later approved, a separate integration specification must define:

- Provider
- Authentication
- Callback/webhook handling
- Payment states
- Failure handling
- Security
- Testing

---

# 32. Logistics Integration

## IR-LOGISTICS-001 — Courier Integration

**Statement**

Direct courier/logistics API integration shall remain outside the mandatory MVP.

**Priority:** Won't Have Now  
**Status:** DEFERRED

The MVP may maintain internal shipment statuses without receiving live courier data.

---

# 33. External Certification Integration

## IR-CERT-001 — External Certification Authority

**Statement**

Integration with a government or independent certification authority shall remain outside the MVP unless a real authorized integration becomes available.

**Priority:** Won't Have Now  
**Status:** DEFERRED

---

# 34. Analytics Integration

## IR-ANALYTICS-001 — External Analytics

External analytics services may be considered later for operational or portfolio measurement but are not mandatory for MVP completion.

**Priority:** Could  
**Status:** DEFERRED

---

# 35. Hosting and Database Dependencies

Hosting and managed database providers are infrastructure dependencies.

They will be selected during architecture/deployment design.

Provider-specific requirements should not be introduced prematurely unless required.

This helps avoid unnecessary vendor lock-in.

---

# 36. External Integration Failure Principle

Where an optional external integration exists, the system should fail predictably.

Example:

```text
Email service unavailable
        ↓
Core order record still preserved
```

An optional notification failure should not silently destroy a valid transaction.

Specific failure behavior will be defined for each approved integration.

---

# 37. Data-to-Functional Traceability Examples

| Data Requirement | Related Functional Area |
|---|---|
| DR-ART-001 | FR-ART-001 through FR-ART-004 |
| DR-PROD-001 | FR-PROD-* |
| DR-ORDER-001 | FR-ORDER-004 through FR-ORDER-013 |
| DR-CUSTOM-001 | FR-CUSTOM-* |
| DR-REV-001 | FR-REV-* |
| DR-VERIFY-001 | FR-VERIFY-* |
| DR-CERT-001 | FR-CERT-* |

---

# 38. Constraint-to-Scope Traceability

| Constraint | Impact |
|---|---|
| CR-PLATFORM-001 | UI/architecture |
| CR-BUDGET-001 | Hosting/tool choice |
| CR-TIME-001 | MVP size |
| CR-SCOPE-002 | Recommendation scope |
| CR-SCOPE-003 | Verification architecture |
| CR-PAY-001 | Commerce design |
| CR-RESEARCH-001 | Requirement validation status |

---

# 39. Integration Priority Summary

## Required Infrastructure Capability

- Persistent database
- Image/file storage where needed
- Deployment environment

## Optional

- Email service

## Deferred

- Real payment gateway
- Courier API
- External certification authority
- Advanced analytics service

---

# 40. Current Data Model Direction

The current requirements suggest core entities such as:

```text
User
CustomerProfile
ArtisanProfile
Category
Product
ProductImage
Cart
CartItem
Order
OrderItem
CustomRequest
Quotation
Review
Notification
VerificationRecord*
CertificateRecord*
```

`*` Conditional / optional modules.

This is not yet the final database schema.

Entity relationships and normalization will be defined during database design.

---

# 41. Requirement Count Summary

Current draft includes approximately:

| Category | Count |
|---|---:|
| Data Requirements | 40+ |
| Constraint Requirements | 15 |
| Integration Requirements | 7 |
| Mandatory External Business Integrations | 0 |

Exact totals may change during consolidated review.

---

# 42. Engineering Decision

Craft BD should maintain a clear separation between:

```text
Functional Requirement
= Behavior

Data Requirement
= Information needed

Constraint
= Boundary

Integration
= External-system dependency
```

This separation will improve:

- SRS clarity
- Database design
- Architecture decisions
- Testing
- Scope control
- Requirement traceability

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Data, Constraint & Integration Requirements  
**Status:** Draft / Provisional v0.1  
**Next Step:** Requirement Acceptance Criteria & Traceability Matrix Baseline
