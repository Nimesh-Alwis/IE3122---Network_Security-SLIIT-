# Endpoint, Zero Trust and Incident Response

> **Study pack:** IE3032 Network Security final papers — June 2022, June 2023, June 2024 and May 2026.
> **Format:** Simplified exam question + **Simple English exam answer**. Original year, question ID and marks are retained.
> **Source:** Uploaded year-specific `.md` transcripts. Where the transcript lacks a diagram/packet capture or a requested ACL is technically inconsistent, the limitation is explicitly marked.
> **Cisco:** Command examples assume common Cisco IOS syntax; interface/feature support varies by platform. Passwords shown are **exam-provided example credentials**, not safe production passwords.

## 2022 Paper

### 2022 Q2.1 — 4 marks

**Question (Simple English):** Explain two categories of endpoint security with examples.

**Answer (Simple English):**

**Endpoint protection software:** antivirus/EDR and host firewall protect devices against malware and unauthorized activity. **Endpoint management/hardening:** patch management, device encryption, strong authentication and secure configuration reduce exploitable weaknesses. **Source note:** paper names no specific categories; these are useful functional categories rather than a claimed lecturer taxonomy.

### 2022 Q2.3.1 — 3 marks

**Question (Simple English):** Give three integrity requirements for the online student-tutor platform.

**Answer (Simple English):**

**Data integrity in storage:** prevent unauthorized edits to bids, user profiles and learning materials via access controls and audit logs. **Integrity in transit:** use TLS and authenticated APIs to detect tampering. **Integrity of updates/actions:** validate inputs, verify file hashes/signatures where appropriate and keep tamper-evident records of changes.

### 2022 Q2.3.2(i) — 5 marks

**Question (Simple English):** List five components of a password policy.

**Answer (Simple English):**

Minimum length; uniqueness/no commonly breached passwords; secure storage (salted password hashes); MFA especially for privileged users; lockout/rate-limit and password-reset procedure. Avoid routine forced expiry without evidence of compromise unless required by policy.

### 2022 Q2.3.2(ii) — 4 marks

**Question (Simple English):** List four phases of worm incident response.

**Answer (Simple English):**

**Preparation:** response plan, backups, EDR. **Detection/analysis:** identify worm and affected hosts. **Containment/eradication:** isolate devices, kill malicious processes, remove persistence and patch weaknesses. **Recovery/lessons learned:** restore and verify clean systems, monitor, improve controls. Some incident-handling frameworks split these into more detailed stages.

### 2022 Q2.3.2(iii) — 3 marks

**Question (Simple English):** Compare two network-testing tools useful during a worm attack.

**Answer (Simple English):**

**Nmap:** scans hosts/ports/services to find exposed services and infected/reachable hosts; does not remove malware. **Wireshark:** captures/analyzes packets to spot worm scanning, suspicious destinations and lateral movement; does not remove malware. Use EDR/AV for eradication.

### 2022 Q2.4 — 4 marks

**Question (Simple English):** Explain Zero Trust using one example.

**Answer (Simple English):**

**Zero Trust = never trust automatically; verify every access request.** Example: even an employee on office Wi-Fi must authenticate with MFA and be authorized to reach a finance server. Device posture, least privilege and continuous checks limit lateral movement.

