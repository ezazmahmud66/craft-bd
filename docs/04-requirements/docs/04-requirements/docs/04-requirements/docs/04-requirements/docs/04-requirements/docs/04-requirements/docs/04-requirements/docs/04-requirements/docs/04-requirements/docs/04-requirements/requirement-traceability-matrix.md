# Craft BD — Requirement Acceptance Criteria & Traceability Matrix Baseline

## 1. Purpose

This document establishes the initial Requirement Traceability Matrix (RTM) for Craft BD.

The RTM connects important project requirements to their origins, supporting rules, acceptance criteria, and future test cases.

The purpose is to ensure that requirements are not implemented without a clear reason and are not tested without a defined expected behavior.

---

# 2. Traceability Model

Craft BD will use the following traceability structure:

```text
Stakeholder
      ↓
Goal / Pain Point
      ↓
Requirement
      ↓
Business / Security Rule
      ↓
Acceptance Criteria
      ↓
Use Case
      ↓
Test Case
```

Example:

```text
STK-01 Customer
      ↓
PP-02 Quotation ambiguity
      ↓
FR-CUSTOM-025
Approve Quotation
      ↓
BR-CUSTOM-001
Approval Before Production
      ↓
Acceptance Criteria
Only request owner can approve
      ↓
UC-CUSTOM-004
      ↓
TC-CUSTOM-005
```

---

# 3. Traceability Status

Each mapping may have one of the following states:

| Status | Meaning |
|---|---|
| COMPLETE | All currently required links exist |
| PARTIAL | Some downstream artifacts are pending |
| PROVISIONAL | Requirement depends on unresolved validation |
| DEFERRED | Requirement is not part of the current MVP |
| NOT STARTED | Traceability has not yet been created |

Because UML and test cases are developed in later phases, many current mappings are expected to be `PARTIAL`.

---

# 4. Authentication Traceability

| Source | Need | Requirement | Related Rule / Security | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| STK-01 / STK-02 | Account access | FR-AUTH-001 / 002 | SR-AUTH-001 | Valid registration creates appropriate account | TC-AUTH-001 | PARTIAL |
| STK-01 / STK-02 / STK-03 | Secure access | FR-AUTH-003 | SR-AUTH-002 | Valid credentials authenticate; invalid credentials fail | TC-AUTH-002 | PARTIAL |
| STK-01 / STK-02 / STK-03 | End session | FR-AUTH-004 | SR-AUTH-005 | Protected action unavailable after logout | TC-AUTH-003 | PARTIAL |
| STK-03 / STK-04 | Role separation | FR-AUTH-005 | SR-AUTHZ-002 | User receives only permitted role functions | TC-AUTHZ-001 | PARTIAL |

---

# 5. Artisan Traceability

| Source | Need / Pain Point | Requirement | Rule / Security | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| STK-02 | Professional identity | FR-ART-001 | BR-ART-001 | Artisan can maintain own approved profile fields | TC-ART-001 | PARTIAL |
| STK-01 | Understand maker | FR-ART-002 | BR-ART-002 | Public profile shows approved public information | TC-ART-002 | PARTIAL |
| STK-02 | Manage profile | FR-ART-003 | SR-OWN / BR-ART-001 | Artisan cannot edit another artisan profile | TC-ART-003 | PARTIAL |
| STK-01 / STK-02 | Connect maker and product | FR-ART-004 | DR-ART-002 | Correct artisan products displayed | TC-ART-004 | PARTIAL |

---

# 6. Product Management Traceability

| Source | Need | Requirement | Rule / Security | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| STK-02 | Add product | FR-PROD-001 | DR-PROD-002 | Valid product stored under correct artisan | TC-PROD-001 | PARTIAL |
| STK-02 | Edit product | FR-PROD-002 | BR-PROD-001 / SR-OWN-001 | Owner may edit; non-owner denied | TC-PROD-002 | PARTIAL |
| STK-02 | Stop selling product | FR-PROD-003 | BR-PROD-006 | Product deactivated without destroying order history | TC-PROD-003 | PARTIAL |
| STK-02 | Define price | FR-PROD-004 | BR-PROD-003 | Valid price accepted; invalid price rejected | TC-PROD-004 | PARTIAL |
| STK-02 | Maintain availability | FR-PROD-005 | BR-PROD-004 | Negative stock rejected | TC-PROD-005 | PARTIAL |
| STK-02 | Product image | FR-PROD-006 | SR-FILE-001–005 | Valid authorized image accepted | TC-PROD-006 | PARTIAL |
| STK-01 / STK-02 | Categorization | FR-PROD-007 | BR-PROD-002 | Invalid category cannot be assigned | TC-PROD-007 | PARTIAL |

---

# 7. Product Discovery Traceability

| Source | Need / Pain Point | Requirement | Supporting Rule | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| STK-01 | Discover crafts | FR-DISC-001 | BR-PROD-005 | Eligible products visible in catalog | TC-DISC-001 | PARTIAL |
| STK-01 | Understand product | FR-DISC-002 | PR-DATA-002 | Product details shown without private data | TC-DISC-002 | PARTIAL |
| STK-01 | Browse category | FR-DISC-003 | DR-PROD-003 | Category returns matching eligible products | TC-DISC-003 | PARTIAL |
| STK-01 | Find specific product | FR-DISC-004 | SR-INPUT-005 | Supported search returns relevant products | TC-DISC-004 | PARTIAL |
| STK-01 | Narrow choices | FR-DISC-005 / 006 | SR-INPUT-005 | Valid filters restrict results correctly | TC-DISC-005 | PARTIAL |
| STK-01 | Material-based discovery | FR-DISC-007 | DR-PROD-006 | Material filter returns matching products | TC-DISC-006 | PROVISIONAL |
| STK-01 | Craft-type discovery | FR-DISC-008 | DR-PROD-006 | Craft-type filter returns matching products | TC-DISC-007 | PROVISIONAL |

---

# 8. Craft Context Traceability

| Source | Need / Pain Point | Requirement | Supporting Data | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| C1 / STK-01 | Cultural understanding | FR-CRAFT-001 | DR-PROD-006 | Existing approved craft context is accessible | TC-CRAFT-001 | PROVISIONAL |
| STK-02 / STK-03 | Maintain craft info | FR-CRAFT-002 | SR-AUTHZ-002 | Only authorized role may modify context | TC-CRAFT-002 | PROVISIONAL |

Primary user validation is still required before this module receives stronger priority.

---

# 9. Cart Traceability

| Source | Need | Requirement | Business Rule | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| STK-01 | Review intended purchase | FR-CART-001 | BR-CART-001 | Customer sees own cart only | TC-CART-001 | PARTIAL |
| STK-01 | Add product | FR-CART-002 | BR-CART-003 | Eligible product added to own cart | TC-CART-002 | PARTIAL |
| STK-01 | Change quantity | FR-CART-003 | BR-CART-002 | Valid quantity updates; invalid rejected | TC-CART-003 | PARTIAL |
| STK-01 | Remove item | FR-CART-004 | BR-CART-001 | Selected own cart item removed | TC-CART-004 | PARTIAL |
| Business Logic | Accurate total | FR-CART-005 | BR-CART-004 | Authoritative total calculated correctly | TC-CART-005 | PARTIAL |

---

# 10. Standard Order Traceability

| Source | Need | Requirement | Rule / Security | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| STK-01 | Begin checkout | FR-ORDER-001 | BR-ORDER-004 | Empty checkout cannot proceed | TC-ORDER-001 | PARTIAL |
| STK-01 | Delivery | FR-ORDER-002 | PR-DATA-003 | Required valid delivery info accepted | TC-ORDER-002 | PARTIAL |
| STK-01 | Verify order before purchase | FR-ORDER-003 | BR-ORDER-003 | Summary shown before confirmation | TC-ORDER-003 | PARTIAL |
| STK-01 | Place order | FR-ORDER-004 | BR-ORDER-003 | Valid confirmed checkout creates order | TC-ORDER-004 | PARTIAL |
| Business Logic | Persistent transaction | FR-ORDER-005 | DR-ORDER-001 | Unique persistent order created | TC-ORDER-005 | PARTIAL |
| Business Logic | Historical consistency | FR-ORDER-006 / 007 | BR-ORDER-002 / 007 | Order item and price snapshot preserved | TC-ORDER-006 | PARTIAL |
| STK-01 | Track purchase | FR-ORDER-013 | BR-ORDER-008 / SR-OWN-002 | Owner sees current status; other customer denied | TC-ORDER-007 | PARTIAL |

---

# 11. Simulated Payment Traceability

| Source | Need | Requirement | Constraint / Rule | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| Academic MVP | Demonstrate payment flow | FR-ORDER-014 | CR-PAY-001 | Supported simulated method selectable | TC-PAY-001 | PARTIAL |
| Academic MVP | Payment state | FR-ORDER-015 | BR-ORDER-009 | Simulated state recorded without real payment | TC-PAY-002 | PARTIAL |
| STK-01 | See payment state | FR-ORDER-016 | PR-DATA-002 | Customer sees own payment status | TC-PAY-003 | PARTIAL |
| Future | Real transaction | IR-PAY-001 | CR-BUDGET-002 | Not required in MVP | — | DEFERRED |

---

# 12. Review Traceability

| Source | Need | Requirement | Rule / Security | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| STK-01 | Read experience | FR-REV-001 | BR-REV-005 | Eligible public reviews displayed safely | TC-REV-001 | PARTIAL |
| STK-01 | Rate purchase | FR-REV-002 | BR-REV-001 / SR-AUTHZ-008 | Eligible purchaser may rate | TC-REV-002 | PARTIAL |
| STK-01 | Write review | FR-REV-003 | BR-REV-001 | Eligible purchaser may submit review | TC-REV-003 | PARTIAL |
| Platform | Review integrity | FR-REV-004 | BR-REV-003 | Artisan cannot remove legitimate review | TC-REV-004 | PARTIAL |
| STK-03 | Moderation | FR-REV-005 | BR-REV-004 | Authorized admin may moderate | TC-REV-005 | PARTIAL |

---

# 13. Custom Order Traceability — Request Creation

| Source | Pain Point / Need | Requirement | Rule / Data | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| C2 / STK-01 | Structured customization | FR-CUSTOM-001 | DR-CUSTOM-001 | Authenticated customer may start eligible request | TC-CUSTOM-001 | PROVISIONAL |
| PP-01 | Requirement ambiguity | FR-CUSTOM-002–009 | DR-CUSTOM-004 | Submitted specifications persist correctly | TC-CUSTOM-002 | PROVISIONAL |
| STK-01 | Submit request | FR-CUSTOM-010 | BR-CUSTOM-006 | Valid mandatory data creates request | TC-CUSTOM-003 | PROVISIONAL |
| Business Logic | Initial workflow state | FR-CUSTOM-011 | BR-CUSTOM-007 | New request receives approved initial state | TC-CUSTOM-004 | PROVISIONAL |
| STK-01 | View own request | FR-CUSTOM-012 / 013 | SR-OWN-003 | Owner sees own request; others denied | TC-CUSTOM-005 | PROVISIONAL |

---

# 14. Custom Order Traceability — Artisan Review

| Source | Pain Point / Need | Requirement | Rule / Security | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| A1 / A3 | Organized requests | FR-CUSTOM-014 | BR-CUSTOM-003 | Artisan sees assigned requests only | TC-CUSTOM-006 | PROVISIONAL |
| PP-01 | Complete requirements | FR-CUSTOM-015 | PR-DATA-004 | Assigned artisan sees required request data | TC-CUSTOM-007 | PROVISIONAL |
| STK-02 | Review request | FR-CUSTOM-016 | BR-CUSTOM-007 | Valid request enters under-review state | TC-CUSTOM-008 | PROVISIONAL |
| STK-02 | Reject infeasible work | FR-CUSTOM-017 | BR-CUSTOM-013 | Eligible request may be rejected | TC-CUSTOM-009 | PROVISIONAL |

---

# 15. Custom Order Traceability — Quotation

| Source | Pain Point / Need | Requirement | Rule / Data | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| PP-02 | Informal quotation ambiguity | FR-CUSTOM-018 | BR-CUSTOM-004 | Assigned artisan creates quotation | TC-CUSTOM-010 | PROVISIONAL |
| STK-01 / STK-02 | Clear price | FR-CUSTOM-019 | BR-CUSTOM-005 | Invalid quoted price rejected | TC-CUSTOM-011 | PROVISIONAL |
| STK-01 | Expected completion | FR-CUSTOM-020 | DR-CUSTOM-009 | Completion estimate stored | TC-CUSTOM-012 | PROVISIONAL |
| STK-02 | Explain quotation | FR-CUSTOM-021 | DR-CUSTOM-007 | Notes remain associated with quotation | TC-CUSTOM-013 | PROVISIONAL |
| STK-02 | Submit quotation | FR-CUSTOM-022 / 023 | BR-CUSTOM-004 / 007 | Valid quote becomes available to customer | TC-CUSTOM-014 | PROVISIONAL |

---

# 16. Custom Order Traceability — Customer Approval

| Source | Pain Point / Need | Requirement | Rule / Security | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| PP-02 | Clear agreement | FR-CUSTOM-024 | PR-DATA-004 | Request owner sees quotation | TC-CUSTOM-015 | PROVISIONAL |
| STK-01 | Explicit approval | FR-CUSTOM-025 | BR-CUSTOM-001 / 002 | Only owner can approve valid quote | TC-CUSTOM-016 | PROVISIONAL |
| STK-01 | Reject quote | FR-CUSTOM-026 | BR-CUSTOM-002 | Only owner can reject valid quote | TC-CUSTOM-017 | PROVISIONAL |
| Business Logic | Decision audit | FR-CUSTOM-027 | DR-CUSTOM-010 / 011 | Decision and time persist | TC-CUSTOM-018 | PROVISIONAL |
| STK-01 / STK-02 | Agreement before work | FR-CUSTOM-028 | BR-CUSTOM-001 | Production blocked until approval | TC-CUSTOM-019 | PROVISIONAL |

---

# 17. Custom Order Traceability — Production & Tracking

| Source | Pain Point / Need | Requirement | Rule | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| A1 / A3 | Organized production | FR-CUSTOM-029 | BR-CUSTOM-007 | Approved request enters production validly | TC-CUSTOM-020 | PROVISIONAL |
| STK-02 | Record QC stage | FR-CUSTOM-030 | BR-CUSTOM-007 | Valid QC state recorded | TC-CUSTOM-021 | PROVISIONAL |
| STK-02 | Ready state | FR-CUSTOM-031 | BR-CUSTOM-007 | Valid transition to ready-to-ship | TC-CUSTOM-022 | PROVISIONAL |
| STK-02 | Shipment status | FR-CUSTOM-032 | BR-CUSTOM-007 | Valid actor marks shipped | TC-CUSTOM-023 | PROVISIONAL |
| STK-01 / STK-02 | Completion | FR-CUSTOM-033 | BR-CUSTOM-007 | Eligible order reaches delivered state | TC-CUSTOM-024 | PROVISIONAL |
| PP-03 | Repeated progress questions | FR-CUSTOM-034 | BR-CUSTOM-012 | Customer sees accurate current status | TC-CUSTOM-025 | PROVISIONAL |
| A1 / A3 | Manage active work | FR-CUSTOM-035 | BR-CUSTOM-003 | Artisan sees relevant active work | TC-CUSTOM-026 | PROVISIONAL |

---

# 18. Verification Traceability

| Source | Need | Requirement | Rule / Security | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| Trust hypothesis | Platform product record | FR-VERIFY-001 | BR-VERIFY-003 | Unique valid verification ID assigned | TC-VERIFY-001 | PROVISIONAL |
| STK-01 | Scan product reference | FR-VERIFY-002 | BR-VERIFY-001 | QR opens correct Craft BD record | TC-VERIFY-002 | PROVISIONAL |
| STK-01 | View record | FR-VERIFY-003 | PR-DATA-002 | Only approved public data displayed | TC-VERIFY-003 | PROVISIONAL |
| Platform | Safe invalid lookup | FR-VERIFY-004 | BR-VERIFY-004 / SR-VERIFY-002 | Invalid ID exposes no unrelated record | TC-VERIFY-004 | PROVISIONAL |

---

# 19. Certificate Traceability

| Source | Need | Requirement | Rule | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| Platform hypothesis | Certificate record | FR-CERT-001 | BR-CERT-001 | Authorized admin creates record | TC-CERT-001 | PROVISIONAL |
| Business Logic | Unique certificate | FR-CERT-002 | BR-CERT-003 | Certificate ID unique | TC-CERT-002 | PROVISIONAL |
| STK-01 | View certificate | FR-CERT-003 | BR-CERT-002 | Display does not imply unsupported authority | TC-CERT-003 | PROVISIONAL |
| Platform | Product link | FR-CERT-004 | BR-CERT-004 | Certificate links to correct product | TC-CERT-004 | PROVISIONAL |

This module remains optional.

---

# 20. Notification Traceability

| Source | Need | Requirement | Rule | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| STK-02 | Know new request exists | FR-NOTIF-001 | BR-NOTIF-002 | Correct artisan receives awareness event | TC-NOTIF-001 | PARTIAL |
| STK-01 | Know quote is ready | FR-NOTIF-002 | BR-NOTIF-001 | Correct customer receives notification | TC-NOTIF-002 | PROVISIONAL |
| STK-02 | Know customer decision | FR-NOTIF-003 / 004 | BR-NOTIF-001 | Assigned artisan notified appropriately | TC-NOTIF-003 | PARTIAL |
| STK-01 | Know progress | FR-NOTIF-005 | BR-NOTIF-002 | Important status events generate awareness | TC-NOTIF-004 | PROVISIONAL |
| User | View notifications | FR-NOTIF-006 | SR-OWN-005 | User accesses own notifications only | TC-NOTIF-005 | PARTIAL |

---

# 21. Administration Traceability

| Source | Need | Requirement | Rule / Security | Acceptance Direction | Future Test | Status |
|---|---|---|---|---|---|---|
| STK-03 | User governance | FR-ADMIN-001 / 002 | BR-ADMIN-001 / SR-ADMIN-002 | Authorized admin manages user status | TC-ADMIN-001 | PARTIAL |
| STK-03 | Category governance | FR-ADMIN-003–005 | BR-ADMIN-005 | Category management preserves integrity | TC-ADMIN-002 | PARTIAL |
| STK-03 | Content governance | FR-ADMIN-006–008 | BR-ADMIN-002 | Only approved moderation actions allowed | TC-ADMIN-003 | PARTIAL |
| STK-03 | Exceptional support | FR-ADMIN-011 / 012 | BR-ADMIN-003 | Admin action limited to approved authority | TC-ADMIN-004 | PARTIAL |

---

# 22. Security Traceability Matrix

| Security Requirement | Protected Area | Future Test |
|---|---|---|
| SR-AUTH-001 | Password storage | TC-SEC-AUTH-001 |
| SR-AUTHZ-001 | Server authorization | TC-SEC-AUTHZ-001 |
| SR-OWN-001 | Artisan product ownership | TC-SEC-OWN-001 |
| SR-OWN-002 | Customer order isolation | TC-SEC-OWN-002 |
| SR-OWN-003 | Custom request isolation | TC-SEC-OWN-003 |
| SR-OWN-004 | Artisan assignment | TC-SEC-OWN-004 |
| SR-FILE-001–006 | Upload security | TC-SEC-FILE-* |
| SR-SECRET-001 / 002 | Secret management | TC-SEC-CONFIG-001 |
| SR-TRANSPORT-001 | HTTPS | TC-SEC-TRANS-001 |
| SR-ADMIN-002 | Admin authorization | TC-SEC-ADMIN-001 |

---

# 23. Privacy Traceability Matrix

| Privacy Requirement | Protected Data / Flow | Verification Direction |
|---|---|---|
| PR-DATA-001 | Personal-data collection | Data-model review |
| PR-DATA-002 | Public/private separation | API/UI review |
| PR-DATA-003 | Delivery information | Cross-user access test |
| PR-DATA-004 | Custom-order data | Customer/artisan access test |
| PR-DATA-005 | Reference images | File-access test |
| PR-DATA-006 | Artisan public profile | Public-field inspection |
| PR-DATA-009 | Demo deployment | Demo-data review |
| PR-DATA-010 | Research files | Repository review |

---

# 24. NFR Traceability Direction

Non-functional requirements will later map to quality tests.

| NFR | Verification |
|---|---|
| NFR-PERF-001 | Response-time test |
| NFR-PERF-002 | Search performance test |
| NFR-USE-001 | Responsive UI test |
| NFR-USE-003 | Form-validation test |
| NFR-USE-005 | Usability / UAT |
| NFR-REL-002 | Invalid-transition test |
| NFR-MNT-002 | Git workflow review |
| NFR-COMP-001 | Browser compatibility test |
| NFR-AVL-001 | Deployment availability check |
| NFR-ERR-003 | Unauthorized access test |

---

# 25. Requirement-to-Use-Case Direction

Use cases have not yet been formally developed.

Future mappings should include examples such as:

| Requirement | Future Use Case |
|---|---|
| FR-AUTH-003 | UC-AUTH-001 Login |
| FR-PROD-001 | UC-PROD-001 Create Product |
| FR-ORDER-004 | UC-ORDER-001 Place Order |
| FR-CUSTOM-010 | UC-CUSTOM-001 Submit Custom Request |
| FR-CUSTOM-022 | UC-CUSTOM-003 Create Quotation |
| FR-CUSTOM-025 | UC-CUSTOM-004 Approve Quotation |
| FR-CUSTOM-034 | UC-CUSTOM-007 Track Custom Order |
| FR-VERIFY-003 | UC-VERIFY-001 View Verification Record |

Formal use-case IDs will be finalized in the Use Case phase.

---

# 26. Acceptance Criteria Standard

Acceptance criteria should describe observable outcomes.

Preferred structure:

```text
Given
<starting context>

When
<actor performs action>

Then
<observable system result>
```

Example:

```text
Given:
Customer A owns Custom Request CR-100.

When:
Customer B attempts to approve its quotation.

Then:
The system denies the action and does not alter the quotation decision.
```

---

# 27. Positive and Negative Criteria

Important requirements should include both:

```text
Positive Path
+
Negative / Failure Path
```

Example:

### Positive

Valid artisan updates own product.

Expected:

Product updated.

### Negative

Artisan attempts to update another artisan's product.

Expected:

Access denied.

This approach improves test quality and security coverage.

---

# 28. Requirement Acceptance Gate

A requirement should not be considered implementation-complete merely because a UI exists.

The completion chain should be:

```text
Requirement
      ↓
Implementation
      ↓
Business Rule Enforcement
      ↓
Security Enforcement
      ↓
Acceptance Criteria Passed
      ↓
Required Test Passed
```

Only then should the requirement be considered technically satisfied.

---

# 29. Traceability Gap Rule

If implementation is created but no requirement supports it:

```text
Implementation
      ↓
No Requirement
```

the feature should be reviewed as possible scope creep.

If a requirement exists but no implementation or test exists:

```text
Requirement
      ↓
No Implementation / Test
```

the requirement remains incomplete.

---

# 30. Research Validation Traceability

Primary research findings should later map back to provisional requirements.

Example:

```text
Interview C02
Interview A01
      ↓
Finding RF-04
      ↓
PP-02 Confirmed
      ↓
FR-CUSTOM-018
FR-CUSTOM-025
      ↓
Status changed:
PROVISIONAL → APPROVED
```

If research contradicts the hypothesis:

```text
PROVISIONAL
      ↓
Review
      ↓
Rewrite / Defer / Remove
```

Requirements must not remain protected merely because documentation already exists.

---

# 31. Current Traceability Gaps

The following artifacts are intentionally not yet complete:

- Final primary-research evidence links
- Formal Use Cases
- UML models
- Architecture-component mapping
- API endpoint mapping
- Database-table mapping
- Implementation references
- Final test cases
- UAT results

These will be added during their respective project phases.

---

# 32. MVP Traceability Priority

The highest traceability priority should remain on:

```text
Authentication
+
Authorization
+
Product Management
+
Standard Ordering
+
Custom Order Workflow
+
Security
+
Testing
```

Conditional features such as certificate functionality should not receive more engineering effort than the core workflows.

---

# 33. Requirement Coverage Principle

The project should eventually be able to answer:

### Why does this feature exist?

→ Requirement / stakeholder evidence.

### Who needs it?

→ Stakeholder or system source.

### What rule controls it?

→ Business/security rule.

### How do we know it works?

→ Acceptance criteria / test case.

### Where is it implemented?

→ Future code/API/UI mapping.

---

# 34. Current RTM Status

| Area | Current Traceability |
|---|---|
| Stakeholder → Requirement | Established |
| Pain Point → Requirement | Established for priority workflows |
| Requirement → Business Rule | Established |
| Requirement → Security Rule | Established for major protected flows |
| Requirement → Acceptance Criteria | Baseline established |
| Requirement → Use Case | Planned |
| Requirement → UML | Planned |
| Requirement → Architecture | Planned |
| Requirement → Code | Planned |
| Requirement → Test Case | IDs planned |
| Requirement → UAT | Planned |

---

# 35. Engineering Decision

Craft BD will maintain requirement traceability throughout development rather than creating an RTM only at the end of the academic project.

The intended lifecycle is:

```text
Requirement
→ Design
→ Build
→ Test
→ Evidence
```

This supports stronger Software Engineering practice and helps prevent:

- Feature creep
- Missing requirements
- Untested business rules
- Unexplained implementation decisions
- Weak academic documentation

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Requirement Acceptance Criteria & Traceability Matrix Baseline  
**Status:** Draft / Provisional v0.1  
**Primary Research Dependency:** Open  
**Next Step:** Requirement Priority, Dependency & Conflict Review
