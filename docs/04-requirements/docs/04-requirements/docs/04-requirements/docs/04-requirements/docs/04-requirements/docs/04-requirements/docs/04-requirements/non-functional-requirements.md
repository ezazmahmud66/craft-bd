# Craft BD — Non-Functional Requirements Baseline

## 1. Purpose

This document defines the measurable and verifiable non-functional requirements for Craft BD.

The requirements describe quality attributes and operational constraints such as:

- Performance
- Usability
- Reliability
- Maintainability
- Compatibility
- Availability
- Scalability

Security and privacy requirements are maintained separately because they require more detailed controls.

---

# 2. Non-Functional Requirement Standard

NFR identifiers follow:

`NFR-CATEGORY-NNN`

Examples:

- NFR-PERF-001
- NFR-USE-001
- NFR-REL-001
- NFR-MNT-001
- NFR-COMP-001

Each NFR should be measurable or objectively verifiable.

---

# 3. Performance Requirements

## NFR-PERF-001 — Normal Page Response

**Statement**

Under normal academic demonstration conditions, commonly used application pages should complete their primary server-dependent response within approximately 3 seconds for at least 90% of tested requests, excluding third-party network delays and large file uploads.

**Priority:** Should  
**Status:** DRAFT

**Verification**

Measure representative requests during system testing.

---

## NFR-PERF-002 — Product Search Response

**Statement**

For the expected academic MVP dataset, product search results should be returned within approximately 2 seconds for at least 90% of controlled test requests under normal test conditions.

**Priority:** Should  
**Status:** DRAFT

**Verification**

Run repeated search tests against the deployed or controlled test environment.

---

## NFR-PERF-003 — Core API Response

**Statement**

Core API operations that do not involve file upload or external services should generally respond within approximately 2 seconds under normal academic demonstration conditions.

**Priority:** Should  
**Status:** DRAFT

---

## NFR-PERF-004 — File Upload Feedback

**Statement**

When a supported image upload is initiated, the system shall provide visible success or failure feedback after the upload operation completes.

**Priority:** Should  
**Status:** DRAFT

This requirement does not define a fixed upload duration because network speed and file size may vary.

---

# 4. Usability Requirements

## NFR-USE-001 — Responsive Core Workflows

**Statement**

Core customer, artisan, and administrator workflows shall remain usable on both desktop and mobile browser layouts.

**Priority:** Must  
**Status:** DRAFT

**Verification**

Test representative core workflows at desktop and mobile viewport sizes.

---

## NFR-USE-002 — Navigation Consistency

**Statement**

Primary navigation elements shall use consistent labels and placement across pages serving the same user role.

**Priority:** Should  
**Status:** DRAFT

---

## NFR-USE-003 — Form Validation Feedback

**Statement**

When a user submits invalid form data, the interface shall indicate the relevant validation problem without requiring the user to infer the failure from a generic error.

**Priority:** Must  
**Status:** DRAFT

---

## NFR-USE-004 — Action Feedback

**Statement**

User actions that create, update, delete, approve, reject, or change workflow state shall provide visible success or failure feedback.

**Priority:** Must  
**Status:** DRAFT

---

## NFR-USE-005 — Core Task Completion

**Statement**

During usability testing, representative users should be able to complete the selected core task scenarios without developer intervention after receiving only basic task instructions.

**Priority:** Should  
**Status:** PROVISIONAL

Candidate tasks:

- Find a product
- Submit a custom request
- Review a quotation
- Provide a quotation
- Update an order status

Exact usability-test criteria will be finalized before UAT.

---

## NFR-USE-006 — Artisan Workflow Simplicity

**Statement**

Frequently used artisan actions shall avoid unnecessary navigation or repeated entry of information already stored by the system.

**Priority:** Should  
**Status:** PROVISIONAL

This requirement should be evaluated during usability testing rather than by subjective developer judgment alone.

---

# 5. Reliability Requirements

## NFR-REL-001 — Transaction Record Preservation

**Statement**

Successfully confirmed orders and approved custom-order records shall remain persistently stored unless changed through an authorized workflow.

**Priority:** Must  
**Status:** DRAFT

---

## NFR-REL-002 — Invalid State Transition Protection

**Statement**

The system shall reject workflow-state transitions that violate approved business rules.

**Priority:** Must  
**Status:** DRAFT

Related:

- BR-ORDER-005
- BR-CUSTOM-007

---

## NFR-REL-003 — Failure Feedback

**Statement**

When a server-side operation fails, the system shall return an appropriate failure response and shall not present the operation to the user as successfully completed.

**Priority:** Must  
**Status:** DRAFT

---

## NFR-REL-004 — Data Consistency

**Statement**

Operations involving related records shall preserve approved referential and business integrity.

Examples:

- Order ↔ Customer
- Product ↔ Artisan
- Quotation ↔ Custom Request
- Review ↔ Eligible Purchase

**Priority:** Must  
**Status:** DRAFT

---

## NFR-REL-005 — Historical Price Stability

**Statement**

Changes to current product prices shall not modify the stored transaction-time price of previously confirmed standard orders.

**Priority:** Must  
**Status:** DRAFT

---

# 6. Maintainability Requirements

## NFR-MNT-001 — Modular Code Organization

**Statement**

The application shall organize major responsibilities into identifiable modules or components rather than placing unrelated application logic in a single monolithic source file.

**Priority:** Must  
**Status:** DRAFT

---

## NFR-MNT-002 — Source-Control Traceability

**Statement**

Major project changes shall be maintained through the approved Git-based workflow using meaningful commits and Pull Requests.

**Priority:** Must  
**Evidence:** ACADEMIC / TECHNICAL  
**Status:** DRAFT

---

## NFR-MNT-003 — Environment Configuration

**Statement**

Environment-specific configuration and secrets shall be separated from normal source code using the approved configuration mechanism.

**Priority:** Must  
**Status:** DRAFT

---

## NFR-MNT-004 — Documentation

**Statement**

Core modules, architecture decisions, setup instructions, and required deployment configuration shall be documented sufficiently for another project team member to understand the intended setup.

**Priority:** Must  
**Status:** DRAFT

---

## NFR-MNT-005 — Automated Test Support

**Statement**

The codebase shall support automated testing for selected critical business logic and security-sensitive workflows.

**Priority:** Must  
**Status:** DRAFT

The exact coverage target will be established during the testing phase rather than inventing an unsupported percentage at this stage.

---

## NFR-MNT-006 — Coding Convention

**Statement**

The project shall use an agreed coding and naming convention consistently within each implementation technology.

**Priority:** Should  
**Status:** DRAFT

---

# 7. Compatibility Requirements

## NFR-COMP-001 — Desktop Browser Support

**Statement**

The deployed MVP shall support the current project-approved desktop browsers used during system and acceptance testing.

**Priority:** Must  
**Status:** DRAFT

The final browser/version list shall be recorded during test planning.

---

## NFR-COMP-002 — Mobile Browser Layout

**Statement**

Core workflows shall remain functional in a modern mobile-browser layout without requiring a native mobile application.

**Priority:** Must  
**Status:** DRAFT

---

## NFR-COMP-003 — Responsive Layout Integrity

**Statement**

At approved test viewport sizes, core interface content shall not require unintended horizontal scrolling to perform the primary workflow.

**Priority:** Should  
**Status:** DRAFT

Exceptions may apply to intentionally scrollable data structures where explicitly designed.

---

# 8. Availability Requirements

## NFR-AVL-001 — Academic Deployment Availability

**Statement**

The final portfolio/demo version shall be deployed to an environment accessible outside the development machine during scheduled demonstration or evaluation periods, subject to the selected hosting provider's service limitations.

**Priority:** Must  
**Status:** DRAFT

---

## NFR-AVL-002 — No Unsupported Enterprise Uptime Claim

**Statement**

The academic MVP shall not claim enterprise-level uptime guarantees unless availability is actually monitored and supported by the selected infrastructure.

**Priority:** Must  
**Status:** DRAFT

Therefore statements such as:

`99.99% uptime guaranteed`

shall not be used without supporting evidence.

---

# 9. Scalability Requirements

## NFR-SCL-001 — Reasonable Growth Support

**Statement**

The application architecture and relational data model should allow the academic dataset to grow without requiring fundamental redesign of the core Customer, Artisan, Product, Order, and Custom Order relationships.

**Priority:** Should  
**Status:** DRAFT

---

## NFR-SCL-002 — No Enterprise-Scale Claim

**Statement**

The project shall not claim support for enterprise-scale traffic or data volume unless such capacity has been tested and demonstrated.

**Priority:** Must  
**Status:** DRAFT

---

# 10. Data Quality Requirements

## NFR-DATA-001 — Required Data Validation

**Statement**

Mandatory business data shall be validated before it is accepted into persistent storage.

**Priority:** Must  
**Status:** DRAFT

Examples:

- Product price
- Quantity
- Required registration information
- Quotation price

---

## NFR-DATA-002 — Referential Integrity

**Statement**

The system shall prevent or appropriately handle invalid references between core related records.

**Priority:** Must  
**Status:** DRAFT

Examples:

- Product referencing nonexistent artisan
- Quotation referencing nonexistent custom request
- Review referencing invalid product

---

# 11. Error Handling Requirements

## NFR-ERR-001 — User-Safe Error Message

**Statement**

User-facing error responses shall communicate that an operation failed without exposing sensitive technical details such as credentials, secrets, stack traces, or internal configuration.

**Priority:** Must  
**Status:** DRAFT

---

## NFR-ERR-002 — Not-Found Handling

**Statement**

Requests for unavailable or nonexistent records shall return an appropriate not-found or equivalent response rather than exposing unrelated records.

**Priority:** Must  
**Status:** DRAFT

---

## NFR-ERR-003 — Authorization Failure Handling

**Statement**

Unauthorized or forbidden operations shall return an appropriate access-denied response and shall not perform the requested protected action.

**Priority:** Must  
**Status:** DRAFT

---

# 12. Accessibility Direction

Full formal accessibility conformance is not currently claimed.

However, the MVP should follow practical accessibility principles where feasible.

## NFR-USE-007 — Form Labels

**Statement**

Core form inputs shall have understandable labels or equivalent accessible identification.

**Priority:** Should  
**Status:** DRAFT

---

## NFR-USE-008 — Keyboard-Accessible Core Actions

**Statement**

Primary interactive controls used in core workflows should remain operable through standard browser keyboard interaction where supported by the chosen UI components.

**Priority:** Should  
**Status:** DRAFT

---

# 13. Backup / Recovery Direction

Because the final infrastructure has not yet been selected, enterprise backup guarantees cannot yet be specified.

## NFR-REL-006 — Development Data Recovery

**Statement**

The project team shall maintain reproducible source code and configuration documentation so that the application can be redeployed if the demonstration environment is lost.

**Priority:** Must  
**Status:** DRAFT

Production database backup requirements will be revisited if Craft BD moves beyond academic deployment.

---

# 14. NFR Verification Strategy

Each NFR should later map to an appropriate verification method.

| Requirement Type | Possible Verification |
|---|---|
| Performance | Timing test |
| Usability | Usability/UAT test |
| Reliability | System/integration test |
| Maintainability | Code/document review |
| Compatibility | Browser/device test |
| Availability | Deployment check |
| Data Integrity | Database/API test |
| Error Handling | Negative test |

---

# 15. Examples of Bad vs Good NFRs

## Performance

Bad:

> The system should be fast.

Better:

> Product search should return results within approximately 2 seconds for at least 90% of controlled academic test requests.

---

## Usability

Bad:

> The website should be user friendly.

Better:

> Representative users should be able to complete selected core workflows during usability testing without developer intervention.

---

## Reliability

Bad:

> The system should be reliable.

Better:

> Invalid custom-order state transitions shall be rejected.

---

## Maintainability

Bad:

> Code should be maintainable.

Better:

> Major application responsibilities shall be organized into identifiable modules and documented.

---

# 16. NFR Priority Summary

## Must

- Responsive core workflows
- Validation feedback
- Action feedback
- Data consistency
- State integrity
- Modular code organization
- Configuration separation
- Documentation
- Testing support
- Deployment availability
- Appropriate error handling

## Should

- Performance targets
- Usability testing targets
- Artisan workflow simplicity
- Coding convention
- Growth support
- Practical accessibility

---

# 17. Relationship With Security Requirements

Security requirements are not fully defined in this document.

They will be maintained separately using:

- SR-AUTH
- SR-AUTHZ
- SR-OWN
- SR-INPUT
- SR-FILE
- SR-SECRET
- SR-LOG
- SR-TRANSPORT

This avoids hiding critical security requirements inside a generic statement such as:

> The system shall be secure.

---

# 18. Relationship With Privacy Requirements

Privacy requirements will be documented separately for:

- Data minimization
- Public/private data separation
- Order information
- Custom-order reference images
- Demo data
- Retention considerations

---

# 19. NFR Count

Current draft includes:

| Category | Count |
|---|---:|
| Performance | 4 |
| Usability / Accessibility | 8 |
| Reliability / Recovery | 6 |
| Maintainability | 6 |
| Compatibility | 3 |
| Availability | 2 |
| Scalability | 2 |
| Data Quality | 2 |
| Error Handling | 3 |
| **Total** | **36** |

The count may change after architecture and testing review.

---

# 20. Current NFR Decision

The NFR baseline should be treated as:

**Realistic Academic Quality Targets**

rather than:

**Enterprise Marketing Claims**

Craft BD should demonstrate measurable quality where practical while avoiding unsupported claims about:

- Massive scalability
- Enterprise availability
- Perfect security
- Unlimited performance

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Non-Functional Requirements Baseline  
**Status:** Draft v0.1  
**Next Step:** Security & Privacy Requirements Baseline
