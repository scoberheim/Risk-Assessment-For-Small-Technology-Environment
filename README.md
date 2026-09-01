# Cybersecurity-Risk-Assessment-Risk-Register

# Risk Assessment Methodology

## 1. Purpose

The purpose of this methodology is to provide a consistent and repeatable approach for identifying, analysing, prioritising and treating information security risks.

The methodology is designed to support alignment with recognised security frameworks, including the **NIST Cybersecurity Framework (NIST CSF)** and **ISO/IEC 27001**.

---

## 2. Core Assessment Steps

### Step 1 – Define Scope and Objectives

Clearly define the scope of the assessment, including the systems, applications, infrastructure, data and users being assessed.

The assessment objectives should also be established. These may include:

* Identifying and prioritising information security risks
* Assessing the effectiveness of existing security controls
* Supporting compliance with security frameworks
* Identifying areas requiring risk treatment or additional controls
* Providing information to support management decision-making

For this assessment, the scope includes the systems and infrastructure documented within the accompanying Asset Register.

---

### Step 2 – Asset Identification and Valuation

Identify and document the assets within the defined assessment scope.

Assets may include:

* Hardware
* Virtual machines
* Servers
* Network infrastructure
* Applications and software
* Cloud services
* Data
* Security and monitoring services

Each asset is assigned a unique Asset ID and assessed according to its business importance.

The potential impact on the **Confidentiality, Integrity and Availability (CIA)** of each asset is considered using the following scale:

| Rating         | Description                                           |
| -------------- | ----------------------------------------------------- |
| **Low (1)**    | Compromise would have limited impact                  |
| **Medium (2)** | Compromise would have a noticeable or moderate impact |
| **High (3)**   | Compromise would have significant impact              |

Confidentiality, Integrity and Availability are assessed independently because an asset may have different levels of importance across each security objective.

The CIA assessment provides an input into the subsequent risk impact assessment.

---

### Step 3 – Threat and Vulnerability Identification

Identify credible threats and vulnerabilities that could affect the assets within scope.

Threats may include:

* Malware and ransomware
* Unauthorised access
* Credential compromise
* Insider error or misuse
* Data loss
* Network attacks
* System failure
* Misconfiguration
* Third-party or supply-chain compromise

Vulnerabilities and weaknesses may be identified through:

* Configuration reviews
* Vulnerability scanning
* Security testing
* Review of system architecture
* Review of existing controls
* Threat modelling
* Previous incidents or known weaknesses

Where appropriate, recognised techniques such as **STRIDE** or vulnerability scoring methods such as **CVSS** may be used to support the assessment.

---

### Step 4 – Risk Analysis and Calculation

Each identified risk is assessed according to its **likelihood** and **impact**.

Likelihood represents the probability that the identified threat will successfully exploit the vulnerability.

Impact represents the potential consequence to the organisation if the risk materialises. Impact may include effects on:

* Confidentiality
* Integrity
* Availability
* Operations
* Financial performance
* Legal or regulatory obligations
* Reputation

For this assessment, risk is calculated using:

**Risk Score = Likelihood × Impact**

Both likelihood and impact are scored from **1 to 3**.

| Rating         | Likelihood          | Impact                   |
| -------------- | ------------------- | ------------------------ |
| **1 – Low**    | Unlikely to occur   | Limited consequences     |
| **2 – Medium** | Possible occurrence | Moderate consequences    |
| **3 – High**   | Likely to occur     | Significant consequences |

The resulting score is classified using the following risk matrix:

| Likelihood \ Impact |    1 – Low | 2 – Medium |     3 – High |
| ------------------- | ---------: | ---------: | -----------: |
| **1 – Low**         |    1 – Low |    2 – Low |   3 – Medium |
| **2 – Medium**      |    2 – Low | 4 – Medium |     6 – High |
| **3 – High**        | 3 – Medium |   6 – High | 9 – Critical |

Where appropriate, quantitative approaches such as **CVSS** or **Annual Loss Expectancy (ALE)** may be used to provide additional analysis.

---

### Step 5 – Prioritisation and Mitigation

Risks are prioritised according to their calculated risk rating, with higher risks receiving greater attention.

For each risk, an appropriate treatment strategy is selected:

* **Mitigate** – Implement or improve controls to reduce the likelihood or impact.
* **Transfer** – Transfer some or all of the financial or operational impact to a third party, such as through insurance or outsourcing.
* **Accept** – Formally accept the risk where it falls within the organisation's risk appetite.
* **Avoid** – Remove the activity, system or process responsible for the risk.

Existing security controls are considered when determining the remaining level of risk.

---

### Step 6 – Reporting and Documentation

The assessment findings are documented within a **Risk Register**.

The Risk Register should record, where applicable:

* Risk ID
* Asset
* Threat
* Vulnerability
* Existing controls
* Likelihood
* Impact
* Inherent risk
* Risk treatment
* Recommended actions
* Risk owner
* Target completion date
* Residual risk
* Risk status

Significant risks should be communicated to appropriate stakeholders to support informed decision-making, resource allocation and risk acceptance.

---

### Step 7 – Continuous Review

Risk assessment is treated as an ongoing process rather than a one-time activity.

The assessment should be reviewed periodically and when significant changes occur, including:

* Introduction of new systems or technologies
* Significant infrastructure changes
* Changes to business processes
* Security incidents
* Major vulnerabilities or emerging threats
* Changes in regulatory or compliance requirements
* Changes to the organisation's risk appetite

For this project, the risk register should be reviewed at least annually or following a significant change to the assessed environment.

---

## 3. Assessment Flow

The overall assessment process follows:

**Define Scope → Identify & Value Assets → Identify Threats & Vulnerabilities → Analyse Risk → Prioritise & Treat → Report → Review**

This provides a repeatable process for identifying information security risks and ensuring that risks are appropriately documented, treated and monitored.

