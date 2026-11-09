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

The purpose of this Software Requirements Specification (SRS) is to define the functional, quality, security, privacy, data, integration, and constraint requirements for the Craft BD software system.

This document converts the controlled Craft BD Requirement Baseline v0.1 into a structured software specification that can guide subsequent activities including:

- Use-case analysis
- UML modeling
- UI/UX design
- Software architecture
- Database design
- API design
- Implementation
- Testing
- User Acceptance Testing
- Deployment
- Maintenance
- Academic evaluation

The SRS is intended to serve as the primary software-requirement reference for the project.

Requirements already established during Phase 04 retain their existing identifiers and classifications.

Material requirement changes shall follow the approved Craft BD requirement-change process rather than being introduced silently inside the SRS.

---

## 1.2 Product Scope

Craft BD is a responsive web-based platform designed to support the discovery, understanding, management, and purchasing of Bangladeshi handicraft products while providing stronger connections between products, artisans, and relevant craft information.

The system supports three primary software actors:

- Customer
- Artisan / Seller
- Administrator

The current product direction combines standard digital-commerce capabilities with artisan-oriented and craft-oriented information.

Core system capabilities include:

- User registration and authentication
- Role-based access
- Artisan profiles
- Product management
- Product browsing and searching
- Product categorization
- Shopping cart
- Checkout
- Standard ordering
- Order-status tracking
- Platform administration
- Security and privacy controls

The current product hypothesis also includes a structured custom-order workflow in which a customer may submit customization requirements to an artisan.

The provisional custom-order flow is:

```text
Customer Request
      ↓
Artisan Review
      ↓
Quotation
      ↓
Customer Approval
      ↓
Production
      ↓
Status Tracking
      ↓
Completion
```

This workflow remains a **Provisional Must-Have** because primary customer and artisan research has not yet been completed.

Craft BD may also support selected contextual and supporting capabilities such as:

- Craft-context information
- Product material information
- Region/craft-type information
- Product reviews
- Basic notifications
- QR-linked Craft BD product records

These supporting capabilities are subject to their approved priorities and validation status.

The following capabilities are not mandatory components of the current MVP:

- Real payment gateway integration
- Advanced AI-based recommendation
- Gift recommendation engine
- Event/workshop management
- Real-time chat
- Blockchain verification
- Courier API integration
- Native mobile application
- External certification authority integration
- Advanced analytics platform

The academic MVP may use simulated payment states to demonstrate commerce workflow without processing real financial transactions.

---

## 1.3 Product Positioning

Craft BD shall not be defined only as a generic handicraft e-commerce website.

The current product direction emphasizes a combination of:

```text
Craft Discovery
      +
Artisan Identity
      +
Product Information
      +
Cultural / Craft Context
      +
Structured Customization
```

Standard commerce functions support this product experience rather than representing the entire product definition.

The structured custom-order workflow is currently the strongest proposed differentiating workflow, subject to primary user validation.

---

## 1.4 Intended Audience

This SRS is intended for the following audiences.

### Project Development Team

The development team will use this document to understand:

- Required system behavior
- Requirement priorities
- Business rules
- Security requirements
- Data requirements
- Scope constraints
- Integration boundaries

---

### Academic Supervisor / Faculty

The academic supervisor or faculty may use the SRS to evaluate:

- Requirement quality
- Scope
- Software Engineering process
- Traceability
- Consistency between requirements and later design artifacts
- Implementation alignment

---

### Software Designers

Designers will use the SRS as input for:

- Use cases
- UML diagrams
- User-interface flows
- Architecture
- Database design
- API design

---

### Developers

Developers will use requirement identifiers and acceptance criteria to determine what system behavior must be implemented.

Implementation should remain traceable to approved requirements.

---

### Testers

Testing activities will use this SRS to derive:

- Functional tests
- Integration tests
- Negative tests
- Security tests
- Performance tests
- Compatibility tests
- User Acceptance Tests

---

### Future Maintainers

Future maintainers may use the SRS to understand the original purpose, constraints, business rules, and boundaries of the Craft BD system before modifying the software.

---

## 1.5 Definitions, Acronyms, and Abbreviations

| Term | Meaning |
|---|---|
| Craft BD | The software system defined by this SRS |
| SRS | Software Requirements Specification |
| MVP | Minimum Viable Product |
| FR | Functional Requirement |
| NFR | Non-Functional Requirement |
| BR | Business Rule |
| SR | Security Requirement |
| PR | Privacy Requirement |
| DR | Data Requirement |
| IR | Integration Requirement |
| CR | Constraint Requirement |
| CRQ | Requirement Change Request |
| RTM | Requirement Traceability Matrix |
| UAT | User Acceptance Testing |
| UI | User Interface |
| API | Application Programming Interface |
| QR | Quick Response code |
| Customer | A user who discovers, orders, or requests products |
| Artisan | A seller/maker who maintains a Craft BD artisan profile and associated products |
| Administrator | An authorized platform-governance user |
| Standard Order | Purchase of an existing listed product through the normal commerce workflow |
| Custom Order | A request-driven workflow involving customer requirements, artisan review, quotation, customer decision, and production status |
| Quotation | Artisan-provided commercial proposal associated with a custom request |
| Verification Record | A Craft BD platform record accessible through an approved verification identifier |
| Platform Certificate | An optional Craft BD-maintained certificate record that does not automatically represent government or external certification |
| Provisional Requirement | A technically defined requirement that still depends on unresolved evidence or user validation |
| Deferred Requirement | A requirement or capability intentionally excluded from the current MVP |

---

## 1.6 Requirement Identification Convention

Craft BD requirements use the following format:

```text
TYPE-MODULE-NNN
```

Examples:

```text
FR-PROD-001
FR-CUSTOM-025
BR-CUSTOM-001
SR-OWN-001
PR-DATA-001
NFR-USE-001
DR-ORDER-001
IR-PAY-001
CR-SCOPE-001
```

Requirement change requests use:

```text
CRQ-NNN
```

An approved requirement identifier shall not be reused for unrelated system behavior.

---

## 1.7 Requirement Priority Convention

Craft BD uses MoSCoW prioritization.

| Priority | Meaning |
|---|---|
| Must | Required for the current MVP |
| Provisional Must | Expected to be core but still requires validation |
| Should | Important but not essential for first MVP completion |
| Could | Implement if schedule and quality permit |
| Deferred / Won't Have Now | Excluded from the current MVP |

Priority does not indicate how visually impressive a feature is.

Priority is determined using factors such as:

- Core user value
- Evidence
- Security
- Data integrity
- Dependencies
- Technical feasibility
- Schedule
- Academic value

---

## 1.8 Requirement Status Convention

Requirements may use the following states:

| Status | Meaning |
|---|---|
| DRAFT | Defined but not yet formally approved |
| PROVISIONAL | Depends on unresolved validation |
| APPROVED | Accepted into the controlled baseline |
| DEFERRED | Valid but excluded from the current release |
| REJECTED | Not accepted into scope |
| DEPRECATED | Previously used but no longer active |

---

## 1.9 Evidence Convention

Requirement evidence may be classified using categories such as:

- PRIMARY_VALIDATED
- SECONDARY_SUPPORTED
- DERIVED
- TECHNICAL
- SECURITY
- LEGAL
- ACADEMIC
- PROVISIONAL

A technically well-defined requirement shall not be described as user-validated unless supporting primary evidence exists.

---

## 1.10 Document Conventions

The following conventions apply throughout this SRS:

1. Formal requirements retain the identifiers established during Phase 04.
2. The word **shall** indicates required system behavior or constraint.
3. Supporting explanatory text does not automatically create a new requirement.
4. Requirements marked `PROVISIONAL` remain subject to research-driven revision.
5. Deferred features shall not be treated as current implementation commitments.
6. Business rules remain distinct from functional requirements.
7. Security and privacy requirements apply across relevant functional modules.
8. Detailed implementation technology shall not be assumed before the corresponding architecture decision is approved.

---

## 1.11 References

The SRS is primarily derived from the controlled Craft BD project documentation.

### Product Discovery

`docs/01-discovery/`

Relevant artifacts include:

- Market research
- Competitor analysis
- User segmentation
- Problem validation
- Research planning
- Product definition

---

### Feasibility and Scope

`docs/02-scope/`

Relevant artifacts include:

- Technical feasibility
- Operational feasibility
- Economic feasibility
- Schedule feasibility
- Privacy/legal/security feasibility
- Feature prioritization
- MVP scope

---

### Stakeholder and User Analysis

`docs/03-stakeholders/`

Relevant artifacts include:

- Stakeholder register
- Power-interest analysis
- Stakeholder goals and needs
- User segmentation and provisional personas
- Pain points
- User journeys
- Role/responsibility analysis
- Requirement-source mapping

---

### Requirement Baseline

Primary source:

`docs/04-requirements/requirement-baseline-v0.1.md`

Supporting artifacts include:

- `existing-requirement-audit.md`
- `requirement-id-standard.md`
- `functional-requirements-core.md`
- `functional-requirements-commerce.md`
- `functional-requirements-custom-order.md`
- `functional-requirements-supporting.md`
- `business-rules.md`
- `non-functional-requirements.md`
- `security-privacy-requirements.md`
- `data-constraint-integration-requirements.md`
- `requirement-traceability-matrix.md`
- `requirement-priority-dependency-conflict-review.md`
- `requirement-change-control.md`

---

## 1.12 Research and Evidence Boundary

Primary customer and artisan research remains incomplete.

Therefore, this SRS shall preserve the provisional status of requirements whose product value depends on unresolved user evidence.

Important provisional areas currently include:

- Structured custom-order importance
- Craft-context importance
- QR-linked product-record value
- Selected discovery/filtering behaviors
- Recommendation-related needs

Synthetic personas and synthetic interview examples shall not be represented as primary user-research evidence.

When valid primary research becomes available, affected requirements shall be reviewed through the approved requirement-change process.

---

## 1.13 Relationship to Future Project Artifacts

This SRS will provide requirement input to later project artifacts.

```text
SRS
 ↓
Use Cases
 ↓
UML / System Analysis
 ↓
Architecture
 ↓
Database + API
 ↓
Implementation
 ↓
Testing
 ↓
UAT
```

Later artifacts must remain traceable to this SRS and the underlying Requirement Baseline.

---

## Section Status

**Section:** 1 — Introduction  
**Status:** Draft v0.1 Complete  
**Source:** Requirement Baseline v0.1 and Phase 01–04 project artifacts  
**New Requirements Introduced:** None  
**Primary Research Dependency:** Explicitly preserved

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
