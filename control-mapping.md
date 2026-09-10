# Control Mapping — NIST CSF 2.0

This document maps existing and planned controls in the Technical Security Lab to the NIST Cybersecurity Framework (CSF) 2.0. It complements the [Asset Register](./asset-register.md) and [Risk Assessment & Risk Register](./risk-assessment-and-register.md) by showing which framework functions are currently addressed, and where gaps remain.

## Why NIST CSF 2.0

NIST CSF 2.0 was chosen because it's function-based rather than prescriptive, making it a natural fit for mapping against a homelab that already has documented controls (segmentation, firewall policy, access restrictions) without forcing an enterprise-scale control set onto a single-host environment.

## Mapping

| Function | Category | Lab Control(s) Applied | Status | Gap / Recommendation |
|---|---|---|---|---|
| **Identify** | Asset Management (ID.AM) | Asset Register documents all VMs, cloud assets, and criticality ratings | Implemented | Add data classification per asset |
| **Identify** | Risk Assessment (ID.RA) | Risk Register with likelihood/impact scoring | Implemented | Schedule periodic re-assessment (e.g. quarterly) |
| **Identify** | Governance (ID.GV) | This repository serves as informal governance documentation | Partial | Document a lab security policy / rules of engagement for testing |
| **Protect** | Identity Management & Access Control (PR.AA) | Administrative access restricted to authorized systems | Partial | Add MFA on Proxmox/OPNsense web UIs; adopt unique credentials per system |
| **Protect** | Data Security (PR.DS) | Network segmentation isolates Cyber Lab (VLAN 30) from Primary LAN | Implemented | Add disk encryption on Proxmox host; review Azure Storage access policy |
| **Protect** | Platform Security (PR.PS) | OPNsense firewall rules control inter-segment traffic | Implemented | Establish a patch management cadence for all VMs |
| **Protect** | Technology Infrastructure Resilience (PR.IR) | Single Proxmox host, no redundancy | Not implemented | Define and implement a backup/DR procedure |
| **Detect** | Continuous Monitoring (DE.CM) | Microsoft Sentinel Workspace centralizes logging | Partial | Document which log sources currently feed Sentinel; close coverage gaps |
| **Detect** | Adverse Event Analysis (DE.AE) | No documented alerting/analytics rules | Not implemented | Build baseline Sentinel analytics rules mapped to expected lab activity |
| **Respond** | Incident Management (RS.MA) | No documented incident response process | Not implemented | Write a lightweight IR runbook (even for a homelab, this demonstrates capability) |
| **Recover** | Incident Recovery Plan Execution (RC.RP) | No backup or recovery procedure documented | Not implemented | Define recovery point/time objectives and test a restore from backup |

## Status Key
- **Implemented** — control is in place and documented elsewhere in this repo or the homelab repo
- **Partial** — some element of the control exists but doesn't fully meet the category's intent
- **Not implemented** — no corresponding control currently exists

## Next Steps
The "Not implemented" and "Partial" rows above are the natural backlog for this project — each could become its own short deliverable (an IR runbook, a backup policy, an MFA rollout) that further builds out this GRC case study.
