# Craft BD — Functional Requirements Baseline Part 1

## 1. Purpose

This document defines the formal functional requirements for the first group of Craft BD modules:

Authentication → User/Profile → Artisan → Product → Product Discovery

Each requirement includes a unique ID, source, priority, evidence status, requirement status, and acceptance criteria.

This is a Phase 04 baseline and may be revised through requirement change control.

---

# 2. Requirement Status Legend

| Status | Meaning |
|---|---|
| DRAFT | Written but not yet formally approved |
| PROVISIONAL | Depends on unresolved user validation |
| APPROVED | Accepted into the requirement baseline |
| DEFERRED | Valid idea but outside current release |
| REJECTED | Not included |
| DEPRECATED | Previously approved but later retired |

---

# 3. Priority Legend

| Priority | Meaning |
|---|---|
| Must | Required for MVP |
| Should | Important but not essential for first release |
| Could | Implement only if time permits |
| Won't / Deferred | Excluded from current MVP |

---

# 4. Authentication Requirements

## FR-AUTH-001 — Customer Registration

**Statement**

The system shall allow a new user to register a customer account using the required account information.

**Source:** STK-01 Customer  
**Priority:** Must  
**Evidence:** DERIVED / Standard Platform Requirement  
**Status:** DRAFT

**Acceptance Criteria**

Given a visitor who does not already have an account, when valid required registration information is submitted, then the system shall create a customer account and prevent registration when required information is invalid or an account conflict exists.

---

## FR-AUTH-002 — Artisan Registration

**Statement**

The system shall allow a new user to register an artisan/seller account using the required account information.

**Source:** STK-02 Artisan  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

Given a visitor submitting valid artisan registration information, when registration succeeds, then an artisan account shall be created and associated with an artisan profile.

---

## FR-AUTH-003 — User Login

**Statement**

The system shall allow a registered user to authenticate using valid credentials.

**Source:** STK-01, STK-02, STK-03  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

Valid credentials shall allow authentication. Invalid credentials shall not authenticate the user. Successful authentication shall allow access according to the user's authorized role.

---

## FR-AUTH-004 — User Logout

**Statement**

The system shall allow an authenticated user to terminate their current authenticated session.

**Source:** STK-01, STK-02, STK-03  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

After logout, protected functionality shall no longer be accessible through the terminated authentication session.

---

## FR-AUTH-005 — Role Recognition

**Statement**

The system shall identify an authenticated user's assigned role and use that role when determining permitted functionality.

**Source:** STK-03, STK-04  
**Priority:** Must  
**Evidence:** SECURITY / DERIVED  
**Status:** DRAFT

**Supported MVP Roles**

| Role | Code |
|---|---|
| Customer | CUSTOMER |
| Artisan / Seller | ARTISAN |
| Administrator | ADMIN |

Detailed authorization rules will be specified separately under Security Requirements.

---

# 5. Customer Profile Requirements

## FR-USER-001 — View Own Profile

**Statement**

The system shall allow an authenticated customer to view their own profile information.

**Source:** STK-01 Customer  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

A customer shall be able to access their own profile but shall not receive another customer's private profile data through the same functionality.

---

## FR-USER-002 — Update Own Profile

**Statement**

The system shall allow an authenticated customer to update supported fields of their own profile.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

Valid profile changes shall be stored for the authenticated customer. Invalid values shall be rejected. A customer shall not modify another customer's profile.

---

# 6. Artisan Profile Requirements

## FR-ART-001 — Create Artisan Profile

**Statement**

The system shall allow an artisan account to maintain an artisan profile containing the supported professional information.

**Source:** STK-02 Artisan  
**Priority:** Must  
**Evidence:** SECONDARY_SUPPORTED  
**Status:** DRAFT

Supported profile information may include:

Name, location/region, expertise, experience, biography and profile image.

**Acceptance Criteria**

An artisan shall be able to save valid supported profile information, and the saved information shall remain associated with that artisan account.

---

## FR-ART-002 — View Artisan Profile

**Statement**

The system shall allow users to view the public profile of an artisan associated with Craft BD products.

**Source:** STK-01 Customer, STK-02 Artisan  
**Priority:** Must  
**Evidence:** SECONDARY_SUPPORTED  
**Status:** DRAFT

**Acceptance Criteria**

When a valid public artisan profile is requested, the system shall display its permitted public information without exposing private account or authentication information.

---

## FR-ART-003 — Update Own Artisan Profile

**Statement**

The system shall allow an authenticated artisan to update supported information in their own artisan profile.

**Source:** STK-02  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

An artisan shall be able to modify their own permitted profile fields but shall not modify another artisan's profile.

---

## FR-ART-004 — Display Artisan Products

**Statement**

The system shall display products associated with an artisan from the artisan's public profile where such products are available for display.

**Source:** STK-01, STK-02  
**Priority:** Must  
**Evidence:** SECONDARY_SUPPORTED  
**Status:** DRAFT

**Acceptance Criteria**

Selecting an artisan profile shall allow a user to identify the products currently associated with that artisan according to product visibility rules.

---

# 7. Product Management Requirements

## FR-PROD-001 — Create Product

**Statement**

The system shall allow an authenticated artisan to create a product associated with their own artisan account.

**Source:** STK-02 Artisan  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

A product shall contain the required product fields defined by the approved data requirements.

**Acceptance Criteria**

A valid product submission shall create a product associated with the authenticated artisan. Missing or invalid mandatory information shall prevent successful creation.

---

## FR-PROD-002 — Edit Own Product

**Statement**

The system shall allow an authenticated artisan to modify permitted information for a product they own.

**Source:** STK-02  
**Priority:** Must  
**Evidence:** DERIVED + SECURITY  
**Status:** DRAFT

**Acceptance Criteria**

An artisan owning the product shall be able to save valid changes. An artisan who does not own the product shall not be allowed to modify it.

---

## FR-PROD-003 — Deactivate Own Product

**Statement**

The system shall allow an authenticated artisan to deactivate an owned product so that it is no longer available for normal customer ordering.

**Source:** STK-02  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

After successful deactivation, the product shall no longer be available for new normal customer orders while historical records referencing the product shall remain preserved where required.

---

## FR-PROD-004 — Maintain Product Price

**Statement**

The system shall allow an authorized artisan to define and update the current selling price of an owned product.

**Source:** STK-02  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

The system shall reject invalid price values and display the valid current price for applicable product interactions.

---

## FR-PROD-005 — Maintain Product Stock

**Statement**

The system shall allow an authorized artisan to maintain the available stock quantity of an owned standard product where inventory tracking applies.

**Source:** STK-02  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

Stock quantity shall not accept invalid negative values, and availability shall reflect the stored valid stock information.

---

## FR-PROD-006 — Upload Product Images

**Statement**

The system shall allow an authenticated artisan to upload supported images for an owned product subject to file-validation rules.

**Source:** STK-02  
**Priority:** Must  
**Evidence:** DERIVED  
**Related Security Area:** SR-FILE  
**Status:** DRAFT

**Acceptance Criteria**

Supported valid images shall be associated with the product. Unsupported or invalid uploads shall be rejected according to file-security requirements.

---

## FR-PROD-007 — Assign Product Category

**Statement**

The system shall require a product to be associated with an available product category according to the approved category model.

**Source:** STK-01, STK-02, STK-03  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

A product shall not reference an invalid category, and valid category information shall be available for product discovery.

---

## FR-PROD-008 — Store Product Description

**Statement**

The system shall allow an artisan to provide a description for an owned product.

**Source:** STK-01, STK-02  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

A valid product description shall be stored and displayed on the relevant product-details view.

---

## FR-PROD-009 — Store Product Material Information

**Statement**

The system shall allow supported material information to be associated with a product.

**Source:** STK-01 Customer  
**Priority:** Should  
**Evidence:** SECONDARY_SUPPORTED  
**Status:** DRAFT

**Acceptance Criteria**

Where material information exists, users shall be able to view it through the relevant product information interface.

---

## FR-PROD-010 — Store Craft Type / Region Information

**Statement**

The system shall allow supported craft-type and region information to be associated with a product where applicable.

**Source:** STK-01, product-discovery analysis  
**Priority:** Should  
**Evidence:** SECONDARY_SUPPORTED  
**Status:** DRAFT

**Acceptance Criteria**

Valid stored craft-type or region information shall be retrievable for relevant product display or filtering functionality.

---

# 8. Product Discovery Requirements

## FR-DISC-001 — Browse Available Products

**Statement**

The system shall allow users to browse products that are currently available for public display.

**Source:** STK-01 Customer  
**Priority:** Must  
**Evidence:** SECONDARY_SUPPORTED  
**Status:** DRAFT

**Acceptance Criteria**

The product catalog shall display eligible products and shall exclude products that are not currently permitted for normal public display.

---

## FR-DISC-002 — View Product Details

**Statement**

The system shall allow users to view the supported public details of an available product.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** SECONDARY_SUPPORTED  
**Status:** DRAFT

The product-details view may contain:

Product name, images, price, description, stock/availability, category, material, artisan and supported craft information.

**Acceptance Criteria**

Requesting a valid available product shall display its permitted information and a relationship to the relevant artisan where applicable.

---

## FR-DISC-003 — Browse Products by Category

**Statement**

The system shall allow users to browse products associated with a selected available category.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

Selecting a valid category shall return products associated with that category according to product visibility rules.

---

## FR-DISC-004 — Search Products

**Statement**

The system shall allow users to search available products using supported searchable product information.

**Source:** STK-01  
**Priority:** Must  
**Evidence:** SECONDARY_SUPPORTED  
**Status:** DRAFT

Initial supported search may include product name and other approved searchable fields.

**Acceptance Criteria**

A search containing a supported matching term shall return relevant eligible product records. Products not permitted for public display shall not be exposed through search.

---

## FR-DISC-005 — Filter Products by Category

**Statement**

The system shall allow users to filter available products using product category.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** SECONDARY_SUPPORTED  
**Status:** DRAFT

**Acceptance Criteria**

Applying a valid category filter shall restrict the result set to products belonging to the selected category.

---

## FR-DISC-006 — Filter Products by Price Range

**Statement**

The system shall allow users to filter available products using a supported price range.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** DERIVED  
**Status:** DRAFT

**Acceptance Criteria**

Applying a valid minimum and/or maximum price shall exclude products outside the requested supported range.

---

## FR-DISC-007 — Filter Products by Material

**Statement**

The system shall allow users to filter available products by supported material information where material data is available.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** PROVISIONAL / SECONDARY_SUPPORTED  
**Status:** PROVISIONAL

**Acceptance Criteria**

Selecting a supported material shall restrict results to eligible products associated with that material.

---

## FR-DISC-008 — Filter Products by Craft Type

**Statement**

The system shall allow users to filter products using supported craft-type information where such information is available.

**Source:** STK-01  
**Priority:** Should  
**Evidence:** PROVISIONAL  
**Status:** PROVISIONAL

**Acceptance Criteria**

Selecting a supported craft type shall return eligible products associated with that craft type.

---

# 9. Craft Context Requirements

These requirements remain more dependent on primary user validation.

## FR-CRAFT-001 — View Basic Craft Context

**Statement**

The system shall allow users to view available contextual craft information associated with a relevant product or craft type.

**Source:** STK-01 Customer  
**Priority:** Should  
**Evidence:** PROVISIONAL / SECONDARY_SUPPORTED  
**Status:** PROVISIONAL

Possible information may include:

Origin, materials, technique, traditional use and cultural context.

**Acceptance Criteria**

Where approved craft-context information exists, the system shall make that information accessible from the relevant product/craft experience.

---

## FR-CRAFT-002 — Maintain Craft Context

**Statement**

The system shall allow an authorized role to create or update supported craft-context information according to the approved content-ownership policy.

**Source:** STK-02 / STK-03  
**Priority:** Should  
**Evidence:** DERIVED from FR-CRAFT-001  
**Status:** PROVISIONAL

**Acceptance Criteria**

Only an authorized role shall be able to create or modify shared craft-context information.

The exact content owner will be finalized before implementation.

---

# 10. Deferred Discovery Requirements

The following capabilities are not included in the current core functional baseline.

| Capability | Decision | Reason |
|---|---|---|
| Product comparison | Deferred | Not required for core MVP |
| Wishlist | Could / Optional | Standard convenience feature |
| Advanced recommendation | Deferred | Insufficient behavioral data |
| Gift recommendation | Deferred | Weak core evidence |
| Product journey | Optional | Scope dependent |

If later approved, these features will receive their own stable requirement IDs.

---

# 11. Cross-Requirement Business Rules

The following business rules will be formalized separately.

**Product Ownership**

An artisan shall not modify another artisan's product through normal artisan functionality.

**Product Visibility**

Only products satisfying approved visibility rules may appear in public discovery.

**Valid Category**

Products must reference valid available categories.

**Stock Integrity**

Invalid negative inventory values are not permitted.

**Public vs Private Information**

Product and artisan discovery shall expose only information classified for public display.

---

# 12. Security Dependencies

This requirement group depends on future security requirements for:

Authentication security → authorization → ownership validation → input validation → file-upload security → privacy boundaries.

Functional permissions described in this document do not replace server-side security requirements.

---

# 13. Traceability Examples

| Stakeholder / Need | Functional Requirement |
|---|---|
| STK-01 — Discover products | FR-DISC-001 |
| STK-01 — Search products | FR-DISC-004 |
| STK-01 — Understand artisan | FR-ART-002 |
| STK-02 — Present artisan identity | FR-ART-001 |
| STK-02 — Manage products | FR-PROD-001 through FR-PROD-010 |
| Customer craft-context hypothesis | FR-CRAFT-001 |

---

# 14. Part 1 Requirement Count

Current Part 1 formal draft contains:

| Module | Requirements |
|---|---:|
| Authentication | 5 |
| Customer Profile | 2 |
| Artisan | 4 |
| Product | 10 |
| Discovery | 8 |
| Craft Context | 2 |
| **Total** | **31** |

The number of requirements itself is not a quality metric.

Requirements may later be revised, merged, deferred, or expanded based on validation and SRS review.

---

# 15. Current Validation Boundary

Requirements such as authentication, product management, and basic product discovery can continue into detailed system design.

Requirements involving cultural-context importance remain provisional.

Primary customer and artisan research may alter their priority.

---

# 16. Requirement Quality Check

The Part 1 requirements are written to support:

Unique identification  
→ clear actor/action  
→ priority  
→ evidence status  
→ acceptance criteria  
→ future test mapping

Future formal testing should trace these requirements to corresponding test cases such as:

`TC-AUTH-NNN`, `TC-PROD-NNN`, `TC-DISC-NNN`.

---

## Document Status

**Phase:** 04 — Requirement Finalization  
**Document:** Functional Requirements Baseline Part 1  
**Modules:** AUTH, USER, ART, PROD, DISC, CRAFT  
**Status:** Draft v0.1  
**Primary Research Dependency:** Partial  
**Next Step:** Commerce & Standard Order Functional Requirements
