# Risk Assessment & Risk Register — Technical Security Lab

This document extends the asset register and architecture documentation already in this repository. It defines the risk assessment methodology used, and applies it to the lab's assets to produce a risk register.

---

## 1. Risk Assessment Methodology

### 1.1 Purpose
The purpose of this assessment is to identify, analyze, and prioritize risks to the confidentiality, integrity, and availability of assets within the homelab environment, and to document appropriate treatment options. This mirrors the qualitative risk assessment approach used in enterprise GRC programs (e.g., NIST SP 800-30).

### 1.2 Scope
In scope: all assets listed in the Asset Register (Proxmox host, OPNsense firewall, Windows Server, Windows 11, Ubuntu, Kali Linux, Azure Storage Account, Microsoft Sentinel Workspace) and the network segments (Primary LAN, VLAN 30 / Cyber Lab).

### 1.3 Likelihood Scale

| Rating | Level | Description |
|---|---|---|
| 1 | Rare | Would only occur in exceptional circumstances |
| 2 | Unlikely | Could occur but not expected |
| 3 | Possible | Might occur at some point |
| 4 | Likely | Will probably occur in most circumstances |
| 5 | Almost Certain | Expected to occur, possibly multiple times |

### 1.4 Impact Scale

| Rating | Level | Description |
|---|---|---|
| 1 | Negligible | Minimal disruption, no data loss, quickly resolved |
| 2 | Minor | Limited disruption to one system, no sensitive data exposed |
| 3 | Moderate | Disruption to lab operations, possible exposure of lab data |
| 4 | Major | Compromise spreads beyond intended segment, significant rebuild effort |
| 5 | Severe | Compromise reaches primary home network/devices, sustained data loss |

### 1.5 Risk Rating Matrix (Likelihood × Impact)

| | Impact 1 | Impact 2 | Impact 3 | Impact 4 | Impact 5 |
|---|---|---|---|---|---|
| **Likelihood 5** | 5 Low | 10 Medium | 15 High | 20 Critical | 25 Critical |
| **Likelihood 4** | 4 Low | 8 Medium | 12 High | 16 Critical | 20 Critical |
| **Likelihood 3** | 3 Low | 6 Medium | 9 Medium | 12 High | 15 High |
| **Likelihood 2** | 2 Low | 4 Low | 6 Medium | 8 Medium | 10 Medium |
| **Likelihood 1** | 1 Low | 2 Low | 3 Low | 4 Low | 5 Low |

**Rating bands:** Low (1–4) · Medium (5–10) · High (11–16) · Critical (17–25)

### 1.6 Treatment Options
Each identified risk is assigned one of: **Mitigate** (reduce likelihood/impact via controls), **Accept** (residual risk tolerable, document rationale), **Transfer** (e.g., insurance/cloud provider SLA), or **Avoid** (remove the asset/activity).

---

## 2. Risk Register

| ID | Asset | Threat | Vulnerability | Likelihood | Impact | Inherent Risk | Existing Controls | Residual Risk | Treatment | Recommendation |
|---|---|---|---|---|---|---|---|---|---|---|
| R-01 | Proxmox Host | Unauthorized administrative access | Single hypervisor, web UI reachable on LAN, no documented MFA | 3 | 5 | 15 (High) | Access restricted to authorized systems | 9 (Medium) | Mitigate | Enable MFA on Proxmox web UI; restrict access to a dedicated management VLAN |
| R-02 | Proxmox Host | Hardware failure | No redundancy (single node, single 256GB SSD, no RAID) | 3 | 4 | 12 (High) | None documented | 12 (High) | Mitigate | Implement scheduled VM backups to separate storage; document a recovery procedure |
| R-03 | OPNsense Firewall | Firewall misconfiguration allowing lateral movement | Manually maintained rule set; no periodic rule review noted | 3 | 4 | 12 (High) | VLAN segmentation, NAT, firewall rules between segments | 8 (Medium) | Mitigate | Schedule periodic firewall rule reviews; document a change-control process |
| R-04 | VLAN 30 (Cyber Lab) | VLAN hopping / segmentation bypass | Security testing traffic in same physical infrastructure as primary LAN | 2 | 5 | 10 (Medium) | Dedicated VLAN, firewall policy between segments | 8 (Medium) | Mitigate | Periodically test segmentation (e.g., attempt lateral movement from Kali VM to primary LAN) |
| R-05 | Kali Linux VM | Malicious tooling escapes lab boundary | Offensive security tools present in an environment adjacent to home network | 2 | 5 | 10 (Medium) | Isolated to VLAN 30, firewall-controlled | 6 (Medium) | Mitigate | Snapshot VM before testing; disable outbound internet access on this VM by default |
| R-06 | Windows Server | Unpatched OS / services | No documented patch management process | 3 | 3 | 9 (Medium) | None documented | 9 (Medium) | Mitigate | Establish a patching cadence; document patch levels in the asset register |
| R-07 | Windows 11 Desktop | Unpatched OS / malware | General-purpose endpoint, no documented AV/EDR | 3 | 2 | 6 (Medium) | None documented | 6 (Medium) | Mitigate | Enable Windows Defender/EDR logging; forward events to Sentinel |
| R-08 | Ubuntu Server/Desktop | Unpatched services, weak SSH config | No documented hardening baseline | 3 | 3 | 9 (Medium) | None documented | 9 (Medium) | Mitigate | Apply a hardening baseline (e.g., CIS Benchmark for Ubuntu); disable password-based SSH |
| R-09 | Azure Storage Account | Public exposure of stored data | Misconfigured access policy/SAS token | 2 | 4 | 8 (Medium) | None documented | 8 (Medium) | Mitigate | Enforce private endpoints/access keys rotation; enable Azure Defender for Storage |
| R-10 | Microsoft Sentinel Workspace | Logging/detection gaps | Data connectors and analytics rules not fully documented | 2 | 3 | 6 (Medium) | Centralized monitoring exists | 6 (Medium) | Mitigate | Document which log sources feed Sentinel; validate detection coverage against MITRE ATT&CK |
| R-11 | All lab assets | Lack of backup/DR strategy | No documented backup procedure across environment | 3 | 4 | 12 (High) | None documented | 12 (High) | Mitigate | Define and document a backup schedule, retention, and a tested restore procedure |
| R-12 | Lab environment (physical) | Physical access/theft | Home environment, physical security not documented | 2 | 3 | 6 (Medium) | Not documented | 6 (Medium) | Accept / Mitigate | Document physical placement/access controls; disk encryption on host |
| R-13 | Administrative accounts (all systems) | Credential compromise | No documented MFA/password policy across lab | 3 | 4 | 12 (High) | Access restricted to authorized systems | 8 (Medium) | Mitigate | Enforce MFA where supported; adopt a password manager and unique credentials per system |

---

## 3. Notes on Use
- Likelihood/Impact ratings above are illustrative professional judgments for the case study — adjust them to reflect your own risk appetite and observed conditions.
- Residual risk reflects the effect of controls already documented in the repo's Security Controls section; where none exist, residual risk equals inherent risk.
- This register should be reviewed and updated as the lab evolves (new assets, controls implemented, or architecture changes).
