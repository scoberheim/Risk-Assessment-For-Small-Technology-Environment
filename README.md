[README.md](https://github.com/user-attachments/files/32059552/README.md)
# GRC Case Study — Technical Security Lab

This repository documents the Governance, Risk and Compliance (GRC) work applied to my [Technical Security Lab](https://github.com/scoberheim/blob/technical-security-lab) homelab — a Proxmox/OPNsense environment built to practice security architecture, network segmentation, and risk management.

## Overview

Using the homelab as a case study, this project applies core GRC practices to a real, documented technical environment:

- **Asset identification** — cataloging every system in the lab and classifying it by criticality
- **Risk assessment** — identifying threats and vulnerabilities against those assets, scoring them, and recommending treatment
- **Control mapping** *(in progress)* — aligning existing and planned controls to a recognized framework

The goal is to demonstrate practical GRC skills — not just theory — grounded in a real, inspectable environment rather than a hypothetical scenario.

## Contents

| Document | Description |
|---|---|
| [Asset Register](./asset-register.md) | Full inventory of lab assets, with type, criticality, and ownership |
| [Risk Assessment & Risk Register](./risk-assessment-and-register.md) | Methodology, likelihood/impact scoring, and the full risk register |
| [Control Mapping](./control-mapping.md) | Mapping of existing lab controls to NIST CSF 2.0 |

## Methodology

Risk is assessed qualitatively using a 5x5 Likelihood x Impact matrix, an approach consistent with NIST SP 800-30 guidance on conducting risk assessments. Each risk in the register is scored, mapped to a risk band (Low / Medium / High / Critical), and assigned a treatment option (Mitigate, Accept, Transfer, or Avoid). Full detail is in the [Risk Assessment & Risk Register](./risk-assessment-and-register.md) document.

## Skills Demonstrated

- Asset identification and classification
- Qualitative risk assessment (likelihood x impact scoring)
- Risk treatment planning
- Network segmentation and security architecture (see homelab repo)
- GRC documentation and reporting

## Roadmap

- [x] Map existing lab controls to NIST CSF 2.0
- [ ] Add a business impact analysis (BIA) for key assets
- [ ] Document a backup and disaster recovery policy based on findings in the risk register

## How to Navigate This Repo

Every document above is a standard markdown file, so clicking any link renders it directly in GitHub — tables, headers, and formatting included. No external tools or logins are needed to view any part of this project.
