# Craft BD — MVP Scope Definition v0.1

## 1. Document Status

**Version:** 0.1  
**Status:** PROVISIONAL  
**Phase:** Phase 02 — Feasibility & Scope Analysis  
**Primary User Validation:** Pending

This document defines the current recommended Minimum Viable Product (MVP) scope for Craft BD.

The scope may change after real customer and artisan research.

---

# 2. MVP Goal

The Craft BD MVP should demonstrate a complete and professionally engineered workflow where:

- Customers can discover Bangladeshi handicrafts
- Customers can understand relevant artisan and craft information
- Customers can purchase standard products
- Customers can submit structured custom-order requests
- Artisans can review requests and provide quotations
- Customers can approve quotations
- Artisans can update production progress
- Customers can track order status
- Administrators can perform essential platform-governance tasks

The MVP should prioritize workflow completeness, security, testing, and usability over feature quantity.

---

# 3. MVP Product Definition

The provisional Craft BD MVP is:

> A role-based web platform for discovering Bangladeshi handicrafts and artisans, purchasing standard products, and managing structured custom craft orders through quotation, approval, production, and delivery states.

---

# 4. Primary User Roles

The MVP will support three roles:

## Customer

Main responsibilities:

- Browse products
- Search/filter products
- View artisan information
- View craft information
- Add products to cart
- Place standard orders
- Submit custom requests
- Review artisan quotations
- Approve/reject quotations
- Track order progress
- Submit eligible reviews

---

## Artisan

Main responsibilities:

- Maintain artisan profile
- Add/manage products
- View custom-order requests
- Review requirements
- Submit quotations
- Update custom-order status
- Manage relevant product information

---

## Administrator

Main responsibilities:

- Manage users
- Manage categories
- Moderate content
- Review platform data
- Manage verification/certificate-related records if included
- Handle exceptional administrative operations

---

# 5. Core MVP Modules

The MVP should contain the following major modules.

## Module 1 — Authentication & Access Control

Must include:

- User registration
- Login
- Logout
- Customer role
- Artisan role
- Administrator role
- Role-based authorization
- Ownership validation

---

## Module 2 — Artisan Management

Must include:

- Artisan profile
- Artisan biography
- Expertise
- Experience
- Location / region
- Artisan product listing

Optional profile content:

- Artisan story
- Profile image

---

## Module 3 — Product Management

Must include:

- Product creation
- Product editing
- Product deletion / deactivation
- Product category
- Price
- Stock
- Product images
- Product description
- Artisan relationship

Should include:

- Materials
- Craft type
- Region
- Craft story

---

## Module 4 — Product Discovery

Must include:

- Product catalog
- Category browsing
- Product details
- Search

Should include:

- Filtering by category
- Price
- Material
- Craft type

---

## Module 5 — Standard Commerce

Must include:

- Add to cart
- Update cart quantity
- Remove from cart
- Checkout
- Order creation
- Order details
- Order status

Should include:

- Simulated payment
- Order history

Real financial transactions are not required for the MVP.

---

# 6. Structured Custom-Order Module

This is the current provisional signature workflow.

## Customer Request

Customer should be able to provide:

- Product type
- Design
- Color
- Size
- Material
- Quantity
- Reference image
- Instructions

---

## Artisan Review

The artisan should be able to:

- View customer requirements
- Review reference image
- Accept request for quotation
- Reject request where appropriate

---

## Quotation

The artisan should be able to provide:

- Proposed price
- Estimated completion date
- Quotation notes

---

## Customer Decision

Customer should be able to:

- Approve quotation
- Reject quotation

Production must not begin before quotation approval.

---

# 7. Custom-Order Status Model

Recommended backend states:

```text
REQUESTED
↓
UNDER_REVIEW
↓
QUOTED
↓
CUSTOMER_APPROVED
↓
IN_PRODUCTION
↓
QUALITY_CHECK
↓
READY_TO_SHIP
↓
SHIPPED
↓
DELIVERED
```

Alternative terminal states:

```text
REJECTED
CANCELLED
```

Customer-facing labels may be simplified.

---

# 8. Review Module

Should include:

- Product rating
- Product review
- Review date
- Reviewer relationship

Important business rule:

> Only an eligible customer associated with a completed purchase should normally be allowed to review a product.

Administrator may moderate inappropriate content.

---

# 9. Craft Information Module

Should include basic contextual information such as:

- Craft origin
- Materials
- Technique
- Traditional use
- Cultural meaning

This feature should remain lightweight in MVP.

The goal is not to build a large cultural encyclopedia.

---

# 10. Product Journey

Current classification:

**Optional MVP / Could Have**

Possible stages:

Raw Material  
→ Design  
→ Making  
→ Finishing  
→ Quality Check  
→ Final Product

If implemented, each stage may contain:

- Title
- Description
- Image
- Sequence

This feature should be removed before core workflow quality is reduced.

---

# 11. QR-Linked Product Record

Current classification:

**Should Have if schedule permits**

Possible flow:

QR Code  
→ Verification URL  
→ Craft BD Product Record

The page may display:

- Product ID
- Artisan
- Region
- Materials
- Craft type
- Production information
- Certificate record

The system must not claim that QR alone guarantees physical authenticity.

---

# 12. Digital Certificate

Current classification:

**Optional**

Possible data:

- Certificate ID
- Product ID
- Artisan
- Region
- Materials
- Issue date
- Verification code

For MVP purposes, this represents a Craft BD platform record.

It must not be described as government certification unless an authorized external process exists.

---

# 13. Recommendation Feature

Current MVP decision:

**Not Core**

If implemented later:

Use a simple content-based approach based on:

- Category
- Material
- Region
- Craft type
- Price range

Advanced machine-learning recommendation is outside the initial MVP.

---

# 14. Planned MVP Screens

The exact UI may change during design, but the MVP currently requires approximately the following screens.

## Public / General

1. Home
2. Product Catalog
3. Product Details
4. Artisan Profile
5. Login
6. Registration

---

## Customer

7. Customer Dashboard
8. Cart
9. Checkout
10. Order History
11. Order Details
12. Custom Order Request
13. Custom Order Details
14. Quotation Review
15. Customer Profile

---

## Artisan

16. Artisan Dashboard
17. Artisan Profile Management
18. Product Management
19. Add/Edit Product
20. Custom Request List
21. Custom Request Details
22. Quotation Form
23. Active Custom Orders

---

## Administrator

24. Admin Dashboard
25. User Management
26. Category Management
27. Product/Content Moderation
28. Certificate / Verification Management if implemented

---

# 15. MVP Core User Journey — Standard Product

```text
Customer
   ↓
Browse
   ↓
Search / Filter
   ↓
Product Details
   ↓
Artisan Information
   ↓
Add to Cart
   ↓
Checkout
   ↓
Place Order
   ↓
Track Order
   ↓
Delivered
   ↓
Review
```

---

# 16. MVP Core User Journey — Custom Product

```text
Customer
   ↓
Custom Request
   ↓
Structured Requirements
   ↓
Artisan Review
   ↓
Quotation
   ↓
Customer Approval
   ↓
Production
   ↓
Progress Updates
   ↓
Quality Check
   ↓
Delivery
```

---

# 17. MVP Admin Journey

```text
Admin Login
   ↓
Dashboard
   ↓
Manage Users / Categories
   ↓
Moderate Content
   ↓
Manage Exceptional Platform Actions
```

Admin should not manually approve every normal transaction.

---

# 18. In-Scope Functionality

Current MVP scope includes:

- Web application
- Responsive UI
- Customer accounts
- Artisan accounts
- Administrator account
- Role-based access control
- Artisan profiles
- Product catalog
- Search
- Filtering
- Product details
- Cart
- Checkout
- Standard orders
- Order status
- Structured custom requests
- Quotations
- Customer approval
- Custom-order status
- Reference-image upload
- Reviews
- Basic craft information
- Simulated payment
- Basic admin operations

Possible scope extensions:

- QR-linked product record
- Product journey
- Digital certificate

---

# 19. Explicitly Out of Scope for MVP

The following are excluded from MVP v0.1:

- Native Android application
- Native iOS application
- Real-time live chat
- Video calling
- Blockchain-based certification
- Advanced AI recommendation
- AI chatbot
- Complex recommendation engine
- Real payment gateway as mandatory feature
- Logistics-company API integration
- Full warehouse management
- Full accounting system
- Enterprise ERP
- Complex event/workshop management
- Advanced BI dashboard
- Multi-vendor financial settlement system
- Government certification integration
- Automatic physical-product authenticity detection

---

# 20. Data Scope

The MVP is expected to manage:

- Users
- Customer profiles
- Artisan profiles
- Categories
- Products
- Product images
- Craft information
- Cart
- Orders
- Order items
- Custom requests
- Quotations
- Custom-order status
- Reviews
- Optional certificate records
- Optional verification records

---

# 21. Non-Functional MVP Expectations

The MVP should be:

## Usable

Core workflows should be understandable without developer assistance.

## Secure

Authentication, authorization, validation, and secret handling must be implemented.

## Responsive

The web application should support desktop and mobile browser layouts.

## Maintainable

Modules should have clear responsibilities.

## Testable

Core business rules and workflows must have documented tests.

## Deployable

The final application should run outside the developer's local machine.

---

# 22. Definition of MVP Success

The MVP is considered successful when the following can be demonstrated end-to-end.

### Customer

Register  
→ Discover Product  
→ View Artisan  
→ Place Standard Order

and

Submit Custom Request  
→ Receive Quote  
→ Approve  
→ Track Production

### Artisan

Login  
→ Manage Profile  
→ Manage Product  
→ Receive Custom Request  
→ Quote  
→ Update Status

### Administrator

Login  
→ Perform Required Governance Operations

---

# 23. MVP Quality Rule

A feature is not considered complete only because the UI exists.

A feature should include where applicable:

- Database support
- Backend logic
- Authorization
- Validation
- Error handling
- UI
- Testing
- Documentation

---

# 24. Scope Protection Rule

New feature requests during development should follow:

```text
Request
↓
Impact Analysis
↓
Priority Review
↓
Scope Decision
↓
Requirement Change
```

No major feature should be added silently.

---

# 25. Scope Reduction Order

If schedule pressure occurs:

## Remove First

- Recommendation
- Gift discovery
- Events
- Advanced analytics

## Remove / Simplify Next

- Digital certificate
- Product journey
- Wishlist
- QR enhancement

## Protect

- Authentication
- Authorization
- Artisan profile
- Product catalog
- Standard order
- Custom-order workflow
- Testing
- Deployment

---

# 26. MVP Portfolio Value

The MVP should allow the project team to demonstrate:

- Product discovery
- Requirements engineering
- Role-based access control
- Relational data modeling
- State-based workflows
- API design
- Secure file handling
- Business-rule implementation
- Testing
- Git workflow
- Deployment
- Documentation

---

# 27. Current MVP Risk

The main unresolved MVP dependency is:

> Whether real users validate structured custom ordering as an important problem.

Therefore, custom ordering remains a **provisional core feature** until primary research is completed.

---

# 28. MVP Decision

Current recommended release:

**Craft BD MVP v0.1**

Core:

```text
Identity
+
Artisan
+
Product
+
Commerce
+
Structured Custom Order
+
Order Management
+
Reviews
```

Supporting:

```text
Craft Context
+
QR Product Record
```

Optional:

```text
Product Journey
+
Digital Certificate
```

Excluded:

```text
Advanced AI
Blockchain
Live Chat
Native App
Mandatory Real Payment
Complex External Integrations
```

---

## Document Status

**Phase:** 02 — Feasibility & Scope Analysis  
**Document:** MVP Scope Definition  
**Version:** 0.1  
**Status:** PROVISIONAL  
**Primary Research Dependency:** Open  
**Next Step:** Formal In-Scope / Out-of-Scope Baseline
