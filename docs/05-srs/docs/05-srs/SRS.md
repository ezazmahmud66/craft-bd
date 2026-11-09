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
