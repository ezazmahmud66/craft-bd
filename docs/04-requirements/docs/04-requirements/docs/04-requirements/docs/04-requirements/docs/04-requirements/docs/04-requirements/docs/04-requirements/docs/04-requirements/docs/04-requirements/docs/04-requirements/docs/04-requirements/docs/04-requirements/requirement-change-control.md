# Craft BD — Requirement Change Control & Baseline Policy

## 1. Purpose

This document defines how Craft BD requirements will be controlled after the first formal requirement baseline is established.

The goal is to prevent:

- Uncontrolled scope growth
- Conflicting requirements
- Silent requirement changes
- Broken traceability
- Implementation without approval
- Testing based on outdated requirements

---

# 2. Core Principle

After requirement baseline approval:

```text
Requirement Change
        ≠
Direct Implementation
```

Instead:

```text
Change Request
      ↓
Impact Analysis
      ↓
Decision
      ↓
Requirement Update
      ↓
Design / Code / Test Update
```

---

# 3. Requirement Baseline Definition

A requirement baseline is an approved snapshot of the current requirement set.

For Craft BD, the first baseline will be:

```text
Requirement Baseline v0.1
```

It represents the currently accepted project scope while explicitly retaining provisional requirements that still depend on primary research.

---

# 4. Baseline Does Not Mean Permanent

Baseline means:

- Controlled
- Versioned
- Traceable
- Reviewable

It does not mean:

```text
Requirement can never change
```

Requirements may change when justified by:

- User research
- Faculty feedback
- Technical constraints
- Security findings
- Usability findings
- Testing
- Schedule pressure
- Business-rule changes

---

# 5. Change Request Identifier

Requirement changes will use:

```text
CRQ-NNN
```

Examples:

```text
CRQ-001
CRQ-002
CRQ-003
```

This must not be confused with `CR-*`, which is used for Constraint Requirements.

---

# 6. Change Request Sources

A requirement change may originate from:

- Customer
- Artisan
- Administrator
- Faculty / Supervisor
- Development Team
- Testing
- Security Review
- Usability Testing
- Primary Research
- Deployment Constraints

The source must be recorded.

---

# 7. Change Request Record

Each requirement change request should contain:

| Field | Description |
|---|---|
| Change ID | CRQ-NNN |
| Requested By | Source |
| Date | Request date |
| Requirement IDs | Affected requirement(s) |
| Proposed Change | Requested modification |
| Reason | Why change is needed |
| Evidence | Research / defect / feedback / constraint |
| Priority | High / Medium / Low |
| Impact | Scope, design, code, test, schedule |
| Decision | Approved / Rejected / Deferred |
| Decision Reason | Engineering rationale |
| Baseline Version | Version affected |

---

# 8. Change Types

Requirement changes may be classified as:

## ADD

Introduce a new requirement.

## MODIFY

Change an existing requirement.

## REMOVE

Remove a requirement from active scope.

## DEFER

Move a requirement to future scope.

## PRIORITY CHANGE

Change Must / Should / Could / Deferred classification.

## BUSINESS RULE CHANGE

Change workflow logic or eligibility.

## CLARIFICATION

Improve wording without materially changing system behavior.

---

# 9. Change Workflow

Craft BD shall follow:

```text
Change Proposed
      ↓
Create CRQ
      ↓
Identify Affected Requirements
      ↓
Impact Analysis
      ↓
Decision
      ↓
Update Documentation
      ↓
Update Traceability
      ↓
Update Implementation / Tests
```

---

# 10. Impact Analysis Areas

Before approving a material change, review its effect on:

- Requirements
- Business Rules
- Security
- Privacy
- Data Model
- APIs
- UI/UX
- UML
- Architecture
- Implementation
- Testing
- Deployment
- Schedule
- Documentation

---

# 11. Example Impact Analysis

Suppose a new requirement is proposed:

> Customer should negotiate quotation price multiple times.

Possible impact:

```text
Requirement
↓
Quotation workflow changes
↓
New quotation-version data
↓
New state transitions
↓
New API endpoints
↓
New UI
↓
New authorization rules
↓
New tests
```

Therefore this should not be accepted merely because the UI change appears simple.

---

# 12. Change Decision Categories

Each change request shall receive one of:

```text
APPROVED
REJECTED
DEFERRED
NEEDS_MORE_EVIDENCE
```

---

# 13. Approval Criteria

A proposed change should be approved when it provides sufficient value and remains acceptable in terms of:

- Evidence
- User value
- Security
- Privacy
- Data integrity
- Scope
- Technical feasibility
- Schedule
- Maintainability
- Academic value

---

# 14. Rejection Criteria

A change may be rejected when it:

- Conflicts with core scope
- Creates excessive complexity
- Lacks sufficient justification
- Violates security/privacy boundaries
- Duplicates existing functionality
- Provides weak value relative to cost
- Threatens delivery quality

---

# 15. Defer Criteria

A requirement should be deferred when:

- It may be useful later
- It is not required for current MVP
- It introduces major external dependencies
- Time is insufficient
- Evidence is currently weak
- Core requirements are higher priority

---

# 16. Primary Research Change Rule

Primary research has authority to change provisional requirements.

Example:

```text
FR-CUSTOM-025
Status: PROVISIONAL
```

If user research strongly supports the workflow:

```text
PROVISIONAL
→ APPROVED
```

If research contradicts it:

```text
PROVISIONAL
→ MODIFY
or
DEFER
or
REJECT
```

Existing documentation effort must not be used as a reason to keep an invalid requirement.

---

# 17. Faculty Feedback Rule

Faculty feedback should be treated seriously but should still be translated into an engineering requirement before implementation.

Example:

```text
Faculty:
"Add chat feature."
```

Should not immediately become:

```text
Build Chat
```

Instead:

```text
Feedback
↓
Problem / Objective
↓
Requirement Impact
↓
Feasibility
↓
Scope Decision
```

---

# 18. Team Suggestion Rule

Developer preference alone is not sufficient justification for a new feature.

Example:

```text
"We know how to build blockchain."
```

does not justify introducing blockchain.

Technology must serve an approved requirement.

---

# 19. Security Change Rule

A security-critical change may override lower-priority feature work.

Example:

If testing reveals authorization failure:

```text
Fix Authorization
```

takes priority over:

```text
Add Certificate UI
```

---

# 20. Requirement ID Stability

After baseline approval, an existing requirement ID shall not be reused for a different requirement.

Example:

If:

```text
FR-PROD-005
```

is removed, another requirement must not later be renamed to `FR-PROD-005`.

Instead:

```text
FR-PROD-005
Status: DEPRECATED
```

or:

```text
Status: REJECTED
```

depending on context.

---

# 21. Requirement Modification Rule

When a requirement changes materially:

- Keep the same ID where the underlying requirement remains conceptually the same
- Record the change history
- Update its wording
- Update acceptance criteria
- Update related artifacts

If the new requirement is fundamentally different, create a new ID.

---

# 22. Change History Example

```text
Requirement:
FR-CUSTOM-020

v0.1:
Estimated completion date required.

v0.2:
Estimated completion may be represented as date or delivery range.

Reason:
Artisan research indicated exact dates may be unrealistic.
```

---

# 23. Traceability Update Rule

An approved requirement change may require updates to:

```text
Stakeholder Mapping
Pain Point
Requirement
Business Rule
Use Case
UML
Database
API
Test Case
```

No material requirement change should leave traceability knowingly inconsistent.

---

# 24. Test Update Rule

If requirement behavior changes, related tests must be reviewed.

Example:

Original rule:

```text
Only delivered orders may be reviewed.
```

Changed rule:

```text
Delivered or completed pickup orders may be reviewed.
```

Then:

```text
BR-REV-001
↓
FR-REV-002
↓
TC-REV-002
```

must all be reviewed.

---

# 25. Change Severity

Changes may be classified as:

## Minor

Wording or documentation clarification with no behavioral impact.

## Moderate

Changes behavior inside an existing module.

## Major

Changes:

- Architecture
- Core workflow
- Scope
- Security model
- Database structure
- Multiple modules

Major changes require stronger review.

---

# 26. Scope Creep Detection

A proposed feature may indicate scope creep when:

```text
New Feature
+
No validated problem
+
No requirement source
+
No MVP dependency
```

If all are missing, default decision should be:

```text
DEFER
```

until justified.

---

# 27. Emergency Change

If implementation reveals a critical issue such as:

- Security vulnerability
- Data corruption
- Broken authorization
- Invalid workflow

a corrective requirement or business-rule change may be prioritized immediately.

However, the change should still be documented afterward through the change-control process.

---

# 28. GitHub Change Workflow

Material requirement changes should use GitHub evidence.

Recommended workflow:

```text
Issue
↓
Change Request Discussion
↓
Task Branch
↓
Requirement Update
↓
Review
↓
Pull Request
↓
Merge
```

---

# 29. Requirement Change GitHub Issue Template Direction

Future requirement-change issues should include:

```text
Affected Requirement:
Proposed Change:
Reason:
Evidence:
Scope Impact:
Security Impact:
Data Impact:
Testing Impact:
Decision:
```

The repository already contains a requirement-change issue template; this policy defines how it should be used.

---

# 30. Baseline Versioning

Recommended requirement versions:

```text
v0.1
Initial controlled baseline

v0.2
Research-informed revision

v1.0
Approved implementation baseline
```

Exact version progression may change depending on project development.

---

# 31. Current Baseline Status

At the end of Phase 04, the requirement set should be treated as:

```text
Requirement Baseline v0.1
```

with two categories:

### Controlled Requirements

Requirements sufficiently defined for design.

### Provisional Requirements

Requirements defined technically but still awaiting product/user validation.

---

# 32. Baseline Freeze Policy

After Phase 04:

Core requirements should not change casually.

Changes require:

```text
Reason
+
Impact
+
Decision
```

However, Phase 01–03 research-dependent requirements remain intentionally open to validation-driven change.

---

# 33. Change Approval Responsibility

For the academic project:

## Development Team

Responsible for:

- Impact analysis
- Technical feasibility
- Documentation
- Implementation consequences

## Faculty / Supervisor

May provide academic or project-direction feedback.

## Customers / Artisans

Provide primary evidence for user-centered requirements.

Final project decisions should combine evidence, feasibility, academic objectives, and scope control.

---

# 34. Conflict Escalation

If stakeholders disagree:

```text
Conflict
↓
Evidence Review
↓
Security / Integrity Check
↓
User Value
↓
Feasibility
↓
Scope Impact
↓
Decision
```

Stakeholder authority alone should not automatically override critical security or integrity constraints.

---

# 35. Example Change Request 1

## CRQ-001

**Request**

Add real-time chat between Customer and Artisan.

**Impact**

- New messaging data model
- Moderation
- Privacy
- Authorization
- Real-time infrastructure
- Notifications
- Testing
- Scope growth

**Current Decision**

`DEFERRED`

**Reason**

Structured custom-order workflow is prioritized over building a separate communication platform.

---

# 36. Example Change Request 2

## CRQ-002

**Request**

Replace simulated payment with real payment gateway.

**Impact**

- External provider
- Security
- Callback handling
- Failure handling
- Provider testing
- Compliance considerations

**Current Decision**

`DEFERRED`

---

# 37. Example Change Request 3

## CRQ-003

**Request**

Remove certificate feature if schedule becomes constrained.

**Impact**

Low impact on core ordering workflow.

**Decision Direction**

`APPROVE if required for scope reduction`

This demonstrates that change control is also used to remove scope, not only add features.

---

# 38. Example Change Request 4

## CRQ-004

**Request**

Allow artisan to edit customer custom requirements after submission.

**Risk**

This may destroy agreement traceability.

**Decision**

Do not approve unrestricted editing.

Alternative:

```text
Customer Change Request
→ Artisan Review
→ Revised Quote
→ Customer Re-Approval
```

---

# 39. Requirement Baseline Audit Questions

Before approving any new baseline version, ask:

- Does every requirement still have a valid purpose?
- Are priorities correct?
- Are deferred items still excluded?
- Are provisional requirements clearly marked?
- Are business rules consistent?
- Are security/privacy controls intact?
- Are affected tests identified?
- Is traceability updated?
- Has scope increased unintentionally?

---

# 40. Baseline Quality Rule

Requirement quality is more important than requirement quantity.

Craft BD should prefer:

```text
Stable
+
Traceable
+
Testable
+
Secure
```

requirements over a large unstructured feature list.

---

# 41. Final Change-Control Policy

After Requirement Baseline v0.1:

```text
No Silent Requirement Changes
No Untracked Scope Addition
No Requirement ID Reuse
No Feature Without Justification
No Material Change Without Impact Review
```

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Requirement Change Control & Baseline Policy  
**Status:** Draft v0.1  
**Baseline Target:** Requirement Baseline v0.1  
**Next Step:** Consolidated Phase 04 Requirement Baseline Summary
