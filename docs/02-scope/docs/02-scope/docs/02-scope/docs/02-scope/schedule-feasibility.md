# Craft BD — Schedule Feasibility Analysis

## 1. Purpose

This document evaluates whether Craft BD can be completed within a realistic academic project timeline.

Schedule feasibility considers:

- Product-discovery work
- Requirements engineering
- Software design
- Development
- Testing
- Deployment
- Documentation
- Team capacity
- Feature dependencies
- Risk of scope expansion

The schedule is currently expressed using relative project weeks because the final academic submission date has not yet been locked in this document.

---

# 2. Scheduling Principle

Craft BD should follow:

Problem Definition  
→ Requirements  
→ Design  
→ Development  
→ Integration  
→ Testing  
→ Deployment  
→ Final Documentation

Development should not begin before the core requirements and architecture are sufficiently stable.

However, lightweight prototyping may occur earlier where needed for validation.

---

# 3. Recommended Delivery Strategy

The recommended development strategy is:

**Incremental + Sprint-Based Development**

Instead of:

Build Everything  
→ Test at the End

Craft BD should use:

Small Scope  
→ Build  
→ Test  
→ Review  
→ Integrate  
→ Continue

---

# 4. Proposed High-Level Schedule

A realistic academic schedule can be organized into approximately:

**12–14 working weeks**

The exact dates should be mapped to the university calendar later.

---

# 5. Phase Timeline

| Week | Main Activity | Output |
|---|---|---|
| Week 1 | Product Discovery | Problem hypotheses, research |
| Week 2 | Feasibility & Scope | MVP scope baseline |
| Week 3 | Stakeholder + Requirement Finalization | Final requirements |
| Week 4 | SRS + Use Cases | SRS baseline |
| Week 5 | UML + UI/UX | System models + wireframes |
| Week 6 | Architecture + Database + API | Technical design |
| Week 7 | Sprint 1 Development | Authentication + roles |
| Week 8 | Sprint 2 Development | Artisan + product modules |
| Week 9 | Sprint 3 Development | Cart + order workflow |
| Week 10 | Sprint 4 Development | Custom-order workflow |
| Week 11 | Sprint 5 Development | QR / certificate / reviews |
| Week 12 | Integration + Testing | Stable integrated build |
| Week 13 | UAT + Bug Fixing | Release candidate |
| Week 14 | Deployment + Documentation | Final release |

---

# 6. Important Schedule Dependency

The following activities depend on earlier decisions.

Example:

Problem Definition  
↓  
Requirement Finalization  
↓  
Database Design  
↓  
API Design  
↓  
Implementation

Therefore, major changes to requirements after development begins may cause schedule delay.

---

# 7. Sprint Structure

Recommended sprint length:

**1 week for academic tracking**

or

**2 weeks if the academic timeline allows**

For this project, one-week development milestones may provide clearer progress visibility.

---

# 8. Development Sprint Proposal

## Sprint 1 — Identity & Access

Deliver:

- Registration
- Login
- Customer role
- Artisan role
- Admin role
- Basic authorization

Dependency:

- User model
- Security design

---

## Sprint 2 — Artisan & Product Discovery

Deliver:

- Artisan profile
- Product creation
- Product listing
- Search
- Filter
- Product details
- Craft information

Dependency:

- Authentication
- Database schema

---

## Sprint 3 — Commerce Workflow

Deliver:

- Wishlist
- Cart
- Checkout
- Order creation
- Order status

Dependency:

- Product module

---

## Sprint 4 — Custom Order

Deliver:

- Custom request
- Reference image
- Artisan review
- Quotation
- Customer approval
- Status workflow

Dependency:

- Customer
- Artisan
- Product
- File upload

---

## Sprint 5 — Product Record & Trust

Deliver:

- Reviews
- QR-linked product record
- Certificate record
- Verification page

Dependency:

- Product
- Order
- Admin

---

# 9. Features That Threaten the Schedule

The following features may significantly increase delivery time:

- Real payment gateway
- Advanced recommendation model
- Live chat
- Blockchain verification
- External logistics integration
- Complex workshop/event module
- Advanced analytics
- Mobile application

These should not be mandatory for the initial MVP.

---

# 10. Critical Path

The likely critical path is:

Requirements  
→ Database Design  
→ Authentication  
→ Product Module  
→ Custom Order  
→ Integration  
→ Testing  
→ Deployment

If any of these are delayed, the final project release may also be delayed.

---

# 11. Parallel Work Opportunities

A team can reduce schedule risk by working in parallel where dependencies allow.

Example:

### Developer A

Frontend wireframes  
→ Customer UI  
→ Product UI

### Developer B

Backend authentication  
→ Product API  
→ Order API

### Developer C

Database  
→ Testing  
→ Documentation

However, parallel work must follow agreed API and data contracts.

---

# 12. Documentation Schedule

Documentation should not be postponed until the final week.

Recommended approach:

Each Phase  
→ Documentation Updated  
→ Commit  
→ PR  
→ Merge

Examples:

Requirements phase  
→ Requirement document

Architecture phase  
→ Architecture Decision Records

Testing phase  
→ Test evidence

This reduces final-week workload.

---

# 13. Testing Schedule

Testing should occur during development.

Recommended:

Feature Implementation  
→ Unit / Component Testing  
→ PR Review  
→ Integration Test

Then later:

Integrated System  
→ System Testing  
→ UAT

Testing only during the final week creates high project risk.

---

# 14. Buffer Time

A realistic project schedule should include buffer time.

Recommended:

**10–20% of available development time**

for:

- Bugs
- Requirement changes
- Deployment issues
- Team-member availability
- Integration conflicts
- Documentation corrections

---

# 15. Schedule Risk Register

| ID | Schedule Risk | Impact | Mitigation |
|---|---|---|---|
| SR-01 | Requirements change after development starts | High | Requirement-change process |
| SR-02 | Too many features added | High | Strict MVP |
| SR-03 | Team member becomes unavailable | Medium–High | Shared documentation and code review |
| SR-04 | Integration delayed | High | Integrate continuously |
| SR-05 | Testing postponed | High | Test during each sprint |
| SR-06 | Deployment attempted only at the end | Medium | Early test deployment |
| SR-07 | Complex payment integration delays release | Medium | Simulated payment |
| SR-08 | Advanced AI consumes excessive time | High | Keep outside core MVP |
| SR-09 | UI is redesigned repeatedly | Medium | Approve wireframe before coding |
| SR-10 | Database changes late | High | Finalize core schema early |

---

# 16. Schedule Priority Order

If time becomes limited, the team should prioritize:

## Priority 1

Core workflows

- Authentication
- Product
- Artisan
- Custom Order
- Order Management

## Priority 2

Quality

- Authorization
- Validation
- Testing
- Error handling

## Priority 3

Supporting Features

- Reviews
- QR record
- Certificate

## Priority 4

Optional Features

- Recommendation
- Gift recommendation
- Events
- Advanced analytics

---

# 17. Schedule Reduction Strategy

If the project falls behind schedule:

Do not immediately increase development speed by reducing quality.

Instead reduce scope.

Example:

Advanced Recommendation  
→ Remove

Events  
→ Remove

Real Payment  
→ Simulate

Product Journey  
→ Simplify

But retain:

Authentication  
+ Product  
+ Artisan  
+ Custom Order  
+ Order Workflow  
+ Testing

---

# 18. Minimum Demonstrable Release

If the project faces severe time constraints, the minimum high-value version should demonstrate:

Customer Registration  
→ Product Discovery  
→ Artisan Information  
→ Custom Request  
→ Artisan Quotation  
→ Customer Approval  
→ Status Update

This workflow demonstrates more Software Engineering value than a large collection of incomplete features.

---

# 19. Schedule Feasibility Decision

## Current Assessment

**FEASIBLE WITH CONTROLLED SCOPE**

The project can reasonably be completed within an academic timeline if:

- MVP scope is frozen before major development
- Advanced features remain optional
- Team members work incrementally
- Integration occurs continuously
- Testing is not postponed
- Requirement changes are controlled

---

# 20. Recommended Schedule Baseline

Current provisional baseline:

**12–14 working weeks**

This estimate should be replaced with exact dates once:

- Final submission deadline
- Team availability
- Academic holidays
- Exam periods
- Faculty review dates

are confirmed.

---

# 21. Industry Recommendation

Craft BD should optimize for:

**Complete + Tested + Deployable**

rather than:

**Large + Feature-Rich + Incomplete**

For academic and portfolio value:

A smaller but professionally engineered release is preferable.

---

## Document Status

**Phase:** 02 — Feasibility & Scope Analysis  
**Document:** Schedule Feasibility  
**Status:** Provisional v0.1  
**Exact Calendar Dates:** Pending  
**Next Step:** Privacy, Legal & Security Feasibility
