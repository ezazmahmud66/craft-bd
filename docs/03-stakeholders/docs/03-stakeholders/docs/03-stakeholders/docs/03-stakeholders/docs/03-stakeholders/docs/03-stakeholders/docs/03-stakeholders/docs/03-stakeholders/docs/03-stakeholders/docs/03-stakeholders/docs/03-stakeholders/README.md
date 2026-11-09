# Craft BD — Phase 03 Stakeholder & User Analysis

## Overview

Phase 03 identifies and analyzes Craft BD stakeholders and user groups.

The phase establishes the stakeholder and user baseline required for:

- Requirement engineering
- UML modeling
- UI/UX design
- Access-control design
- Testing
- Requirement traceability

---

# Documents

## Stakeholder Register

`stakeholder-register.md`

Identifies:

- Primary stakeholders
- Secondary stakeholders
- Regulatory stakeholders
- Future stakeholders
- External technical dependencies

---

## Power–Interest Matrix

`power-interest-matrix.md`

Classifies stakeholders using:

- Manage Closely
- Keep Satisfied
- Keep Informed
- Monitor

---

## Stakeholder Goals, Needs & Expectations

`stakeholder-goals-needs-expectations.md`

Documents stakeholder:

- Goals
- Needs
- Expectations
- Requirement implications

---

## User Segmentation & Personas

`user-segmentation-personas.md`

Defines:

### Customer Segments

- Cultural Craft Explorer
- Custom Craft Buyer
- Gift Buyer
- Trust-Conscious Buyer

### Artisan Segments

- Individual Artisan
- Small Craft Business
- Social-Media-Based Craft Seller

Also contains provisional synthetic personas.

---

## User Goals & Pain Points

`user-goals-painpoints.md`

Maps:

```text
Goal
→ Pain Point
→ Existing Workaround
→ Craft BD Opportunity
→ Validation Status
```

---

## User Journey Baseline

`user-journey-baseline.md`

Defines end-to-end:

- Customer journey
- Artisan journey
- Standard-order flow
- Custom-order flow

---

## Role & Responsibility Matrix

`role-responsibility-matrix.md`

Documents:

- Customer responsibilities
- Artisan responsibilities
- Administrator responsibilities
- System permissions
- Ownership rules
- Project-level RACI

---

## Stakeholder Conflict Analysis

`stakeholder-conflict-analysis.md`

Analyzes conflicts such as:

- Customer flexibility vs artisan simplicity
- Information depth vs seller effort
- Admin control vs workflow speed
- Academic complexity vs project feasibility
- Stakeholder requests vs user evidence

---

## Requirement Source Mapping

`requirement-source-mapping.md`

Maps stakeholder sources to future requirement areas and establishes the foundation for requirement traceability.

---

## Consolidated Review

`stakeholder-analysis-summary.md`

Provides the complete Phase 03 stakeholder and user-analysis summary.

---

# Current Priority Stakeholders

Primary product users:

```text
Customer
+
Artisan / Seller
```

Operational:

```text
Administrator
```

Project governance:

```text
Project Team
+
Academic Supervisor
```

---

# Current Priority User Segments

## Customer

```text
Custom Craft Buyer
+
Cultural Craft Explorer
```

## Artisan / Seller

```text
Individual Artisan
+
Social-Media-Based Craft Seller
```

---

# Current Core Product Hypothesis

```text
Customer
Needs structured customization
        ↕
Craft BD
        ↕
Artisan
Needs organized requirements,
quotation, approval, and status
```

This hypothesis remains subject to primary user validation.

---

# Phase 03 Status

| Activity | Status |
|---|---|
| Stakeholder register | Complete |
| Power–interest analysis | Complete |
| Goals/needs analysis | Complete |
| User segmentation | Provisional Complete |
| Personas | Provisional Complete |
| User pain-point mapping | Provisional Complete |
| User journeys | Provisional Complete |
| Roles/responsibilities | Complete |
| Conflict analysis | Complete |
| Requirement-source mapping | Complete |
| Consolidated review | Complete |
| Primary user validation | Pending |

---

# Important Research Rule

Synthetic personas and inferred pain points are not primary research evidence.

Future interviews should be used to:

```text
Validate
Modify
or
Reject
```

the current user model.

---

## Version

**Phase 03 Baseline:** v0.1  
**Status:** Ready for Review  
**Primary Research Dependency:** Open  
**Next Activity:** Phase 03 Pull Request
