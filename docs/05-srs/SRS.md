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

# 2. Overall Description

## 2.1 Product Perspective

Craft BD is planned as a standalone responsive web-based software system for supporting Bangladeshi handicraft discovery, artisan representation, standard product purchasing, and structured customer-artisan workflows.

The system will provide a shared platform through which:

```text
Customer
   ↕
Craft BD
   ↕
Artisan / Seller
```

while an authorized administrator provides platform governance and exceptional support.

Craft BD is not intended to replace:

- Physical craft production
- Courier operations
- Banking or financial systems
- Government certification systems
- Independent physical-product authentication

Instead, Craft BD manages digital records, information, communication structures, workflow states, and platform-controlled transactions.

---

## 2.2 High-Level System Context

The high-level system context is:

```text
                ┌─────────────────┐
                │    Customer     │
                └────────┬────────┘
                         │
                         ▼
               ┌───────────────────┐
               │     Craft BD      │
               │   Web Platform    │
               └───────┬───────────┘
- Integration tests
                       │
             ┌─────────┴──────────┐
             ▼                    ▼
      ┌─────────────┐      ┌──────────────┐
      │   Artisan   │      │ Administrator│
      │  / Seller   │      │              │
      └─────────────┘      └──────────────┘
```

Optional future external services may include:

- Email provider
- Payment gateway
- Courier/logistics provider
- External certification authority
- Analytics service

These external services are not all mandatory dependencies of the current MVP.

---

## 2.3 Product Functions

Craft BD is divided into several functional areas.

### 2.3.1 Authentication and Access

The system provides:

- Customer registration
- Artisan registration
- Login
- Logout
- Role recognition
- Protected access based on role and authorization

---

### 2.3.2 Customer Profile

Customers may maintain supported account/profile information required for their platform interactions.

Customer profile functionality remains secondary to the core ordering workflows.

---

### 2.3.3 Artisan Profile

The system provides public artisan profiles containing approved information such as:

- Artisan name
- Region/location
- Expertise
- Experience
- Biography
- Associated products

Artisans may manage their own permitted profile information.

---

### 2.3.4 Product Management

Authorized artisans may manage their own products.

Major product functions include:

- Create product
- Edit owned product
- Deactivate owned product
- Maintain price
- Maintain stock
- Upload product images
- Assign category
- Maintain product description
- Provide selected product-context information

---

### 2.3.5 Product Discovery

Users may discover products through:

- Product catalog
- Product-detail pages
- Category browsing
- Search
- Selected filtering

Possible supporting information may include:

- Material
- Craft type
- Region
- Artisan information
- Craft context

Some discovery enhancements remain provisional or lower priority.

---

### 2.3.6 Standard Commerce

The standard commerce workflow supports purchasing an existing listed product.

```text
Product
   ↓
Cart
   ↓
Checkout
   ↓
Order Confirmation
   ↓
Order Record
   ↓
Status Tracking
```

The academic MVP may demonstrate payment behavior using simulated payment states.

---

### 2.3.7 Structured Custom Orders

Craft BD currently includes a structured custom-order workflow as a provisional core capability.

```text
Customer
   ↓
Custom Request
   ↓
Artisan Review
   ↓
Quotation
   ↓
Customer Decision
   ↓
Production Workflow
   ↓
Status Tracking
```

Potential custom requirements include:

- Product type
- Design
- Color
- Size
- Material
- Quantity
- Reference image
- Additional instructions

The exact value and final scope of this workflow remain dependent on primary customer and artisan validation.

---

### 2.3.8 Reviews

Where review functionality is implemented, eligible customers may:

- View product reviews
- Submit ratings
- Submit review text

Review eligibility is controlled through approved business rules.

An artisan shall not be able to remove a legitimate negative review merely because it is unfavorable.

---

### 2.3.9 Notifications

The system may provide basic notifications for important events such as:

- New custom request
- Quotation available
- Quotation approval
- Quotation rejection
- Important order-status changes

The MVP does not require real-time push-notification infrastructure.

---

### 2.3.10 QR-Linked Product Records

Where implemented, Craft BD may provide a QR-linked platform record containing approved product information.

The intended relationship is:

```text
QR Code
   ↓
Craft BD URL
   ↓
Platform Product / Verification Record
```

This functionality shall not be represented as guaranteed independent proof of physical-product authenticity.

---

### 2.3.11 Platform Certificate Records

Craft BD may optionally maintain platform-level certificate records for selected products.

Such records remain optional and shall not be represented as government or independent external certification unless a legitimate external authority is integrated.

---

### 2.3.12 Administration

Authorized administrators may perform selected governance activities such as:

- Manage user status
- Manage categories
- Moderate platform content
- Moderate reviews
- Support exceptional platform cases
- Manage optional verification records
- Manage optional certificate records

The system follows the principle:

**Admin by Exception**

Routine valid Customer–Artisan workflows should not require unnecessary administrator approval.

---

## 2.4 User Classes and Characteristics

### 2.4.1 Customer

The Customer is a primary system user.

Typical customer goals include:

- Discover handicraft products
- Understand product information
- Learn about artisans
- Purchase existing products
- Request customized products
- Review artisan quotations
- Track order progress
- Review eligible purchases

Customers may access Craft BD through desktop or mobile browsers.

The interface should not assume advanced technical knowledge.

---

### 2.4.2 Artisan / Seller

The Artisan is a primary system user responsible for presenting and managing craft products.

Typical artisan goals include:

- Maintain a professional artisan profile
- Add and manage products
- Receive structured custom requests
- Review customer requirements
- Create quotations
- Manage approved custom-order progress

Artisan usability is particularly important because some target users may rely primarily on mobile devices and may already use simpler social-media-based selling workflows.

Therefore, unnecessary administrative complexity should be avoided.

The exact usability needs remain subject to primary artisan research.

---

### 2.4.3 Administrator

The Administrator is an authorized operational user responsible for platform governance.

Typical administrator responsibilities include:

- User-status management
- Category management
- Content moderation
- Review moderation
- Exceptional support actions
- Optional verification/certificate management

Administrators are not expected to participate in every normal customer-artisan transaction.

---

## 2.5 Stakeholders That Are Not Direct System Actors

Not every project stakeholder is a software actor.

Relevant non-actor stakeholders include:

### Project Development Team

Responsible for analysis, design, development, testing, deployment, and documentation.

### Academic Supervisor / Faculty

Provides academic guidance and evaluates the Software Engineering process and project outcome.

### Regulatory and Consumer-Protection Stakeholders

Influence privacy, digital-commerce, security, and user-protection constraints but do not necessarily interact directly with the Craft BD software.

### Future External Providers

Examples may include:

- Payment provider
- Courier provider
- Email provider
- External certification organization

These become software actors or external systems only if approved integrations are implemented.

---

## 2.6 Operating Environment

Craft BD is intended to operate as a responsive web application.

### Client Environment

Users are expected to access Craft BD using:

- Desktop web browsers
- Laptop web browsers
- Mobile web browsers

A native mobile application is not required for the initial MVP.

---

### Server Environment

The deployed system is expected to include:

```text
Web Client
    ↓
Application / API Layer
    ↓
Relational Database
```

Persistent file/image storage may also be required.

The exact hosting provider, programming framework, database technology, and storage provider will be selected during architecture and implementation planning.

---

### Network Environment

The deployed application requires internet connectivity for normal remote access.

Communication with the production deployment shall use HTTPS.

---

## 2.7 Design and Implementation Constraints

### 2.7.1 Responsive Web Constraint

The initial Craft BD release shall be implemented as a responsive web application.

A separate native Android or iOS application is not required.

---

### 2.7.2 Small-Team Constraint

The architecture and implementation shall remain manageable for a small academic project team.

Unnecessary architectural complexity should be avoided.

---

### 2.7.3 Architecture Constraint

The current preferred architectural direction is:

```text
Responsive Frontend
        ↓
REST-style API
        ↓
Modular Monolithic Backend
        ↓
Relational Database
```

This remains an architecture direction rather than a finalized technology-stack decision.

A microservice architecture is not required for the MVP.

---

### 2.7.4 Budget Constraint

Development and academic deployment should use free or low-cost infrastructure where practical.

The current MVP shall not depend on unnecessary paid commercial services.

---

### 2.7.5 Schedule Constraint

The project scope must remain achievable within the academic project schedule.

When schedule pressure occurs:

```text
Reduce Optional Scope
        ↓
Protect Core Quality
```

Security, core workflow correctness, testing, and deployment shall not be sacrificed merely to preserve optional features.

---

### 2.7.6 Payment Constraint

The MVP may use simulated payment.

Real payment integration is not required.

Actual financial credentials such as:

- Card PIN
- Bank password
- Mobile financial service PIN

shall not be required by the academic MVP.

---

### 2.7.7 Verification Constraint

QR-linked Craft BD records shall not automatically be described as proof that a physical item is authentic.

---

### 2.7.8 Certification Constraint

Craft BD platform certificate records shall not be represented as government certification without legitimate external authority.

---

### 2.7.9 Technology Constraint

Implementation technologies shall be selected based on:

- Project requirements
- Team capability
- Maintainability
- Security
- Deployment feasibility
- Academic schedule

A technology shall not be selected merely because it is fashionable.

---

## 2.8 Assumptions

The current SRS is based on the following assumptions.

### AS-01 — Browser Access

A responsive web application is sufficient for the initial Customer, Artisan, and Administrator workflows.

---

### AS-02 — Internet Availability

Users have sufficient internet access to use the web platform when performing online Craft BD activities.

---

### AS-03 — Artisan Browser Access

Target artisans can access the platform through a supported desktop or mobile web browser.

This assumption should be reviewed during artisan research.

---

### AS-04 — Relational Data Suitability

Core Craft BD data such as users, artisans, products, orders, custom requests, quotations, and reviews can be appropriately represented using a relational data model.

---

### AS-05 — Simulated Payment Sufficiency

Simulated payment is sufficient for demonstrating the academic commerce workflow.

---

### AS-06 — External Services Are Optional

The core application can operate without real payment, courier, external certification, and advanced analytics integrations.

---

### AS-07 — Structured Customization Value

The structured custom-order workflow is assumed to provide sufficient value compared with informal customer-artisan communication.

This assumption remains **unvalidated** and requires primary research.

---

## 2.9 Dependencies

### 2.9.1 Authentication Dependency

Protected functionality depends on successful authentication and authorization.

```text
Authentication
      ↓
Authorization
      ↓
Ownership
      ↓
Protected Action
```

---

### 2.9.2 Artisan–Product Dependency

Products managed by artisans depend on a valid artisan relationship.

```text
Artisan
   ↓
Product
   ↓
Discovery
```

---

### 2.9.3 Standard Commerce Dependency

```text
Product
   ↓
Cart
   ↓
Checkout
   ↓
Order
```

A valid standard order therefore depends on valid product and customer information.

---

### 2.9.4 Review Dependency

Product-review eligibility depends on the approved purchase condition.

```text
Customer
   ↓
Eligible Purchase
   ↓
Review
```

---

### 2.9.5 Custom Order Dependency

```text
Customer + Artisan
       ↓
Custom Request
       ↓
Quotation
       ↓
Customer Approval
       ↓
Production
```

Production is dependent on quotation approval.

---

### 2.9.6 Verification Dependency

```text
Product
   ↓
Verification Record
   ↓
Verification Identifier
   ↓
QR Reference
```

The verification module therefore depends on stable product records.

---

### 2.9.7 Certificate Dependency

Certificate functionality depends on:

- Valid product
- Authorized administration
- Approved certificate model

It remains optional.

---

## 2.10 Research and Validation Dependencies

Several product requirements remain dependent on primary research.

### High-Priority Validation Areas

- Structured custom-order usefulness
- Artisan willingness to manage structured requests
- Artisan willingness to update workflow statuses
- Customer value from quotation approval
- Craft-context usefulness
- QR-linked product-record usefulness

Until primary evidence is available, related requirements shall remain marked as provisional where applicable.

---

## 2.11 Third-Party Dependencies

The current MVP intentionally minimizes third-party dependency.

### Required Infrastructure Categories

The system may require:

- Deployment hosting
- Relational database hosting
- Persistent file/image storage

### Optional External Services

- Email provider

### Deferred External Services

- Real payment gateway
- Courier/logistics API
- External certification authority
- Advanced analytics provider

Failure to implement a deferred integration shall not be considered failure of the core MVP.

---

## 2.12 Scope Boundary

Craft BD is responsible for digital workflow and information management.

Craft BD may:

```text
Record production status
```

but does not:

```text
Physically manufacture the product
```

Craft BD may:

```text
Record quality-check status
```

but does not:

```text
Physically inspect the product
```

Craft BD may:

```text
Record shipment status
```

but does not:

```text
Operate a courier service
```

Craft BD may:

```text
Display a QR-linked platform record
```

but does not automatically:

```text
Prove physical authenticity
```

These boundaries prevent the SRS from claiming capabilities that the software itself cannot perform.

---

## 2.13 Product Evolution Direction

Potential future evolution may include:

- Real payment integration
- Courier integration
- Improved recommendations
- Expanded craft-content features
- Events/workshops
- External certification
- Advanced analytics
- Native applications

These possibilities are not commitments in the current MVP.

They require future requirement-change review before implementation.

---

## 2.14 Overall Product Principle

The initial Craft BD release should prioritize:

```text
Complete Core Workflow
        +
Security
        +
Traceability
        +
Testing
        +
Deployment
```

over:

```text
Large Feature Count
```

The success of the academic MVP should therefore be evaluated by the completeness and engineering quality of the approved workflows rather than the number of optional features implemented.

---

## Section Status

**Section:** 2 — Overall Description  
**Status:** Draft v0.1 Complete  
**Requirement Baseline:** v0.1  
**New Functional Requirements Introduced:** None  
**Primary Research Dependency:** Explicitly preserved  
**Next Section:** External Interface Requirements

# 3. External Interface Requirements

## 3.1 Purpose

This section defines how Craft BD users and approved external systems interact with the software.

The section covers:

- User interfaces
- Application/API interfaces
- Data-storage interfaces
- File-storage interfaces
- Communication interfaces
- Optional external-service interfaces

Detailed visual design, endpoint definitions, and provider-specific configurations will be completed during later UI/UX, architecture, API, and deployment phases.

---

## 3.2 User Interface Requirements

Craft BD shall provide a responsive web-based user interface.

The interface shall support the approved Customer, Artisan, Administrator, and public workflows.

The interface design shall follow the relevant usability requirements defined under `NFR-USE-*`.

---

## 3.3 Public User Interface

Users who are not authenticated may access approved public information.

Potential public interfaces include:

- Home / landing page
- Product catalog
- Product details
- Category browsing
- Product search
- Public artisan profiles
- Public craft-context information where available
- Published product reviews
- QR-linked public verification records where implemented

Private account or transaction information shall not be exposed through public interfaces.

---

## 3.4 Customer Interface

Authenticated customers shall receive access to Customer-authorized functions.

The customer interface may include:

### Account

- Login/logout
- Customer profile
- Account information

### Product Discovery

- Browse products
- Search
- Filter
- Product details
- Artisan profile
- Craft information where supported

### Standard Commerce

- Shopping cart
- Checkout
- Order confirmation
- Order history where implemented
- Order details
- Order-status tracking
- Simulated payment status

### Custom Order

Where the provisional custom-order module is included:

- Create custom request
- Enter customization details
- Upload reference image
- View submitted requests
- View quotation
- Approve/reject quotation
- Track custom-order status

### Reviews

Where the customer is eligible:

- Submit product rating
- Submit product review

### Notifications

Where implemented:

- View relevant notifications
- View important order/custom-order updates

---

## 3.5 Artisan Interface

Authenticated artisans shall receive access to approved Artisan functions.

The artisan interface may include:

### Artisan Profile

- View own profile
- Update own permitted profile information
- View associated products

### Product Management

- Create product
- Edit owned product
- Deactivate owned product
- Maintain price
- Maintain stock
- Upload product images
- Assign supported product information

### Standard Order Operations

Where artisan-side standard-order management is required:

- View relevant orders
- Perform authorized order-status updates

### Custom Order Operations

Where the structured custom-order module is included:

- View assigned custom requests
- View submitted customer requirements
- Mark request under review
- Reject eligible request
- Create quotation
- Submit quotation
- View customer decision
- Update approved production statuses

The interface should minimize unnecessary data-entry and administrative burden.

---

## 3.6 Administrator Interface

The administrator interface shall be restricted to authenticated and authorized administrators.

Potential administrator functionality includes:

- View approved user-account information
- Activate/deactivate user status
- Create/update/deactivate categories
- Moderate product content
- Moderate artisan-profile content
- Moderate reviews
- View approved order information for support
- Perform approved exceptional actions
- Manage verification records where implemented
- Manage certificate records where implemented

The administrator interface shall follow the principle:

```text
Admin by Exception
```

Normal customer-artisan interactions should not require unnecessary administrator involvement.

---

## 3.7 Responsive Interface Requirements

The user interface shall support both desktop and mobile browser layouts.

Core workflow access should remain available at approved desktop and mobile viewport sizes.

Responsive behavior shall be tested for selected workflows including:

- Login
- Product browsing
- Product details
- Cart
- Checkout
- Custom-order submission
- Artisan request management
- Administrator core operations

A native mobile application is not required for the initial MVP.

---

## 3.8 Form Interface Requirements

Forms shall provide sufficient information for users to understand required input.

Relevant forms may include:

- Registration
- Login
- Customer profile
- Artisan profile
- Product creation/editing
- Checkout
- Custom-order request
- Quotation
- Review
- Category management

Mandatory fields shall be distinguishable from optional fields where practical.

Invalid submissions shall provide understandable validation feedback.

---

## 3.9 User Feedback Interface

Important user actions shall provide visible success or failure feedback.

Examples include:

- Registration
- Login
- Product creation
- Product update
- Add to cart
- Checkout
- Order confirmation
- Custom-request submission
- Quotation submission
- Quotation approval
- Status change
- Review submission
- Administrative action

The interface shall not indicate success when the authoritative backend operation has failed.

---

## 3.10 Error Interface

User-facing errors shall be understandable without exposing sensitive implementation information.

Examples of appropriate user-facing outcomes include:

```text
Invalid email or password.
```

```text
You are not authorized to perform this action.
```

```text
The requested record was not found.
```

```text
The uploaded file is not supported.
```

User-facing interfaces shall not intentionally expose:

- Application secrets
- Database credentials
- Internal stack traces
- Private keys
- Sensitive server configuration

---

## 3.11 Application / API Interface

Craft BD is expected to use an application interface between the web client and authoritative backend logic.

The current preferred architectural direction is:

```text
Web Client
    ↓
Application / REST-style API
    ↓
Business Logic
    ↓
Relational Database
```

The exact API framework and endpoint structure will be defined during API-design and architecture phases.

---

## 3.12 API Responsibility

The authoritative application/API layer shall be responsible for enforcing relevant requirements such as:

- Authentication
- Authorization
- Resource ownership
- Business rules
- Input validation
- State-transition validation
- Data-access boundaries

Client-side validation may improve usability but shall not replace authoritative backend validation.

---

## 3.13 API Data Exchange

The final API specification shall define:

- Request structure
- Response structure
- Supported HTTP operations
- Authentication mechanism
- Validation errors
- Authorization failures
- Pagination where required
- Search/filter parameters
- File-upload behavior

The current SRS does not prescribe a final serialization format or framework before architecture approval.

---

## 3.14 API Failure Handling

The application interface shall distinguish appropriate classes of failure.

Examples may include:

- Invalid input
- Authentication failure
- Authorization failure
- Resource not found
- Business-rule violation
- Server failure

A failed protected operation shall not be represented as successful.

---

## 3.15 Database Interface

Craft BD is expected to use a relational database for core persistent application data.

Core data categories include:

- Users
- Artisan profiles
- Products
- Categories
- Cart data
- Orders
- Order items
- Custom requests
- Quotations
- Reviews
- Notifications

Conditional modules may add:

- Verification records
- Certificate records
- Administrative audit records

The final database technology and schema will be defined during database-design activities.

---

## 3.16 Database Integrity Boundary

Application/database interaction shall preserve relevant integrity requirements.

Examples include:

```text
Product → valid Artisan
```

```text
Order → valid Customer
```

```text
OrderItem → valid Order
```

```text
Quotation → valid Custom Request
```

```text
Review → valid Product
```

Invalid relationships shall be prevented or handled according to approved data and business rules.

---

## 3.17 File Storage Interface

Craft BD requires persistent file/image storage where approved upload functionality is implemented.

Potential stored files include:

- Product images
- Artisan profile images
- Custom-order reference images

The storage provider has not yet been selected.

---

## 3.18 File Storage Requirements

The application-to-storage interface shall support:

- Uploading approved files
- Storing or receiving a safe file reference
- Associating stored content with the correct application resource
- Retrieving authorized content
- Preventing unauthorized association or access

The system shall not rely on untrusted client filenames as authoritative storage paths.

---

## 3.19 Public and Private File Access

Different files may have different visibility.

### Public or Potentially Public

Examples:

- Product images
- Approved artisan profile images

### Private / Restricted

Examples:

- Customer custom-order reference images

Private files shall follow the authorization rules of the associated resource.

A custom-order reference image shall not automatically become publicly accessible.

---

## 3.20 Communication Interface

The deployed Craft BD system shall support normal web communication between browser clients and the application.

Production deployment shall use HTTPS.

The communication interface shall support the selected application/API protocol and approved file-upload mechanism.

---

## 3.21 HTTPS Requirement

Normal production authentication and protected application communication shall occur over HTTPS.

Plain HTTP shall not intentionally be used to transmit production authentication credentials.

Related requirements include:

- `SR-TRANSPORT-001`
- `SR-TRANSPORT-002`

---

## 3.22 Notification Interface

Craft BD may provide internal notification functionality.

The initial MVP may implement:

- In-app notifications
- Dashboard alerts

Optional future support may include:

- Email notifications

Real-time mobile push notifications and SMS are not required.

---

## 3.23 Email Interface

Email integration is optional.

If an email service is implemented, it may support selected events such as:

- Account-related messages
- Custom quotation availability
- Important order updates

The core business transaction shall not depend solely on successful email delivery.

Example:

```text
Quotation Saved Successfully
        ↓
Email Delivery Fails
        ↓
Quotation Record Still Exists
```

The exact email provider remains undecided.

Related requirement:

`IR-EMAIL-001`

---

## 3.24 Payment Interface

The academic MVP does not require a real payment-provider interface.

The MVP may use:

```text
Simulated Payment
```

to demonstrate payment-related workflow states.

Related requirement:

`IR-PAY-001 — DEFERRED`

If real payment is introduced later, a separate integration specification must define:

- Provider
- Authentication
- Transaction creation
- Callback/webhook handling
- Success/failure states
- Security
- Error handling
- Testing

---

## 3.25 Logistics Interface

Direct courier/logistics API integration is not required for the MVP.

Craft BD may record internal status such as:

```text
READY_TO_SHIP
SHIPPED
DELIVERED
```

without receiving live courier information.

Related requirement:

`IR-LOGISTICS-001 — DEFERRED`

---

## 3.26 External Certification Interface

Craft BD does not currently depend on a government or independent external certification interface.

Any Craft BD certificate functionality remains a platform-maintained record unless a legitimate external certification service is later integrated.

Related requirement:

`IR-CERT-001 — DEFERRED`

---

## 3.27 Verification Interface

Where QR-linked verification is implemented, a user may access an approved verification URL using a valid verification identifier.

High-level interaction:

```text
QR / Verification Link
       ↓
Craft BD Verification Endpoint
       ↓
Approved Public Product Record
```

Invalid verification identifiers shall not expose unrelated records.

---

## 3.28 Analytics Interface

External analytics integration is not required for the MVP.

If analytics is introduced later, it shall be reviewed for:

- Privacy
- Data minimization
- Security
- Scope
- Academic value

Related requirement:

`IR-ANALYTICS-001 — DEFERRED`

---

## 3.29 Browser Interface Compatibility

The final approved browser-support matrix will be established during test planning.

The MVP is expected to support modern project-approved desktop and mobile browsers.

Browser-specific implementation shall not intentionally remove access to core functionality without documented reason.

---

## 3.30 Interface Security Principle

Every protected interface shall follow:

```text
Request
   ↓
Authentication
   ↓
Authorization
   ↓
Ownership
   ↓
Business Rule
   ↓
Validation
   ↓
Action
```

A user interface control such as a hidden button does not replace backend access control.

---

## 3.31 Interface Privacy Principle

Interfaces shall expose only the information required for the authorized interaction.

Example:

A public artisan page may expose:

- Public name
- Biography
- Expertise
- Products

but shall not expose:

- Password data
- Authentication secrets
- Private account information

Similarly, Customer A shall not receive Customer B's private order information through any user or API interface.

---

## 3.32 Interface Dependency Summary

| Interface | MVP Status |
|---|---|
| Responsive Web UI | Required |
| Application/API Interface | Required |
| Relational Database Interface | Required |
| File Storage Interface | Required where uploads exist |
| HTTPS | Required |
| In-App Notification | Should |
| Email | Optional |
| Real Payment Gateway | Deferred |
| Courier API | Deferred |
| External Certification | Deferred |
| External Analytics | Deferred |

---

## 3.33 Interface Design Boundary

This SRS defines required interface behavior and boundaries.

It does not yet define:

- Final page layout
- Visual design system
- Final API endpoint URLs
- Final request schemas
- Final database tables
- Final storage provider
- Final hosting provider
- Final email provider

These decisions belong to later design phases.

---

## Section Status

**Section:** 3 — External Interface Requirements  
**Status:** Draft v0.1 Complete  
**Final UI Design:** Pending  
**Final API Contract:** Pending  
**Final Provider Selection:** Pending  
**New Product Requirements Introduced:** None  
**Next Section:** Functional Requirements

# 4. Functional Requirements

## 4.1 Functional Requirement Convention

Functional requirements in this SRS retain the identifiers established during Phase 04.

Format:

`FR-MODULE-NNN`

Each requirement should be interpreted together with its related:

- Business Rules
- Security Requirements
- Privacy Requirements
- Data Requirements
- Acceptance Criteria
- Priority
- Validation Status

This SRS does not silently renumber or redefine existing requirements.

---

# 4.2 Authentication and Access Requirements

## FR-AUTH-001 — Customer Registration

**Statement**

The system shall allow a new user to register a customer account using the required account information.

**Actor:** Visitor / Customer  
**Priority:** Must  
**Status:** DRAFT  
**Evidence:** DERIVED / Standard Platform Requirement

**Acceptance Criteria**

Given a visitor who does not already have an account, when valid registration information is submitted, then the system shall create a customer account.

Invalid mandatory information or account conflicts shall prevent successful registration.

---

## FR-AUTH-002 — Artisan Registration

**Statement**

The system shall allow a new user to register an artisan/seller account using the required account information.

**Actor:** Visitor / Artisan  
**Priority:** Must  
**Status:** DRAFT  
**Evidence:** DERIVED

**Acceptance Criteria**

A valid artisan registration shall create an artisan account and associate it with the corresponding artisan-profile structure.

---

## FR-AUTH-003 — User Login

**Statement**

The system shall allow a registered user to authenticate using valid credentials.

**Actors:**

- Customer
- Artisan
- Administrator

**Priority:** Must  
**Status:** DRAFT  
**Evidence:** DERIVED

**Acceptance Criteria**

Valid credentials shall authenticate the user.

Invalid credentials shall not create an authenticated session.

After authentication, access shall remain subject to role and authorization rules.

---

## FR-AUTH-004 — User Logout

**Statement**

The system shall allow an authenticated user to terminate their current authenticated session.

**Priority:** Must  
**Status:** DRAFT

**Acceptance Criteria**

After successful logout, the terminated authentication context shall no longer authorize protected application actions.

---

## FR-AUTH-005 — Role Recognition

**Statement**

The system shall identify an authenticated user's assigned role and use the role when determining access to protected functionality.

Supported MVP roles include:

- CUSTOMER
- ARTISAN
- ADMIN

**Priority:** Must  
**Status:** DRAFT  
**Related Security:** `SR-AUTHZ-*`

---

# 4.3 Customer Profile Requirements

## FR-USER-001 — View Own Profile

**Statement**

The system shall allow an authenticated customer to view permitted information from their own customer profile.

**Actor:** Customer  
**Priority:** Should  
**Status:** DRAFT

**Acceptance Criteria**

The customer shall be able to view their own profile without receiving another customer's private information.

---

## FR-USER-002 — Update Own Profile

**Statement**

The system shall allow an authenticated customer to modify supported fields of their own customer profile.

**Actor:** Customer  
**Priority:** Should  
**Status:** DRAFT

**Acceptance Criteria**

Valid updates shall be stored for the authenticated customer.

A customer shall not be able to modify another customer's profile.

---

# 4.4 Artisan Requirements

## FR-ART-001 — Create and Maintain Artisan Profile

**Statement**

The system shall allow an artisan account to maintain an artisan profile containing approved professional information.

Possible profile information includes:

- Name
- Region/location
- Expertise
- Experience
- Biography
- Profile image

**Actor:** Artisan  
**Priority:** Must  
**Status:** DRAFT  
**Evidence:** SECONDARY_SUPPORTED

**Acceptance Criteria**

Valid artisan profile information shall be associated with the authenticated artisan account.

---

## FR-ART-002 — View Artisan Profile

**Statement**

The system shall allow users to view approved public information associated with an artisan profile.

**Actors:**

- Public User
- Customer

**Priority:** Must  
**Status:** DRAFT  
**Evidence:** SECONDARY_SUPPORTED

**Acceptance Criteria**

The public artisan profile shall expose only fields approved for public display.

Private authentication/account information shall not be exposed.

---

## FR-ART-003 — Update Own Artisan Profile

**Statement**

The system shall allow an authenticated artisan to modify supported information in their own artisan profile.

**Actor:** Artisan  
**Priority:** Must  
**Status:** DRAFT

**Related Rules:**

- `BR-ART-001`
- Ownership security requirements

**Acceptance Criteria**

The artisan may update permitted fields of their own profile.

The artisan shall not be permitted to modify another artisan's profile through normal artisan functionality.

---

## FR-ART-004 — Display Artisan Products

**Statement**

The system shall allow users to view eligible products associated with an artisan from the artisan's public profile.

**Actors:**

- Public User
- Customer

**Priority:** Must  
**Status:** DRAFT

**Acceptance Criteria**

Products displayed for an artisan shall correspond to the correct artisan relationship and product-visibility rules.

---

# 4.5 Product Management Requirements

## FR-PROD-001 — Create Product

**Statement**

The system shall allow an authenticated artisan to create a product associated with their own artisan account.

**Actor:** Artisan  
**Priority:** Must  
**Status:** DRAFT

**Related Data:** `DR-PROD-*`

**Acceptance Criteria**

A valid product submission shall create a product associated with the authenticated artisan.

Missing or invalid mandatory information shall prevent successful creation.

---

## FR-PROD-002 — Edit Own Product

**Statement**

The system shall allow an authenticated artisan to modify permitted information for a product they own.

**Actor:** Artisan  
**Priority:** Must  
**Status:** DRAFT

**Related Rules:**

- `BR-PROD-001`
- `SR-OWN-001`

**Acceptance Criteria**

The owning artisan may save valid changes.

A non-owning artisan shall be denied.

---

## FR-PROD-003 — Deactivate Own Product

**Statement**

The system shall allow an authenticated artisan to deactivate an owned product so that the product is no longer available for normal customer ordering.

**Actor:** Artisan  
**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-PROD-006`

**Acceptance Criteria**

A deactivated product shall no longer be available for new normal orders while historical transaction records remain preserved where required.

---

## FR-PROD-004 — Maintain Product Price

**Statement**

The system shall allow an authorized artisan to define and update the current selling price of an owned product.

**Actor:** Artisan  
**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-PROD-003`

**Acceptance Criteria**

Invalid price values shall be rejected.

Valid current price information shall be available to approved commerce functions.

---

## FR-PROD-005 — Maintain Product Stock

**Statement**

The system shall allow an authorized artisan to maintain the available stock quantity of an owned standard product where inventory tracking applies.

**Actor:** Artisan  
**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-PROD-004`

**Acceptance Criteria**

Negative or otherwise invalid stock values shall be rejected.

---

## FR-PROD-006 — Upload Product Images

**Statement**

The system shall allow an authenticated artisan to upload supported images for an owned product.

**Actor:** Artisan  
**Priority:** Must  
**Status:** DRAFT

**Related Security:**

- `SR-FILE-001`
- `SR-FILE-002`
- `SR-FILE-003`
- `SR-FILE-004`
- `SR-FILE-005`

**Acceptance Criteria**

Valid supported files shall be associated with the correct product.

Invalid or unauthorized uploads shall be rejected.

---

## FR-PROD-007 — Assign Product Category

**Statement**

The system shall require a product to reference an available valid product category according to the approved category model.

**Actor:** Artisan  
**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-PROD-002`

---

## FR-PROD-008 — Store Product Description

**Statement**

The system shall allow an artisan to provide and maintain a description for an owned product.

**Actor:** Artisan  
**Priority:** Must  
**Status:** DRAFT

**Acceptance Criteria**

Valid product-description information shall be stored and made available on the relevant public product-details interface.

---

## FR-PROD-009 — Store Product Material Information

**Statement**

The system shall allow supported material information to be associated with a product.

**Actor:** Artisan  
**Priority:** Should  
**Status:** DRAFT  
**Evidence:** SECONDARY_SUPPORTED

**Acceptance Criteria**

Where material information exists, permitted users shall be able to view the approved information.

---

## FR-PROD-010 — Store Craft Type / Region Information

**Statement**

The system shall allow supported craft-type and region information to be associated with a product where applicable.

**Actor:** Artisan  
**Priority:** Should  
**Status:** DRAFT  
**Evidence:** SECONDARY_SUPPORTED

**Acceptance Criteria**

Valid stored craft-type and region information shall be available for approved product display and supported discovery behavior.

---

# 4.6 Product Discovery Requirements

## FR-DISC-001 — Browse Available Products

**Statement**

The system shall allow users to browse products that are currently eligible for public display.

**Actors:**

- Public User
- Customer

**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-PROD-005`

**Acceptance Criteria**

Eligible products shall appear in the public catalog.

Products that do not satisfy visibility rules shall not appear as normally available products.

---

## FR-DISC-002 — View Product Details

**Statement**

The system shall allow users to view approved public details of an available product.

**Actors:**

- Public User
- Customer

**Priority:** Must  
**Status:** DRAFT

Product details may include:

- Product name
- Images
- Price
- Description
- Availability
- Category
- Material
- Artisan
- Supported craft information

**Acceptance Criteria**

A valid eligible product shall display its approved public information and relevant artisan association.

---

## FR-DISC-003 — Browse Products by Category

**Statement**

The system shall allow users to browse available products associated with a selected valid category.

**Priority:** Must  
**Status:** DRAFT

**Acceptance Criteria**

Selecting an available category shall return eligible products associated with that category.

---

## FR-DISC-004 — Search Products

**Statement**

The system shall allow users to search available products using supported searchable information.

**Priority:** Must  
**Status:** DRAFT

**Related Security:** `SR-INPUT-005`

**Acceptance Criteria**

A supported matching search term shall return relevant eligible products.

Products that are not permitted for public display shall not be exposed through search.

---

## FR-DISC-005 — Filter Products by Category

**Statement**

The system shall allow users to filter available products using category information.

**Priority:** Should  
**Status:** DRAFT

**Acceptance Criteria**

Applying a valid category filter shall restrict results to eligible products belonging to the selected category.

---

## FR-DISC-006 — Filter Products by Price Range

**Statement**

The system shall allow users to filter available products using a supported price range.

**Priority:** Should  
**Status:** DRAFT

**Acceptance Criteria**

Valid minimum and/or maximum price criteria shall exclude products outside the selected range.

---

## FR-DISC-007 — Filter Products by Material

**Statement**

The system shall allow users to filter available products using supported material information where such data is available.

**Priority:** Should  
**Status:** PROVISIONAL  
**Evidence:** PROVISIONAL / SECONDARY_SUPPORTED

**Acceptance Criteria**

Selecting a supported material shall restrict results to eligible products associated with that material.

---

## FR-DISC-008 — Filter Products by Craft Type

**Statement**

The system shall allow users to filter available products using supported craft-type information where such data is available.

**Priority:** Should  
**Status:** PROVISIONAL  
**Evidence:** PROVISIONAL

**Acceptance Criteria**

Selecting a supported craft type shall restrict results to eligible products associated with that craft type.

---

# 4.6.1 Craft Context Requirements

## FR-CRAFT-001 — View Basic Craft Context

**Statement**

The system shall allow users to view approved contextual craft information associated with a relevant product or craft type where such information exists.

Possible information may include:

- Origin
- Materials
- Technique
- Traditional use
- Cultural context

**Priority:** Should  
**Status:** PROVISIONAL  
**Evidence:** PROVISIONAL / SECONDARY_SUPPORTED

**Acceptance Criteria**

Where approved contextual information exists, it shall be accessible through the relevant product or craft interface.

---

## FR-CRAFT-002 — Maintain Craft Context

**Statement**

The system shall allow an authorized role to create or update supported craft-context information according to the approved content-ownership policy.

**Priority:** Should  
**Status:** PROVISIONAL

**Acceptance Criteria**

Only an authorized role shall be permitted to modify shared craft-context information.

The final content-owning role shall be finalized before implementation.

---

# 4.6.2 Functional Dependency Summary

The requirements in this part follow the dependency direction:

```text
Authentication
      ↓
Role / Ownership

Artisan
      ↓
Product
      ↓
Discovery
```

Product-discovery functionality depends on valid product records.

Product management depends on valid artisan ownership.

Protected modification functions depend on authentication, authorization, and ownership enforcement.

---

# 4.6.3 Functional Requirement Status Summary

| Module | IDs | MVP Status |
|---|---|---|
| Authentication | FR-AUTH-001–005 | Must |
| Customer Profile | FR-USER-001–002 | Should |
| Artisan | FR-ART-001–004 | Must |
| Product | FR-PROD-001–010 | Must / Should |
| Discovery | FR-DISC-001–008 | Must / Should / Provisional |
| Craft Context | FR-CRAFT-001–002 | Provisional Should |

---

# 4.6.4 Research Boundary

The following requirements remain especially dependent on later primary user evidence:

- FR-DISC-007
- FR-DISC-008
- FR-CRAFT-001
- FR-CRAFT-002

Their inclusion in this SRS means that they are formally documented.

It does not mean that their user value has already been validated.

---

## Part Status

**SRS Section:** 4 — Functional Requirements  
**Completed Modules:** AUTH, USER, ART, PROD, DISC, CRAFT  
**Status:** Draft v0.1  
**Requirement IDs Changed:** No  
**New Requirements Introduced:** No  
**Research Boundary:** Preserved

## 4.7 Shopping Cart Requirements

### FR-CART-001 — View Cart

**Statement**

The system shall allow an authenticated customer to view the products currently stored in their own shopping cart.

**Actor:** Customer  
**Priority:** Must  
**Status:** DRAFT

**Acceptance Criteria**

The cart shall display applicable information including:

- Product
- Unit price
- Quantity
- Line total
- Cart total

A customer shall not receive another customer's private cart data.

---

### FR-CART-002 — Add Product to Cart

**Statement**

The system shall allow an authenticated customer to add an eligible available standard product to their own cart.

**Actor:** Customer  
**Priority:** Must  
**Status:** DRAFT

**Related Business Rules:**

- `BR-CART-001`
- `BR-CART-003`

**Acceptance Criteria**

Given an eligible available product, when the customer submits a valid quantity, the product shall be added to the customer's cart.

Unavailable or invalid products shall not be added successfully.

---

### FR-CART-003 — Update Cart Quantity

**Statement**

The system shall allow an authenticated customer to update the quantity of an item in their own cart within approved availability limits.

**Actor:** Customer  
**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-CART-002`

**Acceptance Criteria**

A valid quantity update shall:

- Update the cart item
- Recalculate the line total
- Recalculate the cart total

Invalid quantities shall be rejected.

---

### FR-CART-004 — Remove Cart Item

**Statement**

The system shall allow an authenticated customer to remove an item from their own cart.

**Actor:** Customer  
**Priority:** Must  
**Status:** DRAFT

**Acceptance Criteria**

After successful removal:

- The item shall no longer appear in the active cart
- Cart totals shall be recalculated

---

### FR-CART-005 — Calculate Cart Total

**Statement**

The system shall calculate the current cart total using authoritative product prices and valid cart quantities.

**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-CART-004`

**Acceptance Criteria**

The cart total shall equal the sum of valid cart-item line totals.

Client-supplied total values shall not be treated as authoritative transaction totals.

---

## 4.8 Standard Order and Checkout Requirements

### FR-ORDER-001 — Initiate Checkout

**Statement**

The system shall allow an authenticated customer with at least one eligible cart item to initiate checkout.

**Actor:** Customer  
**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-ORDER-004`

**Acceptance Criteria**

Checkout shall not proceed when no eligible items are available for ordering.

---

### FR-ORDER-002 — Provide Delivery Information

**Statement**

The system shall allow the customer to provide the required delivery information for the order.

**Actor:** Customer  
**Priority:** Must  
**Status:** DRAFT

**Privacy Dependency:** `PR-DATA-003`

**Acceptance Criteria**

Mandatory delivery information shall be validated before order confirmation is permitted.

---

### FR-ORDER-003 — Review Checkout Summary

**Statement**

The system shall allow the customer to review the order summary before final confirmation.

**Actor:** Customer  
**Priority:** Must  
**Status:** DRAFT

The summary may include:

- Products
- Quantities
- Prices
- Total
- Delivery information
- Selected payment option

**Acceptance Criteria**

Viewing the checkout summary shall not automatically create a confirmed order.

An explicit confirmation action shall be required.

---

### FR-ORDER-004 — Confirm Standard Order

**Statement**

The system shall allow the customer to confirm a valid standard order through the approved checkout workflow.

**Actor:** Customer  
**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-ORDER-003`

**Acceptance Criteria**

A valid confirmation shall create a persistent order associated with the authenticated customer.

---

### FR-ORDER-005 — Create Order Record

**Statement**

The system shall create a uniquely identifiable order record after successful order confirmation.

**Priority:** Must  
**Status:** DRAFT

**Related Data:** `DR-ORDER-001`

**Acceptance Criteria**

The newly created order shall remain retrievable through approved authorized workflows.

---

### FR-ORDER-006 — Store Order Items

**Statement**

The system shall preserve the products and quantities included in a confirmed order as order-item records.

**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-ORDER-002`

**Acceptance Criteria**

Changing the customer's cart after confirmation shall not alter the items already stored in the confirmed order.

---

### FR-ORDER-007 — Store Order Price Snapshot

**Statement**

The system shall preserve the applicable transaction-time price for each confirmed order item.

**Priority:** Must  
**Status:** DRAFT

**Related Rules:**

- `BR-ORDER-002`
- `BR-ORDER-007`

**Acceptance Criteria**

A later change to the product's current price shall not change the stored price of an earlier confirmed order.

---

### FR-ORDER-008 — Clear Purchased Cart Items

**Statement**

The system shall remove successfully purchased items from the customer's active cart after successful order creation.

**Actor:** Customer  
**Priority:** Must  
**Status:** DRAFT

**Acceptance Criteria**

Purchased items shall not remain as active duplicate cart entries unless intentionally added again later.

---

### FR-ORDER-009 — Assign Initial Order Status

**Statement**

The system shall assign an approved initial workflow state to each newly created standard order.

**Priority:** Must  
**Status:** DRAFT

The exact initial state will be finalized in the standard-order state model.

---

### FR-ORDER-010 — Update Order Status

**Statement**

The system shall allow an authorized actor to update a standard order's status according to approved state-transition rules.

**Actors:**

- Authorized Artisan where applicable
- Administrator where authorized

**Priority:** Must  
**Status:** DRAFT

**Related Rules:**

- `BR-ORDER-005`
- `BR-ORDER-006`

**Acceptance Criteria**

Valid authorized transitions shall be recorded.

Invalid or unauthorized transitions shall be rejected.

---

### FR-ORDER-011 — View Own Order History

**Statement**

The system shall allow an authenticated customer to view their own standard-order history.

**Actor:** Customer  
**Priority:** Should  
**Status:** DRAFT

**Acceptance Criteria**

The order-history interface shall not expose another customer's private order records.

---

### FR-ORDER-012 — View Order Details

**Statement**

The system shall allow an authenticated customer to view permitted details of an order they own.

**Actor:** Customer  
**Priority:** Must  
**Status:** DRAFT

Order details may include:

- Order identifier
- Order items
- Quantities
- Prices
- Total
- Delivery information
- Payment status
- Order status

**Related Security:** `SR-OWN-002`

---

### FR-ORDER-013 — Track Current Order Status

**Statement**

The system shall allow an authorized customer to view the current approved status of an order they own.

**Actor:** Customer  
**Priority:** Must  
**Status:** DRAFT

**Acceptance Criteria**

The current stored state shall be displayed to the authorized customer.

A different customer shall not receive private status information for the order.

---

### FR-ORDER-014 — Select Supported Payment Method

**Statement**

The system shall allow a customer to select from the payment methods supported by the academic MVP.

**Actor:** Customer  
**Priority:** Should  
**Status:** DRAFT

For the current MVP, supported payment behavior may be simulated.

---

### FR-ORDER-015 — Record Simulated Payment Status

**Statement**

The system shall record the approved simulated payment status associated with an order.

**Priority:** Should  
**Status:** DRAFT  
**Evidence:** TECHNICAL / ACADEMIC

Possible states may include:

```text
PENDING
PAID_SIMULATED
FAILED_SIMULATED
```

The final payment-state model will be defined during design.

---

### FR-ORDER-016 — Display Payment Status

**Statement**

The system shall allow an authorized customer to view the payment status recorded for their own order.

**Actor:** Customer  
**Priority:** Should  
**Status:** DRAFT

---

### Real Payment Integration Boundary

`IR-PAY-001`

**Status:** DEFERRED

Real payment-gateway integration is not required for the current academic MVP.

If real payment is later approved, it shall require a separate integration specification and requirement-change review.

---

## 4.8.1 Standard Order State Direction

The exact state machine will be finalized during UML/workflow design.

The current provisional direction is:

```text
PENDING
   ↓
CONFIRMED
   ↓
PROCESSING
   ↓
READY_TO_SHIP
   ↓
SHIPPED
   ↓
DELIVERED
```

Possible terminal state:

```text
CANCELLED
```

Unnecessary status complexity should be avoided.

---

## 4.8.2 Standard Order Dependency

The standard commerce workflow depends on:

```text
Customer
   +
Product
   ↓
Cart
   ↓
Checkout
   ↓
Order
   ↓
Order Status
```

The order workflow shall preserve:

- Ownership
- Price integrity
- Product history
- Valid state transitions

---

## 4.9 Review and Rating Requirements

### FR-REV-001 — View Product Reviews

**Statement**

The system shall allow users to view eligible published reviews associated with a product.

**Actors:**

- Public User
- Customer

**Priority:** Should  
**Status:** DRAFT

**Related Privacy Rule:** `BR-REV-005`

**Acceptance Criteria**

Published reviews shall not expose private customer information beyond approved public reviewer information.

---

### FR-REV-002 — Submit Product Rating

**Statement**

The system shall allow an eligible authenticated customer to submit a rating for a product associated with an approved eligible purchase.

**Actor:** Customer  
**Priority:** Should  
**Status:** DRAFT

**Related Requirements:**

- `BR-REV-001`
- `SR-AUTHZ-008`

**Acceptance Criteria**

An eligible customer shall be able to submit a valid rating.

An ineligible customer shall be prevented from submitting the rating successfully.

---

### FR-REV-003 — Submit Product Review

**Statement**

The system shall allow an eligible authenticated customer to submit textual review content for a product associated with an approved eligible purchase.

**Actor:** Customer  
**Priority:** Should  
**Status:** DRAFT

**Related Rule:** `BR-REV-001`

**Acceptance Criteria**

A valid eligible review shall remain associated with:

- Customer
- Product

according to the approved review data model.

---

### FR-REV-004 — Prevent Unauthorized Review Modification

**Statement**

The system shall prevent an artisan from editing or deleting a legitimate customer review through normal artisan functionality.

**Actor:** Artisan  
**Priority:** Must if review functionality is implemented  
**Status:** DRAFT

**Related Rule:** `BR-REV-003`

**Acceptance Criteria**

An artisan shall not receive normal functionality to remove a legitimate review merely because the review is unfavorable.

---

### FR-REV-005 — Moderate Review

**Statement**

The system shall allow an authorized administrator to perform approved moderation actions on reviews that violate platform rules.

**Actor:** Administrator  
**Priority:** Should  
**Status:** DRAFT

**Related Rules:**

- `BR-REV-004`
- `BR-ADMIN-001`

**Acceptance Criteria**

Only an authorized administrative actor shall receive moderation capability.

Moderation shall remain subject to approved platform rules.

---

## 4.9.1 Review Eligibility Boundary

Review functionality depends on an approved eligibility condition.

Current direction:

```text
Customer
   ↓
Eligible Purchase
   ↓
Review Permission
```

A review interface alone shall not determine eligibility.

The backend shall enforce the approved rule.

---

## 4.9.2 Standard Order vs Custom Order

These workflows remain separate.

### Standard Order

```text
Existing Product
→ Cart
→ Checkout
→ Confirmed Order
```

### Custom Order

```text
Customer Requirements
→ Artisan Review
→ Quotation
→ Customer Approval
→ Production
```

A custom-order request shall not automatically be treated as a standard confirmed order before the relevant custom workflow conditions are satisfied.

---

## 4.9.3 Commerce Security Dependencies

The commerce requirements depend on:

- Authentication
- Authorization
- Cart ownership
- Order ownership
- Input validation
- Price integrity
- State-transition rules
- Review eligibility

Example:

```text
Customer Browser sends total = 100
```

does not mean:

```text
Order total = 100
```

The authoritative backend shall calculate or verify transaction values according to approved business rules.

---

## 4.9.4 Functional Requirement Status Summary

| Module | IDs | MVP Status |
|---|---|---|
| Cart | FR-CART-001–005 | Must |
| Standard Order / Checkout | FR-ORDER-001–013 | Must / Should |
| Simulated Payment | FR-ORDER-014–016 | Should |
| Review | FR-REV-001–005 | Should with mandatory integrity controls |
| Real Payment | IR-PAY-001 | Deferred |

---

## 4.9.5 Acceptance Test Direction

Future tests should cover both positive and negative behavior.

Examples:

### Order Ownership

Given Customer A owns an order.

When Customer B attempts to access that order.

Then:

```text
ACCESS DENIED
```

---

### Historical Price

Given a confirmed order stores a product price.

When the artisan later changes the current product price.

Then:

```text
Confirmed order price remains unchanged.
```

---

### Review Eligibility

Given a customer does not satisfy the approved purchase condition.

When the customer attempts to review the product.

Then:

```text
REVIEW REJECTED
```

---

## Part Status

**SRS Section:** 4 — Functional Requirements  
**Completed Modules:** CART, ORDER, REV  
**Status:** Draft v0.1  
**Requirement IDs Changed:** No  
**Real Payment:** Deferred  
**New Requirements Introduced:** None  
**Next Module:** Structured Custom Order

## 4.10 Structured Custom Order Requirements

### 4.10.1 Module Status

The structured custom-order module is currently classified as:

**Provisional Must Have**

The workflow is technically defined, but its final product value remains dependent on primary Customer and Artisan research.

Current workflow:

```text
Customer
   ↓
Custom Request
   ↓
Artisan Review
   ↓
Quotation
   ↓
Customer Decision
   ↓
Production
   ↓
Status Tracking
   ↓
Completion
```

A custom request shall not automatically become a production order.

---

### FR-CUSTOM-001 — Start Custom Order Request

**Statement**

The system shall allow an authenticated customer to initiate a custom-order request for an eligible artisan or product context.

**Actor:** Customer  
**Priority:** Provisional Must  
**Status:** PROVISIONAL

**Acceptance Criteria**

Only an authenticated customer shall be allowed to create a request through normal customer functionality.

The created request shall belong to that customer.

---

### FR-CUSTOM-002 — Provide Product Type

**Statement**

The system shall allow the customer to specify the requested product type.

**Priority:** Provisional Must  
**Status:** PROVISIONAL

---

### FR-CUSTOM-003 — Provide Design Requirement

**Statement**

The system shall allow the customer to provide supported design information for the requested custom product.

**Priority:** Provisional Must  
**Status:** PROVISIONAL

---

### FR-CUSTOM-004 — Provide Color Requirement

**Statement**

The system shall allow the customer to provide color requirements where applicable.

**Priority:** Should  
**Status:** PROVISIONAL

---

### FR-CUSTOM-005 — Provide Size Requirement

**Statement**

The system shall allow the customer to provide supported size information where applicable.

**Priority:** Provisional Must  
**Status:** PROVISIONAL

---

### FR-CUSTOM-006 — Provide Material Requirement

**Statement**

The system shall allow the customer to provide preferred material information where applicable.

**Priority:** Should  
**Status:** PROVISIONAL

---

### FR-CUSTOM-007 — Provide Quantity

**Statement**

The system shall require a valid requested quantity for the custom order.

**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-CUSTOM-006`

**Acceptance Criteria**

Valid positive quantities shall be accepted.

Invalid quantities shall be rejected.

---

### FR-CUSTOM-008 — Upload Reference Image

**Statement**

The system shall allow the customer to upload a supported reference image with the custom-order request.

**Priority:** Should  
**Status:** PROVISIONAL

**Related Security:**

- `SR-FILE-*`
- `PR-DATA-005`

**Acceptance Criteria**

Valid authorized images shall be associated with the correct custom request.

Unsupported or unauthorized files shall be rejected.

---

### FR-CUSTOM-009 — Provide Additional Instructions

**Statement**

The system shall allow the customer to provide additional textual instructions.

**Priority:** Should  
**Status:** PROVISIONAL

---

### FR-CUSTOM-010 — Submit Custom Request

**Statement**

The system shall allow a customer to submit the custom-order request after required information passes validation.

**Actor:** Customer  
**Priority:** Provisional Must  
**Status:** PROVISIONAL

**Acceptance Criteria**

A valid submission shall create a persistent custom-request record containing the approved required data.

---

### FR-CUSTOM-011 — Assign Initial Request Status

**Statement**

The system shall assign an approved initial state to a newly submitted custom request.

**Priority:** Must  
**Status:** DRAFT

Current provisional initial state:

```text
REQUESTED
```

---

### FR-CUSTOM-012 — View Own Custom Requests

**Statement**

The system shall allow an authenticated customer to view custom requests belonging to their own account.

**Priority:** Must  
**Status:** DRAFT

**Related Security:** `SR-OWN-003`

---

### FR-CUSTOM-013 — View Custom Request Details

**Statement**

The system shall allow the request owner to view the stored details and current status of their custom request.

**Priority:** Must  
**Status:** DRAFT

---

## 4.10.2 Artisan Review Requirements

### FR-CUSTOM-014 — View Assigned Custom Requests

**Statement**

The system shall allow an authenticated artisan to view custom requests assigned to that artisan.

**Actor:** Artisan  
**Priority:** Provisional Must  
**Status:** PROVISIONAL

**Related Rules:**

- `BR-CUSTOM-003`
- `SR-OWN-004`

**Acceptance Criteria**

An artisan shall not receive normal workflow access to a request assigned to another artisan.

---

### FR-CUSTOM-015 — View Customer Requirements

**Statement**

The system shall allow the assigned artisan to view the customization information submitted with the request.

**Priority:** Provisional Must  
**Status:** PROVISIONAL

Applicable information may include:

- Product type
- Design
- Color
- Size
- Material
- Quantity
- Reference image
- Instructions

subject to privacy rules.

---

### FR-CUSTOM-016 — Mark Request Under Review

**Statement**

The system shall allow the assigned artisan to mark an eligible request as under review.

**Priority:** Must  
**Status:** DRAFT

Current provisional state:

```text
UNDER_REVIEW
```

---

### FR-CUSTOM-017 — Reject Custom Request

**Statement**

The system shall allow the assigned artisan to reject an eligible request when the artisan cannot or will not proceed.

**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-CUSTOM-013`

**Acceptance Criteria**

A rejected request shall enter the approved rejected state and shall not proceed directly into production.

---

## 4.10.3 Quotation Requirements

### FR-CUSTOM-018 — Create Quotation

**Statement**

The system shall allow the assigned artisan to create a quotation for an eligible custom request.

**Actor:** Artisan  
**Priority:** Provisional Must  
**Status:** PROVISIONAL

---

### FR-CUSTOM-019 — Provide Quoted Price

**Statement**

The system shall require a valid quoted price for a quotation.

**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-CUSTOM-005`

**Acceptance Criteria**

Invalid quotation prices shall be rejected.

---

### FR-CUSTOM-020 — Provide Estimated Completion

**Statement**

The system shall allow the artisan to provide an estimated completion date or another approved completion estimate.

**Priority:** Provisional Must  
**Status:** PROVISIONAL

---

### FR-CUSTOM-021 — Provide Quotation Notes

**Statement**

The system shall allow the artisan to provide additional notes with the quotation.

**Priority:** Should  
**Status:** PROVISIONAL

---

### FR-CUSTOM-022 — Submit Quotation

**Statement**

The system shall allow the assigned artisan to submit a valid quotation associated with the relevant custom request.

**Priority:** Must  
**Status:** DRAFT

**Related Rule:** `BR-CUSTOM-004`

**Acceptance Criteria**

A valid submitted quotation shall remain associated with the correct custom request and become available to its owner.

---

### FR-CUSTOM-023 — Update Request to Quoted Status

**Statement**

The system shall update an eligible custom request to the approved quoted state after a valid quotation is submitted.

**Priority:** Must  
**Status:** DRAFT

Current provisional state:

```text
QUOTED
```

---

## 4.10.4 Customer Quotation Decision Requirements

### FR-CUSTOM-024 — View Quotation

**Statement**

The system shall allow the request owner to view the valid quotation associated with their custom request.

**Actor:** Customer  
**Priority:** Provisional Must  
**Status:** PROVISIONAL

The quotation may display:

- Quoted price
- Estimated completion
- Artisan notes
- Relevant customer requirements

---

### FR-CUSTOM-025 — Approve Quotation

**Statement**

The system shall allow the request owner to approve an eligible quotation.

**Actor:** Customer  
**Priority:** Provisional Must  
**Status:** PROVISIONAL

**Related Rules:**

- `BR-CUSTOM-001`
- `BR-CUSTOM-002`
- `SR-AUTHZ-007`

**Acceptance Criteria**

Only the request owner shall be able to approve the quotation through normal customer functionality.

Successful approval shall be persisted.

---

### FR-CUSTOM-026 — Reject Quotation

**Statement**

The system shall allow the request owner to reject an eligible quotation.

**Actor:** Customer  
**Priority:** Provisional Must  
**Status:** PROVISIONAL

**Related Rule:** `BR-CUSTOM-002`

---

### FR-CUSTOM-027 — Record Quotation Decision

**Statement**

The system shall persist the customer's quotation decision and the associated decision time.

**Priority:** Must  
**Status:** DRAFT

**Related Data:**

- `DR-CUSTOM-010`
- `DR-CUSTOM-011`

---

## 4.10.5 Production Activation

### FR-CUSTOM-028 — Activate Approved Custom Order

**Statement**

The system shall allow a custom request to enter the production workflow only after a valid quotation has been approved by the request owner.

**Priority:** Must  
**Status:** DRAFT

**Related Rules:**

- `BR-CUSTOM-001`
- `SR-AUTHZ-006`

**Acceptance Criteria**

A request without valid quotation approval shall not transition into production.

---

## 4.10.6 Production Status Requirements

### FR-CUSTOM-029 — Mark In Production

**Statement**

The system shall allow the assigned artisan to update an eligible approved custom order to `IN_PRODUCTION`.

**Priority:** Provisional Must  
**Status:** PROVISIONAL

---

### FR-CUSTOM-030 — Mark Quality Check

**Statement**

The system shall allow the assigned artisan to record `QUALITY_CHECK` where that state is included in the approved workflow.

**Priority:** Should  
**Status:** PROVISIONAL

The software records the state.

It does not physically perform quality inspection.

---

### FR-CUSTOM-031 — Mark Ready to Ship

**Statement**

The system shall allow the assigned artisan to update an eligible custom order to `READY_TO_SHIP`.

**Priority:** Must  
**Status:** DRAFT

---

### FR-CUSTOM-032 — Mark Shipped

**Statement**

The system shall allow an authorized actor to update an eligible custom order to `SHIPPED`.

**Priority:** Must  
**Status:** DRAFT

The MVP does not require courier API integration.

---

### FR-CUSTOM-033 — Mark Delivered

**Statement**

The system shall allow an eligible custom order to be recorded as `DELIVERED` according to approved completion rules.

**Priority:** Must  
**Status:** DRAFT

The final actor responsible for confirming delivery will be defined during workflow design.

---

## 4.10.7 Tracking Requirements

### FR-CUSTOM-034 — View Custom Order Status

**Statement**

The system shall allow the request owner to view the current approved status of their custom order.

**Actor:** Customer  
**Priority:** Provisional Must  
**Status:** PROVISIONAL

---

### FR-CUSTOM-035 — View Active Custom Orders

**Statement**

The system shall allow an artisan to view active custom orders requiring or undergoing artisan action.

**Actor:** Artisan  
**Priority:** Provisional Must  
**Status:** PROVISIONAL

---

### FR-CUSTOM-036 — View Completed Custom Orders

**Statement**

The system shall allow authorized Customers and Artisans to view completed custom orders relevant to them.

**Priority:** Should  
**Status:** DRAFT

---

## 4.10.8 Cancellation Requirements

### FR-CUSTOM-037 — Request Cancellation

**Statement**

The system shall allow an authorized customer to request cancellation of an eligible custom order where approved cancellation rules permit.

**Priority:** Should  
**Status:** PROVISIONAL

**Related Rule:** `BR-CUSTOM-014`

---

### FR-CUSTOM-038 — Record Cancelled State

**Statement**

The system shall record an approved custom-order cancellation using the appropriate terminal state.

**Priority:** Should  
**Status:** DRAFT

Current provisional state:

```text
CANCELLED
```

---

## 4.10.9 Custom Order State Model

The provisional workflow is:

```text
REQUESTED
    ↓
UNDER_REVIEW
    ↓
QUOTED
    ↓
CUSTOMER_APPROVED
    ↓
IN_PRODUCTION
    ↓
QUALITY_CHECK
    ↓
READY_TO_SHIP
    ↓
SHIPPED
    ↓
DELIVERED
```

Possible terminal alternatives:

```text
REJECTED
CANCELLED
```

The formal state machine will be completed during UML/system-analysis work.

---

## 4.10.10 State Integrity Requirements

The system shall reject invalid state transitions according to:

`BR-CUSTOM-007`

Examples of normally invalid transitions include:

```text
REQUESTED → SHIPPED
```

```text
QUOTED → IN_PRODUCTION
```

without customer approval.

```text
REJECTED → IN_PRODUCTION
```

```text
DELIVERED → IN_PRODUCTION
```

---

## 4.10.11 Requirement Change After Approval

A significant unresolved scenario is:

> What happens if the customer requests a design change after approving the quotation?

The current direction is that unrestricted editing shall not be allowed.

A possible future controlled workflow is:

```text
Customer Change Request
        ↓
Artisan Impact Review
        ↓
Revised Quotation
        ↓
Customer Re-Approval
```

This behavior is not yet a committed MVP feature.

If introduced, it shall follow requirement-change control.

---

## 4.10.12 Privacy Boundary

Custom-order data may contain:

- Customer instructions
- Reference images
- Size information
- Design details
- Delivery-related data

Normal access should be restricted to:

```text
Request Owner
      +
Assigned Artisan
      +
Authorized Administrator where required
```

Related requirements include:

- `PR-DATA-004`
- `PR-DATA-005`
- `BR-CUSTOM-011`

---

## 4.10.13 Security Boundary

Protected custom-order actions require:

```text
Authentication
      ↓
Role Authorization
      ↓
Ownership / Assignment
      ↓
Valid Workflow State
      ↓
Business Rule Validation
      ↓
Action
```

Examples:

### Wrong Customer

Customer B attempts to approve Customer A's quotation.

Expected:

```text
ACCESS DENIED
```

### Wrong Artisan

Artisan B attempts to quote a request assigned to Artisan A.

Expected:

```text
ACCESS DENIED
```

### Production Before Approval

Artisan attempts production before valid customer approval.

Expected:

```text
TRANSITION REJECTED
```

---

## 4.10.14 Customer-Facing Status Simplification

The backend may maintain detailed workflow states while the customer interface presents a simpler status model.

Example:

```text
Request Sent
→ Quote Ready
→ Approved
→ In Production
→ Ready
→ Shipped
→ Delivered
```

Any simplified status shall remain consistent with the authoritative workflow state.

Related rule:

`BR-CUSTOM-012`

---

## 4.10.15 Notification Dependencies

The custom workflow may generate meaningful notification events including:

### Customer

- Quotation available
- Production started
- Ready to ship
- Shipped
- Delivered

### Artisan

- New custom request
- Quotation approved
- Quotation rejected
- Cancellation request

Notification delivery shall not become the authoritative source of workflow state.

---

## 4.10.16 Custom Order Requirement Traceability

| Need / Pain Point | Requirement Area |
|---|---|
| PP-01 Requirement ambiguity | FR-CUSTOM-002–010 |
| PP-02 Quotation ambiguity | FR-CUSTOM-018–028 |
| PP-03 Repeated progress questions | FR-CUSTOM-029–036 |
| Clear customer agreement | FR-CUSTOM-024–028 |
| Complete artisan specification | FR-CUSTOM-015 |
| Organized artisan work | FR-CUSTOM-014, FR-CUSTOM-035 |

---

## 4.10.17 Future Use Cases

The current requirements are expected to support use cases such as:

```text
UC-CUSTOM-001 — Submit Custom Request
UC-CUSTOM-002 — Review Custom Request
UC-CUSTOM-003 — Create Quotation
UC-CUSTOM-004 — Approve Quotation
UC-CUSTOM-005 — Reject Quotation
UC-CUSTOM-006 — Update Custom Order Status
UC-CUSTOM-007 — Track Custom Order
```

Formal use-case specifications will be created in the later Use Case phase.

---

## 4.10.18 Future Test Direction

Important test scenarios shall include:

```text
TC-CUSTOM-001 — Request Submission
TC-CUSTOM-002 — Customer Ownership
TC-CUSTOM-003 — Artisan Assignment
TC-CUSTOM-004 — Quotation Creation
TC-CUSTOM-005 — Quotation Approval
TC-CUSTOM-006 — Production Guard
TC-CUSTOM-007 — State Transition
TC-CUSTOM-008 — Customer Tracking
TC-CUSTOM-009 — Reference Image Security
TC-CUSTOM-010 — Cancellation
```

---

## 4.10.19 Validation Boundary

A substantial portion of the module remains:

```text
PROVISIONAL
```

because:

```text
Technically Complete Workflow
        ≠
Validated User Need
```

Primary Customer and Artisan research must determine whether the structured workflow provides sufficient value compared with existing informal processes.

---

## 4.10.20 MVP Decision Rule

If primary research supports the workflow:

```text
Provisional Must
→ Must
```

If evidence indicates the workflow is too complex or does not solve a meaningful problem:

```text
Review
→ Simplify
or
Rewrite
or
Defer
```

The project shall not preserve the workflow solely because substantial documentation has already been produced.

---

## 4.10.21 Engineering Significance

If validated, the custom-order module represents a strong Software Engineering component because it contains:

- Multiple actors
- Structured requirements
- Ownership
- Authorization
- Quotation
- Explicit approval
- State transitions
- File handling
- Privacy
- Business rules
- Negative scenarios
- Traceability
- Testable workflow integrity

---

## Part Status

**SRS Section:** 4.10 — Structured Custom Order  
**Requirements:** FR-CUSTOM-001–038  
**Status:** Provisional Draft v0.1  
**Requirement IDs Changed:** No  
**New Requirements Introduced:** No  
**Primary Research Dependency:** Critical  
**Next Module:** Notifications, Verification, Certificate & Administration

## 4.11 Notification Requirements

The notification module provides awareness of meaningful system events.

Notifications shall support workflows rather than become the authoritative source of order or custom-order state.

The MVP does not require:

- SMS notifications
- Native push notifications
- Real-time messaging infrastructure

Basic in-app notifications or dashboard alerts are sufficient.

---

### FR-NOTIF-001 — Notify Artisan of New Custom Request

**Statement**

The system shall make the assigned artisan aware when a new custom-order request requiring artisan review has been submitted.

**Actor:** Artisan  
**Priority:** Should  
**Status:** DRAFT

**Acceptance Criteria**

A new custom request shall generate an appropriate notification or pending-action indicator for the correct assigned artisan.

Another artisan shall not receive private request information without authorization.

---

### FR-NOTIF-002 — Notify Customer of Available Quotation

**Statement**

The system shall make the request owner aware when an artisan submits a quotation for their custom-order request.

**Actor:** Customer  
**Priority:** Should  
**Status:** PROVISIONAL

**Acceptance Criteria**

The notification shall be associated with the correct request owner.

---

### FR-NOTIF-003 — Notify Artisan of Quotation Approval

**Statement**

The system shall make the assigned artisan aware when the customer approves a quotation.

**Actor:** Artisan  
**Priority:** Should  
**Status:** DRAFT

---

### FR-NOTIF-004 — Notify Artisan of Quotation Rejection

**Statement**

The system shall make the assigned artisan aware when the customer rejects a quotation.

**Actor:** Artisan  
**Priority:** Should  
**Status:** DRAFT

---

### FR-NOTIF-005 — Notify Customer of Relevant Status Change

**Statement**

The system shall make the customer aware when an important standard-order or custom-order status relevant to them changes.

**Actor:** Customer  
**Priority:** Should  
**Status:** PROVISIONAL

Meaningful events may include:

- Production started
- Ready to ship
- Shipped
- Delivered

The exact notification-event list will be finalized during workflow design.

---

### FR-NOTIF-006 — View Notifications

**Statement**

The system shall allow an authenticated user to view notifications associated with their own account.

**Actors:**

- Customer
- Artisan

**Priority:** Should  
**Status:** DRAFT

**Related Requirements:**

- `BR-NOTIF-001`
- `SR-OWN-005`

**Acceptance Criteria**

User A shall not be able to retrieve User B's private notifications through normal functionality.

---

### FR-NOTIF-007 — Mark Notification as Read

**Statement**

The system shall allow an authenticated user to mark an owned notification as read where notification read-state functionality is implemented.

**Priority:** Could / Should  
**Status:** DRAFT

---

## 4.11.1 Notification Principle

Notifications should primarily represent:

```text
Action Required
      or
Meaningful Status Change
```

The system should avoid unnecessary alerts for insignificant internal events.

Example:

```text
Quotation Submitted
        ↓
Customer Notification
```

However:

```text
Notification Missing
```

shall not mean:

```text
Quotation Missing
```

The business record remains authoritative.

---

# 4.12 QR / Product Verification Record Requirements

## 4.12.1 Verification Scope

The verification module is intended to provide access to a Craft BD-maintained platform record.

Current model:

```text
QR Code
   ↓
Craft BD Verification URL
   ↓
Product / Verification Record
```

A QR-linked Craft BD record shall not automatically be interpreted as independent proof that the physical item itself is authentic.

---

### FR-VERIFY-001 — Generate Verification Identifier

**Statement**

The system shall allow an authorized process to assign a unique verification identifier to an eligible Craft BD product record.

**Priority:** Should — Conditional  
**Status:** PROVISIONAL

**Related Rule:** `BR-VERIFY-003`

**Acceptance Criteria**

An active verification identifier shall uniquely resolve to its intended Craft BD verification record.

---

### FR-VERIFY-002 — Generate QR-Linked Verification Reference

**Statement**

The system shall allow an authorized process to generate a QR code or equivalent scannable reference linked to an eligible Craft BD verification record.

**Priority:** Should — Conditional  
**Status:** PROVISIONAL

**Acceptance Criteria**

Opening a valid generated verification reference shall lead to the corresponding Craft BD record.

---

### FR-VERIFY-003 — View Verification Record

**Statement**

The system shall allow a user to view approved public information associated with a valid verification identifier.

**Actors:**

- Public User
- Customer

**Priority:** Should — Conditional  
**Status:** PROVISIONAL

Possible public information may include:

- Product identifier
- Product name
- Artisan
- Region
- Craft type
- Materials
- Approved production information
- Platform certificate information where implemented

**Related Rule:** `BR-VERIFY-001`

---

### FR-VERIFY-004 — Handle Invalid Verification Identifier

**Statement**

The system shall clearly indicate when a requested verification identifier does not correspond to an active valid Craft BD verification record.

**Priority:** Should  
**Status:** DRAFT

**Related Security:** `SR-VERIFY-002`

**Acceptance Criteria**

An invalid identifier shall:

- Return an appropriate invalid/not-found result
- Not expose unrelated product records
- Not expose private information

---

### FR-VERIFY-005 — Manage Verification Record Status

**Statement**

The system shall allow an authorized administrator to manage the approved status of a verification record where the verification module is implemented.

**Actor:** Administrator  
**Priority:** Should — Conditional  
**Status:** PROVISIONAL

Possible administrative actions may include:

- Activate
- Deactivate
- Review record status

---

## 4.12.2 Verification Trust Boundary

Correct interpretation:

```text
Valid QR
   ↓
Valid Craft BD Platform Record
```

Incorrect unsupported interpretation:

```text
Valid QR
   ↓
Guaranteed Authentic Physical Product
```

Craft BD shall not make the second claim unless a reliable external or physical authentication mechanism is introduced through approved requirement change.

---

# 4.13 Platform Certificate Requirements

## 4.13.1 Certificate Scope

The certificate module is currently:

**Could Have / Optional**

If implemented, the system provides a:

```text
Craft BD Platform Certificate Record
```

It does not automatically provide:

- Government certification
- Legal authenticity certification
- Independent third-party certification

---

### FR-CERT-001 — Create Platform Certificate Record

**Statement**

The system shall allow an authorized administrator to create a Craft BD platform certificate record for an eligible product.

**Actor:** Administrator  
**Priority:** Could  
**Status:** PROVISIONAL

**Related Rule:** `BR-CERT-001`

---

### FR-CERT-002 — Assign Unique Certificate Identifier

**Statement**

The system shall assign a unique identifier to each valid Craft BD certificate record.

**Priority:** Could  
**Status:** PROVISIONAL

**Related Rule:** `BR-CERT-003`

---

### FR-CERT-003 — View Certificate Record

**Statement**

The system shall allow permitted users to view approved public information associated with an active Craft BD certificate record.

**Priority:** Could  
**Status:** PROVISIONAL

**Related Rule:** `BR-CERT-002`

---

### FR-CERT-004 — Link Certificate to Product

**Statement**

The system shall associate a valid Craft BD certificate record with the relevant eligible product record.

**Priority:** Could  
**Status:** PROVISIONAL

**Related Rule:** `BR-CERT-004`

---

### FR-CERT-005 — Deactivate or Revoke Certificate Record

**Statement**

The system shall allow an authorized administrator to deactivate or revoke a Craft BD platform certificate record according to approved platform rules.

**Actor:** Administrator  
**Priority:** Could  
**Status:** PROVISIONAL

Historical information required for audit or record consistency shall not be silently destroyed.

---

## 4.13.2 Certificate Scope Protection

If project schedule becomes constrained:

```text
Certificate Module
      ↓
Defer First
```

before reducing:

```text
Security
Core Orders
Custom Workflow*
Testing
Deployment
```

`* Subject to primary research validation.`

---

# 4.14 Administration Requirements

## 4.14.1 Administration Principle

Craft BD administration follows:

```text
Normal Valid Workflow
      ↓
Customer / Artisan
```

and:

```text
Governance / Exception
      ↓
Administrator
```

The administrator shall not automatically approve every normal transaction.

---

### FR-ADMIN-001 — View User Accounts

**Statement**

The system shall allow an authorized administrator to view permitted user-account information required for approved platform administration.

**Actor:** Administrator  
**Priority:** Must  
**Status:** DRAFT

**Privacy Boundary**

Only information necessary for approved administrative purposes shall be exposed.

---

### FR-ADMIN-002 — Manage User Status

**Statement**

The system shall allow an authorized administrator to perform approved user-account status actions.

**Actor:** Administrator  
**Priority:** Must  
**Status:** DRAFT

Possible actions may include:

- Activate
- Deactivate

**Related Security:** `SR-ADMIN-*`

---

### FR-ADMIN-003 — Create Category

**Statement**

The system shall allow an authorized administrator to create a valid product category.

**Priority:** Must  
**Status:** DRAFT

---

### FR-ADMIN-004 — Update Category

**Statement**

The system shall allow an authorized administrator to modify approved information for an existing product category.

**Priority:** Must  
**Status:** DRAFT

---

### FR-ADMIN-005 — Deactivate Category

**Statement**

The system shall allow an authorized administrator to deactivate a category according to approved data-integrity rules.

**Priority:** Should  
**Status:** DRAFT

**Related Rule:** `BR-ADMIN-005`

**Acceptance Criteria**

Deactivating a category shall not silently destroy historical product or order information.

---

## 4.14.2 Content Moderation Requirements

### FR-ADMIN-006 — Moderate Product Content

**Statement**

The system shall allow an authorized administrator to perform approved moderation actions on product content that violates platform rules.

**Priority:** Should  
**Status:** DRAFT

---

### FR-ADMIN-007 — Moderate Artisan Profile Content

**Statement**

The system shall allow an authorized administrator to perform approved moderation actions on artisan-profile content that violates platform rules.

**Priority:** Should  
**Status:** DRAFT

---

### FR-ADMIN-008 — Moderate Reviews

**Statement**

The system shall allow an authorized administrator to moderate reviews according to approved platform rules.

**Priority:** Should  
**Status:** DRAFT

This requirement supports the same administration capability referenced by `FR-REV-005`.

The implementation should avoid duplicating the underlying moderation logic.

---

## 4.14.3 Verification Administration

### FR-ADMIN-009 — Manage Verification Records

**Statement**

The system shall allow an authorized administrator to manage Craft BD verification records where the verification module is implemented.

**Priority:** Should — Conditional  
**Status:** PROVISIONAL

---

### FR-ADMIN-010 — Manage Certificate Records

**Statement**

The system shall allow an authorized administrator to manage Craft BD platform certificate records where the certificate module is implemented.

**Priority:** Could — Conditional  
**Status:** PROVISIONAL

---

## 4.14.4 Exceptional Order Administration

### FR-ADMIN-011 — View Order for Authorized Support

**Statement**

The system shall allow an authorized administrator to view permitted order information where required for approved support or governance purposes.

**Priority:** Should  
**Status:** DRAFT

**Acceptance Criteria**

Administrative access shall remain subject to approved authorization and privacy rules.

---

### FR-ADMIN-012 — Perform Approved Exceptional Order Action

**Statement**

The system shall allow an authorized administrator to perform only specifically approved exceptional order actions where normal workflow cannot resolve the issue.

**Priority:** Should / Could  
**Status:** DRAFT

This requirement does not grant unrestricted order manipulation.

Specific exceptional actions shall be defined before implementation.

---

## 4.14.5 Administrative Authorization

Administrative access shall require:

```text
Authenticated
      +
ADMIN Role
      +
Approved Permission
      +
Relevant Business Rule
```

The following is insufficient:

```text
Admin Button Hidden from Customer
```

because frontend visibility is not an authorization control.

Related requirements include:

- `BR-ADMIN-001`
- `BR-ADMIN-003`
- `SR-ADMIN-001`
- `SR-ADMIN-002`

---

## 4.14.6 Administrative Auditability

High-impact administrative actions should be traceable where practical.

Candidate actions include:

- User deactivation
- Content moderation
- Review moderation
- Verification deactivation
- Certificate revocation
- Exceptional order action

Related:

`SR-LOG-003`

---

# 4.15 Functional Scope Summary

The complete functional-requirement structure is now:

| Module | Requirement IDs | Current Position |
|---|---|---|
| Authentication | FR-AUTH-001–005 | Must |
| Customer Profile | FR-USER-001–002 | Should |
| Artisan | FR-ART-001–004 | Must |
| Product | FR-PROD-001–010 | Must / Should |
| Discovery | FR-DISC-001–008 | Must / Should / Provisional |
| Craft Context | FR-CRAFT-001–002 | Provisional Should |
| Cart | FR-CART-001–005 | Must |
| Standard Order | FR-ORDER-001–016 | Must / Should |
| Review | FR-REV-001–005 | Should |
| Custom Order | FR-CUSTOM-001–038 | Provisional Must / Supporting |
| Notifications | FR-NOTIF-001–007 | Should |
| Verification | FR-VERIFY-001–005 | Conditional Should |
| Certificate | FR-CERT-001–005 | Could |
| Administration | FR-ADMIN-001–012 | Must / Should / Conditional |

---

# 4.16 Deferred Functional Scope

The following capabilities remain outside the current mandatory MVP:

- Product comparison
- Advanced personalized recommendation
- Gift recommendation engine
- Event/workshop management
- Real-time customer-artisan chat
- Real payment processing
- Courier API integration
- Blockchain-based verification
- Native mobile application
- External certification authority integration
- Advanced analytics

These capabilities shall not be treated as implementation commitments unless approved through requirement change control.

---

# 4.17 Functional Requirement Security Principle

All protected functional requirements remain subject to:

```text
Authentication
      ↓
Authorization
      ↓
Ownership / Assignment
      ↓
Business Rule
      ↓
Input Validation
      ↓
Operation
```

A functional requirement describes system behavior.

It does not override applicable security, privacy, data-integrity, or business-rule requirements.

---

# 4.18 Functional Requirement Validation Boundary

Requirements fall into three broad categories.

### Controlled Core

Examples:

- Authentication
- Product management
- Standard ordering
- Core administration
- Security enforcement

### Research-Dependent / Provisional

Examples:

- Structured custom-order importance
- Craft-context value
- Material/craft-type discovery
- QR-linked product record value

### Optional / Conditional

Examples:

- Certificate records
- Selected notifications
- Verification management

Primary research findings may change provisional requirements through the approved change-control process.

---

# 4.19 Section 4 Completion Status

The SRS now contains the full functional requirement baseline covering:

```text
AUTH
USER
ART
PROD
DISC
CRAFT
CART
ORDER
REV
CUSTOM
NOTIF
VERIFY
CERT
ADMIN
```

No requirement identifier has been intentionally renumbered from the Phase 04 baseline.

---

## Section Status

**Section:** 4 — Functional Requirements  
**Status:** Draft v0.1 Complete  
**Requirement Source:** Phase 04 Requirement Baseline v0.1  
**Requirement IDs Changed:** No  
**Unsupported New Features Added:** No  
**Primary Research Dependency:** Preserved  
**Next Section:** Business Rules
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
