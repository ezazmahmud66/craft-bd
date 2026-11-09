# Craft BD — Stakeholder Conflict Analysis

## 1. Purpose

This document identifies potential conflicts among Craft BD stakeholders and defines how those conflicts should be analyzed and resolved.

The objective is to prevent:

- Requirement contradictions
- Scope creep
- Poor usability
- Operational bottlenecks
- Security weaknesses
- Unbalanced product decisions

The analysis is provisional because primary user research is still pending.

---

# 2. Conflict Analysis Principle

A stakeholder request should not automatically become a system requirement.

Instead:

```text
Stakeholder Request
      ↓
Underlying Need
      ↓
Conflict Analysis
      ↓
Evidence
      ↓
Business / User Value
      ↓
Technical Impact
      ↓
Decision
```

---

# 3. Conflict CF-01 — Customer Flexibility vs Artisan Simplicity

## Customer Perspective

Customer may want:

- Free-form communication
- Unlimited clarification
- Flexible changes
- Direct messaging

## Artisan Perspective

Artisan may want:

- Fewer messages
- Clear requirements
- Reduced repeated questions
- Less administrative work

## Conflict

Too much flexibility can create communication overhead.

Too much structure can frustrate customers.

## Recommended Resolution

Use:

```text
Structured Required Fields
+
Optional Notes
+
Reference Image
```

instead of unlimited real-time messaging.

## Decision

**Balanced Structured Workflow**

---

# 4. Conflict CF-02 — Detailed Product Information vs Fast Product Entry

## Customer Perspective

Customer wants:

- Materials
- Region
- Artisan story
- Craft story
- Detailed product description

## Artisan Perspective

Artisan wants:

- Quick product upload
- Minimal repetitive data entry

## Conflict

More fields improve information quality but increase seller effort.

## Recommended Resolution

Separate fields into:

### Required

- Product name
- Category
- Price
- Stock
- Description
- Image

### Optional / Enrichment

- Craft story
- Cultural context
- Product journey
- Detailed production information

## Decision

**Essential Data Required, Enrichment Optional**

---

# 5. Conflict CF-03 — Customer Customization vs Production Feasibility

## Customer Perspective

Customer may request any:

- Design
- Material
- Size
- Color
- Deadline

## Artisan Perspective

Not every request may be technically or practically possible.

## Conflict

Customer expectation may exceed artisan capability.

## Recommended Resolution

Custom request flow should allow:

```text
Request
→ Artisan Review
→ Accept for Quote / Reject
```

A submitted request should not automatically become an accepted order.

## Decision

**Artisan Feasibility Review Required**

---

# 6. Conflict CF-04 — Customer Wants Immediate Production vs Artisan Needs Approval

## Customer Perspective

Customer may expect quick processing.

## Artisan Perspective

Artisan needs confirmed:

- Price
- Scope
- Requirements
- Approval

before beginning work.

## Recommended Resolution

Production begins only after:

```text
Quotation
→ Customer Approval
```

## Decision

**Explicit Approval Required Before Production**

---

# 7. Conflict CF-05 — Customer Wants Frequent Updates vs Artisan Administrative Burden

## Customer Perspective

Customer wants progress visibility.

## Artisan Perspective

Frequent manual updates consume time.

## Conflict

Too many status stages create unnecessary administrative work.

## Recommended Resolution

Use a small number of meaningful statuses.

Example:

```text
Approved
→ In Production
→ Ready
→ Shipped
→ Delivered
```

The backend may contain more detailed states if required.

## Decision

**Minimal Meaningful Status Updates**

---

# 8. Conflict CF-06 — Customer Privacy vs Artisan Operational Need

## Customer Perspective

Customer expects private information to remain protected.

## Artisan Perspective

Artisan needs enough information to:

- Fulfill order
- Review customization
- Coordinate delivery where applicable

## Conflict

Providing too much customer data creates privacy risk.

Providing too little may prevent fulfillment.

## Recommended Resolution

Use:

**Minimum Necessary Data Access**

Artisan receives only information required for the relevant transaction.

## Decision

**Least-Privilege Data Exposure**

---

# 9. Conflict CF-07 — Artisan Control vs Platform Governance

## Artisan Perspective

Artisan may want full control over:

- Products
- Reviews
- Profile
- Product records

## Admin Perspective

Admin needs:

- Moderation
- Platform integrity
- Rule enforcement

## Conflict

Artisan should control their legitimate business content, but should not control platform-governance records or remove legitimate customer feedback freely.

## Recommended Resolution

Artisan:

```text
Manage Own Product/Profile
```

Admin:

```text
Moderate Policy Violations
```

Reviews:

Seller cannot arbitrarily remove legitimate negative reviews.

## Decision

**Ownership + Governance Separation**

---

# 10. Conflict CF-08 — Admin Control vs User Workflow Speed

## Admin Perspective

Admin may prefer manual approval for:

- Products
- Users
- Orders
- Updates

## User Perspective

Customers and artisans expect fast workflows.

## Conflict

Excessive approval creates operational bottlenecks.

## Recommended Resolution

Use:

```text
Normal Action
→ User Managed

Exceptional / Risky Action
→ Admin
```

## Decision

**Admin by Exception**

---

# 11. Conflict CF-09 — Platform Trust vs Unsupported Authenticity Claims

## Customer Perspective

Customer may want confidence that a product is genuine.

## Product / Business Perspective

QR and digital records may appear useful for trust.

## Risk

The system may falsely imply:

```text
QR = Guaranteed Authenticity
```

which is not technically justified.

## Recommended Resolution

Use wording such as:

- QR-linked Product Record
- Platform Verification Record

Do not claim:

- Government certification
- Guaranteed physical authenticity

without a real verification process.

## Decision

**Transparent Trust Claims**

---

# 12. Conflict CF-10 — Academic Feature Richness vs Project Feasibility

## Faculty / Academic Perspective

The project should demonstrate sufficient Software Engineering depth.

## Team Perspective

The team may want to add many advanced features to appear impressive.

## Constraint

Academic time and team capacity are limited.

## Conflict

Feature quantity may reduce implementation quality.

## Recommended Resolution

Prioritize features that demonstrate engineering depth:

- RBAC
- Custom-order workflow
- State transitions
- Testing
- Architecture
- Database design
- Traceability

rather than adding:

- Blockchain
- Live chat
- Advanced AI
- Unnecessary integrations

## Decision

**Depth Over Feature Count**

---

# 13. Conflict CF-11 — Faculty Suggestion vs User Evidence

## Scenario

Faculty suggests adding a feature.

Example:

> Add AI chatbot.

## Risk

Faculty has high project influence, but the feature may have weak user value.

## Recommended Process

```text
Suggestion
→ Identify User Problem
→ Check Evidence
→ Analyze Scope
→ Assess Academic Value
→ Approve / Defer / Reject
```

## Decision

Faculty feedback is important, but major features should still pass impact analysis.

---

# 14. Conflict CF-12 — Project Team Preference vs Real User Need

## Scenario

Developers may prefer a technically interesting feature.

Example:

- Blockchain
- AI recommendation
- Real-time chat

## Risk

Development interest becomes mistaken for user need.

## Recommended Resolution

Require:

```text
Problem
+
Evidence
+
Value
+
Feasibility
```

before major scope addition.

## Decision

**Evidence Before Technology**

---

# 15. Conflict CF-13 — Standard Commerce vs Product Differentiation

## Business Perspective

Standard e-commerce features are necessary:

- Products
- Cart
- Checkout
- Orders

## Product Strategy Perspective

These features alone do not differentiate Craft BD.

## Conflict

Too much time spent on generic commerce may reduce effort available for distinctive workflows.

## Recommended Resolution

Treat standard commerce as supporting infrastructure.

Focus product differentiation on validated areas such as:

- Artisan context
- Structured customization
- Product information
- Traceability

## Decision

**Commerce Supports the Product — It Is Not the Entire Product**

---

# 16. Conflict CF-14 — Marketplace Breadth vs MVP Focus

## Possible Business Desire

Support:

- Every handicraft category
- Every seller type
- Events
- Gifts
- Recommendations
- Logistics
- Payments
- Analytics

## MVP Constraint

The project must remain deliverable.

## Recommended Resolution

Focus initial MVP on:

```text
Customer
↕
Artisan
↕
Product
↕
Structured Order Workflow
```

## Decision

**Narrow Initial Scope**

---

# 17. Conflict CF-15 — Real Payment vs Academic Safety

## User Perspective

Real payment makes the system feel complete.

## Project Perspective

Real payment introduces:

- External dependencies
- Security concerns
- Provider setup
- Transaction handling
- Additional testing

## Recommended Resolution

Use simulated payment for the academic MVP.

## Decision

**Real Payment Deferred**

---

# 18. Conflict CF-16 — Recommendation Feature vs Lack of Data

## Product Perspective

Personalized recommendations may appear attractive.

## Technical Reality

The academic MVP has limited:

- User history
- Purchase data
- Behavioral data

## Conflict

Advanced recommendation may be technically weak or artificial.

## Recommended Resolution

Either:

- Defer recommendation

or

- Use simple content-based logic later

## Decision

**Advanced Recommendation Not Core MVP**

---

# 19. Conflict Resolution Criteria

When stakeholder needs conflict, evaluate:

| Criterion | Question |
|---|---|
| User Value | Which option better supports important user goals? |
| Evidence | Which need is better supported? |
| Business Value | Which option supports the product direction? |
| Feasibility | Can it be implemented reliably? |
| Security | Does the decision create risk? |
| Usability | Does it increase unnecessary user effort? |
| Schedule | Can it fit the academic timeline? |
| Maintainability | Can the team support it? |
| Academic Value | Does it support course outcomes? |

---

# 20. Conflict Resolution Workflow

```text
Conflict Identified
       ↓
Identify Stakeholders
       ↓
Identify Underlying Needs
       ↓
Review Evidence
       ↓
Identify Alternatives
       ↓
Analyze Impact
       ↓
Select Option
       ↓
Document Decision
```

For major decisions:

```text
Decision
→ ADR / Requirement Change / Issue
```

as appropriate.

---

# 21. Priority Rule

When priorities conflict, the current recommended order is:

```text
Safety / Legal / Security
        ↓
Core User Need
        ↓
Core Business Workflow
        ↓
Academic Requirement
        ↓
Schedule Feasibility
        ↓
Optional Feature Preference
```

This is a decision guide, not an absolute rule; context must still be reviewed.

---

# 22. Conflict Register Summary

| ID | Conflict | Current Decision |
|---|---|---|
| CF-01 | Customer flexibility vs artisan simplicity | Structured + optional notes |
| CF-02 | Information depth vs fast product entry | Required + optional fields |
| CF-03 | Custom request vs feasibility | Artisan review |
| CF-04 | Speed vs quote confirmation | Approval before production |
| CF-05 | Progress visibility vs admin burden | Minimal meaningful statuses |
| CF-06 | Privacy vs fulfillment | Minimum necessary access |
| CF-07 | Artisan control vs governance | Ownership + moderation separation |
| CF-08 | Admin control vs speed | Admin by exception |
| CF-09 | Trust vs authenticity claim | Transparent platform record |
| CF-10 | Feature richness vs feasibility | Engineering depth |
| CF-11 | Faculty suggestion vs evidence | Impact analysis |
| CF-12 | Developer preference vs user need | Evidence first |
| CF-13 | Commerce vs differentiation | Commerce as support |
| CF-14 | Breadth vs MVP | Narrow scope |
| CF-15 | Real payment vs academic risk | Simulated payment |
| CF-16 | Recommendation vs insufficient data | Defer / simplify |

---

# 23. Most Important Product Conflict

The most important current conflict is:

```text
Customer wants flexibility
        ↕
Artisan wants simplicity
```

Craft BD's current product hypothesis attempts to solve this with:

```text
Structured Customization
+
Clear Quotation
+
Explicit Approval
+
Minimal Status Updates
```

This hypothesis must be tested with real customers and artisans.

---

# 24. Main Project Governance Risk

A major risk is:

> The most powerful stakeholder may dominate requirements even when another stakeholder experiences the actual problem.

Therefore:

```text
Power
≠
Automatic Requirement Priority
```

Requirement priority should combine:

```text
Evidence
+ User Value
+ Feasibility
+ Project Constraints
```

---

# 25. Current Conflict Analysis Decision

No major conflict currently makes Craft BD infeasible.

However, the project should carefully protect:

- User simplicity
- Artisan workload
- Customer privacy
- Role separation
- Scope control
- Honest trust claims
- Evidence-driven prioritization

---

## Document Status

**Phase:** 03 — Stakeholder & User Analysis  
**Document:** Stakeholder Conflict Analysis  
**Status:** Provisional v0.1  
**Primary Research Dependency:** Open  
**Next Step:** Stakeholder-to-Requirement Source Mapping
