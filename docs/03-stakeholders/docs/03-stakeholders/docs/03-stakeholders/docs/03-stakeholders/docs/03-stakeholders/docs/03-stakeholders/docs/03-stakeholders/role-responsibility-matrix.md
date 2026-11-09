# Craft BD — Role & Responsibility Matrix

## 1. Purpose

This document defines the current responsibilities and system-access boundaries of the major Craft BD roles.

It supports:

- Requirement engineering
- Role-based access control
- Use case modeling
- Security design
- UI/UX design
- Responsibility separation
- Testing

The matrix is provisional and may change after primary research and requirement finalization.

---

# 2. Core System Roles

The current MVP contains three primary application roles:

1. Customer
2. Artisan / Seller
3. Administrator

Other stakeholders such as:

- Academic Supervisor
- Project Team
- Regulatory Authorities

influence the project but are not normal application actors.

---

# 3. Responsibility Principle

Craft BD should follow:

```text
Right User
   ↓
Right Action
   ↓
Right Resource
```

Example:

Customer A  
→ Can view Customer A's private order

Customer A  
→ Cannot view Customer B's private order

Artisan A  
→ Can edit Artisan A's products

Artisan A  
→ Cannot edit Artisan B's products

Admin  
→ Can perform approved administrative actions

---

# 4. Customer Responsibilities

Customer is responsible for:

- Maintaining own account information
- Providing correct order information
- Providing accurate custom-order requirements
- Reviewing quotation details
- Approving or rejecting quotations
- Providing valid delivery information
- Following platform rules
- Submitting appropriate reviews

Customer is not responsible for:

- Managing other users
- Creating artisan products
- Modifying another customer's orders
- Issuing certificates
- Performing administrative moderation

---

# 5. Artisan Responsibilities

Artisan / Seller is responsible for:

- Maintaining own profile
- Maintaining own product information
- Providing accurate product details
- Reviewing assigned custom requests
- Providing quotations
- Updating relevant production/order status
- Managing stock where applicable
- Following agreed custom-order requirements

Artisan is not responsible for:

- Editing another artisan's products
- Managing unrelated customer accounts
- Approving own quotation on behalf of customer
- Performing unrestricted administrative actions
- Issuing platform-wide verification records unless explicitly authorized

---

# 6. Administrator Responsibilities

Administrator is responsible for platform governance.

Possible responsibilities include:

- User management
- Category management
- Content moderation
- Review moderation
- Exceptional account actions
- Platform configuration
- Verification/certificate management where approved

Administrator should not become responsible for every normal transaction.

Normal workflow should remain primarily between:

```text
Customer
    ↕
System
    ↕
Artisan
```

---

# 7. System Permission Matrix

| Capability | Customer | Artisan | Admin |
|---|---:|---:|---:|
| Register | Yes | Yes | Controlled |
| Login | Yes | Yes | Yes |
| Manage Own Profile | Yes | Yes | Yes |
| Browse Products | Yes | Yes | Yes |
| View Artisan Profile | Yes | Yes | Yes |
| Search / Filter | Yes | Yes | Yes |
| Create Product | No | Yes | Optional Admin |
| Edit Own Product | No | Yes | Yes |
| Edit Another Artisan Product | No | No | Administrative Only |
| Manage Categories | No | No | Yes |
| Add to Cart | Yes | No | No |
| Checkout | Yes | No | No |
| Place Standard Order | Yes | No | No |
| View Own Customer Orders | Yes | No | Administrative |
| View Relevant Seller Orders | No | Yes | Administrative |
| Submit Custom Request | Yes | No | No |
| View Own Custom Request | Yes | Assigned Artisan | Admin if required |
| Provide Quotation | No | Assigned Artisan | No |
| Approve Quotation | Request Owner | No | No |
| Reject Quotation | Request Owner | No | No |
| Update Production Status | No | Assigned Artisan | Administrative Override if justified |
| Submit Product Review | Eligible Customer | No | No |
| Moderate Review | No | No | Yes |
| Issue Platform Certificate | No | No | Authorized Admin |
| Manage Users | No | No | Yes |
| Moderate Content | No | No | Yes |

---

# 8. Ownership Rules

Authorization should consider both:

```text
Role
+
Resource Ownership
```

Role alone is not enough.

Example:

An artisan role may have permission to edit products.

But:

```text
Artisan A
   ↓
Product A
   ✅ Edit

Artisan A
   ↓
Product B owned by Artisan B
   ❌ Edit
```

---

# 9. Customer Ownership Rules

A customer should normally access:

- Own profile
- Own cart
- Own wishlist
- Own orders
- Own custom requests
- Quotations related to own requests

Customer must not access another customer's private transaction data.

---

# 10. Artisan Ownership Rules

An artisan should normally access:

- Own artisan profile
- Own products
- Custom requests assigned to them
- Orders containing their relevant products where business rules allow
- Quotations they created
- Production statuses they are responsible for

Artisan should not receive unnecessary customer private information.

---

# 11. Administrator Access Principle

Administrator access should follow:

**Minimum Necessary Administrative Privilege**

Admin should not automatically receive unlimited access merely because implementation is easier.

Administrative access must be justified by business need.

---

# 12. Custom-Order Responsibility Matrix

| Activity | Customer | Artisan | Admin |
|---|---|---|---|
| Create Request | Responsible | — | — |
| Provide Requirements | Responsible | Reviews | — |
| Review Request | — | Responsible | Monitor if needed |
| Create Quote | — | Responsible | — |
| Review Quote | Responsible | — | — |
| Approve Quote | Responsible | — | — |
| Begin Production | — | Responsible | — |
| Update Production Status | — | Responsible | Exceptional override |
| View Progress | Responsible | Responsible | Monitor |
| Complete Workflow | Confirm/View | Responsible | Exceptional handling |

---

# 13. Standard Order Responsibility Matrix

| Activity | Customer | Artisan | Admin |
|---|---|---|---|
| Select Product | Responsible | — | — |
| Maintain Product | — | Responsible | Moderate |
| Add to Cart | Responsible | — | — |
| Checkout | Responsible | — | — |
| Create Order | System / Customer Action | — | — |
| Prepare Product | — | Responsible | — |
| Update Relevant Status | View | Responsible | Exceptional handling |
| Review Product | Eligible Customer | — | Moderate |

---

# 14. RACI-Style Project Responsibility Matrix

RACI means:

**R — Responsible**  
Performs the work.

**A — Accountable**  
Ultimately owns the result.

**C — Consulted**  
Provides input.

**I — Informed**  
Receives updates.

---

# 15. Project-Level RACI

| Activity | Project Team | Faculty | Customer | Artisan |
|---|---|---|---|---|
| Product Discovery | A/R | C | C | C |
| User Research | A/R | C | R as participant | R as participant |
| Scope Definition | A/R | C | C | C |
| Requirements | A/R | C | C | C |
| Architecture | A/R | C | I | I |
| UI/UX | A/R | C | C | C |
| Development | A/R | I | I | I |
| Testing | A/R | C | C for UAT | C for UAT |
| Academic Review | R | A | I | I |
| Deployment | A/R | I | I | I |
| Documentation | A/R | C | I | I |

---

# 16. Important RACI Interpretation

RACI should not be confused with system permissions.

Example:

Faculty may be:

```text
Accountable / Consulted
```

for academic evaluation.

But faculty does not need:

```text
Admin Login
```

inside the Craft BD application.

---

# 17. Separation of Duties

Important activities should not be controlled by the same actor where this creates conflict.

Example:

```text
Artisan Creates Quotation
        ↓
Customer Approves Quotation
```

The artisan should not approve the quotation on behalf of the customer.

Similarly:

```text
Customer Writes Review
        ↓
Admin Moderates if necessary
```

Seller should not be able to delete legitimate negative reviews simply because the review is unfavorable.

---

# 18. Least Privilege Principle

Each role should receive only the permissions required to perform its responsibilities.

Example:

Customer needs:

```text
Create Order
```

but not:

```text
Manage Categories
```

Artisan needs:

```text
Manage Own Product
```

but not:

```text
Manage All Users
```

---

# 19. Sensitive Administrative Operations

High-risk admin actions may include:

- Deactivating users
- Removing content
- Changing verification records
- Issuing certificates
- Overriding order state

These actions should later receive:

- Authorization checks
- Confirmation where appropriate
- Logging / auditability

---

# 20. Role Conflict Example

Suppose an artisan asks:

> I want to change the customer's custom request after they submit it.

This creates integrity risk.

Better responsibility:

Customer  
→ Owns original submitted requirements

Artisan  
→ Reviews requirements

If change is required:

```text
Change Request
→ Customer Confirms
→ Updated Record
```

rather than silently modifying customer instructions.

---

# 21. Permission Test Examples

Future tests should include:

## Test 1

Customer A attempts to access Customer B's order.

Expected:

**Denied**

---

## Test 2

Artisan A attempts to edit Artisan B's product.

Expected:

**Denied**

---

## Test 3

Customer attempts to access admin category management.

Expected:

**Denied**

---

## Test 4

Artisan tries to start production before quotation approval.

Expected:

**Denied**

---

## Test 5

Eligible customer reviews completed purchased product.

Expected:

**Allowed**

---

# 22. Future Access-Control Model

Later security design may implement:

```text
Authentication
      ↓
Role Check
      ↓
Ownership Check
      ↓
Business Rule Check
      ↓
Allow / Deny
```

Example:

```text
Is user Artisan?
        ↓ Yes
Does Artisan own product?
        ↓ Yes
Is requested action permitted?
        ↓ Yes
ALLOW
```

---

# 23. Role-to-UML Mapping

Current likely UML actors:

```text
Customer
Artisan
Administrator
```

Possible external system actors only if integrations are implemented:

```text
Payment Service
Email Service
Logistics Service
```

These should not be added to UML merely because they could exist in the future.

---

# 24. Responsibility Design Risk

A major risk is giving administrators too many responsibilities because admin implementation appears convenient.

This may create:

- Operational bottlenecks
- Security risk
- Poor scalability
- Unrealistic workflows

Therefore:

```text
User-Owned Action
→ User

Governance Action
→ Admin
```

wherever practical.

---

# 25. Current Responsibility Decision

The MVP responsibility model should remain:

```text
CUSTOMER
Discover
Order
Customize
Approve
Review

ARTISAN
Present
Manage Product
Quote
Produce
Update

ADMIN
Govern
Moderate
Manage Exceptions
```

---

## Document Status

**Phase:** 03 — Stakeholder & User Analysis  
**Document:** Role & Responsibility Matrix  
**Status:** Provisional v0.1  
**Primary Research Dependency:** Open  
**Next Step:** Stakeholder Conflict Analysis
