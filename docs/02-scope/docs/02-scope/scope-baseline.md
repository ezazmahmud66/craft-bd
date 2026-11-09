# Craft BD — Scope Baseline v0.1

## 1. Purpose

This document defines the provisional project boundary for Craft BD.

It specifies:

- What the project will include
- What the project will not include
- Which capabilities are optional
- Which dependencies may affect scope
- How future scope changes will be controlled

This baseline is provisional because primary user validation is still pending.

---

# 2. Scope Statement

Craft BD will be developed as a responsive web application that connects customers with Bangladeshi artisans and handicraft products.

The system will primarily support:

- Handicraft discovery
- Artisan representation
- Product information
- Standard product ordering
- Structured custom-order requests
- Quotation and approval
- Order-status management
- Reviews
- Basic platform administration

Supporting cultural and product-context information may also be included where feasible.

---

# 3. In-Scope User Roles

The system will support:

## Customer

Can:

- Register and log in
- Browse products
- Search/filter products
- View artisan profiles
- View product/craft information
- Add products to cart
- Place orders
- Submit custom-order requests
- Review quotations
- Approve/reject quotations
- Track order status
- Submit eligible reviews
- Manage own profile

---

## Artisan

Can:

- Register/login as appropriate
- Maintain artisan profile
- Add products
- Edit own products
- Manage product information
- Receive custom requests
- Review customer requirements
- Provide quotations
- Update custom-order status
- View relevant order information

---

## Administrator

Can:

- Manage users
- Manage categories
- Moderate platform content
- Review product/artisan information
- Manage exceptional platform actions
- Manage certificate/verification records if included
- Perform required administrative governance

---

# 4. In-Scope Functional Areas

## Authentication

Included:

- Registration
- Login
- Logout
- Role identification
- Authorization
- Ownership checks

---

## Artisan Profiles

Included:

- Name
- Biography
- Location / region
- Experience
- Expertise
- Associated products

Possible additions:

- Artisan story
- Profile image

---

## Product Management

Included:

- Product name
- Category
- Price
- Stock
- Description
- Images
- Artisan association

Should include where practical:

- Materials
- Craft type
- Region
- Basic craft information

---

## Product Discovery

Included:

- Product catalog
- Category browsing
- Search
- Product details

Should include:

- Basic filtering

---

# 5. Standard Commerce Scope

Included:

Customer  
→ Product  
→ Cart  
→ Checkout  
→ Order  
→ Order Status

Functions include:

- Add to cart
- Update cart
- Remove item
- Checkout
- Order creation
- Order history
- Order details
- Status tracking

Payment may be simulated.

---

# 6. Custom-Order Scope

Provisionally included:

Customer  
→ Custom Request  
→ Artisan Review  
→ Quotation  
→ Customer Approval  
→ Production  
→ Status Updates  
→ Delivery

Customer may provide:

- Design
- Color
- Size
- Material
- Quantity
- Reference image
- Instructions

Artisan may provide:

- Quoted price
- Estimated completion date
- Notes

---

# 7. Custom-Order Business Boundary

Craft BD will manage the digital workflow.

The system will not physically:

- Manufacture the product
- Perform real quality inspection
- Package the product
- Deliver the product

Instead, the system records workflow status such as:

```text
IN_PRODUCTION
QUALITY_CHECK
READY_TO_SHIP
SHIPPED
DELIVERED
```

---

# 8. Review Scope

Included:

- Rating
- Review text
- Review date
- Product association
- Customer association

Recommended business rule:

Only an eligible customer associated with a completed purchase can review the relevant product.

---

# 9. Craft Information Scope

Should include lightweight contextual information such as:

- Origin
- Materials
- Technique
- Traditional use
- Cultural meaning

The MVP will not attempt to become a complete digital encyclopedia of Bangladeshi crafts.

---

# 10. QR Product Record Scope

Possible MVP extension:

QR  
→ Verification URL  
→ Product Record

Record may include:

- Product ID
- Artisan
- Region
- Materials
- Craft type
- Production information

Important boundary:

The QR code represents access to a Craft BD record.

It does not automatically prove physical authenticity.

---

# 11. Digital Certificate Scope

Optional.

If implemented, Craft BD may maintain:

- Certificate ID
- Product
- Artisan
- Region
- Materials
- Issue date
- Verification code

The certificate will represent a Craft BD platform record.

It will not be presented as:

- Government certification
- Legal authenticity certification
- Independent external certification

unless a future authorized integration exists.

---

# 12. In-Scope Non-Functional Areas

The MVP will consider:

- Usability
- Security
- Performance
- Reliability
- Maintainability
- Responsive design
- Testability
- Deployability

Exact measurable targets will be finalized during SRS preparation.

---

# 13. In-Scope Engineering Activities

The project includes:

- Product discovery
- Requirement analysis
- Feasibility analysis
- SRS
- Use cases
- UML diagrams
- UI/UX design
- Architecture design
- Database design
- API design
- Security design
- Implementation
- Testing
- UAT
- Deployment
- Documentation
- Git-based collaboration

---

# 14. Out-of-Scope — Platform Type

The first release will not include:

- Native Android app
- Native iOS app
- Desktop application

The initial product will be:

**Responsive Web Application**

---

# 15. Out-of-Scope — Communication

The MVP will not include:

- Real-time live chat
- Voice calling
- Video calling
- Social-network-style messaging system

Structured custom-order communication will be handled through system workflows.

---

# 16. Out-of-Scope — Advanced AI

The MVP will not depend on:

- Large recommendation models
- Generative AI chatbot
- Image-generation features
- AI-based authenticity detection
- Advanced predictive analytics

A simple content-based recommendation may be considered later.

---

# 17. Out-of-Scope — Blockchain

The MVP will not use blockchain for:

- Certificates
- Product verification
- Ownership
- Transaction records

Reason:

The technical complexity does not provide sufficient MVP value.

---

# 18. Out-of-Scope — Real Financial Infrastructure

The MVP will not:

- Store card numbers
- Store payment PINs
- Store bank credentials
- Build its own payment processing system

Real payment gateway integration is optional and not required for academic completion.

---

# 19. Out-of-Scope — Logistics Infrastructure

The MVP will not include:

- Courier-company API integration
- Real-time delivery GPS
- Warehouse management
- Fleet management
- Route optimization

Delivery status may be represented using internal order states.

---

# 20. Out-of-Scope — Enterprise Operations

The MVP will not provide:

- ERP
- Payroll
- Accounting
- Procurement
- Full inventory warehouse management
- Supplier-management system
- Multi-vendor financial settlement engine

---

# 21. Out-of-Scope — Certification Authority

Craft BD will not act as:

- Government certification authority
- Legal authenticity authority
- Independent craft-certification organization

Platform records should be described accurately.

---

# 22. Out-of-Scope — Large Event Platform

The initial release will not include full:

- Event registration
- Ticketing
- Workshop payment
- Attendance management
- Venue management

Basic informational content may be added in a future release if validated.

---

# 23. Optional Scope

The following may be implemented only if core development is stable:

- Wishlist
- Product journey
- QR-linked product record
- Digital certificate
- Simple content-based recommendation

These are not allowed to delay:

- Core workflow
- Testing
- Deployment
- Documentation

---

# 24. Scope Dependencies

Important dependencies include:

Authentication  
→ Role Authorization

Artisan Profile  
→ Product Management

Product  
→ Cart / Order

Customer + Artisan  
→ Custom Order

Custom Order  
→ Quotation  
→ Approval  
→ Status

Completed Order  
→ Review

Product Record  
→ QR Lookup

---

# 25. Scope Constraints

Current constraints include:

- Academic timeline
- Small development team
- Limited project budget
- Limited real production data
- Primary user research still pending
- No guaranteed access to commercial APIs
- Need to satisfy Software Engineering course outcomes

---

# 26. Scope Assumptions

The current scope assumes:

- A web application is sufficient for MVP users
- Customers can use common e-commerce interactions
- Artisans can operate a simple responsive dashboard
- Simulated payment is sufficient academically
- Custom-order workflow remains a core candidate
- Free/low-cost hosting can support the academic demo

These assumptions may require revision.

---

# 27. Scope Change Control

After this baseline, major scope changes should follow:

```text
Change Requested
      ↓
Requirement Change Issue
      ↓
Impact Analysis
      ↓
Review
      ↓
Approve / Reject
      ↓
Documentation Update
      ↓
Implementation
```

Impact analysis should consider:

- Requirements
- UI
- Backend
- Database
- API
- Security
- Testing
- Schedule

---

# 28. Example Scope Change

Example request:

> Add live chat between customer and artisan.

Required analysis:

User Problem  
→ Is it validated?

Technical Cost  
→ Real-time communication infrastructure

Schedule Impact  
→ Additional development/testing

Security Impact  
→ Private messaging/moderation

Decision:

Could be moved to future scope rather than automatically added.

---

# 29. Scope Protection Rule

The project will follow:

**Core Quality Before Feature Quantity**

No optional feature should reduce the quality of:

- Authentication
- Authorization
- Product management
- Order management
- Custom-order workflow
- Validation
- Testing
- Deployment

---

# 30. MVP Boundary Summary

## IN

```text
Responsive Web App
Customer
Artisan
Admin
Authentication
Authorization
Artisan Profile
Product Catalog
Search / Filtering
Cart
Checkout
Orders
Structured Custom Orders
Quotation
Approval
Order Status
Reviews
Basic Craft Context
Simulated Payment
```

## OPTIONAL

```text
Wishlist
Product Journey
QR Product Record
Digital Certificate
Simple Recommendation
```

## OUT

```text
Native Mobile App
Live Chat
Blockchain
Advanced AI
Mandatory Real Payment
Logistics Integration
ERP
Warehouse System
Government Certification
Advanced Analytics
```

---

# 31. Scope Baseline Decision

The current Craft BD scope is:

**FEASIBLE AND CONTROLLED**

provided that optional features remain secondary to the core workflow.

The scope remains **provisional** until primary user research confirms or challenges the current custom-order direction.

---

## Document Status

**Phase:** Phase 02 — Feasibility & Scope Analysis  
**Document:** Scope Baseline  
**Version:** 0.1  
**Status:** PROVISIONAL  
**Primary Research Dependency:** Open  
**Next Step:** Constraints, Dependencies & Assumptions Register
