# Information Security Risk Assessment

## Overview

This project demonstrates a practical information security risk assessment
process for a fictional organisation.

The assessment identifies information security risks, evaluates their
likelihood and potential impact, considers existing controls, and develops
appropriate risk treatment actions.

The project is designed to demonstrate practical application of GRC
principles rather than simply theoretical knowledge.

---

## Objectives

The objectives of this assessment are to:

- Identify and document key information security risks
- Identify relevant assets, threats and vulnerabilities
- Assess inherent risk based on likelihood and impact
- Identify existing security controls
- Determine residual risk after considering existing controls
- Develop appropriate risk treatment plans
- Assign risk owners and review dates
- Produce a structured risk register that can support management decision-making

---

## Assessment Scope

The assessment covers:

- Information assets
- IT infrastructure
- Applications and services
- Users and access
- Data
- Third-party dependencies
- Physical and environmental considerations

The assessment considers risks affecting:

- Confidentiality
- Integrity
- Availability

### Out of Scope

The following areas are outside the scope of this assessment:

- [Add your exclusions here]

---
## Methodology

Risk Assessment Methodology

This project uses a qualitative information-security risk assessment methodology based on a 5 × 5 likelihood and impact matrix.

Risks are identified by evaluating threats and vulnerabilities associated with organisational assets and considering the effectiveness of existing controls. Each risk is assessed according to its likelihood of occurrence and potential impact on confidentiality, integrity and availability.

An inherent risk score is calculated by multiplying likelihood by impact. Risks are then evaluated against defined risk acceptance criteria and assigned an appropriate treatment strategy: avoid, mitigate, transfer or accept.

Following the identification of proposed controls, residual risk is assessed to determine whether the remaining risk falls within the organisation's defined risk appetite.

Each risk is assigned an owner responsible for monitoring and managing the risk. The risk register is reviewed periodically and following significant organisational, technological or security changes.

The methodology is aligned with ISO 27005 risk-management principles and informed by NIST SP 800-30.
---

## Risk Rating Methodology

Risk is assessed using a likelihood × impact model.

### Likelihood

| Rating | Description |
|---|---|
| 1 | Rare |
| 2 | Unlikely |
| 3 | Possible |
| 4 | Likely |
| 5 | Almost Certain |

### Impact

| Rating | Description |
|---|---|
| 1 | Insignificant |
| 2 | Minor |
| 3 | Moderate |
| 4 | Major |
| 5 | Severe |

### Risk Score

**Risk Score = Likelihood × Impact**

| Score | Rating |
|---:|---|
| 1–4 | Low |
| 5–9 | Medium |
| 10–14 | High |
| 15–25 | Critical |

---

## Risk Treatment

Identified risks are considered for the following treatment options:

- **Mitigate** – Implement controls to reduce likelihood and/or impact
- **Avoid** – Stop or change the activity creating the risk
- **Transfer** – Transfer some or all of the risk to a third party
- **Accept** – Formally accept the remaining risk

Risk treatment decisions consider the level of risk, existing controls,
business requirements and available resources.

---

## Frameworks and Standards

This project draws on principles from:

- ISO/IEC 27001
- ISO/IEC 27005
- NIST Cybersecurity Framework
- NIST risk management principles

The project is intended as a portfolio demonstration and is not presented
as a formal certification assessment.

---

## Key Deliverables

The repository contains the following evidence:

| File | Description |
|---|---|
| `risk-register.xlsx` | Completed information security risk register |
| `risk-methodology.md` | Detailed assessment methodology |
| `risk-matrix.png` | Likelihood and impact risk matrix |
| `asset-register.xlsx` | Assets considered during the assessment |
| `README.md` | Project overview and methodology |

---

## Example Risk

One example risk identified during the assessment is:

**Risk:** Unauthorised access to sensitive organisational data

**Threat:** Compromised user credentials

**Vulnerability:** Insufficient access controls and authentication protections

**Potential Impact:**
- Confidentiality breach
- Regulatory consequences
- Financial loss
- Reputational damage

**Initial Risk:** High

**Treatment:** Implement stronger authentication, least-privilege access,
access reviews and monitoring.

**Residual Risk:** Medium

---

## Risk Register

The complete risk register can be found here:

[View the Risk Register](./risk-register.xlsx)

---

## Skills Demonstrated

This project demonstrates practical skills in:

- Information security risk assessment
- Risk identification
- Risk analysis
- Risk scoring
- Risk treatment
- Control assessment
- Asset classification
- Risk register development
- GRC documentation
- Security frameworks
- Management reporting

---

## Project Outcome

The completed assessment provides a structured view of the organisation's
information security risk landscape and identifies prioritised actions for
reducing risk.

The project demonstrates how a GRC practitioner can translate technical and
business risks into a structured format that can support risk-based
decision-making.

---

## Disclaimer

This is a fictional portfolio project created for educational and
professional development purposes. No real organisational information or
confidential data has been used.
