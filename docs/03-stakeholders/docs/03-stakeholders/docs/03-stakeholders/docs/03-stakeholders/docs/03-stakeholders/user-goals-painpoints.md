# Craft BD — User Goals & Pain-Point Mapping

## 1. Purpose

This document maps the major goals, potential pain points, current workarounds, and Craft BD opportunities for the priority user segments.

The objective is to ensure that future features and requirements are connected to identifiable user problems rather than being added without justification.

Because primary research is still pending, several pain points remain hypotheses.

---

# 2. Mapping Framework

Each user problem is analyzed using:

**Goal**  
What the user wants to achieve.

**Potential Pain Point**  
What may prevent or complicate that goal.

**Current Workaround**  
How the user may currently solve the problem.

**Craft BD Opportunity**  
How the proposed system could improve the situation.

**Validation Status**  
Whether the problem is validated, partially supported, or still an open hypothesis.

---

# 3. Customer Segment C1 — Cultural Craft Explorer

## Goal C1-G01

Discover suitable Bangladeshi handicraft products.

### Potential Pain Point

Products may be scattered across:

- Social-media pages
- Different seller accounts
- General e-commerce platforms
- Physical markets

### Current Workaround

Customer may:

Search manually  
→ Browse multiple sources  
→ Compare products individually

### Craft BD Opportunity

Provide:

Central Product Catalog  
+ Categories  
+ Search  
+ Filtering

### Validation Status

**Partially Supported**

---

## Goal C1-G02

Understand the artisan behind a product.

### Potential Pain Point

Typical product listings may provide limited information about:

- Artisan identity
- Expertise
- Experience
- Region

### Current Workaround

Customer may:

- Ask the seller directly
- Search social-media profiles
- Purchase without knowing artisan details

### Craft BD Opportunity

Provide:

Product  
→ Artisan Profile  
→ Expertise / Story / Related Products

### Validation Status

**Partially Supported**

---

## Goal C1-G03

Understand the cultural context of a craft.

### Potential Pain Point

Product descriptions may focus mainly on:

- Price
- Image
- Size

while providing little information about:

- Origin
- Material
- Technique
- Traditional use

### Current Workaround

Customer may search separately on the internet or purchase without this information.

### Craft BD Opportunity

Provide lightweight craft context directly with relevant products.

### Validation Status

**Open / Requires Primary Validation**

---

# 4. Customer Segment C2 — Custom Craft Buyer

## Goal C2-G01

Communicate custom requirements accurately.

### Potential Pain Point

Requirements may be scattered across several chat messages.

Example:

```text
Message 1 → Product photo
Message 2 → Size
Message 3 → Color
Message 4 → Material
Message 5 → Delivery request
```

This may increase misunderstanding.

### Current Workaround

Customer repeatedly communicates with the seller using Messenger, WhatsApp, phone, or another messaging channel.

### Craft BD Opportunity

Structured custom-order form containing:

- Product type
- Size
- Color
- Material
- Quantity
- Reference image
- Instructions

### Validation Status

**High-Priority Hypothesis**

---

## Goal C2-G02

Know the expected custom-order price before production.

### Potential Pain Point

Informal discussions may make it difficult to know which price was finally agreed.

### Current Workaround

Customer relies on chat history or verbal agreement.

### Craft BD Opportunity

Formal quotation:

```text
Artisan Quote
→ Price
→ Completion Estimate
→ Notes
→ Customer Approve / Reject
```

### Validation Status

**High-Priority Hypothesis**

---

## Goal C2-G03

Know whether production has started and how the order is progressing.

### Potential Pain Point

Customer may need to repeatedly ask:

> Is my order ready?

### Current Workaround

Message or call the seller.

### Craft BD Opportunity

Visible status:

```text
Requested
→ Quote Ready
→ Approved
→ In Production
→ Ready
→ Shipped
→ Delivered
```

### Validation Status

**Open / High Priority**

---

## Goal C2-G04

Keep proof of agreed requirements.

### Potential Pain Point

A disagreement may occur regarding:

- Size
- Color
- Design
- Price
- Completion date

### Current Workaround

Customer checks old messages/screenshots.

### Craft BD Opportunity

Maintain one structured order record containing:

Requirements  
+ Quotation  
+ Approval  
+ Status History

### Validation Status

**Open**

---

# 5. Customer Segment C4 — Trust-Conscious Buyer

## Goal C4-G01

Evaluate whether a product/seller appears trustworthy.

### Potential Pain Point

Customer may encounter:

- Limited seller information
- Incomplete product details
- Unverified reviews
- Misleading claims

### Current Workaround

Customer may:

- Check comments
- Ask friends
- Search seller profiles
- Look for previous customer posts

### Craft BD Opportunity

Provide:

- Artisan profile
- Clear product details
- Purchase-linked reviews
- Platform product records

### Validation Status

**Partially Supported**

---

## Goal C4-G02

Understand product information before purchasing.

### Potential Pain Point

Important information may be missing.

### Craft BD Opportunity

Structured fields for:

- Materials
- Price
- Artisan
- Region
- Craft type
- Product description

### Validation Status

**Reasonable / Partially Supported**

---

# 6. Artisan Segment A1 — Individual Artisan

## Goal A1-G01

Showcase products professionally.

### Potential Pain Point

Social-media posts may not provide a structured product catalog.

### Current Workaround

Artisan may:

- Create posts
- Maintain albums
- Reply manually to product questions

### Craft BD Opportunity

Provide:

Artisan Profile  
→ Product Catalog  
→ Product Details

### Validation Status

**Partially Supported**

---

## Goal A1-G02

Receive complete custom-order requirements.

### Potential Pain Point

Customers may submit incomplete information.

Examples:

> “Same design but একটু ছোট।”

or:

> “এইটার মতো একটা বানান।”

This can require repeated clarification.

### Current Workaround

Artisan asks follow-up questions through chat or calls.

### Craft BD Opportunity

Required structured custom fields.

### Validation Status

**High-Priority Hypothesis**

---

## Goal A1-G03

Know whether the customer accepted the quoted price.

### Potential Pain Point

Informal agreement may create confusion.

### Current Workaround

Artisan relies on chat replies.

### Craft BD Opportunity

Explicit:

```text
Quotation
→ Customer Approved
```

before production begins.

### Validation Status

**High-Priority Hypothesis**

---

## Goal A1-G04

Manage multiple custom orders.

### Potential Pain Point

Multiple message threads may become difficult to track.

### Current Workaround

Possible methods:

- Messenger inbox
- Notebook
- Phone notes
- Memory
- Spreadsheet

### Craft BD Opportunity

Custom-order dashboard showing:

- Pending requests
- Awaiting approval
- Active production
- Completed orders

### Validation Status

**Requires Artisan Interviews**

---

# 7. Artisan Segment A3 — Social-Media-Based Seller

## Goal A3-G01

Continue receiving orders without increasing administrative workload.

### Potential Pain Point

A new system may require more effort than Messenger.

This is a critical adoption risk.

### Current Workaround

Continue using social-media messaging.

### Craft BD Opportunity

The workflow must make:

```text
Request Management
+
Quotation
+
Status Tracking
```

simpler than manually organizing multiple conversations.

### Validation Status

**Critical Open Assumption**

---

## Goal A3-G02

Organize customer information and requirements.

### Potential Pain Point

Customer details may be distributed across multiple conversations.

### Current Workaround

Search previous messages manually.

### Craft BD Opportunity

Central custom-order record.

### Validation Status

**High-Priority Hypothesis**

---

## Goal A3-G03

Reduce repetitive progress questions.

### Potential Pain Point

Customers may repeatedly ask about progress.

### Current Workaround

Seller manually responds to each customer.

### Craft BD Opportunity

Customer-visible order status.

### Validation Status

**Requires Validation**

---

# 8. Cross-User Pain Points

Some potential problems affect both customer and artisan.

## PP-01 — Requirement Ambiguity

Customer:

May struggle to explain requirements.

Artisan:

May receive incomplete specifications.

### Opportunity

Structured custom request.

---

## PP-02 — Price Agreement Ambiguity

Customer:

May not know final agreed price.

Artisan:

May not know whether customer accepted the quotation.

### Opportunity

Formal quote + explicit approval.

---

## PP-03 — Status Communication

Customer:

Wants progress visibility.

Artisan:

May want fewer repeated inquiries.

### Opportunity

Shared order-status workflow.

---

## PP-04 — Information Fragmentation

Customer:

Needs product/artisan information.

Artisan:

Needs organized product/order records.

### Opportunity

Centralized platform records.

---

# 9. Pain-Point Priority Matrix

| ID | Pain Point | Customer Impact | Artisan Impact | Current Priority | Validation |
|---|---|---|---|---|---|
| PP-01 | Custom requirement ambiguity | High | High | Critical | Open |
| PP-02 | Informal quotation/approval | High | High | Critical | Open |
| PP-03 | Repeated status communication | High | High | High | Open |
| PP-04 | Product information fragmentation | Medium–High | Medium | High | Partial |
| PP-05 | Limited artisan context | Medium | Medium | Medium | Partial |
| PP-06 | Cultural information gap | Medium | Low | Medium | Open |
| PP-07 | Seller dashboard complexity | Low | High | High | Open |
| PP-08 | Trust concerns | High | Medium | High | Partial |

---

# 10. Strongest Current Opportunity

The strongest provisional two-sided opportunity is:

```text
CUSTOMER
Needs clear customization
        ↓
Structured Request
        ↑
ARTISAN
Needs complete requirements
```

followed by:

```text
CUSTOMER
Needs clear agreement
        ↓
Quotation + Approval
        ↑
ARTISAN
Needs confirmed order
```

and:

```text
CUSTOMER
Needs progress visibility
        ↓
Order Status
        ↑
ARTISAN
Needs fewer repeated questions
```

These relationships make the custom-order workflow potentially valuable to both user groups.

However, primary research must confirm them.

---

# 11. Existing Workaround Principle

An existing workaround is not automatically bad.

Example:

Messenger may already provide:

- Fast communication
- Image sharing
- Notifications
- Familiarity

Therefore, Craft BD must not simply duplicate Messenger.

The system should provide additional value through:

- Structure
- Traceability
- Approval
- Status
- Centralized records

---

# 12. Product Adoption Test

For each proposed workflow ask:

> Is this meaningfully better than the user's current workaround?

Example:

```text
Current:
Messenger + Notes

Craft BD:
10 complicated forms
```

Result:

**Poor product opportunity**

But:

```text
Current:
Scattered messages

Craft BD:
One request
+ quote
+ approval
+ status
```

Potential result:

**Useful improvement**

This must be validated with users.

---

# 13. Pain Point → Requirement Example

Example:

```text
Pain Point:
PP-01 Requirement ambiguity

        ↓

Need:
Customer must provide clear specification

        ↓

Potential Requirement:
System shall allow a customer to submit
structured customization requirements.

        ↓

Possible Feature:
Custom Order Form

        ↓

Test:
Required specifications are stored correctly.
```

---

# 14. Validation Status Rules

Use:

**Validated**

Confirmed by sufficient primary evidence for current project decisions.

**Partially Supported**

Supported by secondary/proxy evidence or limited observations.

**Open**

Not yet sufficiently validated.

**Rejected**

Research indicates that the assumed problem is not meaningful.

---

# 15. Current Validation Summary

## Partially Supported

- Product discovery challenges
- Seller/artisan visibility
- Product information/trust concerns

## High-Priority Open Hypotheses

- Custom requirement ambiguity
- Quotation ambiguity
- Custom-order progress visibility
- Artisan need for structured custom-order management
- Artisan willingness to use Craft BD instead of current messaging workflows

---

# 16. Requirement Priority Implication

The following should not be permanently locked until primary research:

- Custom-order workflow
- Product journey
- QR product record
- Craft story importance
- Recommendation system

However, these may continue as provisional design candidates.

---

# 17. Main Product Risk

The largest current risk is:

> Craft BD could solve a theoretically plausible problem that real customers and artisans do not consider important enough to change their behavior.

Therefore:

```text
Assumption
→ Interview
→ Evidence
→ Decision
```

must remain part of the project process.

---

# 18. Current User-Problem Baseline

The current provisional user-problem model is:

```text
CUSTOMER
│
├── Discover product
├── Understand product / artisan
├── Communicate customization
├── Agree on quote
└── Track progress
        ↕
      CRAFT BD
        ↕
ARTISAN
│
├── Showcase product
├── Receive clear requirements
├── Provide quote
├── Confirm approval
└── Manage order status
```

---

## Document Status

**Phase:** 03 — Stakeholder & User Analysis  
**Document:** User Goals & Pain-Point Mapping  
**Status:** Provisional v0.1  
**Primary Research Dependency:** Open  
**Next Step:** Customer & Artisan Journey Baseline
