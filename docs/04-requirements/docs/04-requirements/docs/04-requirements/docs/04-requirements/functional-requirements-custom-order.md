# Craft BD — Functional Requirements Baseline Part 3

## 1. Purpose

This document defines the formal functional requirements for Craft BD's structured custom-order workflow.

The custom-order module supports a controlled interaction between:

- Customer
- Artisan / Seller
- Administrator where exceptional intervention is required

The workflow covers:

Custom Request  
→ Artisan Review  
→ Quotation  
→ Customer Decision  
→ Production  
→ Status Tracking  
→ Completion

These requirements remain **provisional core requirements** because primary customer and artisan research is still pending.

---

# 2. Custom-Order Workflow Overview

The current provisional workflow is:

```text
Customer
   ↓
Submit Custom Request
   ↓
Artisan Reviews Request
   ↓
Artisan Creates Quotation
   ↓
Customer Reviews Quotation
   ↓
Approve / Reject
   ↓
Production
   ↓
Status Updates
   ↓
Delivery / Completion
```

Possible alternative outcomes include:

```text
Request Rejected
Customer Rejects Quote
Order Cancelled
```

---

# 3. Custom Request Requirements

## FR-CUSTOM-001 — Start Custom Order Request

**Statement**

The system shall allow an authenticated customer to initiate a custom-order request for an eligible artisan or product context.

**Source:** STK-01 Customer  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

**Acceptance Criteria**

A logged-in customer shall be able to begin a custom-order request when the target artisan/product supports custom ordering.

An unauthorized user shall not create a custom request on behalf of another customer.

---

## FR-CUSTOM-002 — Provide Custom Product Type

**Statement**

The system shall allow a customer to specify the requested product type for a custom-order request.

**Source:** STK-01 Customer, STK-02 Artisan  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

**Acceptance Criteria**

The submitted product type shall be stored with the custom request and made available to the assigned artisan.

---

## FR-CUSTOM-003 — Provide Design Requirement

**Statement**

The system shall allow a customer to provide supported design information for a custom-order request.

**Source:** STK-01, STK-02  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

## FR-CUSTOM-004 — Provide Color Requirement

**Statement**

The system shall allow a customer to specify a color requirement where applicable to the requested product.

**Source:** STK-01  
**Priority:** Should — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

## FR-CUSTOM-005 — Provide Size Requirement

**Statement**

The system shall allow a customer to specify supported size information where applicable.

**Source:** STK-01, STK-02  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

## FR-CUSTOM-006 — Provide Material Requirement

**Statement**

The system shall allow a customer to specify preferred material information where applicable.

**Source:** STK-01, STK-02  
**Priority:** Should — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

## FR-CUSTOM-007 — Provide Quantity

**Statement**

The system shall require a customer to specify a valid requested quantity for the custom order.

**Source:** STK-01 / Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

A valid positive quantity shall be accepted.

Invalid or unsupported quantities shall be rejected according to the approved business rules.

---

## FR-CUSTOM-008 — Upload Reference Image

**Statement**

The system shall allow a customer to upload a supported reference image with a custom-order request.

**Source:** STK-01, STK-02  
**Priority:** Should  
**Evidence:** PROVISIONAL / DERIVED  
**Related Security Area:** SR-FILE  
**Status:** PROVISIONAL

**Acceptance Criteria**

A valid supported reference image shall be associated with the request.

Unsupported or unsafe files shall be rejected.

---

## FR-CUSTOM-009 — Provide Additional Instructions

**Statement**

The system shall allow a customer to provide additional textual instructions for a custom-order request.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

**Acceptance Criteria**

Valid additional instructions shall remain associated with the request and be available to the assigned artisan.

---

# 4. Custom Request Submission

## FR-CUSTOM-010 — Submit Custom Request

**Statement**

The system shall allow a customer to submit a custom-order request after all mandatory request information passes validation.

**Source:** STK-01, STK-02  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

**Acceptance Criteria**

A valid submission shall create a persistent custom-request record associated with:

- Customer
- Target artisan / seller
- Relevant product where applicable
- Submitted customization information
- Creation timestamp
- Initial status

Invalid mandatory information shall prevent successful submission.

---

## FR-CUSTOM-011 — Assign Initial Request Status

**Statement**

The system shall assign an approved initial status to a newly submitted custom-order request.

**Source:** Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

Provisional initial state:

```text
REQUESTED
```

---

## FR-CUSTOM-012 — View Own Custom Requests

**Statement**

The system shall allow an authenticated customer to view custom-order requests belonging to their own account.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

A customer shall not receive another customer's private custom-request information through normal customer functionality.

---

## FR-CUSTOM-013 — View Custom Request Details

**Statement**

The system shall allow the request owner to view the stored details and current status of their own custom-order request.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

---

# 5. Artisan Request Review Requirements

## FR-CUSTOM-014 — View Assigned Custom Requests

**Statement**

The system shall allow an authenticated artisan to view custom-order requests assigned to that artisan.

**Source:** STK-02 Artisan  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

**Acceptance Criteria**

The artisan shall only receive requests assigned to them or otherwise accessible under an approved administrative rule.

---

## FR-CUSTOM-015 — View Customer Requirements

**Statement**

The system shall allow the assigned artisan to view the customization information submitted with a custom-order request.

**Source:** STK-02  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

The artisan may view relevant information such as:

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

## FR-CUSTOM-016 — Mark Request Under Review

**Statement**

The system shall allow an authorized assigned artisan to mark an eligible custom request as under review.

**Source:** STK-02 / Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

Provisional state:

```text
UNDER_REVIEW
```

---

## FR-CUSTOM-017 — Reject Custom Request

**Statement**

The system shall allow the assigned artisan to reject an eligible custom-order request when the artisan cannot or will not proceed with quotation.

**Source:** STK-02  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

A rejection shall record the rejected state and may store an optional or required reason according to final business rules.

---

# 6. Quotation Requirements

## FR-CUSTOM-018 — Create Quotation

**Statement**

The system shall allow the assigned artisan to create a quotation for an eligible custom-order request.

**Source:** STK-02 Artisan  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

## FR-CUSTOM-019 — Provide Quoted Price

**Statement**

The system shall require the artisan to provide a valid quoted price when creating a quotation.

**Source:** STK-01, STK-02  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

The system shall reject invalid quotation prices.

---

## FR-CUSTOM-020 — Provide Estimated Completion Date

**Statement**

The system shall allow the artisan to provide an estimated completion date or supported completion estimate for the quotation.

**Source:** STK-01, STK-02  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

## FR-CUSTOM-021 — Provide Quotation Notes

**Statement**

The system shall allow the artisan to provide additional quotation notes.

**Source:** STK-02  
**Priority:** Should  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

## FR-CUSTOM-022 — Submit Quotation

**Statement**

The system shall allow the assigned artisan to submit a valid quotation associated with an eligible custom request.

**Source:** STK-02  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

A successfully submitted quotation shall remain associated with the correct custom request and become available to the request owner.

---

## FR-CUSTOM-023 — Update Request to Quoted Status

**Statement**

The system shall update an eligible custom-order request to the approved quoted state after a valid quotation is submitted.

**Source:** Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

Provisional status:

```text
QUOTED
```

---

# 7. Customer Quotation Decision

## FR-CUSTOM-024 — View Quotation

**Statement**

The system shall allow the owner of a custom-order request to view the valid quotation associated with that request.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** PROVISIONAL / DERIVED  
**Status:** PROVISIONAL

The quotation view should display applicable information such as:

- Quoted price
- Estimated completion date
- Artisan notes
- Associated customization requirements

---

## FR-CUSTOM-025 — Approve Quotation

**Statement**

The system shall allow the request owner to approve an eligible quotation.

**Source:** STK-01  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Related Business Rule:** BR-CUSTOM-001  
**Status:** PROVISIONAL

**Acceptance Criteria**

Only the request owner shall be able to approve the quotation through normal customer functionality.

A successful approval shall be recorded persistently.

---

## FR-CUSTOM-026 — Reject Quotation

**Statement**

The system shall allow the request owner to reject an eligible quotation.

**Source:** STK-01  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

## FR-CUSTOM-027 — Record Quotation Decision

**Statement**

The system shall record the customer's quotation decision and the associated decision time.

**Source:** Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

---

# 8. Production Activation

## FR-CUSTOM-028 — Activate Approved Custom Order

**Statement**

The system shall allow an approved custom request to enter the production workflow only after a valid quotation has been approved by the request owner.

**Source:** STK-01, STK-02 / Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Related Business Rule:** BR-CUSTOM-001  
**Status:** DRAFT

**Acceptance Criteria**

A custom request without customer quotation approval shall not transition into the production state.

---

# 9. Production Status Requirements

## FR-CUSTOM-029 — Mark Custom Order In Production

**Statement**

The system shall allow the assigned artisan to update an approved custom order to the `IN_PRODUCTION` state when the transition is valid.

**Source:** STK-02  
**Priority:** Must  
**Evidence:** PROVISIONAL / DERIVED  
**Status:** PROVISIONAL

---

## FR-CUSTOM-030 — Mark Quality Check

**Statement**

The system shall allow the assigned artisan to record the custom order as being in the `QUALITY_CHECK` state when that state is included in the approved workflow.

**Source:** STK-02  
**Priority:** Should  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

Important:

The software records the state.

It does not itself perform physical quality inspection.

---

## FR-CUSTOM-031 — Mark Ready to Ship

**Statement**

The system shall allow the assigned artisan to update an eligible custom order to the `READY_TO_SHIP` state.

**Source:** STK-02  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

---

## FR-CUSTOM-032 — Mark Shipped

**Statement**

The system shall allow an authorized actor to update an eligible custom order to the `SHIPPED` state.

**Source:** STK-02  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

The MVP records shipment state and does not require courier API integration.

---

## FR-CUSTOM-033 — Mark Delivered

**Statement**

The system shall allow an eligible custom order to be recorded as `DELIVERED` according to the approved completion rules.

**Source:** STK-01, STK-02 / Business Logic  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

The exact actor responsible for confirming delivery will be finalized during workflow design.

---

# 10. Custom Order Tracking

## FR-CUSTOM-034 — View Custom Order Status

**Statement**

The system shall allow the request owner to view the current approved status of their custom order.

**Source:** STK-01 Customer  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

## FR-CUSTOM-035 — View Active Custom Orders

**Statement**

The system shall allow an artisan to view custom orders currently requiring or undergoing artisan action.

**Source:** STK-02  
**Priority:** Must — Provisional  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

---

## FR-CUSTOM-036 — View Completed Custom Orders

**Statement**

The system shall allow authorized customers and artisans to view completed custom orders relevant to them.

**Source:** STK-01, STK-02  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

---

# 11. Cancellation Requirements

## FR-CUSTOM-037 — Request Cancellation

**Statement**

The system shall allow an authorized customer to request cancellation of an eligible custom order where the approved cancellation rules permit.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** DERIVED / PROVISIONAL  
**Status:** PROVISIONAL

The exact cancellation conditions will be defined as business rules.

---

## FR-CUSTOM-038 — Record Cancelled State

**Statement**

The system shall record a valid custom-order cancellation using the approved terminal state.

Provisional state:

```text
CANCELLED
```

**Source:** Business Logic  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

---

# 12. Custom Order State Model

The current provisional state model is:

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

The exact state machine will be formalized during workflow/UML design.

---

# 13. Business Rule Dependencies

The custom-order module requires explicit business rules.

## BR-CUSTOM-001

Production shall not begin before the request owner approves a valid quotation.

## BR-CUSTOM-002

Only the customer who owns the request may approve or reject its quotation.

## BR-CUSTOM-003

Only the assigned artisan or an explicitly authorized administrative role may perform artisan-side actions for the request.

## BR-CUSTOM-004

A quotation must belong to a valid custom-order request.

## BR-CUSTOM-005

A custom-order state transition must follow an approved transition.

## BR-CUSTOM-006

A rejected request shall not proceed to quotation or production unless an approved reopening process exists.

## BR-CUSTOM-007

An artisan shall not silently alter customer-submitted requirements.

## BR-CUSTOM-008

Changes to agreed requirements after quotation approval must follow an approved change process.

## BR-CUSTOM-009

Custom-order private data shall only be accessible to authorized participants.

## BR-CUSTOM-010

The customer-facing status may simplify internal workflow states but shall not misrepresent the actual recorded state.

---

# 14. Requirement Change Risk

Custom orders introduce a major requirement:

> What happens if the customer changes the design after approving the quotation?

The initial MVP should not solve this by allowing unrestricted editing.

Recommended future workflow:

```text
Customer Requests Change
      ↓
Artisan Reviews Impact
      ↓
New / Revised Quote if Required
      ↓
Customer Re-Approves
```

This should later become either:

- a formal change-request workflow, or
- an explicit MVP limitation

depending on scope.

---

# 15. Notification Dependencies

The custom-order workflow may generate notification events such as:

## Customer

- Quotation received
- Quotation decision recorded
- Production started
- Order ready
- Order shipped

## Artisan

- New custom request
- Quotation approved
- Quotation rejected
- Cancellation requested

The exact notification mechanism will be defined separately.

---

# 16. Privacy Dependencies

Custom-order data may contain:

- Reference image
- Design
- Size
- Customer instructions
- Delivery-related information

Access should normally be limited to:

```text
Request Owner
+
Assigned Artisan
+
Authorized Administrator where necessary
```

This functional workflow must be enforced by security and privacy requirements.

---

# 17. Security Dependencies

The module depends on:

- Authentication
- Role authorization
- Resource ownership
- Request assignment
- File validation
- State-transition validation
- Input validation

Example:

```text
Artisan A
tries to quote request assigned to Artisan B
        ↓
DENY
```

---

# 18. Customer-Facing Simplified Status

The backend may maintain detailed states.

The customer interface may present:

```text
Request Sent
→ Quote Ready
→ Approved
→ In Production
→ Ready
→ Shipped
→ Delivered
```

This improves usability while preserving internal state detail.

---

# 19. Workflow Failure Scenarios

Formal testing should include cases such as:

### Scenario 1

Artisan attempts to start production before customer approval.

Expected:

```text
REJECTED
```

### Scenario 2

Customer A attempts to approve Customer B's quotation.

Expected:

```text
ACCESS DENIED
```

### Scenario 3

Artisan B attempts to update Artisan A's custom order.

Expected:

```text
ACCESS DENIED
```

### Scenario 4

Invalid reference-image file is uploaded.

Expected:

```text
UPLOAD REJECTED
```

### Scenario 5

System receives invalid state transition:

```text
REQUESTED → SHIPPED
```

Expected:

```text
TRANSITION REJECTED
```

---

# 20. Traceability Examples

| Need / Pain Point | Requirement |
|---|---|
| PP-01 Requirement ambiguity | FR-CUSTOM-002 through FR-CUSTOM-010 |
| PP-02 Quotation ambiguity | FR-CUSTOM-018 through FR-CUSTOM-027 |
| PP-03 Status communication | FR-CUSTOM-029 through FR-CUSTOM-036 |
| Customer wants clear agreement | FR-CUSTOM-024, FR-CUSTOM-025 |
| Artisan wants complete specifications | FR-CUSTOM-015 |
| Artisan needs organized active work | FR-CUSTOM-035 |

---

# 21. Future Use Cases

Potential use cases include:

```text
UC-CUSTOM-001
Submit Custom Order Request

UC-CUSTOM-002
Review Custom Request

UC-CUSTOM-003
Create Quotation

UC-CUSTOM-004
Approve Quotation

UC-CUSTOM-005
Reject Quotation

UC-CUSTOM-006
Update Custom Order Status

UC-CUSTOM-007
Track Custom Order
```

These will be formalized during the Use Case phase.

---

# 22. Future Test Case Direction

Potential test groups:

```text
TC-CUSTOM-001 — Request Submission
TC-CUSTOM-002 — Request Ownership
TC-CUSTOM-003 — Artisan Assignment
TC-CUSTOM-004 — Quotation Creation
TC-CUSTOM-005 — Quote Approval
TC-CUSTOM-006 — Production Guard
TC-CUSTOM-007 — State Transition
TC-CUSTOM-008 — Customer Tracking
TC-CUSTOM-009 — File Upload
TC-CUSTOM-010 — Cancellation
```

---

# 23. Custom Order Requirement Count

Current formal draft:

| Area | Count |
|---|---:|
| Request Creation | 13 |
| Artisan Review | 4 |
| Quotation | 6 |
| Customer Decision | 4 |
| Production Activation | 1 |
| Production Status | 5 |
| Tracking | 3 |
| Cancellation | 2 |
| **Total** | **38** |

Requirement count may change during formal review.

---

# 24. Validation Status

A large portion of this module remains:

```text
PROVISIONAL
```

because the underlying custom-order problem still requires real customer and artisan validation.

This does not mean the engineering design is invalid.

It means:

```text
Workflow Design
        ≠
Validated User Need
```

Both must eventually align.

---

# 25. MVP Protection Rule

If primary research validates this workflow:

Custom-order functionality should remain one of the strongest protected MVP modules.

If primary research rejects the assumed pain points:

The team must revise the MVP rather than preserving the workflow only because significant documentation has already been created.

---

# 26. Engineering Value

The custom-order module provides strong Software Engineering value because it contains:

- Multiple actors
- Structured data
- Ownership
- Authorization
- State transitions
- Business rules
- Validation
- File upload
- Workflow integrity
- Failure scenarios
- Traceability
- Testing opportunities

Therefore, if user validation supports it, this module should become one of the central portfolio case-study features.

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Functional Requirements Baseline Part 3  
**Module:** CUSTOM  
**Status:** Provisional Draft v0.1  
**Primary Research Dependency:** Critical  
**Next Step:** QR, Verification, Certificate, Notification & Administration Requirements
