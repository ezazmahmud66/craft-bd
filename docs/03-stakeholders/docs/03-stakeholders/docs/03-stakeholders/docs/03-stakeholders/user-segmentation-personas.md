# Craft BD — User Segmentation & Persona Baseline

## 1. Purpose

This document defines the current user segments and provisional personas for Craft BD.

The objectives are to:

- Avoid treating all customers as identical
- Avoid treating all artisans as identical
- Identify priority MVP users
- Support requirement prioritization
- Support UI/UX design
- Support later usability testing
- Identify assumptions that require primary research

The personas in this document are **provisional and synthetic research artifacts**.

They are not representations of completed real-user interviews.

---

# 2. Why User Segmentation Is Required

A generic statement such as:

> "Our user is a customer."

is not sufficient for product design.

Different customers may have different goals.

Example:

```text
Customer A
→ Wants a culturally meaningful handmade product

Customer B
→ Wants a customized wedding gift

Customer C
→ Mainly wants confidence before purchasing
```

Similarly:

```text
Artisan A
→ Individual craft maker

Artisan B
→ Facebook-based seller

Artisan C
→ Small workshop/business owner
```

Their workflows may differ.

---

# 3. Customer Segments

Current Craft BD customer segmentation includes:

| ID | Segment | Main Goal | Current Priority |
|---|---|---|---|
| C1 | Cultural Craft Explorer | Discover meaningful Bangladeshi crafts | High |
| C2 | Custom Craft Buyer | Order a product with specific requirements | Very High |
| C3 | Gift Buyer | Find suitable handmade gifts | Low / Future |
| C4 | Trust-Conscious Buyer | Understand seller/product before purchase | Medium |

---

# 4. C1 — Cultural Craft Explorer

## Description

A customer interested not only in the product itself, but also in:

- Artisan identity
- Craft origin
- Material
- Production technique
- Cultural significance

## Main Goal

Find a handicraft product with meaningful cultural or artisan context.

## Potential Needs

- Product search
- Product categories
- Artisan profile
- Craft story
- Product materials
- Region / origin
- Product images

## Potential Pain Points

- Generic listings provide little cultural information
- Difficult to understand who made the product
- Product story may be separated from the product listing

## Current Evidence Status

**Partially supported**

Primary validation required.

---

# 5. C2 — Custom Craft Buyer

## Description

A customer who wants a handmade product with specific requirements.

Examples may include:

- Customized home decoration
- Personalized gift
- Specific size
- Specific color
- Specific material
- Modified design

## Main Goal

Communicate requirements clearly and receive the expected custom product.

## Potential Needs

- Structured requirement form
- Reference-image upload
- Quotation
- Estimated completion date
- Approval mechanism
- Production-status visibility

## Potential Pain Points

Possible current problems include:

- Requirements spread across chat messages
- Missing specifications
- Price misunderstanding
- No clear approval record
- Repeated status questions

## Current Evidence Status

**High-priority hypothesis**

Requires direct customer validation.

---

# 6. C3 — Gift Buyer

## Description

A customer looking for a craft product for:

- Birthday
- Wedding
- Anniversary
- Corporate gift
- Festival

## Potential Needs

- Occasion filtering
- Budget filtering
- Gift categories
- Recommendation

## Current Priority

**Low / Future**

Reason:

Gift recommendation is not currently a core validated Craft BD problem.

---

# 7. C4 — Trust-Conscious Buyer

## Description

A customer who wants additional confidence before completing an online purchase.

## Potential Needs

- Clear seller information
- Reviews
- Product details
- Order history
- Product record
- Certificate information where appropriate

## Potential Pain Points

- Limited seller information
- Unclear product details
- Difficulty evaluating credibility
- Concern regarding misleading information

## Current Priority

Medium.

---

# 8. Customer Segment Priority

Current MVP priority:

```text
C2 — Custom Craft Buyer
        +
C1 — Cultural Craft Explorer
```

Supporting:

```text
C4 — Trust-Conscious Buyer
```

Future:

```text
C3 — Gift Buyer
```

This priority must be reviewed after primary interviews.

---

# 9. Artisan / Seller Segments

Current seller-side segmentation includes:

| ID | Segment | Description | Priority |
|---|---|---|---|
| A1 | Individual Artisan | Personally produces craft products | Very High |
| A2 | Small Craft Business | Small workshop/business managing products | Medium |
| A3 | Social-Media-Based Seller | Uses Facebook/Messenger or similar channels | Very High |

---

# 10. A1 — Individual Artisan

## Description

An artisan who personally creates and sells handicraft products.

## Main Goals

- Showcase work
- Present expertise
- Receive orders
- Manage custom requests
- Reduce communication confusion

## Potential Needs

- Simple artisan profile
- Easy product upload
- Custom-request management
- Quotation
- Order-status update
- Mobile-friendly dashboard

## Potential Pain Points

- Limited time for administrative tasks
- Repetitive customer questions
- Incomplete custom requirements
- Multiple conversations to track

## Current Priority

**Very High**

---

# 11. A2 — Small Craft Business / Workshop

## Description

A small business or workshop selling products created by one or more craft workers.

## Potential Goals

- Manage multiple products
- Present business identity
- Receive customer orders
- Organize custom requests

## Potential Needs

- Product management
- Order management
- Stock information
- Seller profile

## Possible Future Difference

This segment may eventually require:

- Multiple staff accounts
- More advanced inventory management
- Analytics

These are not required for the current MVP.

## Priority

Medium.

---

# 12. A3 — Social-Media-Based Craft Seller

## Description

A seller who currently receives orders or inquiries through platforms such as Facebook and Messenger.

## Main Goal

Manage customer requests without losing the simplicity of current social-media communication.

## Potential Needs

- Structured custom request
- Reference image
- Quotation
- Approval record
- Customer-order status
- Centralized order information

## Main Adoption Question

> Is Craft BD easier and more useful than simply continuing the conversation through Messenger?

If the answer is no, the proposed workflow may fail regardless of technical quality.

## Current Priority

**Very High**

This segment is especially important for primary research.

---

# 13. Priority Artisan Segments

Current MVP research focus:

```text
A1 — Individual Artisan
        +
A3 — Social-Media-Based Craft Seller
```

Secondary:

```text
A2 — Small Craft Business
```

---

# 14. Persona Design Rule

Personas must not contain fake claims such as:

> "Eight out of ten artisans said..."

unless real research actually produced that result.

Current personas therefore use wording such as:

- May
- Potentially
- Hypothesis
- Needs validation
- Assumed behavior

---

# 15. Provisional Persona P01 — Custom Craft Buyer

## Persona Type

Synthetic / Provisional

## Name

**Nadia Rahman**

Name is fictional and used only to make the persona easier to discuss.

## Approximate Profile

Age: 24–32  
Location: Urban Bangladesh  
Device: Smartphone-first  
Digital familiarity: Moderate–High

## Scenario

Nadia wants a customized handmade decorative product for a special occasion.

She finds a product close to what she wants but needs:

- Different size
- Different color
- Small design modification

## Goal

Order the customized product without repeatedly explaining requirements.

## Possible Current Behavior

```text
Find Seller
→ Send Message
→ Send Reference Image
→ Explain Size
→ Discuss Price
→ Clarify Requirements Again
→ Ask for Progress
```

## Potential Pain Points

- Requirements may become scattered
- Important details may be forgotten
- Quotation may not be clearly recorded
- Production progress may be unclear

## Craft BD Opportunity

```text
Structured Request
→ Quote
→ Approval
→ Production Status
→ Delivery
```

## Important Validation Status

This persona reflects the current product hypothesis.

It is **not evidence that real customers currently behave exactly this way**.

---

# 16. P01 User Story Direction

Potential future user story:

> As a customer, I want to submit my custom-product requirements in a structured form so that the artisan can clearly understand what I want.

This should become a formal requirement only after appropriate requirement review.

---

# 17. Provisional Persona P02 — Cultural Craft Explorer

## Persona Type

Synthetic / Provisional

## Name

**Farhan Ahmed**

## Approximate Profile

Age: 22–35  
Device: Smartphone and laptop  
Digital familiarity: High

## Scenario

Farhan wants to purchase a Bangladeshi handicraft but is interested in more than appearance and price.

He may want to know:

- Where the craft comes from
- Who made it
- What material was used
- How it is traditionally produced

## Goal

Discover a craft product with meaningful information.

## Potential Pain Points

- Product pages may provide only price and basic description
- Artisan identity may be difficult to understand
- Cultural information may be fragmented

## Craft BD Opportunity

```text
Product
+
Artisan
+
Craft Context
```

## Validation Status

Partially supported but still requires primary customer validation.

---

# 18. Provisional Persona P03 — Individual Artisan

## Persona Type

Synthetic / Provisional

## Name

**Shapla Akter**

## Approximate Profile

Occupation: Handicraft artisan  
Device: Smartphone-first  
Digital familiarity: Basic–Moderate

## Scenario

Shapla produces handmade craft products and communicates with customers through social media and messaging.

## Goals

- Showcase products
- Receive customer orders
- Understand custom requirements clearly
- Avoid excessive administrative work

## Potential Pain Points

- Repeated customer questions
- Requirement details scattered through messages
- Difficulty tracking several custom requests
- Repeated progress inquiries

## Craft BD Opportunity

```text
Simple Dashboard
+
Structured Requests
+
Quotation
+
Status Update
```

## Critical UX Requirement

Craft BD must not require Shapla to perform more work than her existing process without providing clear value.

---

# 19. Provisional Persona P04 — Social-Media Seller

## Persona Type

Synthetic / Provisional

## Name

**Rafiul Hasan**

## Approximate Profile

Role: Small online craft seller  
Current channel: Facebook / Messenger  
Device: Smartphone  
Digital familiarity: Moderate

## Scenario

Rafiul publishes products on social media and receives multiple customer messages.

Custom-order discussions may include:

- Product photo
- Price
- Color
- Size
- Delivery date
- Reference image

## Goal

Organize customer requests while maintaining a fast sales workflow.

## Potential Pain Points

- Conversation history becomes difficult to manage
- Requirements are not standardized
- Multiple active customers may become confusing
- Quotation and approval information may be informal

## Craft BD Opportunity

```text
Request Dashboard
→ Requirement Details
→ Quote
→ Approval
→ Active Order
```

## Major Adoption Risk

If creating and managing the request requires too many steps:

```text
Craft BD
> Messenger effort
```

the seller may reject the platform.

Therefore, usability is critical.

---

# 20. Persona Comparison

| Area | P01 Custom Buyer | P02 Craft Explorer | P03 Artisan | P04 Social Seller |
|---|---|---|---|---|
| Product Search | High | Very High | Low | Medium |
| Artisan Information | Medium | High | High | Medium |
| Craft Story | Medium | High | Medium | Low |
| Custom Order | Very High | Low–Medium | High | Very High |
| Quotation | Very High | Low | High | Very High |
| Status Tracking | High | Medium | High | High |
| Mobile UX | High | High | Very High | Very High |
| Simple Workflow | High | High | Critical | Critical |

---

# 21. Key UX Implications

## Customer UX

Should emphasize:

```text
Discover
→ Understand
→ Order / Customize
→ Track
```

## Artisan UX

Should emphasize:

```text
Requests
→ Action Needed
→ Quote
→ Production
→ Status
```

Do not overwhelm artisans with unnecessary dashboards or analytics.

---

# 22. Primary Research Targets

Based on the segmentation, the highest-priority interview targets are:

## Customers

- Custom Craft Buyer
- Cultural Craft Explorer

## Sellers

- Individual Artisan
- Social-Media-Based Craft Seller

Recommended exploratory target remains approximately:

```text
5–8 Customers
+
3–5 Artisans / Sellers
```

The sample is intended for exploratory academic product discovery, not statistical representation.

---

# 23. Persona Validation Questions

Future interviews should test:

## Customer

- How do you currently discover handicraft products?
- Have you ever requested customization?
- How did you communicate requirements?
- What information matters before purchase?
- Do you care about artisan/craft information?
- What makes an online craft purchase trustworthy?

## Artisan

- How do customers currently contact you?
- How do you record custom requirements?
- What information is commonly missing?
- How do you provide quotations?
- How do customers ask about progress?
- Would a structured workflow reduce or increase your work?

---

# 24. Persona Update Rule

After primary research:

```text
Interview Evidence
      ↓
Compare With Persona
      ↓
Confirm / Modify / Reject Assumptions
      ↓
Persona v0.2
```

No persona should be treated as permanent.

---

# 25. Segment-to-Feature Mapping

| Segment | Highest-Relevance Features |
|---|---|
| C1 Cultural Explorer | Search, artisan profile, craft context |
| C2 Custom Buyer | Custom request, quotation, approval, tracking |
| C3 Gift Buyer | Gift filters/recommendations — future |
| C4 Trust-Conscious Buyer | Reviews, clear product/artisan records |
| A1 Individual Artisan | Profile, products, custom-order management |
| A2 Small Craft Business | Product/order management |
| A3 Social Seller | Structured request, quotation, status management |

---

# 26. Current Persona Decision

The strongest provisional MVP user pairing is:

```text
Custom Craft Buyer
        ↕
Structured Custom Order
        ↕
Individual Artisan /
Social-Media Seller
```

Secondary product experience:

```text
Cultural Craft Explorer
        ↓
Product + Artisan + Craft Context
```

---

# 27. Main Persona Risk

The greatest risk is creating detailed fictional personas and then treating them as research evidence.

Therefore:

**Personas guide questions and design.  
Real users validate assumptions.**

---

## Document Status

**Phase:** 03 — Stakeholder & User Analysis  
**Document:** User Segmentation & Persona Baseline  
**Status:** Provisional v0.1  
**Persona Type:** Synthetic / Research-Informed  
**Primary Research Dependency:** Open  
**Next Step:** User Goals & Pain-Point Mapping
