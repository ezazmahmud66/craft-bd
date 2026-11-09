# Craft BD — Customer & Artisan Journey Baseline

## 1. Purpose

This document defines the current provisional end-to-end journeys for Craft BD's two primary user groups:

- Customer
- Artisan / Craft Seller

The journey baseline helps identify:

- User goals
- User actions
- Pain points
- System touchpoints
- Required information
- Potential features
- Future usability-testing scenarios

These journeys are provisional because primary user interviews are still pending.

---

# 2. Journey Mapping Model

Each journey stage considers:

**User Goal**  
What the user wants to achieve.

**User Action**  
What the user does.

**System Touchpoint**  
Where Craft BD interacts with the user.

**Potential Pain Point**  
What may create difficulty.

**Craft BD Response**  
How the system may reduce that problem.

---

# 3. Customer Journey Overview

The current customer journey is:

```text
Discover
   ↓
Evaluate
   ↓
Select
   ↓
Order / Customize
   ↓
Confirm
   ↓
Track
   ↓
Receive
   ↓
Review
```

There are two major paths:

### Standard Product Path

```text
Product
→ Cart
→ Checkout
→ Order
→ Delivery
→ Review
```

### Custom Product Path

```text
Product / Idea
→ Custom Request
→ Artisan Review
→ Quotation
→ Customer Approval
→ Production
→ Delivery
→ Review
```

---

# 4. Customer Journey Stage 1 — Discover

## User Goal

Find a suitable Bangladeshi handicraft product.

## Possible User Actions

- Visit Craft BD
- Browse products
- Browse categories
- Search
- Apply filters

## System Touchpoints

- Home page
- Product catalog
- Category page
- Search
- Filtering

## Potential Pain Points

- Too many unrelated products
- Poor search results
- Difficult navigation
- Limited product information

## Craft BD Response

Provide:

- Clear categories
- Search
- Relevant filters
- Product images
- Basic product information

---

# 5. Customer Journey Stage 2 — Evaluate

## User Goal

Understand whether the product is suitable.

## User Actions

Customer may review:

- Product images
- Price
- Materials
- Description
- Artisan
- Craft type
- Reviews
- Cultural information

## System Touchpoints

- Product Details
- Artisan Profile
- Craft Information
- Reviews

## Potential Pain Points

- Incomplete product information
- Unknown seller
- Unclear material
- Limited trust indicators

## Craft BD Response

Connect:

```text
Product
+
Artisan
+
Structured Product Information
+
Reviews
```

Optional supporting information may include craft context and product journey.

---

# 6. Customer Journey Stage 3A — Standard Purchase

## User Goal

Purchase the listed product.

## User Actions

```text
Product Details
→ Add to Cart
→ Review Cart
→ Checkout
→ Confirm Order
```

## System Touchpoints

- Cart
- Checkout
- Order Confirmation

## Potential Pain Points

- Incorrect quantity
- Unexpected price
- Confusing checkout
- Missing delivery information

## Craft BD Response

Provide:

- Clear cart summary
- Price breakdown
- Quantity validation
- Order confirmation

---

# 7. Customer Journey Stage 3B — Custom Order

## User Goal

Request a customized product.

## User Actions

Customer provides:

- Product type
- Size
- Color
- Material
- Quantity
- Reference image
- Instructions

## System Touchpoint

Custom Order Request Form

## Potential Pain Points

- User may not know all required specifications
- Requirements may be incomplete
- Too many form fields may become frustrating

## Craft BD Response

Use:

- Structured fields
- Clear labels
- Optional fields where appropriate
- Reference-image upload
- Helpful examples

The form should balance:

```text
Enough Structure
        +
Low User Effort
```

---

# 8. Customer Journey Stage 4 — Wait for Artisan Review

## User Goal

Know that the custom request was received.

## User Actions

- View submitted request
- Wait for artisan response

## System Touchpoints

- Custom Order Details
- Request Status

## Potential Pain Point

Customer may not know whether the artisan has seen the request.

## Craft BD Response

Display status such as:

```text
Request Submitted
→ Under Review
```

---

# 9. Customer Journey Stage 5 — Review Quotation

## User Goal

Understand price and delivery expectation before committing.

## User Actions

Customer reviews:

- Quoted price
- Completion estimate
- Artisan notes

Then:

```text
Approve
or
Reject
```

## System Touchpoint

Quotation Review Page

## Potential Pain Points

- Unclear price
- Unclear completion date
- Customer unsure what was included

## Craft BD Response

Quotation should clearly reference the associated custom requirements.

---

# 10. Customer Journey Stage 6 — Track Production

## User Goal

Know the current state of the order.

## User Actions

View custom-order details.

## System Touchpoint

Order / Custom Order Tracking

## Possible Customer-Facing Status

```text
Approved
→ In Production
→ Quality Check
→ Ready
→ Shipped
→ Delivered
```

## Potential Pain Point

Too many technical statuses may confuse customers.

## Craft BD Response

Use simple user-facing labels even if backend workflow is more detailed.

---

# 11. Customer Journey Stage 7 — Receive Product

## User Goal

Receive the ordered product successfully.

## System Touchpoint

Order Details / Delivery Status

## Potential Pain Points

- Incorrect status
- Product differs from agreed customization
- Delivery issue

## MVP Boundary

Craft BD records delivery-related status.

The MVP does not itself operate physical logistics.

---

# 12. Customer Journey Stage 8 — Review

## User Goal

Provide feedback after purchase.

## User Actions

- Give rating
- Write review

## System Touchpoint

Review Form

## Business Rule

Review should normally require an eligible completed purchase.

## Craft BD Value

This can support future customer decision-making and platform trust.

---

# 13. Customer Journey Summary

| Stage | Customer Goal | Main System Touchpoint | Main Risk |
|---|---|---|---|
| Discover | Find product | Catalog/Search | Poor discovery |
| Evaluate | Understand product | Product/Artisan page | Missing information |
| Purchase | Place standard order | Cart/Checkout | Friction |
| Customize | Explain requirements | Custom form | Complexity |
| Quote | Understand offer | Quotation | Ambiguity |
| Track | Know progress | Order status | Poor visibility |
| Receive | Complete transaction | Order details | Delivery mismatch |
| Review | Give feedback | Review form | Fake/ineligible reviews |

---

# 14. Artisan Journey Overview

The current provisional artisan journey is:

```text
Join
  ↓
Create Profile
  ↓
Add Products
  ↓
Receive Request
  ↓
Review Requirements
  ↓
Provide Quote
  ↓
Receive Approval
  ↓
Produce
  ↓
Update Status
  ↓
Complete Order
```

---

# 15. Artisan Journey Stage 1 — Onboarding

## Artisan Goal

Join Craft BD with minimal difficulty.

## Possible Actions

- Register
- Select artisan role
- Complete profile

## System Touchpoints

- Registration
- Artisan Profile Setup

## Potential Pain Points

- Too many fields
- Complicated verification
- Desktop-only interface

## Craft BD Response

Keep onboarding simple and mobile-friendly.

---

# 16. Artisan Journey Stage 2 — Build Profile

## Artisan Goal

Present professional identity.

## Possible Information

- Name
- Location
- Expertise
- Experience
- Biography
- Profile image

## Potential Pain Point

Artisan may not want to write long content.

## Craft BD Response

Use short structured fields and optional narrative content.

---

# 17. Artisan Journey Stage 3 — Add Product

## Artisan Goal

Publish a product quickly.

## User Actions

Add:

- Name
- Category
- Price
- Stock
- Images
- Description
- Material

## System Touchpoint

Product Management

## Potential Pain Points

- Long forms
- Repetitive data entry
- Image-upload difficulty

## Craft BD Response

Prioritize essential information.

Optional craft-context information should not unnecessarily block product creation.

---

# 18. Artisan Journey Stage 4 — Receive Custom Request

## Artisan Goal

Quickly understand what the customer wants.

## System Touchpoint

Custom Request Dashboard

## Artisan Sees

- Customer requirements
- Quantity
- Design
- Material
- Reference image
- Instructions

## Potential Pain Point

Request may still contain insufficient or conflicting information.

## Craft BD Response

Use validation and structured fields before submission.

---

# 19. Artisan Journey Stage 5 — Review Request

## Artisan Goal

Decide whether the request is feasible.

## Possible Actions

- Review requirements
- Accept for quotation
- Reject request where necessary

## Potential Future Need

Clarification mechanism may eventually be required.

However, real-time chat is not currently part of the MVP.

---

# 20. Artisan Journey Stage 6 — Provide Quotation

## Artisan Goal

Communicate a clear offer.

## Artisan Provides

- Proposed price
- Estimated completion date
- Notes

## System Touchpoint

Quotation Form

## Potential Pain Points

- Incorrect pricing
- Customer misunderstanding
- Quote changes

## Craft BD Response

Store quotation as a clear platform record associated with the request.

---

# 21. Artisan Journey Stage 7 — Receive Customer Decision

## Artisan Goal

Know whether production should begin.

## Expected Rule

```text
Quotation
     ↓
Customer Approval
     ↓
Production Allowed
```

Without approval:

```text
Production should not begin
```

## System Touchpoint

Custom Order Details / Artisan Dashboard

---

# 22. Artisan Journey Stage 8 — Production

## Artisan Goal

Complete the agreed custom product.

## System Role

Craft BD does not manufacture the product.

It records workflow progress.

Possible states:

```text
IN_PRODUCTION
→ QUALITY_CHECK
→ READY_TO_SHIP
```

---

# 23. Artisan Journey Stage 9 — Update Status

## Artisan Goal

Update customer without repeatedly sending messages.

## System Touchpoint

Status Update Action

## Potential Pain Point

Too many status updates may become administrative burden.

## Craft BD Response

Only use meaningful milestones.

Example:

```text
In Production
Ready
Shipped
```

rather than requiring constant micro-updates.

---

# 24. Artisan Journey Stage 10 — Complete Order

## Artisan Goal

Finish the workflow and maintain order history.

## System Touchpoints

- Active Orders
- Completed Orders
- Order Details

## Potential Value

Centralized history may make multiple orders easier to manage.

## Validation Status

Requires artisan research.

---

# 25. Artisan Journey Summary

| Stage | Artisan Goal | Main System Touchpoint | Main Risk |
|---|---|---|---|
| Join | Enter platform | Registration | Difficult onboarding |
| Profile | Present identity | Profile Management | Too much data entry |
| Product | Showcase product | Product Management | Complex form |
| Request | Understand customer | Request Dashboard | Missing information |
| Quote | Propose terms | Quotation | Ambiguity |
| Approval | Confirm order | Order Details | Unclear acceptance |
| Production | Make product | Status Workflow | Admin overhead |
| Update | Inform customer | Status Control | Too many updates |
| Complete | Close order | Order History | Poor organization |

---

# 26. Shared Customer–Artisan Journey

The most important interaction currently appears to be:

```text
CUSTOMER                        ARTISAN

Submit Request
      ───────────────────────→ Receive Request

                              Review Requirements

Receive Quote
      ←─────────────────────── Send Quotation

Approve Quote
      ───────────────────────→ Receive Approval

                              Start Production

View Status
      ←─────────────────────── Update Status

Receive Product
      ←─────────────────────── Complete Order
```

This represents the core provisional Craft BD interaction.

---

# 27. Journey Pain-Point Hotspots

Current highest-risk points are:

## JP-01 — Custom Request Submission

Risk:

Too complicated for customer.

## JP-02 — Requirement Understanding

Risk:

Information still insufficient for artisan.

## JP-03 — Quotation

Risk:

Price/terms unclear.

## JP-04 — Status Management

Risk:

Too much work for artisan.

## JP-05 — Adoption

Risk:

Messenger remains easier than Craft BD.

These should receive special attention during usability testing.

---

# 28. Journey Design Principle

Craft BD should not maximize the number of screens.

It should minimize effort required to complete the user goal.

Therefore:

```text
Fewer Meaningful Steps
>
More Feature-Rich Steps
```

---

# 29. Journey-to-UI Implication

The journey suggests major future screens such as:

## Customer

- Product Catalog
- Product Details
- Artisan Profile
- Cart
- Checkout
- Custom Request
- Quotation Review
- Order Tracking
- Review Form

## Artisan

- Dashboard
- Profile Management
- Product Management
- Custom Request List
- Request Details
- Quotation Form
- Active Orders

These remain provisional until UI/UX design.

---

# 30. Journey-to-UML Implication

The journey will later support:

- Use Case Diagram
- Activity Diagram
- Sequence Diagram
- State Diagram

Example:

```text
Submit Custom Request
→ Review Request
→ Provide Quote
→ Approve Quote
→ Update Production Status
```

can become both an Activity Diagram and Sequence Diagram scenario.

---

# 31. Journey-to-Testing Implication

Future usability and system testing should include complete journeys rather than isolated screens.

Example test scenario:

```text
Customer creates request
→ Artisan receives request
→ Artisan quotes
→ Customer approves
→ Artisan updates status
→ Customer sees correct status
```

This validates the end-to-end business workflow.

---

# 32. Primary Research Validation

Future interviews and usability testing should determine:

- Whether customers understand the custom-order flow
- Whether the request form captures useful information
- Whether artisans can quote easily
- Whether status updates reduce communication effort
- Whether the workflow is preferable to existing methods

---

# 33. Current Journey Decision

The current provisional core journey is:

```text
Discover
→ Understand
→ Request / Order
→ Agree
→ Produce
→ Track
→ Complete
```

For the custom-order experience:

```text
Customer Need
        ↕
Structured Workflow
        ↕
Artisan Action
```

remains the central design hypothesis.

---

## Document Status

**Phase:** 03 — Stakeholder & User Analysis  
**Document:** Customer & Artisan Journey Baseline  
**Status:** Provisional v0.1  
**Primary Research Dependency:** Open  
**Next Step:** Role & Responsibility Matrix
