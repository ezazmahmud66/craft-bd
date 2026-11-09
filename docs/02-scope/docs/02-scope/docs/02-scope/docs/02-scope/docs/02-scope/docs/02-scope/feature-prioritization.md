# Craft BD — Feature Feasibility & Prioritization Matrix

## 1. Purpose

This document prioritizes the proposed Craft BD capabilities based on:

- User value
- Current evidence
- Technical complexity
- Operational complexity
- Academic relevance
- Schedule feasibility
- Security considerations
- Portfolio value

The goal is to prevent feature overload and define a realistic MVP.

The prioritization is provisional because primary user research is still pending.

---

# 2. Prioritization Method

Craft BD uses the MoSCoW method.

## Must Have

Essential for the core product workflow.

Without these features, the MVP would not demonstrate the intended product value.

## Should Have

Important and valuable, but the system can still operate without them in the first release.

## Could Have

Useful enhancements that should only be implemented if time allows.

## Won't Have Now

Features intentionally excluded from the current MVP.

They may be reconsidered in future releases.

---

# 3. Prioritization Criteria

Each feature is evaluated using:

**User Value**  
Does it solve an important user problem?

**Evidence**  
Is the problem supported by research?

**Complexity**  
How difficult is the implementation?

**Dependency**  
Does another feature depend on it?

**Academic Value**  
Does it demonstrate Software Engineering concepts?

**Schedule Impact**  
Can it be completed within the academic timeline?

---

# 4. Feature Prioritization Matrix

| Feature | Evidence | Complexity | User Value | MoSCoW | Release Decision |
|---|---|---:|---:|---|---|
| User Registration | Strong / Necessary | Moderate | High | Must | MVP |
| Login | Strong / Necessary | Moderate | High | Must | MVP |
| Role-Based Access Control | Strong / Necessary | Moderate | High | Must | MVP |
| Customer Profile | Standard Need | Low | Medium | Should | MVP |
| Artisan Profile | Partially Supported | Low | High | Must | MVP |
| Product Catalog | Strong | Low | High | Must | MVP |
| Product Categories | Strong | Low | High | Must | MVP |
| Product Details | Strong | Low | High | Must | MVP |
| Search | Strong | Low | High | Must | MVP |
| Filtering | Strong | Low–Moderate | Medium–High | Should | MVP |
| Craft Story | Partially Supported | Low | Medium | Should | MVP if manageable |
| Product Journey | Limited Evidence | Low–Moderate | Medium | Could | Optional MVP |
| Wishlist | Standard Commerce | Low | Medium | Could | Optional |
| Shopping Cart | Supporting Commerce | Moderate | High | Must | MVP |
| Checkout | Supporting Commerce | Moderate | High | Must | MVP |
| Order Placement | Strong | Moderate | High | Must | MVP |
| Order Tracking | Strong | Moderate | High | Must | MVP |
| Simulated Payment | Academic Need | Low–Moderate | Medium | Should | MVP |
| Real Payment Gateway | Weak MVP Need | High | Medium | Won't | Future |
| Product Reviews | Standard Trust Mechanism | Moderate | Medium–High | Should | MVP |
| Verified-Purchase Review Rule | Strong Design Value | Moderate | High | Must | MVP |
| Custom Order Request | High-Priority Hypothesis | Moderate | High | Must* | MVP* |
| Custom Requirement Form | High-Priority Hypothesis | Moderate | High | Must* | MVP* |
| Artisan Quotation | High-Priority Hypothesis | Moderate | High | Must* | MVP* |
| Customer Quote Approval | High-Priority Hypothesis | Moderate | High | Must* | MVP* |
| Custom Order Status | High-Priority Hypothesis | Moderate | High | Must* | MVP* |
| Reference Image Upload | Supporting Custom Order | Moderate | High | Should | MVP |
| QR-linked Product Record | Partially Supported | Moderate | Medium | Should | MVP if scope allows |
| Digital Certificate Record | Limited / Partial | Moderate | Medium | Could | Optional |
| Personalized Recommendation | Weak Evidence | Moderate–High | Medium | Could | Future |
| Advanced AI Recommendation | Weak Evidence | High | Low MVP Value | Won't | Reject MVP |
| Gift Recommendation | Weak Evidence | Moderate | Low–Medium | Could | Future |
| Events / Workshops | Weak Core Relevance | Moderate | Low | Won't | Future |
| Live Chat | Weak Core Need | High | Medium | Won't | Future |
| Blockchain Verification | No MVP Need | High | Low | Won't | Reject MVP |
| Logistics API Integration | External Dependency | High | Medium | Won't | Future |
| Native Mobile App | Not Required | High | Medium | Won't | Future |
| Advanced Analytics | Not Core | High | Low–Medium | Won't | Future |

\* Custom-order features are currently Must-Have **provisionally** because they represent the strongest current Craft BD differentiation. Their status must be reviewed after real user research.

---

# 5. Proposed MVP Core

The recommended current MVP contains five major capability groups.

## 5.1 Identity & Access

Must include:

- User registration
- Login
- Customer role
- Artisan role
- Administrator role
- Role-based authorization

---

# 6. Craft Discovery

Must include:

- Product catalog
- Categories
- Search
- Product details
- Artisan profile

Should include:

- Filtering
- Craft story

Could include:

- Product journey

---

# 7. Commerce Workflow

Must include:

- Cart
- Checkout
- Order creation
- Order status

Should include:

- Simulated payment
- Product review

Important:

Real financial transactions are not required for MVP.

---

# 8. Structured Custom Order

Current provisional core workflow:

Customer  
→ Submit Requirements  
→ Artisan Reviews  
→ Artisan Provides Quotation  
→ Customer Approves  
→ Production  
→ Status Updates  
→ Delivery

Must include:

- Custom request
- Structured specification fields
- Artisan review
- Quotation
- Customer approval
- Controlled status transitions

Should include:

- Reference-image upload

This workflow is currently one of Craft BD's strongest portfolio and Software Engineering features.

---

# 9. Product Information & Trust

Potential MVP:

- Artisan information
- Product materials
- Product origin
- Reviews
- QR-linked product record

Optional:

- Digital certificate record
- Product journey

These features should not create unsupported authenticity claims.

---

# 10. Must-Have Feature Set

Current provisional Must-Have list:

1. User Registration
2. Authentication
3. Role-Based Authorization
4. Artisan Profile
5. Product Catalog
6. Product Categories
7. Product Details
8. Search
9. Shopping Cart
10. Checkout
11. Order Placement
12. Order Status
13. Structured Custom Request
14. Artisan Quotation
15. Customer Approval
16. Custom-Order Status
17. Verified-Purchase Review Rule

---

# 11. Should-Have Feature Set

Recommended Should-Have:

- Customer profile
- Product filtering
- Craft story
- Reference-image upload
- Simulated payment
- Product reviews
- QR-linked product record

These should be implemented after Must-Have functionality is stable.

---

# 12. Could-Have Feature Set

If sufficient time remains:

- Wishlist
- Product journey
- Digital certificate record
- Simple content-based recommendation

These features must not delay core development or testing.

---

# 13. Won't-Have-Now Features

The following are intentionally excluded from the initial MVP:

- Real payment gateway
- Advanced AI recommendation
- Gift recommendation engine
- Live chat
- Blockchain verification
- Logistics API integration
- Native mobile application
- Advanced analytics
- Full event / workshop management

This is a deliberate scope decision rather than a technical limitation.

---

# 14. Feature Dependency Map

Important dependencies:

Authentication  
→ Role Authorization

Artisan Profile  
→ Product Management

Product  
→ Cart  
→ Checkout  
→ Order

Customer + Artisan  
→ Custom Order

Custom Order  
→ Quotation  
→ Approval  
→ Status Tracking

Completed Order  
→ Product Review

Product Record  
→ QR Verification

This dependency order should influence development planning.

---

# 15. MVP Dependency Flow

Recommended implementation sequence:

Authentication  
↓  
Roles  
↓  
Artisan Profile  
↓  
Product Catalog  
↓  
Cart / Order  
↓  
Custom Order  
↓  
Quotation / Approval  
↓  
Status Management  
↓  
Review  
↓  
QR / Certificate Extensions

---

# 16. Feature Removal Rule

If the project falls behind schedule, features should be removed in this order:

### Remove First

- Recommendation
- Gift recommendation
- Events
- Advanced analytics

### Then Remove / Simplify

- Digital certificate
- Product journey
- Wishlist
- QR enhancement

### Protect Until Last

- Authentication
- Authorization
- Product
- Artisan
- Order
- Custom-order workflow
- Testing

---

# 17. Academic Value Prioritization

Features with high Software Engineering learning value include:

## Role-Based Access

Demonstrates:

- Security
- Authorization
- Actor separation

## Custom Order Workflow

Demonstrates:

- Complex requirements
- State transitions
- Business rules
- UML
- Testing

## Order Management

Demonstrates:

- Entity relationships
- Data consistency
- Status management

## QR Product Record

Demonstrates:

- Unique identifiers
- Verification workflow
- Data retrieval

These features provide stronger portfolio value than simply adding more product pages.

---

# 18. Portfolio Value

The final portfolio should emphasize:

**Problem-Solving Workflow**

rather than:

**Number of Features**

Strong portfolio discussion points may include:

- Requirement traceability
- Role-based authorization
- Custom-order state machine
- Product / artisan data model
- REST API design
- QR-linked product record
- Testing strategy
- Deployment
- Architecture decisions

---

# 19. Provisional MVP Definition

The current recommended Craft BD MVP is:

> A role-based web platform where customers can discover Bangladeshi handicrafts and artisans, purchase products through a basic commerce workflow, and submit structured custom-order requests that artisans can review, quote, and progress through controlled order states.

Supporting context may include:

- Craft story
- Product information
- Reviews
- QR-linked records

---

# 20. Important Validation Dependency

The custom-order workflow is currently treated as a provisional Must-Have because it provides the strongest differentiation from generic e-commerce.

However:

Real customer and artisan research  
→ must confirm or challenge this decision.

If primary research does not validate the custom-order problem, the MVP must be reconsidered.

---

# 21. Current Scope Philosophy

Craft BD should prefer:

**Small + Complete + Tested + Deployable**

over:

**Large + Feature-Rich + Incomplete**

---

# 22. Prioritization Decision

## Must Have

Core product and custom-order workflow.

## Should Have

Important supporting experience.

## Could Have

Enhancements only if time remains.

## Won't Have Now

High-complexity or weakly validated features.

---

## Document Status

**Phase:** 02 — Feasibility & Scope Analysis  
**Document:** Feature Feasibility & Prioritization  
**Status:** Provisional v0.1  
**Primary Research Dependency:** Open  
**Next Step:** MVP Scope Definition
