# Craft BD — Operational Feasibility Analysis

## 1. Purpose

This document evaluates whether Craft BD can be practically operated by its intended users and administrators.

Operational feasibility focuses on:

- User ability to understand the system
- Workflow simplicity
- Adoption barriers
- Training requirements
- Administrative effort
- Day-to-day operational sustainability
- Role responsibilities
- Potential user resistance

The current assessment is provisional because real primary user validation is still pending.

---

# 2. Primary Operational Users

Craft BD currently has three main operational roles:

1. Customer
2. Artisan / Craft Seller
3. Administrator

The Customer and Artisan are the primary product users.

The Administrator supports governance and platform operation.

---

# 3. Customer Operational Feasibility

## Main Customer Activities

Customers may need to:

- Register and log in
- Browse products
- Search and filter
- View artisan information
- View craft information
- Add products to cart
- Place orders
- Submit custom-order requests
- Review quotations
- Approve or reject quotations
- Track order progress
- View QR-linked product records
- Submit reviews

## Operational Assessment

**Feasible**

Most customer activities follow familiar e-commerce patterns.

The main operational risk is not basic shopping.

The main risk is making the platform too complex by presenting too much information or too many actions on one screen.

---

# 4. Customer Usability Recommendations

The customer interface should follow a simple journey:

Discover  
→ Understand  
→ Decide  
→ Order  
→ Track

Avoid forcing customers to navigate through unnecessary screens.

Recommended principles:

- Clear navigation
- Simple search
- Mobile-friendly design
- Visible pricing
- Simple product details
- Clear custom-order steps
- Easy order-status visibility
- Clear call-to-action buttons

---

# 5. Customer Custom-Order Workflow

The custom-order process should be understandable without training.

Recommended flow:

Customer selects custom order  
→ Enters requirements  
→ Submits request  
→ Artisan reviews  
→ Artisan sends quotation  
→ Customer reviews quotation  
→ Customer approves / rejects  
→ Production begins  
→ Customer tracks status

## Operational Feasibility

**Feasible**

## Main Risk

Users may become confused if too many statuses are shown.

Therefore, backend states may be detailed while the customer interface uses simplified labels.

Example:

Backend:

REQUESTED  
UNDER_REVIEW  
QUOTED  
CUSTOMER_APPROVED  
IN_PRODUCTION  
QUALITY_CHECK  
READY_TO_SHIP  
SHIPPED  
DELIVERED

Customer-facing:

Request Sent  
→ Quote Ready  
→ Approved  
→ In Production  
→ Ready  
→ Shipped  
→ Delivered

This reduces complexity.

---

# 6. Artisan Operational Feasibility

## Main Artisan Activities

Artisans may need to:

- Create or maintain profile information
- Add products
- Update product information
- Manage stock
- Receive custom-order requests
- Review customer specifications
- Provide quotations
- Update production status
- Manage assigned orders
- Provide product journey information
- Maintain certificate-related information when permitted

## Operational Assessment

**Feasible with usability constraints**

Artisans may have different levels of technical experience.

Therefore, the artisan dashboard must remain simple.

---

# 7. Artisan Adoption Risks

Possible operational barriers include:

- Limited familiarity with complex dashboards
- Preference for Facebook / Messenger
- Limited time for digital administration
- Mobile-first usage
- Difficulty maintaining detailed product information
- Repeated data entry
- Poor internet connectivity in some situations

These risks require usability testing.

---

# 8. Artisan UX Recommendations

The Artisan Dashboard should prioritize:

## Dashboard Home

Show only important information:

- Pending custom requests
- Quotations waiting for response
- Active orders
- Products
- Notifications

Avoid showing too many analytics in the initial MVP.

---

## Product Creation

Recommended product form:

Basic Information  
→ Price  
→ Stock  
→ Images  
→ Craft Information

Optional information should not block product publishing unless required.

---

## Custom Order Management

Recommended structure:

Request List  
→ Open Request  
→ View Customer Requirements  
→ Provide Quote  
→ Update Status

This is operationally simpler than relying on multiple unrelated screens.

---

# 9. Mobile Usability

Mobile compatibility should be treated as important.

Possible artisan behavior may include:

Phone  
→ Product photo  
→ Upload  
→ Update product  
→ Respond to customer

Therefore, the interface should not assume desktop-only usage.

## Recommendation

Responsive web application.

A separate native mobile application is not required for the MVP.

---

# 10. Administrator Operational Feasibility

## Main Administrator Activities

The Administrator may need to:

- Manage user accounts
- Review artisan accounts
- Manage categories
- Monitor product information
- Moderate inappropriate content
- Manage reports
- Issue or approve certificate records
- Manage cultural content
- Monitor platform activity

## Operational Assessment

**Feasible**

However, admin responsibilities should be limited.

An academic project should avoid creating unnecessary manual approval for every normal action.

---

# 11. Admin Workload Risk

Example of poor design:

Every product  
→ Admin approval  
→ Every update  
→ Admin approval  
→ Every order  
→ Admin approval

This creates unnecessary operational bottlenecks.

Recommended approach:

Admin should focus on:

- Governance
- Moderation
- Exceptional actions
- Verification-related actions
- User-management issues

Normal customer-artisan interactions should operate without constant admin intervention.

---

# 12. Artisan Onboarding

A new artisan may need:

1. Create account
2. Select Artisan role
3. Complete artisan profile
4. Provide required information
5. Begin adding products

If later verification is required:

Registration  
→ Profile Submission  
→ Admin Review  
→ Verified Artisan

## Recommendation

Do not design complex identity-verification requirements until the project determines what level of verification is actually required.

---

# 13. Customer Onboarding

Customer onboarding should remain minimal.

Possible flow:

Visit Platform  
→ Browse Without Login  
→ Login Required for Action

Login may be required for:

- Wishlist
- Cart persistence
- Orders
- Custom requests
- Reviews

## Recommendation

Allow public browsing where possible.

Do not force registration merely to view products.

---

# 14. Operational Role Separation

Recommended responsibility:

| Activity | Customer | Artisan | Admin |
|---|---|---|---|
| Browse Products | Yes | Yes | Yes |
| Purchase Product | Yes | No | No |
| Create Product | No | Yes | Optional |
| Edit Own Product | No | Yes | Yes |
| Submit Custom Request | Yes | No | No |
| Provide Quotation | No | Yes | No |
| Approve Quotation | Yes | No | No |
| Manage Own Orders | Yes | Yes | Monitor |
| Submit Review | Yes | No | No |
| Moderate Review | No | No | Yes |
| Issue Certificate | No | No | Yes / Authorized Role |
| Manage Users | No | No | Yes |

---

# 15. Training Requirements

## Customer

Expected training:

**None**

The interface should be self-explanatory.

---

## Artisan

Expected training:

**Minimal**

Possible support:

- Simple onboarding guide
- Tooltips
- Example product
- Short user guide

---

## Administrator

Expected training:

**Moderate**

Admin should understand:

- User roles
- Content-management rules
- Verification process
- Moderation responsibilities
- Security considerations

---

# 16. Support Requirements

For the academic MVP, support can remain simple.

Possible support features:

- FAQ
- Basic help pages
- Contact form
- Clear error messages

Live customer-support chat is not required.

---

# 17. Notification Feasibility

Notifications may help operational workflows.

Examples:

Customer:

- Quotation received
- Order approved
- Production started
- Order shipped

Artisan:

- New custom request
- Quotation approved
- Customer cancelled request

## MVP Recommendation

Use:

- In-app notification
or
- Simple status indicators

Email notification may be added if practical.

Real-time push notifications are not required.

---

# 18. Content Management Feasibility

Craft BD contains content beyond products:

- Craft stories
- Artisan biographies
- Production journeys
- Cultural information

This creates a content-maintenance responsibility.

## Operational Risk

Outdated or incorrect cultural/product information may reduce trust.

## Recommendation

Define ownership.

Example:

Artisan  
→ Own biography / product information

Admin  
→ Shared cultural content / moderation

---

# 19. Product Record / Certificate Operations

If certificate records are included:

Product  
→ Verification Review  
→ Certificate Issued  
→ QR Linked

## Operational Question

Who has authority to issue certificates?

For the MVP:

Recommended authority:

**Administrator**

This avoids artisans issuing their own platform verification records without oversight.

---

# 20. Operational Risks

| ID | Risk | Impact | Mitigation |
|---|---|---|---|
| OR-01 | Artisan finds dashboard too complex | High | Simple mobile-friendly UX |
| OR-02 | Users continue using Messenger instead | High | Make structured workflow clearly easier |
| OR-03 | Too many order statuses confuse users | Medium | Simplified user-facing status |
| OR-04 | Admin workload becomes too large | Medium | Minimize unnecessary approval steps |
| OR-05 | Product data becomes outdated | Medium | Allow easy editing |
| OR-06 | Cultural content is inaccurate | Medium | Content ownership / review |
| OR-07 | Custom requests contain incomplete data | High | Required structured fields |
| OR-08 | Customer forgets quotation response | Medium | Clear pending-action status |

---

# 21. Adoption Risk

One of the biggest risks is:

> Users may prefer their existing communication channels even if Craft BD provides a structured workflow.

Therefore, Craft BD should not make the workflow more difficult than Messenger.

The product should provide clear benefits such as:

- Requirements stored together
- Clear quotation
- Visible approval
- Order status
- Product record

---

# 22. Operational Success Indicators

The MVP should allow a test user to complete key workflows without developer assistance.

## Customer Task

Find product  
→ Understand product/artisan  
→ Submit custom request  
→ Approve quotation  
→ Track status

## Artisan Task

View request  
→ Understand requirements  
→ Provide quotation  
→ Update production status

## Admin Task

Manage required platform information and verification actions.

If users cannot complete these independently, the workflow requires redesign.

---

# 23. Operational Feasibility Summary

## Customer Operation

**Feasible**

Minimal training required.

## Artisan Operation

**Feasible with strong usability requirements**

Mobile-friendly and simplified workflows are important.

## Administrator Operation

**Feasible**

Admin workload should remain controlled.

---

# 24. Operational Recommendation

Craft BD should prioritize:

**Simple Workflow  
+ Clear Roles  
+ Mobile-Friendly Design  
+ Minimal Repetition**

over:

**Complex Dashboards  
+ Excessive Approval  
+ Too Many Features**

---

## Feasibility Decision

**Overall Operational Feasibility:** FEASIBLE

### Conditions

- User interface must remain simple
- Artisan workflows must support mobile usage
- Admin responsibilities must be controlled
- Custom-order workflow must reduce rather than increase operational effort
- Real user testing should validate usability

---

## Document Status

**Phase:** 02 — Feasibility & Scope Analysis  
**Document:** Operational Feasibility  
**Status:** Draft v0.1  
**Next Step:** Economic Feasibility Analysis
