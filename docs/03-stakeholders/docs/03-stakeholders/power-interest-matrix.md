# Craft BD — Stakeholder Power–Interest Matrix

## 1. Purpose

This document classifies Craft BD stakeholders according to:

- Power / Influence
- Interest in the project

The purpose is to determine:

- Communication priority
- Requirement input priority
- Review frequency
- Decision involvement
- Stakeholder management strategy

The analysis is provisional because primary user research is still pending.

---

# 2. Power–Interest Model

The matrix uses four categories:

## Manage Closely

High Power + High Interest

These stakeholders require frequent communication and active involvement.

## Keep Satisfied

High Power + Lower Direct Interest

These stakeholders should receive sufficient information and must not be ignored.

## Keep Informed

Lower Power + High Interest

These stakeholders should receive regular updates and opportunities to provide feedback.

## Monitor

Lower Power + Lower Interest

These stakeholders require limited communication unless their relevance changes.

---

# 3. Power–Interest Matrix

| Stakeholder | Power | Interest | Classification |
|---|---|---|---|
| Customer | Medium | High | Keep Informed |
| Artisan / Craft Seller | High | High | Manage Closely |
| Administrator | High | High | Manage Closely |
| Project Development Team | Very High | Very High | Manage Closely |
| Academic Supervisor / Faculty | Very High | High | Manage Closely |
| Small Craft Business Owner | Medium | High | Keep Informed |
| Social-Media-Based Craft Seller | Medium | High | Keep Informed |
| Regulatory Authorities | High | Medium | Keep Satisfied |
| Consumer Protection Authorities | Medium–High | Medium | Keep Satisfied |
| Payment Service Provider | Medium | Low for MVP | Monitor |
| Logistics / Courier Partner | Medium | Low for MVP | Monitor |
| External Certification Organization | High Potential Power | Low Current Interest | Keep Satisfied / Monitor |

---

# 4. Manage Closely

## STK-02 — Artisan / Craft Seller

### Why

Artisans are one of the primary value providers of Craft BD.

The success of several major workflows depends on artisan participation.

Examples:

- Product management
- Artisan profile
- Custom-order handling
- Quotation
- Production status

### Management Strategy

- Include in requirement validation
- Test usability with artisan users
- Validate custom-order workflow
- Minimize unnecessary complexity
- Collect regular feedback

---

## STK-03 — Administrator

### Why

The administrator has significant control over:

- User management
- Categories
- Moderation
- Verification-related actions
- Platform governance

Poor admin design may affect the entire platform.

### Management Strategy

- Define clear permissions
- Avoid excessive manual workload
- Validate administrative workflows
- Define governance responsibilities

---

## STK-04 — Project Development Team

### Why

The development team controls:

- Technical design
- Scope implementation
- Architecture
- Testing
- Documentation
- Deployment

### Risk

The team may unintentionally prioritize technically interesting features over real user problems.

### Management Strategy

- Use evidence-driven decisions
- Maintain GitHub traceability
- Review scope regularly
- Separate assumptions from validated requirements

---

## STK-05 — Academic Supervisor / Faculty

### Why

The supervisor has very high influence over:

- Academic acceptance
- Project direction
- Evaluation
- Course requirements
- Deliverable expectations

### Management Strategy

- Provide milestone updates
- Maintain clear documentation
- Demonstrate Software Engineering process
- Record important faculty feedback
- Convert major feedback into GitHub issues or requirement changes where appropriate

---

# 5. Keep Informed

## STK-01 — Customer

### Why

Customers have very high product interest but less direct project-control power.

However, their feedback is essential for validating whether the system solves a real problem.

### Management Strategy

- Conduct interviews
- Perform usability testing
- Validate discovery and custom-order workflows
- Gather feedback before finalizing requirements

Important:

Low formal project power does not mean low product importance.

Customer evidence should strongly influence product decisions.

---

## STK-06 — Small Craft Business Owner

### Why

Small workshop or business owners may represent a seller segment with different needs from individual artisans.

Potential requirements include:

- Multiple products
- Inventory management
- Order organization
- Business identity

### Management Strategy

Include in user research if the project targets this segment.

---

## STK-07 — Social-Media-Based Craft Seller

### Why

This segment is especially important for validating the custom-order problem.

They may currently use:

Social Media  
→ Messenger  
→ Manual Requirement Collection  
→ Manual Quotation  
→ Manual Status Updates

### Management Strategy

- Prioritize interviews
- Understand existing workflow
- Identify real communication problems
- Compare Craft BD workflow against their current process

---

# 6. Keep Satisfied

## STK-08 — Regulatory Authorities

### Why

They may have high influence through:

- Data-protection requirements
- Cybersecurity requirements
- Digital-commerce rules

However, they are not direct users of the MVP.

### Management Strategy

- Monitor applicable laws
- Maintain privacy/security requirements
- Avoid unsupported compliance claims
- Review before real commercial deployment

---

## STK-09 — Consumer Protection Authorities

### Why

Consumer-facing commercial systems may be influenced by consumer-protection requirements.

### Management Strategy

Ensure:

- Accurate product information
- Transparent transactions
- Clear customer communication
- Appropriate complaint handling where required

---

## STK-12 — External Certification Organization

### Current Position

Not a core MVP dependency.

### Potential Future Influence

High if Craft BD later claims externally recognized product certification.

### Management Strategy

Do not create dependency until future certification scope is approved.

---

# 7. Monitor

## STK-10 — Payment Service Provider

Current MVP uses simulated payment.

Therefore, the provider currently has limited influence on core project development.

### Management Strategy

Monitor only if real payment integration becomes approved scope.

---

## STK-11 — Logistics / Courier Partner

The MVP does not require external logistics integration.

### Management Strategy

Monitor as future scope.

Internal shipping statuses are sufficient for the initial version.

---

# 8. Visual Matrix

```text
                         HIGH POWER
                             ↑
                             │
     KEEP SATISFIED          │          MANAGE CLOSELY
                             │
 Regulatory Authorities     │  Artisan / Seller
 Consumer Protection        │  Administrator
 Certification Body*        │  Project Team
                             │  Academic Supervisor
                             │
─────────────────────────────┼─────────────────────────────→
                             │                      INTEREST
                             │
        MONITOR              │          KEEP INFORMED
                             │
 Payment Provider           │  Customer
 Logistics Partner          │  Small Craft Business
                             │  Social-Media Seller
                             │
                             ↓
                          LOW POWER
```

`*` External certification authority is future-scope dependent.

---

# 9. Important Interpretation

The matrix should not be interpreted as:

High Power = More Important User

For example:

Customer  
→ Medium Project Power  
→ Very High Product Importance

Academic Supervisor  
→ Very High Project Power  
→ Not a primary product user

Therefore two different concepts must remain separate:

**Stakeholder Influence**

and

**User Value**

---

# 10. Requirement Priority Implication

Requirement decisions should consider both:

```text
Stakeholder Influence
        +
User Evidence
        +
Business Value
        +
Technical Feasibility
```

No stakeholder should automatically receive every requested feature.

---

# 11. Communication Strategy

| Stakeholder | Communication Strategy |
|---|---|
| Customer | Interviews, usability testing, feedback |
| Artisan | Interviews, workflow validation, usability testing |
| Administrator | Workflow review |
| Project Team | Frequent GitHub collaboration |
| Faculty | Milestone review and academic feedback |
| Regulatory Bodies | Compliance monitoring |
| External Providers | Integration-specific communication if required |

---

# 12. Decision Escalation

If stakeholder requirements conflict:

```text
Conflict
   ↓
Identify Stakeholders
   ↓
Identify User / Business Value
   ↓
Review Evidence
   ↓
Analyze Technical Impact
   ↓
Review Scope
   ↓
Document Decision
```

High stakeholder power alone should not automatically determine product functionality.

---

# 13. Example Conflict

Suppose:

Customer requests:

> Direct chat with artisan.

Artisan requests:

> Fewer messages and less communication workload.

Possible conflict:

Customer  
→ Wants flexibility

Artisan  
→ Wants structure

Instead of automatically adding live chat:

Analyze:

Current Problem  
→ Communication confusion

Possible Solution  
→ Structured Custom Request + Quotation + Status

Therefore, the solution may satisfy both stakeholders without implementing live chat.

---

# 14. Project Management Priority

Current stakeholder-management priority:

## Critical

1. Project Team
2. Academic Supervisor
3. Artisan / Seller
4. Customer

## High

5. Administrator
6. Social-Media-Based Seller

## Medium

7. Small Craft Business
8. Regulatory / Consumer-Protection considerations

## Future

9. Payment Provider
10. Logistics Provider
11. External Certification Organization

---

# 15. Current Research Priority

Primary research should prioritize:

```text
Customer
   +
Individual Artisan
   +
Social-Media-Based Craft Seller
```

Reason:

These groups provide the strongest evidence for validating the current Craft BD problem hypotheses.

---

# 16. Main Stakeholder Risk

A major project risk is:

> High-power internal stakeholders may influence product decisions more strongly than actual user evidence.

Examples:

- Project team prefers technically impressive feature
- Faculty suggests additional functionality
- Users may not actually need it

Mitigation:

```text
Suggestion
   ↓
Problem Evidence
   ↓
Requirement Analysis
   ↓
Scope Impact
   ↓
Decision
```

---

# 17. Power–Interest Decision

The most closely managed stakeholders are:

- Artisan / Seller
- Administrator
- Project Team
- Academic Supervisor

Customers remain a critical research and feedback stakeholder even though they have less formal project power.

External providers should remain outside core MVP decision-making unless their integrations become approved scope.

---

## Document Status

**Phase:** 03 — Stakeholder & User Analysis  
**Document:** Stakeholder Power–Interest Matrix  
**Status:** Provisional v0.1  
**Primary Research Dependency:** Open  
**Next Step:** Stakeholder Goals & Expectations Analysis
