# Craft BD — Economic Feasibility Analysis

## 1. Purpose

This document evaluates whether Craft BD can be developed, deployed, and maintained within the financial constraints of an academic Software Engineering project.

The analysis separates:

1. Academic / Portfolio MVP Cost
2. Future Commercial Deployment Cost

This distinction is important because infrastructure suitable for an academic prototype may not be appropriate for a real commercial platform.

---

# 2. Economic Feasibility Categories

Craft BD costs can be divided into:

- Development cost
- Source-control and collaboration cost
- Hosting cost
- Database cost
- File-storage cost
- Domain cost
- Payment-integration cost
- Third-party service cost
- Maintenance cost
- Future scaling cost

---

# 3. Academic MVP Cost Strategy

The academic version should use free or low-cost development infrastructure wherever practical.

The objective is not to build enterprise infrastructure.

The objective is to demonstrate:

- Correct Software Engineering process
- Functional workflows
- Secure architecture
- Testing
- Deployment
- Documentation

---

# 4. Source Control Cost

Craft BD currently uses GitHub.

GitHub's Free plan supports:

- Public repositories
- Private repositories
- Issues
- Pull Requests
- Projects
- 2,000 GitHub Actions minutes per month for private repositories

## Estimated Academic Cost

**$0/month**

## Feasibility

Highly feasible.

---

# 5. Frontend Hosting

A frontend application can potentially be deployed using services such as Vercel or similar platforms.

Vercel currently provides a Hobby plan at:

**$0/month**

However, the Hobby plan is intended for personal and non-commercial use.

Therefore:

### Academic / Portfolio Prototype

Potentially suitable.

### Future Commercial Product

A commercial-compatible paid plan or alternative infrastructure should be selected.

## Academic Cost

Potentially:

**$0/month**

---

# 6. Backend Hosting

Several cloud platforms provide low-cost or free development hosting.

For example, Render provides free web services for testing, hobby development, and previews.

However, Render explicitly states that free services have limitations and should not be used for production applications.

Paid compute is available when a persistent production service is required.

## Academic MVP

Possible cost:

**$0/month**

subject to free-tier limitations.

## Small Production Deployment

A basic paid backend may begin at a low monthly cost depending on the selected provider and resource requirements.

Final provider selection will occur during deployment planning.

---

# 7. Database Cost

Craft BD will likely use a relational database.

Possible managed database platforms may provide free development tiers.

For example, Supabase currently provides a free plan including:

- 500 MB database
- 1 GB file storage
- Limited free project capacity

This may be sufficient for an academic prototype with sample product, artisan, order, and certificate data.

## Academic MVP

Potential database cost:

**$0/month**

## Production

A paid plan may become necessary when:

- Data volume increases
- Backup requirements increase
- Availability requirements increase
- User traffic increases
- Storage demand increases

---

# 8. File Storage Cost

Craft BD may store:

- Product images
- Artisan images
- Custom-order reference images
- Product-journey images

For an academic prototype, free-tier storage may be sufficient.

However, image storage can become a significant production cost when the platform scales.

## Cost-Control Recommendations

- Limit image size
- Compress uploaded images
- Restrict allowed file formats
- Avoid unnecessary duplicate images
- Define file-retention policies

---

# 9. Domain Cost

A custom domain is useful for portfolio presentation but is not technically required.

Example:

Instead of:

craft-bd-host.vercel.app

a production system may later use:

craftbd.example

Domain-registration prices depend on:

- Top-level domain
- Registrar
- Promotions
- Renewal pricing

## Academic MVP Decision

**Optional**

A free hosting subdomain is sufficient for initial deployment.

---

# 10. Payment Gateway Cost

## Option A — Simulated Payment

Craft BD can implement the payment workflow without processing real financial transactions.

Example:

Checkout  
→ Select Payment Method  
→ Simulated Payment Status  
→ Order Created

### Cost

**$0**

### Recommendation

Preferred for the initial academic MVP.

---

## Option B — Real Payment Gateway

A real gateway may involve:

- Business verification
- API integration
- Transaction charges
- Settlement requirements
- Webhook implementation
- Security requirements
- Possible setup or service fees

The exact cost depends on the selected payment provider.

## Recommendation

Do not make real payment processing mandatory for the first academic release.

---

# 11. QR Code Cost

QR-code generation itself does not require a paid commercial service.

Craft BD can generate QR codes that contain:

- Verification URL
or
- Unique product-record identifier

Example:

QR  
→ Craft BD verification URL  
→ Backend record

## Estimated Software Cost

**Minimal / potentially $0**

## Main Cost

Development and verification workflow rather than QR generation itself.

---

# 12. Digital Certificate Cost

A platform-maintained digital certificate record does not require expensive infrastructure.

Possible components:

- Certificate database record
- Unique certificate ID
- Verification URL
- Printable/downloadable certificate

## Academic MVP Cost

Minimal.

No blockchain infrastructure is required.

---

# 13. Recommendation System Cost

## Simple Content-Based Recommendation

Possible implementation:

Category  
+ Material  
+ Region  
+ Craft Type  
+ Price Range

This can run within the existing backend.

### Additional Infrastructure Cost

Minimal.

---

## Advanced AI Recommendation

Could require:

- Large interaction dataset
- Model training
- Model serving
- Additional compute infrastructure

### Economic Impact

Higher.

### MVP Decision

Not financially or technically justified for the initial release.

---

# 14. Third-Party Service Cost

Potential future services may include:

- Email
- SMS
- Cloud storage
- Payment gateway
- Analytics
- Monitoring
- Image processing
- External logistics services

For MVP:

Prefer free development tiers or avoid non-essential integrations.

---

# 15. Academic MVP Direct-Cost Estimate

A realistic low-cost configuration may look like:

| Resource | Possible MVP Cost |
|---|---:|
| GitHub repository | $0 |
| Frontend hosting | $0 |
| Backend development hosting | $0 |
| Development database | $0 |
| Small image-storage requirement | $0 within free-tier limits |
| QR generation | $0 |
| Simulated payment | $0 |
| SSL/TLS through hosting platform | Usually included |
| Custom domain | Optional |
| Development tools | Primarily free/open-source |

## Estimated Minimum Direct Infrastructure Cost

**Approximately $0 for the initial academic prototype**

provided that the project remains within relevant free-tier usage limits.

---

# 16. Important Clarification

A "$0 MVP" does **not** mean the software has no cost.

The team contributes:

- Development time
- Requirement analysis
- Research
- Design
- Testing
- Documentation
- Maintenance effort

These are real project resources even when no salary is paid during the academic project.

---

# 17. Development Effort as Economic Cost

An industry project would calculate engineering labor.

Example roles:

- Product / Requirement Analyst
- UI/UX Designer
- Frontend Developer
- Backend Developer
- QA Engineer
- DevOps / Deployment responsibility

For the academic project, these responsibilities are handled by team members.

Therefore:

## Direct Cash Cost

Low

## Human Resource Cost

Significant

This distinction should be included in project evaluation.

---

# 18. Commercial Deployment Scenario

If Craft BD became a real product, free-tier infrastructure should not automatically be treated as sufficient.

A production system may require:

- Paid application hosting
- Paid managed database
- Persistent backups
- Monitoring
- Larger storage
- Domain
- Transaction services
- Email/SMS
- Security monitoring
- Technical support

A realistic commercial budget would therefore depend heavily on:

- Number of users
- Number of products
- Image volume
- Traffic
- Payment transactions
- Availability requirements
- Backup requirements

---

# 19. Example Early Production Cost Categories

| Component | Cost Behavior |
|---|---|
| Domain | Annual |
| Frontend hosting | Free → Paid as usage/team needs grow |
| Backend compute | Monthly |
| Database | Monthly / usage-based |
| Object storage | Usage-based |
| Email | Usage-based |
| SMS | Per message |
| Payment gateway | Transaction-based |
| Monitoring | Free → usage-based |
| Backup | Included or additional depending on provider |

Exact pricing should be evaluated when the production architecture is selected.

---

# 20. Cost-Control Strategy

Craft BD should follow:

## Stage 1 — Development

Use free local development and free source-control tools.

## Stage 2 — Academic MVP

Use free-tier deployment where appropriate.

## Stage 3 — Portfolio Release

Maintain a low-cost public demonstration deployment.

## Stage 4 — Commercial Validation

Measure actual usage before increasing infrastructure.

## Stage 5 — Production Scaling

Upgrade only the components that require additional capacity.

---

# 21. Build vs Buy Decisions

Some functionality should be built internally:

- Product management
- Artisan profile
- Custom-order workflow
- Quotation
- Product records

Some infrastructure should normally use established services:

- Hosting
- Database hosting
- Email delivery
- Payment processing

Craft BD should not attempt to build its own payment infrastructure or cloud platform.

---

# 22. Feature Cost Impact

| Feature | Relative Cost | MVP Decision |
|---|---|---|
| Product Catalog | Low | Keep |
| Artisan Profile | Low | Keep |
| Craft Story | Low | Keep if validated |
| Product Journey | Low | Scope-dependent |
| Custom Order | Medium development effort | High-priority candidate |
| Quotation | Medium | Keep with custom order |
| QR Product Record | Low–Medium | Feasible |
| Digital Certificate | Medium | Scope carefully |
| Reviews | Low–Medium | Supporting |
| Simulated Payment | Low | Suitable |
| Real Payment Gateway | Medium–High | Optional |
| Simple Recommendation | Medium | Future/optional |
| Advanced AI | High | Reject for initial MVP |
| Live Chat | High | Reject for MVP |
| Blockchain | High | Reject for MVP |
| Logistics Integration | High | Future |

---

# 23. Economic Risks

| ID | Risk | Impact | Mitigation |
|---|---|---|---|
| ER-01 | Free hosting limitations affect demo availability | Medium | Select appropriate deployment provider |
| ER-02 | Image storage increases rapidly | Medium | Compression and limits |
| ER-03 | Paid third-party services increase cost | Medium | Keep optional services outside MVP |
| ER-04 | Real payment creates unnecessary integration cost | Medium | Simulate for academic release |
| ER-05 | Advanced AI increases infrastructure cost | High | Avoid in MVP |
| ER-06 | Overengineering increases development effort | High | Maintain strict scope |
| ER-07 | Free tier changes in future | Medium | Keep provider-independent architecture |

---

# 24. Economic Benefit for Academic Project

The project provides value beyond direct financial return.

It demonstrates:

- Requirement engineering
- Git workflow
- Product discovery
- Architecture
- Database design
- API design
- Security
- State-based workflows
- Testing
- Deployment
- Software documentation

Therefore, the development effort also produces educational and portfolio value.

---

# 25. Economic Feasibility Decision

## Academic MVP

**ECONOMICALLY FEASIBLE**

Direct infrastructure cost can potentially remain close to zero by using suitable free development tiers.

---

## Commercial Deployment

**FEASIBLE, BUT REQUIRES A SEPARATE PRODUCTION BUDGET**

Commercial cost cannot be determined accurately until:

- User volume
- Traffic
- storage
- payment requirements
- availability requirements

are known.

---

# 26. Recommendation

Craft BD should initially prioritize:

**Engineering Quality + Core Workflow**

rather than spending money on:

- Enterprise hosting
- Advanced AI infrastructure
- Blockchain
- Real-time chat
- Complex paid integrations

The project should begin economically small and scale only when usage justifies additional cost.

---

## Document Status

**Phase:** 02 — Feasibility & Scope Analysis  
**Document:** Economic Feasibility  
**Status:** Draft v0.1  
**Next Step:** Schedule Feasibility Analysis
