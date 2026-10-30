# Security Policies, DR/BCP and Network Architecture

> **Study pack:** IE3032 Network Security final papers — June 2022, June 2023, June 2024 and May 2026.
> **Format:** Simplified exam question + **Simple English exam answer**. Original year, question ID and marks are retained.
> **Source:** Uploaded year-specific `.md` transcripts. Where the transcript lacks a diagram/packet capture or a requested ACL is technically inconsistent, the limitation is explicitly marked.
> **Cisco:** Command examples assume common Cisco IOS syntax; interface/feature support varies by platform. Passwords shown are **exam-provided example credentials**, not safe production passwords.

## 2023 Paper

### 2023 Q4.2 — 8 marks

**Question (Simple English):** Identify two key security-policy documents, what each covers and two rules each.

**Answer (Simple English):**

**Information Security Policy:** access, authentication, acceptable use, data protection. Rules: (1) MFA required for privileged access; (2) confidential data must use approved encryption. **Incident Response Policy/Plan:** detection, escalation, containment, evidence and recovery. Rules: (1) report suspected incidents to SOC immediately; (2) isolate confirmed infected devices and preserve logs. The paper does not prescribe document titles; valid named policies should fit the scenario.

### 2023 Q4.3(i) — 4 marks

**Question (Simple English):** Replace expensive leased lines while retaining secure branch links and work-from-home.

**Answer (Simple English):**

Use **site-to-site IPsec over public fibre** for branches and **remote-access VPN with MFA** for home workers. Encryption and authentication protect transit; dual ISP links/backup VPN endpoints improve reliability and can cost less than leased lines.

### 2023 Q4.3(ii) — 4 marks

**Question (Simple English):** Bring public website in-house and filter many internal subnetworks: recommend topology and firewall.

**Answer (Simple English):**

Use an **NGFW with Internet/DMZ/INSIDE security zones** and VLAN-aware inter-zone policies. Put public website in a DMZ; protect internal servers and segment departments. Diagram: `Internet → NGFW → DMZ(web)` and `NGFW → internal core/VLANs`. Allow only business-required connections and monitor/IPS. Redundant firewalls reduce a single point of failure.

## 2024 Paper

### 2024 Q4.2 — 8 marks

**Question (Simple English):** Name two DR/BCP policy documents, describe and give two rules each.

**Answer (Simple English):**

**Business Continuity Plan (BCP):** keeps critical business services working during disruption. Rules: (1) activate alternate connectivity/work location for critical teams; (2) review and exercise continuity procedures regularly. **Disaster Recovery Plan (DRP):** restores IT systems/data after incident. Rules: (1) maintain offline/immutable verified backups; (2) periodically test restoration against documented RTO/RPO targets.

### 2024 Q4.3 — 8 marks

**Question (Simple English):** Design HQ security topology for public email/web servers, growing VLANs and inter-subnet filtering.

**Answer (Simple English):**

```text
Internet → Edge Router → HA NGFW
                         ├→ DMZ (public web/mail)
                         └→ Internal core / VLANs
                            ├→ Staff VLAN
                            ├→ HR/Finance VLAN
                            └→ Management VLAN
```
**Choose NGFW:** application-aware IPS/logging, zone policies for Internet→DMZ, DMZ→internal and VLAN-to-VLAN traffic. Deny unneeded traffic; add HA/monitoring and least privilege.

## 2026 Paper

### 2026 Q4.2 — 8 marks

**Question (Simple English):** Identify two security governance/DR/BCP documents; explain purpose, coverage, two rules each.

**Answer (Simple English):**

**Information Security Policy:** defines access, classification and security responsibilities. Rules: (1) MFA for admins; (2) least-privilege access with quarterly review. **BCP/DR Plan:** continuity, RTO/RPO, backups, alternate sites, restoration. Rules: (1) test recoveries periodically; (2) keep immutable/off-site backups and documented restore priority. Other suitable paired documents can be accepted if clearly justified.

### 2026 Q4.3(i) — 4 marks

**Question (Simple English):** Draw HQ architecture with Internet analytics platform, DMZ, internal HR/Finance and departmental VLAN inspection.

**Answer (Simple English):**

```text
Internet → Edge router → HA NGFW
                         ├→ Analytics DMZ (public front end)
                         └→ Internal segmentation firewall/core
                            ├→ HR VLAN
                            ├→ Finance VLAN
                            ├→ Department VLANs
                            └→ Management VLAN
```
Allow only specific external→DMZ ports, approved DMZ→backend APIs, and explicit inter-VLAN flows; deny direct Internet→HR/Finance.

### 2026 Q4.3(ii) — 4 marks

**Question (Simple English):** Recommend and justify best HQ firewall architecture.

**Answer (Simple English):**

**Layered NGFW architecture:** perimeter NGFW separates Internet/DMZ/inside; internal segmentation policies inspect sensitive VLAN traffic. Application identification, IPS, logging and least privilege protect analytics and internal financial records. Use an HA pair to reduce firewall single point of failure.

