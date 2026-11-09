# Craft BD — Stakeholder Goals, Needs & Expectations Analysis

## 1. Purpose

This document analyzes the major Craft BD stakeholders in terms of:

- Goals
- Needs
- Expectations
- Problems
- Desired outcomes
- Potential requirement implications

The analysis supports later requirement engineering, UML modeling, UI/UX design, and system prioritization.

Some needs remain provisional because primary customer and artisan interviews are still pending.

---

# 2. Difference Between Goal, Need, and Expectation

## Goal

What the stakeholder ultimately wants to achieve.

Example:

A customer wants to obtain a suitable handmade product.

## Need

What the stakeholder requires in order to achieve the goal.

Example:

Clear product information and an easy ordering process.

## Expectation

How the stakeholder expects the system to behave.

Example:

The system should clearly show order status.

---

# 3. STK-01 — Customer

## Primary Goal

Discover and obtain suitable Bangladeshi handicraft products with sufficient information and a manageable purchasing experience.

## Secondary Goals

- Understand who made the product
- Learn relevant craft information
- Compare suitable products
- Request customized products
- Know order progress
- Provide feedback after purchase

---

## Customer Needs

### CN-01 — Easy Product Discovery

Customer needs:

- Product catalog
- Categories
- Search
- Filtering
- Product details

### Requirement Implication

The system should provide efficient browsing and search functionality.

---

### CN-02 — Clear Product Information

Customer may need:

- Price
- Materials
- Images
- Description
- Artisan
- Craft type
- Availability

### Requirement Implication

Product information should be structured and easy to understand.

---

### CN-03 — Artisan Context

Customer may want to know:

- Artisan identity
- Location
- Expertise
- Experience
- Related products

### Current Evidence

Partially supported.

Primary validation remains pending.

---

### CN-04 — Simple Purchase Process

Customer expects:

Product  
→ Cart  
→ Checkout  
→ Order Confirmation

The process should not contain unnecessary steps.

---

### CN-05 — Structured Customization

For customized craft products, customers may need a structured way to specify:

- Size
- Color
- Material
- Design
- Quantity
- Reference image
- Instructions

### Current Status

High-priority hypothesis.

Requires real-user validation.

---

### CN-06 — Clear Quotation

Customer should understand:

- Proposed price
- Estimated completion date
- Artisan notes

before approving custom production.

---

### CN-07 — Status Visibility

Customer expects to know:

- Whether a request was received
- Whether quotation is ready
- Whether production has started
- Whether the product has shipped
- Whether the order is complete

---

### CN-08 — Trust

Customer may expect:

- Accurate product information
- Genuine platform records
- Purchase-linked reviews
- Clear artisan identity
- Transparent order information

The system must not make unsupported authenticity guarantees.

---

# 4. Customer Expectations

| ID | Expectation |
|---|---|
| CE-01 | Interface should be easy to understand |
| CE-02 | Product information should be clear |
| CE-03 | Search should return relevant results |
| CE-04 | Cart and checkout should be simple |
| CE-05 | Custom requirements should remain stored correctly |
| CE-06 | Quotation information should be clear |
| CE-07 | Order status should be visible |
| CE-08 | Private information should not be exposed |
| CE-09 | Reviews should be trustworthy |
| CE-10 | Mobile browser experience should remain usable |

---

# 5. STK-02 — Artisan / Craft Seller

## Primary Goal

Showcase products and manage customer orders efficiently without creating excessive digital workload.

## Secondary Goals

- Present professional identity
- Reach customers
- Receive organized custom requests
- Reduce communication confusion
- Provide quotations
- Track active work

---

# 6. Artisan Needs

### AN-01 — Professional Profile

Artisan may need to present:

- Name
- Location
- Expertise
- Experience
- Biography
- Products

---

### AN-02 — Easy Product Management

Artisan should be able to:

- Add product
- Edit product
- Update stock
- Update price
- Upload images
- Deactivate product

The process should remain simple.

---

### AN-03 — Structured Customer Requirements

Instead of receiving incomplete messages such as:

> “এইটার মতো একটা বানিয়ে দেন।”

the system should help capture structured information.

Example:

Design  
+ Size  
+ Material  
+ Quantity  
+ Reference Image  
+ Instructions

---

### AN-04 — Quotation Management

Artisan needs a controlled process to provide:

- Price
- Completion estimate
- Notes

and know whether the customer accepted the quotation.

---

### AN-05 — Work Status Management

Artisan may need to update:

Requested  
→ Approved  
→ In Production  
→ Ready  
→ Shipped

without repeatedly explaining progress manually.

---

### AN-06 — Low Administrative Burden

The system should not require artisans to complete excessive forms or approval steps.

This is particularly important for sellers who currently rely on simple social-media workflows.

---

### AN-07 — Mobile-Friendly Usage

Artisans may frequently access the platform from phones.

Therefore:

Responsive design is an important operational requirement.

---

# 7. Artisan Expectations

| ID | Expectation |
|---|---|
| AE-01 | Dashboard should remain simple |
| AE-02 | Product creation should be quick |
| AE-03 | Custom request information should be complete |
| AE-04 | Customer approval should be clearly visible |
| AE-05 | Order statuses should be easy to update |
| AE-06 | Artisans should only manage their own products/orders |
| AE-07 | Mobile browser usage should work properly |
| AE-08 | System should reduce rather than increase communication effort |

---

# 8. STK-03 — Administrator

## Primary Goal

Maintain safe and organized platform operations.

## Main Needs

Administrator may require:

- User management
- Category management
- Content moderation
- Exceptional account handling
- Verification-related management
- Review moderation
- Platform oversight

---

# 9. Administrator Expectations

| ID | Expectation |
|---|---|
| ADE-01 | Administrative actions must be protected |
| ADE-02 | Roles should be clearly separated |
| ADE-03 | Users should be manageable |
| ADE-04 | Categories should be manageable |
| ADE-05 | Moderation actions should be traceable |
| ADE-06 | Admin workload should remain manageable |

---

# 10. Admin Operational Constraint

Administration should not become a bottleneck.

Avoid:

```text
Every Product
→ Admin Approval

Every Order
→ Admin Approval

Every Update
→ Admin Approval
```

Prefer:

```text
Normal Workflow
→ Automatic / User Managed

Exceptional Case
→ Administrator
```

---

# 11. STK-04 — Project Development Team

## Primary Goal

Deliver a complete, maintainable, testable, and deployable Software Engineering project.

## Main Needs

- Stable requirements
- Clear scope
- Architecture baseline
- Git workflow
- Testable modules
- Documentation
- Reasonable technical complexity

---

# 12. Development Team Expectations

| ID | Expectation |
|---|---|
| DE-01 | Requirements should be traceable |
| DE-02 | Scope changes should be controlled |
| DE-03 | Architecture should remain manageable |
| DE-04 | Code ownership should be clear |
| DE-05 | Pull Requests should be reviewed |
| DE-06 | Core workflows should be testable |
| DE-07 | Secrets should not enter source control |
| DE-08 | Deployment should be reproducible |

---

# 13. STK-05 — Academic Supervisor / Faculty

## Primary Goal

Evaluate whether the project demonstrates appropriate Software Engineering knowledge and process.

## Main Needs

Evidence of:

- Requirement engineering
- Process model selection
- UML
- System design
- Complexity analysis
- Cost estimation
- Testing
- Documentation
- Tool usage
- Working implementation

---

# 14. Faculty Expectations

| ID | Expectation |
|---|---|
| FE-01 | Project scope should be realistic |
| FE-02 | Requirements should be justified |
| FE-03 | UML should align with requirements |
| FE-04 | Implementation should reflect design |
| FE-05 | Testing should be demonstrated |
| FE-06 | Engineering decisions should be explainable |
| FE-07 | Project should demonstrate course outcomes |
| FE-08 | Documentation should remain consistent |

---

# 15. STK-07 — Social-Media-Based Craft Seller

## Primary Goal

Manage customer inquiries and custom requests more systematically than informal chat-only workflows.

## Potential Needs

- Centralized requirements
- Reference images
- Quotation records
- Approval records
- Status management
- Product catalog
- Customer-order history

## Important Research Question

Will this seller actually prefer Craft BD over continuing to use Messenger?

This must be tested rather than assumed.

---

# 16. Regulatory / Compliance Expectations

Relevant regulatory stakeholders may expect the platform to operate responsibly regarding:

- Personal information
- Cybersecurity
- Consumer-facing transactions
- Product information
- User protection

These expectations should be translated into system constraints rather than application screens.

---

# 17. Conflicting Stakeholder Needs

Stakeholder goals may conflict.

## Conflict Example 1

Customer wants:

Maximum flexibility in custom communication.

Artisan wants:

Minimum communication burden.

### Possible Resolution

Use:

Structured requirements  
+ Controlled quotation  
+ Status updates

instead of unlimited real-time communication.

---

## Conflict Example 2

Customer wants:

Detailed artisan/product information.

Artisan wants:

Fast product creation.

### Possible Resolution

Use:

Required essential fields  
+ Optional advanced fields

---

## Conflict Example 3

Admin wants:

Strong control.

Users want:

Fast workflow.

### Possible Resolution

Admin intervenes mainly for exceptional or governance-related operations.

---

# 18. Stakeholder Need → Requirement Traceability

Example:

```text
Customer Need
CN-07 Status Visibility
        ↓
Requirement
System shall display current order status
        ↓
Design
Order Status Component
        ↓
Implementation
Order API + UI
        ↓
Test
Verify customer sees correct status
```

This pattern will later be expanded in requirement traceability.

---

# 19. Core User Value Comparison

## Customer Value

```text
Discover
+
Understand
+
Order
+
Customize
+
Track
```

## Artisan Value

```text
Showcase
+
Receive Structured Request
+
Quote
+
Manage
+
Update
```

## Admin Value

```text
Govern
+
Moderate
+
Protect
```

---

# 20. High-Priority Needs

Current high-priority needs are:

## Customer

- Product discovery
- Clear information
- Simple order process
- Status visibility
- Structured customization*

## Artisan

- Simple product management
- Structured customer requests*
- Quotation management*
- Manageable workflow
- Mobile usability

`*` Requires primary validation.

---

# 21. Needs That Must Not Be Assumed as Validated

The following remain hypotheses:

- Customers strongly value craft stories
- Customers strongly value product journey
- Customers strongly value QR records
- Customers require personalized recommendations
- Artisans strongly prefer Craft BD's custom workflow
- Customers require another general craft marketplace

These must not be represented as validated user findings.

---

# 22. Requirement Engineering Implication

Future requirements should not be written as:

> We want to add feature X.

Instead:

```text
Stakeholder
   ↓
Goal
   ↓
Need / Problem
   ↓
Evidence
   ↓
Requirement
   ↓
Solution
```

---

# 23. Current Analysis Decision

The strongest current product relationship is:

```text
Customer
       ↕
Structured Craft Transaction
       ↕
Artisan
```

Supporting the relationship are:

```text
Product Information
Craft Context
Order Workflow
Status Visibility
Platform Governance
```

The exact importance of custom-order functionality remains subject to primary research.

---

## Document Status

**Phase:** 03 — Stakeholder & User Analysis  
**Document:** Stakeholder Goals, Needs & Expectations  
**Status:** Provisional v0.1  
**Primary Research Dependency:** Open  
**Next Step:** User Segmentation & Persona Baseline
