# Craft BD — Privacy, Legal & Security Feasibility

## 1. Purpose

This document evaluates the privacy, legal, consumer-protection, and security considerations relevant to Craft BD.

The objective is not to provide legal advice.

The objective is to identify constraints that should influence system requirements, architecture, data design, authentication, file handling, product information, and future commercial deployment.

---

# 2. Current Bangladesh Legal Context

Craft BD may process information relating to customers, artisans, products, orders, reviews, and custom requests.

Relevant Bangladesh frameworks currently include:

**Personal Data Protection Act, 2026**

The Act establishes requirements relating to lawful processing of personal data, including consent-based processing in applicable situations and responsibilities for protecting personal data.

**Cyber Security Act, 2026**

The Act provides the current cybersecurity legal framework in Bangladesh.

It was subsequently amended in 2026.

**Digital Commerce Operation Guidelines, 2021**

These guidelines remain relevant to digital-commerce operations in Bangladesh.

**Consumer Rights Protection Act, 2009**

Consumer-facing commercial activity should also consider applicable consumer-protection obligations.

The team should review current official requirements again before any real commercial launch.

---

# 3. Privacy Feasibility

Craft BD can operate without collecting excessive personal information.

Recommended principle:

**Collect only what is necessary for the intended service.**

For example:

Customer Account  
→ Name  
→ Email / Contact Information  
→ Delivery Information when required

Artisan Account  
→ Name  
→ Craft Profile  
→ Business / Public Contact Information where appropriate

The academic MVP does not require unnecessary sensitive information.

---

# 4. Data Minimization

Craft BD should avoid collecting data simply because it may be useful later.

Examples of information that should not be collected without a clear requirement include:

National identity information  
Financial credentials  
Unnecessary date of birth  
Private family information  
Sensitive personal documents

Data collection should follow:

Purpose  
→ Necessary Data  
→ User Notice / Appropriate Basis  
→ Secure Processing  
→ Retention Decision

---

# 5. Personal Data Categories

Possible Craft BD personal data may include:

| Data | Example | Sensitivity |
|---|---|---|
| Identity | Name | Normal personal data |
| Account | Email, username | Personal data |
| Contact | Phone number | Personal data |
| Delivery | Address | Personal data |
| Artisan profile | Biography, public location | Personal / public-facing data |
| Orders | Customer-order relationship | Transaction data |
| Reviews | User-generated content | Account-linked data |
| Custom request | Design requirements | Transaction data |
| Uploaded image | Reference image | User-provided content |
| Authentication | Password hash | Security-sensitive |

Passwords themselves must never be stored in readable form.

---

# 6. Consent and Transparency

Users should understand why their data is collected.

Before production use, Craft BD should provide an appropriate privacy notice explaining areas such as:

What information is collected  
→ Why it is collected  
→ How it is used  
→ Who can access it  
→ How long it may be retained  
→ How users can request appropriate account/data actions

The exact legal wording should be reviewed before commercial deployment.

---

# 7. Password Security

Craft BD must never store:

Plain-text passwords.

Recommended flow:

Password  
→ Secure Password-Hashing Algorithm  
→ Hash Stored in Database

Authentication credentials should not be exposed through:

Logs  
API responses  
Client-side code  
GitHub commits

---

# 8. Authorization

Authentication answers:

> Who is this user?

Authorization answers:

> What is this user allowed to do?

Craft BD requires server-side authorization.

Examples:

Customer  
→ Cannot edit artisan product

Artisan A  
→ Cannot modify Artisan B's product

Customer A  
→ Cannot view private order data belonging to Customer B

Normal Artisan  
→ Cannot issue admin-controlled certificate records

Administrator  
→ Has privileged operations according to approved business rules

Frontend visibility must not be treated as security enforcement.

---

# 9. Role-Based Access Control

Recommended initial roles:

| Operation | Customer | Artisan | Admin |
|---|---:|---:|---:|
| Browse public products | Yes | Yes | Yes |
| Purchase | Yes | No | No |
| Submit custom request | Yes | No | No |
| Manage own product | No | Yes | Yes |
| Quote custom request | No | Assigned Artisan | No / Monitor |
| Approve quotation | Request Owner | No | No |
| Review purchased product | Eligible Customer | No | Moderate |
| Manage users | No | No | Yes |
| Issue platform certificate | No | No | Authorized Admin |

Detailed permissions will be finalized during the security-design phase.

---

# 10. User-Generated Content

Craft BD may contain:

Product descriptions  
Reviews  
Artisan stories  
Custom instructions  
Reference images

These create operational and security risks.

The platform should therefore support appropriate:

Input validation  
Content moderation  
File validation  
Authorization  
Reporting / administrative action

---

# 11. File Upload Security

Craft BD may allow:

Product images  
Artisan images  
Custom-order reference images  
Product-journey images

Uploaded files must not be trusted automatically.

Minimum design considerations:

Allowed file types  
Maximum file sizes  
Filename handling  
Storage isolation  
Authorization  
Malicious-file risk  
Image validation

The implementation method will be decided during system design.

---

# 12. Input Validation

All external input must be considered untrusted.

Validation should occur on the backend for:

Registration  
Login  
Product creation  
Search parameters  
Custom-order requests  
Quotation values  
Reviews  
File uploads  
Order actions

Client-side validation may improve UX but is not sufficient security.

---

# 13. Custom-Order Privacy

A custom-order request may contain:

Reference image  
Design  
Size  
Instructions  
Other customer-provided information

The system should ensure that these records are accessible only to appropriate users.

Recommended model:

Customer who owns request  
↕  
Assigned Artisan  
↕  
Authorized Administrator where necessary

Other customers and unrelated artisans should not access private request details.

---

# 14. Product and Artisan Information

Craft BD should distinguish between:

**Public Information**

Product name  
Public artisan biography  
Product description  
Craft story

and

**Private Operational Information**

Private contact details  
Order data  
Customer address  
Internal moderation data  
Authentication information

This separation should influence the database and API design.

---

# 15. Reviews and Consumer Trust

Reviews should be associated with appropriate accounts.

Recommended business rule:

A customer should normally review a product only after an eligible purchase.

This reduces some forms of fake or unrelated reviews.

Administrators may moderate inappropriate content but should not silently manipulate legitimate ratings to improve product reputation.

---

# 16. Product Information Accuracy

Craft BD may display:

Materials  
Region  
Artisan  
Production information  
Craft type  
Certificate information

The platform should avoid knowingly presenting misleading information.

Responsibility for entering, reviewing, and modifying such information must be defined.

---

# 17. QR Verification Legal / Trust Risk

A QR code provides access to digital information.

It does not automatically prove that the physical item being scanned is authentic.

Recommended terminology:

**QR-linked Product Record**

or

**Platform Verification Record**

Avoid unsupported wording such as:

**Guaranteed Genuine Product**

unless an appropriate physical verification and certification mechanism exists.

---

# 18. Digital Certificate Boundary

For the academic MVP, a Craft BD digital certificate should be treated as:

**A platform-maintained record associated with a product**

rather than:

**Government certification**

or

**Legally recognized authenticity certification**

unless Craft BD later integrates with an authorized external certification process.

---

# 19. Payment Boundary

The academic MVP should not store:

Card numbers  
Mobile financial service PINs  
Bank passwords  
Payment-provider passwords

If real payment integration is added later:

Payment credentials should be handled by an appropriate payment provider rather than Craft BD designing its own payment infrastructure.

For the initial MVP:

**Simulated payment is recommended.**

---

# 20. Consumer Protection Considerations

Because Craft BD includes commerce-related workflows, future commercial deployment should clearly communicate important transaction information such as:

Product information  
Price  
Order details  
Delivery information  
Cancellation / return conditions where applicable  
Seller information  
Customer-support process

Exact obligations should be reviewed against current Bangladesh digital-commerce and consumer-protection requirements before production launch.

---

# 21. Logging

Application logging is useful for:

Debugging  
Security investigation  
Audit of important operations

However, logs should not contain unnecessary secrets.

Avoid logging:

Passwords  
Access tokens  
Payment secrets  
Sensitive authentication information

---

# 22. Secret Management

The following must never be committed to GitHub:

`.env` production files  
Database passwords  
API keys  
Authentication secrets  
Payment credentials  
Private keys

Recommended model:

Repository  
→ `.env.example`

Deployment Environment  
→ Actual secrets

---

# 23. HTTPS

Production communication should use HTTPS.

This helps protect information transmitted between:

Browser  
↕  
Server

Hosting and deployment architecture should enforce secure transport.

---

# 24. Security Risks

| ID | Risk | Impact | Mitigation |
|---|---|---|---|
| SEC-01 | Plain-text password storage | Critical | Secure password hashing |
| SEC-02 | Unauthorized order access | High | Server-side authorization |
| SEC-03 | Artisan modifies another artisan's product | High | Ownership validation |
| SEC-04 | Malicious file upload | High | File validation/restriction |
| SEC-05 | API secret leaked to GitHub | High | Environment variables |
| SEC-06 | Admin endpoint accessed by normal user | High | RBAC |
| SEC-07 | Sensitive information exposed in logs | High | Safe logging |
| SEC-08 | Fake review | Medium | Purchase-linked review rule |
| SEC-09 | Predictable verification code | Medium | Strong unique identifiers |
| SEC-10 | Misleading certificate claims | High | Clear certificate scope |

---

# 25. Privacy Risks

| ID | Risk | Mitigation |
|---|---|
| PR-01 | Collecting unnecessary personal data | Data minimization |
| PR-02 | Public exposure of customer contact information | Public/private field separation |
| PR-03 | Custom-order images exposed to unrelated users | Authorization |
| PR-04 | User data retained indefinitely without purpose | Retention policy |
| PR-05 | Users do not understand data usage | Privacy notice |
| PR-06 | Production data copied into public demos | Use synthetic/demo data |

---

# 26. Academic Demo Data

The public portfolio version should preferably use:

Synthetic Customers  
Synthetic Orders  
Synthetic Addresses  
Demo Products where appropriate

Do not publish real participant interview details or private customer information in the public repository.

---

# 27. Legal Feasibility

From a software-engineering perspective, the proposed Craft BD MVP is legally feasible **provided that the system is designed to respect applicable requirements and does not make unsupported certification or authenticity claims**.

However, a commercial launch would require a separate legal and compliance review.

---

# 28. Security Feasibility

The required security controls are technically achievable using standard web-application engineering practices.

The largest security risks arise from:

Authorization mistakes  
Secret leakage  
Unsafe uploads  
Poor password handling  
Excessive data exposure

These risks are manageable when security requirements are incorporated before implementation.

---

# 29. MVP Recommendation

Include security from the beginning:

Authentication  
+ RBAC  
+ Ownership Rules  
+ Input Validation  
+ Secure Password Storage  
+ File Controls  
+ Secret Management  
+ HTTPS Deployment

Do not postpone these until the final development sprint.

---

# 30. Feasibility Decision

**Privacy Feasibility:** FEASIBLE

**Security Feasibility:** FEASIBLE WITH REQUIRED CONTROLS

**Legal / Compliance Feasibility for Academic MVP:** FEASIBLE

**Commercial Compliance:** REQUIRES FORMAL REVIEW BEFORE REAL-LIFE COMMERCIAL OPERATION

---

# 31. Current Legal References

The project should monitor current official Bangladesh requirements, including:

- Personal Data Protection Act, 2026
- Cyber Security Act, 2026 and applicable amendments
- Digital Commerce Operation Guidelines, 2021
- Consumer Rights Protection Act, 2009

Legal requirements may change during the life of the project.

---

## Document Status

**Phase:** 02 — Feasibility & Scope Analysis  
**Document:** Privacy, Legal & Security Feasibility  
**Status:** Draft v0.1  
**Next Step:** Feature Feasibility & Prioritization Matrix
