# Craft BD — Problem Validation Matrix

## 1. Purpose

This document identifies the current problem hypotheses behind Craft BD and defines how each hypothesis should be validated before it becomes a confirmed product requirement.

The purpose is to prevent the project from implementing features based only on assumptions.

---

# 2. Validation Principle

Craft BD will follow this decision flow:

Problem Hypothesis  
→ Existing Evidence  
→ User Research  
→ Validation Result  
→ Product Decision  
→ Requirement

A proposed feature should not automatically become an MVP requirement unless it solves a validated or strategically necessary problem.

---

# 3. Problem Validation Matrix

| ID | Problem Hypothesis | Current Evidence | Validation Needed | Possible Product Response | Current Status |
|---|---|---|---|---|---|
| PH-01 | Some customers want more information about the artisan behind a handmade product | Existing craft platforms already present maker information, suggesting relevance | Ask customers whether artisan identity affects trust or purchase decisions | Artisan profile | Unvalidated |
| PH-02 | Customers may value cultural context such as origin, history, materials, and techniques | Cultural storytelling is relevant to handicrafts, but user demand is not yet confirmed | Ask customers what information they want before buying a craft | Craft story | Unvalidated |
| PH-03 | Customers may want to understand how handmade products are produced | Current Craft BD concept includes product journey, but direct demand evidence is limited | Test whether production stages influence interest, trust, or purchase decisions | Product-making journey | Unvalidated |
| PH-04 | Custom craft orders may be difficult to manage through informal messaging | Social-commerce sellers often rely on direct communication, but workflow problems must be confirmed | Interview customers and artisans who have experience with custom orders | Structured custom-order workflow | High-priority hypothesis |
| PH-05 | Artisans may repeatedly communicate the same custom requirements such as size, material, design, and quantity | Plausible workflow issue, but not yet directly evidenced | Ask artisans how they currently record and confirm custom requirements | Custom request form | High-priority hypothesis |
| PH-06 | Customers may have difficulty knowing the status of a custom order | Current requirement includes order tracking, but custom-order status need is unverified | Ask users how status is currently communicated | Custom-order status tracking | Unvalidated |
| PH-07 | Customers may want more trustworthy product information | Trust is important in commerce, but specific concerns around handicrafts require research | Ask what information makes customers trust handmade products | Product record / certificate | Unvalidated |
| PH-08 | QR-linked information may improve access to product and artisan records | Technically feasible, but customer value is not confirmed | Ask whether customers would scan and use QR-linked craft information | QR-linked product record | Unvalidated |
| PH-09 | Artisans may struggle to present their craft, expertise, and story consistently | Some marketplaces already provide structured maker profiles | Ask artisans how they currently present themselves and what is difficult | Structured artisan profile | Partially supported |
| PH-10 | Customers may need personalized craft recommendations | Recommendation was included in the initial concept, but no strong problem evidence exists | Ask whether users experience difficulty finding relevant products | Recommendation system | Low-priority / weak evidence |
| PH-11 | Gift buyers may need occasion- and budget-based craft discovery | Plausible but secondary to the current product direction | Interview potential gift buyers | Gift recommendation | Low-priority hypothesis |
| PH-12 | Customers need another general handicraft marketplace | Existing platforms already provide online handicraft shopping | No further validation required for the claim itself | Do not use this as Craft BD's core problem | Rejected as core problem |

---

# 4. High-Priority Hypotheses

The following should receive the most attention during primary research.

## PH-04 — Custom Order Coordination

Possible problem:

Customer requirements may be exchanged through multiple unstructured messages.

Potential consequences may include:

- Missing requirements
- Repeated clarification
- Incorrect size, color, material, or design
- Price misunderstanding
- Approval confusion
- Difficulty tracking production status

These consequences are hypotheses and must be confirmed through interviews.

---

## PH-05 — Artisan Requirement Management

Possible problem:

Artisans may not have a structured method for recording:

- Customer specifications
- Reference images
- Quantity
- Materials
- Quotation
- Approval
- Production status

If validated, this could justify the structured custom-order module.

---

## PH-02 — Craft Context

Possible problem:

A standard product listing may not provide enough information for customers who care about:

- Craft origin
- Artisan background
- Materials
- Techniques
- Cultural meaning

If users do not value this information, Craft BD should reduce the scope of this capability.

---

## PH-07 — Product Information Trust

Possible problem:

Customers may want more confidence in the product information provided by a craft seller.

Possible information may include:

- Artisan identity
- Region
- Materials
- Craft type
- Production information
- Certificate record

The project must avoid confusing platform-maintained information with guaranteed physical authenticity.

---

# 5. Feature Validation Map

| Proposed Feature | Problem It Should Solve | Evidence Strength | MVP Decision Today |
|---|---|---|---|
| Product catalog | Basic product discovery | Strong / standard commerce need | Keep as supporting feature |
| Artisan profile | Limited structured artisan representation | Medium | Likely keep |
| Craft story | Missing cultural context | Low–Medium | Validate |
| Product journey | Limited production visibility | Low | Validate |
| Custom request form | Unstructured customization | Medium hypothesis | Validate with high priority |
| Artisan quotation | Informal price negotiation | Medium hypothesis | Validate with high priority |
| Custom-order status | Poor status communication | Low–Medium | Validate |
| QR product record | Easier access to product information | Low | Validate |
| Digital certificate | Structured verification information | Low | Validate carefully |
| Recommendation | Product discovery difficulty | Low | Future unless validated |
| Gift recommendation | Gift selection difficulty | Low | Future |
| Reviews | Customer feedback/trust | Strong standard requirement | Supporting feature |
| Cart / Checkout | Purchase workflow | Strong standard requirement | Supporting feature |

---

# 6. Validation Decision Rules

After interviews, each hypothesis should receive one of four statuses:

## VALIDATED

Multiple users describe the problem independently and indicate meaningful impact.

Action:

→ Keep or prioritize related feature.

---

## PARTIALLY VALIDATED

The problem exists but only for some users or in limited situations.

Action:

→ Narrow the feature or target segment.

---

## NOT VALIDATED

Users do not experience the problem or do not consider it important.

Action:

→ Remove from MVP or move to future scope.

---

## INCONCLUSIVE

Research sample or evidence is insufficient.

Action:

→ Conduct additional research before making a decision.

---

# 7. Example Validation

Example:

Hypothesis:

> Custom-order requirements are difficult to manage through informal messaging.

Interview results:

Customer 1 → repeated size clarification  
Customer 2 → price changed after discussion  
Artisan 1 → lost reference image in Messenger chat  
Artisan 2 → manually records orders in notebook  

Possible result:

**VALIDATED**

Possible requirement:

> The system shall provide a structured custom-order request containing design, size, material, quantity, reference image, and instructions.

---

# 8. Important Product Rule

A feature should not exist simply because:

- It looks modern
- A competitor has it
- It uses AI
- It looks impressive in a presentation
- It was included in an early idea

The preferred rule is:

**Validated User Problem → Appropriate Software Solution**

---

# 9. Current Risk

The largest discovery risk for Craft BD is:

> The project may contain many attractive features without proving that users experience the problems those features are intended to solve.

Primary user research is therefore required before final MVP scope and SRS approval.

---

# 10. Current Discovery Position

At this point:

## Strongly Supported

- Handicraft market exists
- Digital handicraft commerce already exists
- Existing platforms support artisan/maker representation
- Generic e-commerce alone is not sufficient differentiation

## Requires Validation

- Detailed cultural storytelling
- Production journey
- Structured custom orders
- Product verification records
- QR usage
- Digital certificates
- Recommendation features

---

## Document Status

**Status:** Validation Planning Draft  
**Phase:** Phase 01 — Product Discovery & Problem Definition  
**Next Step:** Primary User Research Design
