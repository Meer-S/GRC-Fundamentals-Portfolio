# GRC - Project — Security Policy, Risk & Compliance Fundamentals Portfolio
Author: Meer 
A five-part GRC portfolio built around a single fictional company, **Meridian HealthTech Solutions**
(a mid-size healthcare SaaS platform processing Protected Health Information), so that every
deliverable — policies, gap analysis, risk register, vendor assessment, and awareness program —
reads as one coherent, defensible body of work rather than five disconnected templates.

This project is designed to demonstrate the five things a GRC/security-consulting role actually
tests for: writing board-ready governance documents, running a real framework gap analysis,
building a NIST RMF risk register from scratch, assessing third-party/supply-chain risk with a
scored methodology, and designing (and measuring) a human-risk reduction program.

> **Why one fictional company for all five?** Real GRC work doesn't happen in isolated exercises —
> a policy suite drives what an ISO 27001 auditor checks, a gap analysis feeds the risk register,
> and the risk register flags the vendors and the training gaps worth prioritizing. Threading one
> company through all five projects is what makes each deliverable checkable against the others
> instead of just internally consistent.

---

## Company Profile: Meridian HealthTech Solutions

| | |
|---|---|
| **Business** | Cloud-based patient engagement & care-coordination SaaS platform |
| **Customers** | Hospitals and outpatient clinics |
| **Data handled** | Protected Health Information (PHI) for ~15,000 patient records/day |
| **Infrastructure** | AWS-native, multi-tenant, `us-east-1` / `ap-south-1` |
| **Headcount** | ~450 employees — Austin, TX (HQ) and Bengaluru, India (engineering) |
| **Regulatory drivers** | HIPAA Security Rule, HIPAA Breach Notification Rule, first-time ISO/IEC 27001:2022 certification |

All company names, individuals, vendors, control statuses, risk scores, and campaign metrics in
this project are fictional and created for demonstration purposes.

---

## What's in this project

### 1. Security Policy Suite
**`01-Policy-Suite/Project1_Security_Policy_Suite.docx`**

A board-ready policy suite covering the four foundational governance documents every ISO
27001 / HIPAA program is built on:

- **Acceptable Use Policy** (MER-ISP-001)
- **Incident Response Policy** (MER-ISP-002) — including the HIPAA Breach Notification Rule
  risk-assessment and notification-timeline requirements
- **Access Control Policy** (MER-ISP-003) — least privilege, MFA, PAM, access recertification
- **Data Classification Policy** (MER-ISP-004) — a 4-tier scheme (Restricted/Confidential/
  Internal/Public) with handling requirements per tier

Each policy includes purpose, scope, policy statements, roles & responsibilities, enforcement,
and a review cycle, mapped to specific ISO/IEC 27001:2022 Annex A controls and HIPAA Security
Rule citations. The document opens with a board memorandum and closes with a signature block for
CEO, CISO, and Risk & Audit Committee Chair sign-off — written the way it would actually be
routed for approval, not as a generic template.

### 2. ISO/IEC 27001:2022 Gap Analysis
**`02-ISO27001-Gap-Analysis/Project2_ISO27001_Gap_Analysis.xlsx`**

A full **93-control** Annex A gap analysis — every control in the 2022 revision, across all four
themes (Organizational, People, Physical, Technological). For each control:

- Current status (Implemented / Partially Implemented / Not Implemented / Not Applicable)
- Residual risk rating
- A specific gap description (not a boilerplate line — tied to the control itself)
- A remediation recommendation
- Control owner and priority/target-closure date

The **Summary** tab rolls this up with live formulas: overall compliance %, priority breakdown,
and a theme-by-theme maturity view — plus a short readiness note explaining *why* the gaps cluster
where they do (governance/supplier-management controls lag the technical controls, which is the
realistic pattern for an early-stage cloud-native SaaS pursuing first-time certification).

### 3. NIST RMF Risk Assessment
**`03-NIST-RMF-Risk-Assessment/Project3_NIST_RMF_Risk_Assessment.xlsx`**

Applies NIST SP 800-37 Rev. 2 (the Risk Management Framework's seven steps: Prepare → Categorize
→ Select → Implement → Assess → Authorize → Monitor) to the Meridian Care Platform, with:

- A **15-asset inventory** (databases, application tiers, identity provider, source code,
  endpoints, backups, network perimeter, and the people who hold PHI access)
- A **15-risk register** pairing each asset with a realistic threat source and vulnerability,
  scored on a NIST SP 800-30 5×5 likelihood/impact scale with a live formula computing risk
  score, risk rating, and residual rating after treatment
- An executive summary cross-referencing the highest-scoring risks back to the specific ISO
  27001 Annex A gaps (Project 2) that drive them

### 4. Third-Party Vendor Risk Assessment
**`04-Vendor-Risk-Assessment/Project4_Vendor_Risk_Assessment.xlsx`**

- A **6-domain, weighted vendor security questionnaire** (Governance & Compliance, Data
  Protection, Access Control, Incident Response, Business Continuity, Sub-processor/Supply
  Chain Risk) with a defined 0–4 scoring rubric
- Scored responses for **three fictional vendors** representing three different risk profiles a
  healthtech company actually deals with: an AI clinical-transcription startup (undisclosed LLM
  sub-processor), a mature PCI-DSS Level 1 payment processor, and a small staffing vendor with no
  security attestation
- A weighted-formula risk rating per vendor (**High Risk**, **Low Risk**, and **Critical Risk**
  respectively) and a remediation & ongoing-monitoring plan scaled to each rating

### 5. Security Awareness Training Program + Simulated Phishing Campaign
**`05-Security-Awareness-Phishing-Program/`**
- `Project5_Security_Awareness_Program.docx` — full program design: objectives, audience
  segmentation, a 3-module curriculum (fundamentals, role-based deep dives, embedded phishing
  simulation), measurement/KPIs, and roles & responsibilities
- `Project5_Phishing_Campaign_Results.xlsx` — results of a simulated Q3 2026 phishing campaign
  (448 employees, 4 rotating pretexts including a BEC-style executive request): overall and
  department-level click/credential-entry/report rates with a bar chart, a wave-over-wave trend
  against the prior quarter, and a prioritized follow-up training plan by department

---

## Frameworks referenced

| Framework | How it's used |
|---|---|
| ISO/IEC 27001:2022 (Annex A) | Full control gap analysis (Project 2); cited throughout the policy suite and risk register |
| NIST SP 800-37 Rev. 2 (RMF) | Structure for the risk assessment (Project 3) |
| NIST SP 800-30 Rev. 1 | Likelihood/impact scoring methodology (Project 3) |
| NIST SP 800-53 Rev. 5 | Control baseline referenced in the RMF Select step |
| HIPAA Security Rule & Breach Notification Rule | Policy suite (Project 1) and incident response / breach-notification procedures |

## How these projects connect

```
Policy Suite (1)  ──defines control expectations──▶  ISO 27001 Gap Analysis (2)
                                                              │
                                                   gaps feed inherent risk
                                                              ▼
                                              NIST RMF Risk Register (3)
                                                    │                │
                                        highest risks tied      people-risk items
                                        to vendors  ▼            feed training  ▼
                                Vendor Risk Assessment (4)   Awareness & Phishing Program (5)
```

## Notes for reviewers

- Every workbook uses live Excel formulas (`SUMPRODUCT`, `COUNTIFS`, nested `IF`), not
  hardcoded results — change an input and the ratings recalculate.
- All content (control statuses, risk scores, vendor findings, campaign metrics) is fictional
  and was authored to be internally consistent across the five deliverables, not randomly
  generated per file.
- Classification banners, document IDs, and approval workflows are written as they would appear
  in an actual board/audit-committee deliverable, not simplified for portfolio purposes.

---

*Part of [GRCProjects](https://github.com/Meer-S/GRCProjects) — a portfolio of hands-on GRC and
compliance lab work. See Project 6 for the DPDP Act 2023 study guide and lab series.*
