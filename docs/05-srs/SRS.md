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
