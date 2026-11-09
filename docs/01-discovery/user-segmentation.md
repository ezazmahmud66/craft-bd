# Craft BD — Primary Users & User Segmentation

## 1. Purpose

This document identifies the primary and secondary user groups for Craft BD.

The goal is to avoid designing the platform for a vague “general user” and instead define the types of customers, artisans, and administrators whose needs should influence product decisions.

---

# 2. Primary User Groups

Craft BD currently has two primary user groups:

1. Customers
2. Artisans / Craft Sellers

The Administrator is an important operational user but is not the main beneficiary of the product.

---

# 3. Customer Segmentation

Not all customers have the same motivation.

## Segment C1 — Cultural Craft Explorer

### Description

A customer who is interested in traditional Bangladeshi crafts and wants to understand more than the price and appearance of a product.

### Possible Needs

- Learn who made the product
- Understand the craft's origin
- Learn about materials and techniques
- Explore cultural meaning
- Discover products from specific regions or craft traditions

### Potential Craft BD Value

Craft Story  
+ Artisan Profile  
+ Product Journey  
+ Regional/Cultural Information

### Validation Status

Hypothesis — requires user research.

---

## Segment C2 — Custom Craft Buyer

### Description

A customer who wants a handmade product with personalized requirements.

Examples may include:

- Custom color
- Custom size
- Custom design
- Material preference
- Quantity requirement
- Reference image

### Possible Problems

The customer may need repeated communication with a seller to clarify requirements, price, approval, and delivery.

### Potential Craft BD Value

Structured Custom Request  
→ Artisan Review  
→ Quotation  
→ Customer Approval  
→ Production  
→ Delivery

### Validation Status

High-priority hypothesis — requires direct user validation.

---

## Segment C3 — Gift Buyer

### Description

A customer looking for a craft product for a specific occasion or budget.

### Possible Needs

- Budget-based discovery
- Occasion-based suggestions
- Gift packaging
- Gift message
- Easy comparison

### Potential Craft BD Value

Gift Discovery + Recommendation

### Validation Status

Secondary hypothesis.

This should not become an MVP priority unless user research confirms significant demand.

---

## Segment C4 — Trust-Conscious Buyer

### Description

A customer who wants more confidence in the information associated with a handmade product.

### Possible Needs

- Artisan information
- Material information
- Region or production information
- Product record
- Certificate information

### Potential Craft BD Value

Product Record  
+ Digital Certificate  
+ QR-linked Information

### Important Limitation

A QR code alone cannot prove that a physical product is genuine.

Craft BD can verify only the information maintained within its own platform unless a stronger physical verification process is implemented.

### Validation Status

Hypothesis — requires research.

---

# 4. Artisan Segmentation

Craft BD should also avoid treating all artisans as identical users.

---

## Segment A1 — Individual Artisan

### Description

An individual craft producer who creates handmade products personally or with a very small team.

### Possible Needs

- Product visibility
- Personal profile
- Showcase expertise
- Present craft story
- Reach customers
- Receive custom-order requests

### Possible Constraints

- Limited technical skills
- Limited time for platform management
- Irregular product inventory
- Reliance on mobile devices

### Potential Craft BD Value

Simple Artisan Dashboard  
+ Product Management  
+ Custom Order Management

### Validation Status

Primary target hypothesis.

---

## Segment A2 — Small Craft Business / Workshop

### Description

A small workshop or craft business involving multiple artisans or workers.

### Possible Needs

- Manage multiple products
- Receive larger/custom orders
- Track quotations
- Manage production status
- Maintain product information

### Potential Craft BD Value

Product Catalog  
+ Custom Order Workflow  
+ Order Status Management

### Validation Status

Possible target segment.

---

## Segment A3 — Social-Media-Based Seller

### Description

A craft seller currently using Facebook, Instagram, Messenger, WhatsApp, or similar channels.

### Possible Needs

- Structured product presentation
- Standardized customer requirements
- Order status tracking
- Reduced repetitive communication
- Better organization of custom requests

### Potential Craft BD Value

Structured Workflow instead of only conversational order management.

### Validation Status

High-value research target.

---

# 5. Administrator

## Role

The Administrator supports platform operation.

### Responsibilities May Include

- Manage users
- Review artisan information
- Manage categories
- Monitor product information
- Moderate inappropriate content
- Manage certificates or verification records
- Manage cultural information
- Monitor system activity

### Product Role

Administrator is a supporting operational user.

The platform should not be designed around the administrator at the expense of customer and artisan experience.

---

# 6. Primary vs Secondary Users

## Primary Users

Customer  
Artisan / Craft Seller

These users directly receive the main value of Craft BD.

## Secondary User

Administrator

The Administrator enables platform governance and operation.

---

# 7. Recommended Initial Target Users

For the MVP, Craft BD should not attempt to support every possible user type equally.

The recommended initial focus is:

### Customer

**Custom Craft Buyer + Cultural Craft Explorer**

### Artisan

**Individual Artisan + Social-Media-Based Craft Seller**

Reason:

These segments are most closely connected to the current hypotheses around:

- Artisan visibility
- Craft context
- Structured customization
- Product information

---

# 8. Initial User Priority

| User Segment | Priority | Reason |
|---|---|---|
| Custom Craft Buyer | High | Directly related to structured custom-order hypothesis |
| Cultural Craft Explorer | High | Related to craft context and artisan storytelling |
| Individual Artisan | High | Core supply-side user |
| Social-Media-Based Seller | High | Useful for validating current informal order workflow |
| Trust-Conscious Buyer | Medium | Verification value still unvalidated |
| Small Craft Business | Medium | Useful but may add workflow complexity |
| Gift Buyer | Low / Future | Not central to current product problem |

---

# 9. User Segmentation Principle

Craft BD should avoid the assumption:

> “Everyone interested in handicrafts is our target customer.”

Instead:

Target User  
→ Specific Problem  
→ Product Capability  
→ Validation  
→ Requirement

---

# 10. Discovery Questions for Customers

Customer interviews should investigate:

- How they currently discover handmade products
- Where they usually purchase crafts
- What information they need before purchasing
- Whether artisan identity matters
- Whether cultural information matters
- Whether they have ordered customized handmade products
- Problems they experienced during customization
- What creates trust in a handmade product seller

---

# 11. Discovery Questions for Artisans

Artisan interviews should investigate:

- How they currently sell products
- Which channels they use
- How customers contact them
- How custom requirements are recorded
- How quotations are provided
- How order status is communicated
- Whether customer requirements are sometimes unclear
- What information artisans want customers to know about their work
- What difficulties they face using digital selling channels

---

# 12. Current User Hypothesis

The current product hypothesis is that Craft BD may provide the strongest value to:

**Customers who want a deeper understanding or customized version of a craft**

and

**Artisans who need a structured way to present their craft and handle customer requests.**

This hypothesis must be validated through primary research.

---

## Document Status

**Status:** Discovery Draft  
**Phase:** Phase 01 — Product Discovery & Problem Definition  
**Next Step:** Pain-Point Hypothesis & Validation Matrix
