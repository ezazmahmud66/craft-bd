# Craft BD — Discovery Assumptions & Risk Register

## 1. Purpose

This document records the major assumptions, uncertainties, and product risks identified during Phase 01 — Product Discovery & Problem Definition.

The objective is to ensure that Craft BD does not treat unverified assumptions as confirmed requirements.

---

# 2. Discovery Principle

The project will distinguish between:

**Known Evidence**  
→ supported by research

**Assumption**  
→ believed to be true but not yet validated

**Risk**  
→ something that may negatively affect the product, users, development, or academic outcome

---

# 3. Key Product Assumptions

| ID | Assumption | Current Evidence | Validation Method | Status |
|---|---|---|---|---|
| AS-01 | Customers care about artisan identity | Partial | Customer interviews | Open |
| AS-02 | Customers value cultural information about crafts | Partial | Customer interviews | Open |
| AS-03 | Customers value production journey information | Limited | Customer interviews / prototype testing | Open |
| AS-04 | Custom-order communication is difficult | Limited | Customer + artisan interviews | High Priority |
| AS-05 | Artisans need structured custom-order management | Limited | Artisan interviews | High Priority |
| AS-06 | Customers want custom-order progress visibility | Limited | Customer interviews | Open |
| AS-07 | Product-information trust is a meaningful concern | Partial | Interviews | Open |
| AS-08 | QR-linked product information provides useful value | Partial | Interviews + usability testing | Open |
| AS-09 | Digital certificates increase customer confidence | Limited | Customer testing | Open |
| AS-10 | Personalized recommendations are necessary | Weak | User research | Low Priority |
| AS-11 | Gift recommendations solve an important problem | Weak | User research | Low Priority |

---

# 4. Product Risks

## R-01 — Generic E-Commerce Risk

### Description

Craft BD may become too similar to existing online marketplaces.

### Impact

High

### Probability

Medium

### Mitigation

Focus the product around validated craft-specific problems rather than generic commerce features.

---

## R-02 — Feature Overload

### Description

The original concept contains many features:

- Marketplace
- Artisan profiles
- Craft stories
- Production journeys
- QR records
- Digital certificates
- Recommendations
- Gift recommendations
- Custom orders
- Reviews
- Events

Trying to implement everything may reduce overall product quality.

### Impact

High

### Probability

High

### Mitigation

Define a strict MVP after problem validation.

---

## R-03 — Unvalidated Custom-Order Problem

### Description

The structured custom-order workflow may become a major part of Craft BD even though direct user evidence is still missing.

### Impact

High

### Probability

Medium

### Mitigation

Interview real customers and artisans before making this a mandatory MVP feature.

---

## R-04 — False Authenticity Claims

### Description

Users may incorrectly interpret QR codes or digital certificates as proof that a physical product is genuine.

### Impact

High

### Probability

Medium

### Mitigation

Treat QR as access to a platform-maintained product record unless a reliable physical verification mechanism is implemented.

Never claim:

> QR = guaranteed physical authenticity

---

## R-05 — Recommendation Without Data

### Description

Personalized recommendations require meaningful user behavior or preference data.

An academic MVP may not have sufficient data.

### Impact

Medium

### Probability

High

### Mitigation

Keep advanced personalization outside the initial MVP.

If required later, begin with simple content-based recommendations.

---

## R-06 — Artisan Usability Risk

### Description

Some target artisans may have limited experience using complex digital dashboards.

### Impact

High

### Probability

Medium

### Mitigation

Use:

- Simple forms
- Mobile-friendly interfaces
- Clear language
- Minimal workflow steps
- Usability testing with seller-like users

---

## R-07 — Scope Expansion

### Description

New ideas may continually be added during development.

Examples:

- Live chat
- Advanced analytics
- AI chatbot
- Blockchain certificates
- Logistics integration
- Advanced recommendation engine

### Impact

High

### Probability

High

### Mitigation

Every major scope change must follow:

Change Request  
→ Impact Analysis  
→ Approval  
→ Requirement Update  
→ Implementation

---

## R-08 — Academic Time Constraint

### Description

The semester timeline may not allow production-quality implementation of every planned feature.

### Impact

High

### Probability

High

### Mitigation

Prioritize:

1. Core validated workflow
2. Correct system design
3. Testing
4. Documentation
5. Deployment

before optional features.

---

## R-09 — Weak Real User Research

### Description

The product may be designed mainly from assumptions if the team does not interview actual users.

### Impact

High

### Probability

Medium

### Mitigation

Conduct a minimum exploratory pilot involving:

- At least 3 real customers
- At least 2 real artisans / craft sellers

Synthetic interviews must never be counted as real research.

---

## R-10 — Sensitive Data Risk

### Description

The project may unnecessarily collect personal information about customers or artisans.

### Impact

Medium

### Probability

Medium

### Mitigation

Collect only data required for the product.

Avoid unnecessary:

- National ID
- Financial credentials
- Sensitive personal information
- Private participant information

---

# 5. Technical Risks

| ID | Technical Risk | Impact | Current Response |
|---|---|---|---|
| TR-01 | Architecture becomes overly complex | High | Prefer modular monolith |
| TR-02 | Team members create inconsistent code | Medium | Code review + contribution rules |
| TR-03 | Authorization bugs expose another user's data | High | Server-side RBAC |
| TR-04 | Secrets are committed to GitHub | High | `.gitignore` + security policy |
| TR-05 | Database design cannot support custom workflow | High | Design state model before implementation |
| TR-06 | QR links become predictable or unsafe | Medium | Unique verification identifiers |
| TR-07 | File-upload functionality introduces security issues | Medium | File validation and restrictions |
| TR-08 | Features are implemented without tests | High | Definition of Done + test requirements |

---

# 6. Business / Product Risks

| ID | Risk | Impact |
|---|---|---|
| BR-01 | Existing platforms already satisfy most customer needs | High |
| BR-02 | Customers may not care enough about craft stories | Medium |
| BR-03 | Artisans may prefer Messenger over a separate system | High |
| BR-04 | Customers may not scan QR codes | Medium |
| BR-05 | Artisan onboarding may require significant effort | Medium |
| BR-06 | Craft BD may lack enough products to make recommendation useful | Medium |

---

# 7. Academic Project Risks

| Risk | Response |
|---|---|
| Too much implementation, weak SE documentation | Prioritize requirements, UML, testing and traceability |
| Project appears to be ordinary e-commerce | Clearly show validated craft-specific workflows |
| Unsupported claims during presentation | Separate evidence from assumptions |
| Incomplete testing | Maintain test cases throughout development |
| Team contribution is unclear | Track Issues, branches, PRs and commits |
| Faculty changes requirements | Use Requirement Change process |

---

# 8. Risk Priority

Current highest-priority risks are:

### Priority 1
Feature overload

### Priority 2
Generic e-commerce positioning

### Priority 3
Unvalidated custom-order problem

### Priority 4
Weak real-user validation

### Priority 5
Academic timeline / scope

---

# 9. Risk Response Strategy

Craft BD will follow:

Risk Identified  
→ Assess Probability  
→ Assess Impact  
→ Define Mitigation  
→ Assign Owner  
→ Monitor  
→ Update Decision

---

# 10. Discovery Decision Rules

The team should not add a major feature simply because:

- It appears innovative
- It uses AI
- A competitor has it
- It looks impressive
- It was included in the original concept

A major feature should preferably have:

**Validated Problem  
+ Clear Target User  
+ Meaningful Benefit  
+ Technical Feasibility  
+ Acceptable Project Cost**

---

# 11. Current Risk Summary

The most important product risk is not technical.

It is:

> Building a large number of features before confirming which user problems are important.

Therefore, Craft BD should remain problem-driven rather than feature-driven.

---

## Document Status

**Status:** Active Discovery Risk Register  
**Phase:** Phase 01 — Product Discovery & Problem Definition  
**Review Again:** After primary user research and before MVP scope finalization
