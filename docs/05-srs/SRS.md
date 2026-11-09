# Craft BD

# Software Requirements Specification

**Document Version:** 0.1  
**Project:** Craft BD  
**Document Type:** Software Requirements Specification  
**Phase:** 05 — Software Requirements Specification  
**Requirement Baseline Source:** Requirement Baseline v0.1  
**Status:** Draft Skeleton

---

# Document Control

## Revision History

| Version | Date | Description | Status |
|---|---|---|---|
| 0.1 | TBD | Initial SRS structure | Draft |

---

## Document Approval

| Role | Name | Status |
|---|---|---|
| Project Team | TBD | Pending |
| Academic Supervisor / Faculty | TBD | Pending |

---

# 1. Introduction

## 1.1 Purpose

[To be completed]

This section will describe the purpose of the Craft BD Software Requirements Specification and how the document will be used throughout design, implementation, testing, and academic evaluation.

---

## 1.2 Product Scope

[To be completed]

This section will summarize:

- What Craft BD is
- The problem area it addresses
- Core product capabilities
- Current MVP boundary
- Major exclusions

---

## 1.3 Intended Audience

[To be completed]

Expected audiences may include:

- Project development team
- Academic supervisor / faculty
- Software designers
- Developers
- Testers
- Future maintainers

---

## 1.4 Definitions, Acronyms, and Abbreviations

[To be completed]

Examples to be defined:

- SRS
- MVP
- FR
- NFR
- BR
- SR
- PR
- DR
- IR
- CR
- CRQ
- RTM
- QR
- UAT

---

## 1.5 References

[To be completed]

This section will reference approved Craft BD project artifacts such as:

- Requirement Baseline v0.1
- Stakeholder Analysis
- Feasibility Analysis
- Product Discovery documents
- Requirement Traceability Matrix
- Business Rule Register
- Security and Privacy Requirements

Relevant requirements-engineering standards may also be referenced where appropriate.

---

## 1.6 Document Conventions

[To be completed]

This section will define:

- Requirement ID conventions
- Priority notation
- Requirement status notation
- Evidence status
- Terminology used throughout the SRS

---

# 2. Overall Description

## 2.1 Product Perspective

[To be completed]

This section will explain Craft BD's position as a standalone responsive web application and its relationship with customers, artisans, administrators, and optional external services.

---

## 2.2 Product Functions

[To be completed]

High-level functional areas will include:

- Authentication
- Customer profile
- Artisan profile
- Product management
- Product discovery
- Cart and checkout
- Standard orders
- Structured custom orders
- Reviews
- Notifications
- Administration
- Optional verification / certificate functionality

---

## 2.3 User Classes and Characteristics

[To be completed]

Primary system actors:

### Customer

[To be completed]

### Artisan / Seller

[To be completed]

### Administrator

[To be completed]

---

## 2.4 Operating Environment

[To be completed]

Expected environment may include:

- Modern web browser
- Desktop and mobile browser layouts
- Web application server
- Relational database
- Persistent file/image storage
- Internet-connected deployment environment

Final technology choices will be documented during architecture design.

---

## 2.5 Design and Implementation Constraints

[To be completed]

This section will include approved constraints such as:

- Responsive web application
- Small-team-manageable architecture
- Low-cost academic deployment
- No mandatory microservices
- No native mobile application requirement
- Simulated payment permitted
- No blockchain requirement
- No mandatory courier integration

---

## 2.6 Assumptions and Dependencies

[To be completed]

This section will document assumptions such as:

- Browser-based access is sufficient for the MVP
- Artisan mobile-browser usability is important
- External integrations are minimized
- Primary user research is still pending for some provisional requirements

---

## 2.7 Requirement Validation Boundary

[To be completed]

This section will explicitly separate:

- Controlled requirements
- Provisional requirements
- Deferred requirements

Primary user research dependencies will be recorded here.

---

# 3. External Interface Requirements

## 3.1 User Interface Requirements

[To be completed]

This section will describe interface-level requirements for:

- Public pages
- Customer interfaces
- Artisan interfaces
- Administrator interfaces
- Responsive layouts
- Form validation
- Feedback messages

Detailed visual design will be handled during the UI/UX phase.

---

## 3.2 Software Interfaces

[To be completed]

Possible interfaces include:

- Backend API
- Relational database
- File/image storage
- Optional email service
- Future payment gateway

Only approved integrations will be specified as implementation dependencies.

---

## 3.3 Communication Interfaces

[To be completed]

This section will cover application communication requirements such as:

- HTTPS
- Client-server communication
- API request/response conventions

---

## 3.4 External Service Boundaries

[To be completed]

Explicitly deferred or optional services will include:

- Real payment provider
- Courier API
- External certification authority
- External analytics
- Email provider

---

# 4. Functional Requirements

This section will reference and organize the formal functional requirements established in Phase 04.

Requirements will not be silently renumbered or rewritten without requirement-change review.

---

## 4.1 Authentication and Access

Requirements:

`FR-AUTH-*`

[Detailed requirement references to be inserted]

---

## 4.2 Customer Profile

Requirements:

`FR-USER-*`

[To be completed]

---

## 4.3 Artisan Management

Requirements:

`FR-ART-*`

[To be completed]

---

## 4.4 Product Management

Requirements:

`FR-PROD-*`

[To be completed]

---

## 4.5 Product Discovery

Requirements:

`FR-DISC-*`

[To be completed]

---

## 4.6 Craft Context

Requirements:

`FR-CRAFT-*`

[To be completed]

Research-dependent requirements shall remain marked as provisional.

---

## 4.7 Shopping Cart

Requirements:

`FR-CART-*`

[To be completed]

---

## 4.8 Standard Order and Checkout

Requirements:

`FR-ORDER-*`

[To be completed]

---

## 4.9 Review and Rating

Requirements:

`FR-REV-*`

[To be completed]

---

## 4.10 Structured Custom Order

Requirements:

`FR-CUSTOM-*`

[To be completed]

This section shall remain explicitly marked as provisional until primary customer and artisan validation is completed.

---

## 4.11 Notifications

Requirements:

`FR-NOTIF-*`

[To be completed]

---

## 4.12 QR / Product Verification Record

Requirements:

`FR-VERIFY-*`

[To be completed]

Important boundary:

A Craft BD QR-linked record represents a platform record and shall not automatically be described as proof of physical-product authenticity.

---

## 4.13 Platform Certificate

Requirements:

`FR-CERT-*`

[To be completed]

This module remains optional.

---

## 4.14 Administration

Requirements:

`FR-ADMIN-*`

[To be completed]

Administration follows the principle:

**Admin by Exception**

---

# 5. Business Rules

Business rules defined during Phase 04 will be referenced using:

`BR-MODULE-NNN`

---

## 5.1 Product Rules

`BR-PROD-*`

[To be completed]

---

## 5.2 Cart Rules

`BR-CART-*`

[To be completed]

---

## 5.3 Standard Order Rules

`BR-ORDER-*`

[To be completed]

---

## 5.4 Custom Order Rules

`BR-CUSTOM-*`

[To be completed]

---

## 5.5 Review Rules

`BR-REV-*`

[To be completed]

---

## 5.6 Verification and Certificate Rules

`BR-VERIFY-*`  
`BR-CERT-*`

[To be completed]

---

## 5.7 Administration and Privacy Rules

`BR-ADMIN-*`  
`BR-PRIV-*`

[To be completed]

---

# 6. Data Requirements

Data requirements use:

`DR-MODULE-NNN`

---

## 6.1 User Data

`DR-USER-*`

[To be completed]

---

## 6.2 Artisan Data

`DR-ART-*`

[To be completed]

---

## 6.3 Product Data

`DR-PROD-*`

[To be completed]

---

## 6.4 Cart and Order Data

`DR-CART-*`  
`DR-ORDER-*`

[To be completed]

---

## 6.5 Custom Order and Quotation Data

`DR-CUSTOM-*`

[To be completed]

---

## 6.6 Review Data

`DR-REV-*`

[To be completed]

---

## 6.7 Notification Data

`DR-NOTIF-*`

[To be completed]

---

## 6.8 Verification / Certificate Data

`DR-VERIFY-*`  
`DR-CERT-*`

[To be completed]

---

## 6.9 Data Integrity Requirements

[To be completed]

This section will summarize:

- Entity relationships
- Referential integrity
- Historical transaction preservation
- Deactivation vs destructive deletion principles

---

# 7. Security Requirements

Security requirements use:

`SR-*`

---

## 7.1 Authentication Security

`SR-AUTH-*`

[To be completed]

---

## 7.2 Authorization

`SR-AUTHZ-*`

[To be completed]

---

## 7.3 Ownership Enforcement

`SR-OWN-*`

[To be completed]

---

## 7.4 Input Validation

`SR-INPUT-*`

[To be completed]

---

## 7.5 File Upload Security

`SR-FILE-*`

[To be completed]

---

## 7.6 Secret Management

`SR-SECRET-*`

[To be completed]

---

## 7.7 Logging and Auditability

`SR-LOG-*`

[To be completed]

---

## 7.8 Transport Security

`SR-TRANSPORT-*`

[To be completed]

---

## 7.9 Administrator Security

`SR-ADMIN-*`

[To be completed]

---

## 7.10 Verification Security

`SR-VERIFY-*`

[To be completed]

---

# 8. Privacy Requirements

Privacy requirements use:

`PR-DATA-*`

---

## 8.1 Data Minimization

[To be completed]

---

## 8.2 Public and Private Data Separation

[To be completed]

---

## 8.3 Customer Delivery Data

[To be completed]

---

## 8.4 Custom Order Privacy

[To be completed]

---

## 8.5 Uploaded Reference Image Privacy

[To be completed]

---

## 8.6 Artisan Public Information

[To be completed]

---

## 8.7 Academic Demo and Research Privacy

[To be completed]

---

# 9. Non-Functional Requirements

---

## 9.1 Performance

Requirements:

`NFR-PERF-*`

[To be completed]

---

## 9.2 Usability

Requirements:

`NFR-USE-*`

[To be completed]

---

## 9.3 Reliability

Requirements:

`NFR-REL-*`

[To be completed]

---

## 9.4 Maintainability

Requirements:

`NFR-MNT-*`

[To be completed]

---

## 9.5 Compatibility

Requirements:

`NFR-COMP-*`

[To be completed]

---

## 9.6 Availability

Requirements:

`NFR-AVL-*`

[To be completed]

---

## 9.7 Scalability

Requirements:

`NFR-SCL-*`

[To be completed]

---

## 9.8 Data Quality

Requirements:

`NFR-DATA-*`

[To be completed]

---

## 9.9 Error Handling

Requirements:

`NFR-ERR-*`

[To be completed]

---

# 10. Constraint Requirements

Constraints use:

`CR-*`

---

## 10.1 Platform Constraints

`CR-PLATFORM-*`

[To be completed]

---

## 10.2 Architecture Constraints

`CR-ARCH-*`

[To be completed]

---

## 10.3 Budget Constraints

`CR-BUDGET-*`

[To be completed]

---

## 10.4 Schedule Constraints

`CR-TIME-*`

[To be completed]

---

## 10.5 Scope Constraints

`CR-SCOPE-*`

[To be completed]

---

## 10.6 Payment Constraints

`CR-PAY-*`

[To be completed]

---

## 10.7 Verification and Certificate Constraints

`CR-VERIFY-*`  
`CR-CERT-*`

[To be completed]

---

## 10.8 Research Constraints

`CR-RESEARCH-*`

[To be completed]

---

# 11. Integration Requirements

Integration requirements use:

`IR-*`

---

## 11.1 File Storage

`IR-STORAGE-*`

[To be completed]

---

## 11.2 Email

`IR-EMAIL-*`

[To be completed]

---

## 11.3 Payment Gateway

`IR-PAY-*`

Status:

**Deferred**

---

## 11.4 Logistics

`IR-LOGISTICS-*`

Status:

**Deferred**

---

## 11.5 External Certification

`IR-CERT-*`

Status:

**Deferred**

---

## 11.6 Analytics

`IR-ANALYTICS-*`

Status:

**Deferred**

---

# 12. Requirement Priority and Scope

## 12.1 Must-Have Requirements

[To be completed]

---

## 12.2 Provisional Must-Have Requirements

[To be completed]

---

## 12.3 Should-Have Requirements

[To be completed]

---

## 12.4 Could-Have Requirements

[To be completed]

---

## 12.5 Deferred Requirements

[To be completed]

---

# 13. Requirement Dependencies

[To be completed]

Dependency models will include:

```text
Authentication
→ Authorization
→ Ownership
→ Protected Workflow
```

```text
Artisan
→ Product
→ Discovery
→ Commerce
```

```text
Customer + Artisan
→ Custom Request
→ Quotation
→ Approval
→ Production
```

---

# 14. Requirement Traceability

## 14.1 Traceability Model

```text
Stakeholder
→ Need / Pain Point
→ Requirement
→ Business / Security Rule
→ Acceptance Criteria
→ Use Case
→ Test Case
```

---

## 14.2 Requirement Traceability Matrix

[Reference to Phase 04 RTM]

Detailed mappings will continue to be maintained in the dedicated traceability artifact rather than duplicated unnecessarily inside this SRS.

---

# 15. Requirement Verification

[To be completed]

Verification approaches may include:

- Functional testing
- Integration testing
- Security testing
- Negative testing
- Performance testing
- Compatibility testing
- Usability testing
- UAT
- Document review

---

# 16. Deferred and Future Scope

Current deferred areas include:

- Real payment gateway
- Advanced AI recommendation
- Gift recommendation
- Event/workshop management
- Live chat
- Blockchain verification
- Courier API integration
- Native mobile application
- External certification integration
- Advanced analytics

Any return to active scope requires requirement-change review.

---

# 17. Research Validation Status

[To be completed]

This section will identify requirements whose user-value validation remains incomplete.

Key provisional areas currently include:

- Structured custom-order workflow
- Craft-context importance
- QR-linked product-record value
- Recommendation requirements

Synthetic personas shall not be represented as primary research evidence.

---

# 18. Requirement Change Management

Requirement changes shall follow:

`docs/04-requirements/requirement-change-control.md`

Change Request IDs use:

`CRQ-NNN`

Material changes must include impact analysis before implementation.

---

# 19. Known Open Issues

[To be completed]

Potential open items include:

- Primary customer research
- Artisan/seller research
- Final custom-order validation
- Final architecture choice
- Final browser-support matrix
- Final file-upload limits
- Final data-retention policy
- Final standard-order state model
- Final custom-order state model

---

# 20. Supporting Information

## 20.1 Related Project Documents

[To be completed]

---

## 20.2 Requirement Baseline References

Primary source:

`docs/04-requirements/requirement-baseline-v0.1.md`

---

## 20.3 Appendices

Future appendices may include:

### Appendix A — Requirement ID Reference

[To be completed]

### Appendix B — Glossary

[To be completed]

### Appendix C — Deferred Requirement Register

[To be completed]

### Appendix D — Open Research Items

[To be completed]

---

# SRS Status

**Current Version:** 0.1 Skeleton  
**Requirement Baseline:** v0.1  
**Detailed Requirements Added:** No  
**Structure Locked:** Pending Review  
**Primary Research Dependency:** Open  
**Next Step:** SRS Introduction and Product Scope
