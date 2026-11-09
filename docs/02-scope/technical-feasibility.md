# Craft BD — Technical Feasibility Analysis

## 1. Purpose

This document evaluates whether the proposed Craft BD capabilities can be realistically designed, implemented, tested, and deployed within the scope of an academic Software Engineering project.

The analysis considers:

- Implementation complexity
- Technical dependency
- Security risk
- Data requirements
- Integration requirements
- Team effort
- MVP suitability

The current assessment is provisional because primary user validation is still pending.

---

# 2. Technical Feasibility Scale

Each capability is classified as:

### Low Complexity
Can be implemented using common web-development patterns with limited technical risk.

### Moderate Complexity
Requires multiple modules, business rules, state management, or careful integration.

### High Complexity
Requires external services, advanced algorithms, significant security considerations, or substantial development effort.

### Not Recommended for MVP
Technically possible, but the cost or risk is not justified for the first academic release.

---

# 3. Overall Architecture Feasibility

Craft BD can be implemented as a standard full-stack web application.

Recommended high-level architecture:

Frontend  
→ REST API  
→ Backend Application  
→ Relational Database

A modular monolithic architecture is currently considered more suitable than microservices because:

- The development team is small
- The application modules are closely related
- Deployment should remain manageable
- Testing is easier
- Infrastructure cost is lower
- Microservices would introduce unnecessary operational complexity

Final architecture will be decided during the Architecture Design phase.

---

# 4. Feature Feasibility Matrix

| Capability | Complexity | Main Dependency | Technical Risk | MVP Recommendation |
|---|---|---|---|---|
| User Registration & Login | Moderate | Authentication system | Security | Keep |
| Role-Based Access Control | Moderate | Auth + backend authorization | High if poorly implemented | Keep |
| Product Catalog | Low | Database | Low | Keep |
| Search & Filtering | Low–Moderate | Database queries | Low | Keep |
| Artisan Profile | Low | User/product relationship | Low | Keep |
| Craft Story | Low | Content management | Low | Keep |
| Product Journey | Low | Structured content | Low | Keep if scope allows |
| Wishlist | Low | User-product relationship | Low | Supporting |
| Shopping Cart | Moderate | Product/stock data | Medium | Keep |
| Checkout | Moderate | Order workflow | Medium | Keep |
| Order Tracking | Moderate | Order state management | Medium | Keep |
| Reviews & Ratings | Moderate | Order verification | Medium | Keep |
| Structured Custom Order | Moderate | Workflow + database state | Medium | High Priority |
| Artisan Quotation | Moderate | Custom-order module | Medium | High Priority |
| Customer Approval | Moderate | State-transition rules | Medium | High Priority |
| Custom Order Progress | Moderate | State machine | Medium | High Priority |
| QR Product Record | Moderate | Unique identifier + URL | Medium | Feasible |
| Digital Certificate Record | Moderate | Certificate model + admin workflow | Medium | Feasible |
| Real Payment Gateway | High | External payment provider | High | Optional / Later |
| Recommendation System | Moderate–High | User/product data | Medium | Reduce Scope |
| Gift Recommendation | Moderate | Rule/recommendation logic | Low–Medium | Future |
| Events / Workshops | Moderate | Additional module | Medium | Future |
| Live Chat | High | Real-time infrastructure | Medium–High | Not MVP |
| Blockchain Verification | High | Blockchain infrastructure | High | Reject for MVP |
| Advanced AI Recommendation | High | Dataset + model pipeline | High | Not MVP |
| Logistics API Integration | High | External provider | High | Future |

---

# 5. Authentication Feasibility

## Proposed Capability

Users should be able to register and log in.

Planned roles:

- Customer
- Artisan
- Administrator

## Technical Feasibility

**Feasible**

Recommended pattern:

User  
→ Authentication  
→ Server validates identity  
→ Role identified  
→ Authorized resource access

Important:

Role checking must occur on the backend.

Frontend hiding alone is not authorization.

## Complexity

Moderate

## Recommendation

**MVP — Required**

---

# 6. Product Catalog Feasibility

Products may contain:

- Name
- Category
- Price
- Stock
- Description
- Images
- Artisan
- Materials
- Craft information

## Technical Feasibility

**Highly feasible**

This is standard relational application functionality.

Possible relationship:

Artisan  
→ has many Products

Product  
→ belongs to Category

Product  
→ has Images

## Complexity

Low

## Recommendation

**MVP — Required**

---

# 7. Artisan Profile Feasibility

The existing concept includes artisan information such as:

- Location
- Experience
- Expertise
- Biography
- Stories
- Products

## Technical Feasibility

**Highly feasible**

The artisan can be represented as a user role with an associated artisan profile.

Possible structure:

User  
→ ArtisanProfile  
→ Products

## Complexity

Low

## Recommendation

**MVP — Keep**

---

# 8. Craft Story Feasibility

Potential information:

- Origin
- History
- Materials
- Techniques
- Traditional uses
- Cultural meaning

## Technical Feasibility

**Highly feasible**

This is primarily structured content linked to a craft or product.

No advanced technology is required.

## Complexity

Low

## Risk

The main risk is not technical.

The risk is whether users value the information enough to justify the implementation effort.

## Recommendation

**Technically feasible — product value still requires validation**

---

# 9. Product Journey Feasibility

Possible stages:

Raw Material  
→ Design  
→ Making  
→ Finishing  
→ Quality Check  
→ Final Product

## Technical Feasibility

**Feasible**

Possible implementation:

Product  
→ ProductJourney  
→ Multiple JourneyStages

Each stage may include:

- Stage name
- Description
- Image
- Sequence number

## Complexity

Low–Moderate

## Recommendation

**Keep only if scope remains manageable**

---

# 10. Structured Custom Order Feasibility

This is currently one of the strongest proposed Craft BD workflows.

Possible data:

- Product type
- Design
- Color
- Size
- Material
- Quantity
- Reference image
- Instructions

## Technical Feasibility

**Feasible**

The workflow should be implemented using controlled order states.

Example:

REQUESTED  
→ UNDER_REVIEW  
→ QUOTED  
→ CUSTOMER_APPROVED  
→ IN_PRODUCTION  
→ QUALITY_CHECK  
→ READY_TO_SHIP  
→ SHIPPED  
→ DELIVERED

Alternative states may include:

- REJECTED
- CANCELLED

## Complexity

Moderate

## Main Technical Requirements

- Database state management
- Role authorization
- File upload
- Quotation
- Status transitions
- Audit timestamps
- Validation

## Recommendation

**Strong MVP candidate, subject to final user validation**

---

# 11. Custom Quotation Feasibility

Artisan may provide:

- Proposed price
- Notes
- Estimated completion date

Customer can:

- Approve
- Reject

## Technical Feasibility

**Feasible**

Example rule:

A custom order cannot enter production before the customer approves the quotation.

## Complexity

Moderate

## Recommendation

**Include with custom-order module**

---

# 12. QR Product Record Feasibility

QR functionality does not require complex QR technology.

Recommended implementation:

QR Code  
→ Contains verification URL / unique token  
→ User opens Craft BD verification page  
→ Backend retrieves product record

Example:

`/verify/{unique-code}`

The QR code should not contain sensitive product data directly.

## Complexity

Moderate

## Main Risks

- Predictable identifiers
- Invalid/expired records
- Misleading authenticity claims
