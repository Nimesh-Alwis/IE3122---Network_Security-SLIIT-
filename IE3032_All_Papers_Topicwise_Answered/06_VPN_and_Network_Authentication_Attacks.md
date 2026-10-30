# VPN and Network Authentication Attacks

> **Study pack:** IE3032 Network Security final papers — June 2022, June 2023, June 2024 and May 2026.
> **Format:** Simplified exam question + **Simple English exam answer**. Original year, question ID and marks are retained.
> **Source:** Uploaded year-specific `.md` transcripts. Where the transcript lacks a diagram/packet capture or a requested ACL is technically inconsistent, the limitation is explicitly marked.
> **Cisco:** Command examples assume common Cisco IOS syntax; interface/feature support varies by platform. Passwords shown are **exam-provided example credentials**, not safe production passwords.

## 2023 Paper

### 2023 Q3.1 — 6 marks

**Question (Simple English):** Why deploy both site-to-site and remote-access VPNs for a global company?

**Answer (Simple English):**

**Site-to-site IPsec VPN** connects branch/partner networks securely through gateway-to-gateway tunnels; transparent to local users. **Remote-access SSL/IPsec VPN** connects individual travelling/at-home workers to company applications. Use both because network-to-network sites and roaming endpoint users require different access models. Enforce MFA and least privilege.

### 2023 Q3.3 — 5 marks

**Question (Simple English):** Define replay attack, explain how it works and prevent it.

**Answer (Simple English):**

An attacker **captures a valid message/token and resends it later** to trick a receiver into accepting an old transaction or authentication. Countermeasures: unique nonce/challenge, sequence numbers, timestamps with expiry windows, anti-replay checks and protected authenticated sessions. Encryption alone does not always stop replay.

## 2024 Paper

### 2024 Q3.1(i) — 2 marks

**Question (Simple English):** Explain site-to-site versus remote-access VPN.

**Answer (Simple English):**

**Site-to-site VPN:** joins entire branch networks using gateway-to-gateway tunnels. **Remote-access VPN:** lets an individual endpoint/user connect securely to enterprise resources over the Internet.

### 2024 Q3.1(ii) — 4 marks

**Question (Simple English):** Choose secure VPNs for global medical-company branches and staff.

**Answer (Simple English):**

Use **IPsec site-to-site** between hospitals/branches and **remote-access VPN** for travelling/remote clinicians with MFA and device posture checks. Encrypt sensitive data in transit, restrict access to necessary applications and log access.

### 2024 Q3.4 — 5 marks

**Question (Simple English):** What is eavesdropping and how do you prevent it?

**Answer (Simple English):**

**Eavesdropping** is secretly listening to/capturing network communication to obtain sensitive information. It may occur over unencrypted Wi-Fi or compromised networks. **Prevention:** TLS/HTTPS, IPsec/VPNs, strong Wi-Fi encryption with proper certificate validation, segmentation and physical/network access controls.

## 2026 Paper

### 2026 Q3.1 — 6 marks

**Question (Simple English):** Recommend VPN types for overseas distribution centers and travellers.

**Answer (Simple English):**

**Distribution centers:** site-to-site IPsec between fixed branch gateways for always-on secure network links. **Travelling employees:** remote-access VPN with MFA, endpoint checks and least-privilege access on public hotel/airport networks. Both protect data in transit; neither replaces endpoint security.

### 2026 Q3.4 — 5 marks

**Question (Simple English):** Fake login portal appears after DNS manipulation: name attack and two fixes.

**Answer (Simple English):**

**DNS spoofing / DNS cache poisoning (DNS-based redirection):** attacker alters or forges DNS results so the correct domain resolves to a phishing server. **Mitigations:** validate DNSSEC where supported and use trusted protected DNS resolvers; enforce HTTPS certificate validation/HSTS and educate users not to bypass certificate warnings. MFA reduces account takeover impact.

