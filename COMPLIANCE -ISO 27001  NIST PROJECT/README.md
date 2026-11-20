# Enterprise ISO/IEC 27001:2022 \& NIST Cybersecurity Compliance Framework

A comprehensive, production-ready Information Security Management System (ISMS) framework and GRC (Governance, Risk, and Compliance) portfolio. Designed for a enterprise SaaS fintech organization operating in a multi-region AWS cloud infrastructure, adhering to **ISO/IEC 27001:2022**, **NIST CSF**, **GDPR**, and **NDPR** regulatory standards.

\---

## Executive Summary

This project establishes the baseline security governance, risk assessment, gap remediation strategy, and operational response procedures for a cloud-hosted financial transaction platform.

### Key Governance Highlights

* **Framework Alignment:** ISO/IEC 27001:2022 (Annex A Controls), NIST CSF (Identify, Protect, Detect, Respond, Recover).
* **Regulatory Focus:** GDPR (EU Data Protection) \& NDPR (Nigeria Data Protection Regulation) 72-hour breach notification compliance.
* **Target Recovery Objectives:** Critical System RTO: ≤ 4 Hours | RPO: ≤ 1 Hour.
* **Scope Boundary:** AWS Cloud Infrastructure (`us-east-1`), Core API Engine, Relational Data Stores (RDS), CI/CD Pipelines (GitHub Actions), Corporate SaaS, and Managed Endpoint Infrastructure.

\---

## Project Structure \& Artifact Map

```text
├── governance/
│   ├── ISMS\_Scope\_Statement.md         # ISO 27001:2022 Clause 4.3 Boundary Definition
│   ├── POL-AUP-001\_Acceptable\_Use.md   # Information Classification \& Baseline User Rules
│   └── POL-IRP-001\_Incident\_Policy.md  # Governing Incident Response Policy (Annex A.16.1)
├── risk-and-assessment/
│   ├── Asset\_Register.md               # Information Asset Classification \& CIA Scoring
│   ├── Control\_Matrix\_ISO27001.md      # Maturity Model (1-5 Scale) across 20+ Security Domains
│   ├── Statement\_of\_Applicability.md   # Annex A Inclusion/Exclusion Control Justifications
│   └── Gap\_Analysis\_Remediation.md     # Prioritized (P1-P4) Remediation Roadmap \& SLAs
└── operations/
    └── IRP-001\_Incident\_Response\_Plan.md # Operational Incident Lifecycle, CIRT \& SLAs
```

\---

## Core Artifact Descriptions

### 1\. Governance \& Scope Definition

* **`ISMS Scope Statement` (`ISMS-SCOPE-001`)**: Formally sets the ISMS boundary under ISO/IEC 27001 Clause 4.3. Covers all cloud infrastructure, code repositories, data storage, employee endpoints, and core processing pipelines. Defines explicit in-scope/out-of-scope criteria and external interfaces (payment gateways, CSP shared responsibility models).
* **`Acceptable Use Policy` (`POL-AUP-001`)**: Defines rules of conduct for technology resources, clean desk policy, remote work security, MFA mandates, shadow IT restrictions, and a 4-tier data classification model (*Restricted*, *Confidential*, *Internal*, *Public*).

### 2\. Risk Assessment \& Controls Evaluation

* **`Asset Register`**: Catalogues primary and secondary assets, assigning asset owners, storage/hosting locations, and numerical Confidentiality, Integrity, and Availability (**CIA**) rating scores ($1-3$ per vector, total out of $9$).
* **`ISO 27001:2022 Control Matrix`**: Evaluates security control maturity across a 5-point capability scale (`1 - Initial` to `5 - Optimising`). Covers domains such as Access Control (A.9), Cryptography (A.10), Operations Security (A.12), Supplier Relationships (A.15), and Incident Management (A.16).
* **`Statement of Applicability (SoA)`**: Tracks Annex A controls, recording implementation status (*Implemented*, *Partially Implemented*, *Not Implemented*), rationale for inclusion/exclusion, and control owner assignments.
* **`Gap Analysis \& Remediation Roadmap`**: Maps identified control deficiencies (`GAP-001` through `GAP-014`) into prioritized remediation windows:

  * &#x20;**P1 (Critical / 0–30 Days):** Incident Response Plan formalization, Access Control Policy, Operational Runbooks, RACI Matrix.
  * &#x20;**P2 (High / 30–60 Days):** Board approvals, Google Workspace MFA enforcement, tested DRP/BCP, vendor risk assessments.
  * &#x20;**P3 (Medium / 60–90 Days):** Data transfer policies, vulnerability scan-to-patch SLAs.
  * &#x20;**P4 (Low / 90+ Days):** Formal cryptographic key policy, regulatory compliance calendar.

### 3\. Incident Response \& Operational Preparedness

* **`Incident Response Policy \& Plan` (`IRP-001` / `POL-IRP-001`)**: Establishes a 5-phase incident management lifecycle:

  1. **Identification \& Detection:** Initial triage within 15 mins for critical events.
  2. **Containment:** Short-term network isolation, IAM credential revocation, log preservation in write-protected S3 buckets.
  3. **Eradication:** Vulnerability patching, malware removal, Root Cause Analysis (RCA).
  4. **Recovery:** Backup restoration (RTO ≤ 4 hrs, RPO ≤ 1 hr) and 72-hour enhanced post-recovery monitoring.
  5. **Post-Incident Review:** Mandatory PIR within 5 business days for major incidents.
* **Severity SLAs:**

  * **SEV 1 (Critical):** 15-min response | Executive notification within 1 hour.
  * **SEV 2 (High):** 30-min response | Executive notification within 2 hours.
  * **SEV 3 (Medium):** 4-hour response.
  * **SEV 4 (Low):** 24-hour response.

\---

## Security \& Privacy Notice

> \*\*Note:\*\* This repository has been sanitized for public demonstration purposes. Confidential asset identifiers, proprietary architecture details, external hotline numbers, and specific organizational metadata have been generalized or anonymized to ensure security compliance while showcasing real-world GRC documentation standards.

