# IoT and Network Security Fundamentals

> **Study pack:** IE3032 Network Security final papers — June 2022, June 2023, June 2024 and May 2026.
> **Format:** Simplified exam question + **Simple English exam answer**. Original year, question ID and marks are retained.
> **Source:** Uploaded year-specific `.md` transcripts. Where the transcript lacks a diagram/packet capture or a requested ACL is technically inconsistent, the limitation is explicitly marked.
> **Cisco:** Command examples assume common Cisco IOS syntax; interface/feature support varies by platform. Passwords shown are **exam-provided example credentials**, not safe production passwords.

## 2022 Paper

### 2022 Q1.1 — 6 marks

**Question (Simple English):** Explain one function of each IoT layer (Perception, Network, Analysis) with examples.

**Answer (Simple English):**

**Perception:** Sensors collect physical data, e.g., a temperature sensor measures heat. **Network:** Transfers sensor readings via Wi-Fi, Zigbee or cellular networks to servers. **Analysis:** Processes measurements and produces decisions or alerts, e.g., detects abnormal temperature.

### 2022 Q1.2.1 — 3 marks

**Question (Simple English):** Name common IoT attacks mentioned in the report.

**Answer (Simple English):**

Telnet-based device compromise, **DDoS** attacks, unauthorized cryptocurrency mining and theft of confidential information. The report describes Telnet as a common entry method, not a separate outcome.

### 2022 Q1.2.2 — 2 marks

**Question (Simple English):** Choose one IoT attack and explain its vulnerability.

**Answer (Simple English):**

**Example—IoT DDoS botnet:** Default/weak passwords and exposed Telnet let attackers compromise IoT devices. They can then remotely command many devices to flood a target server.

### 2022 Q1.2.3 — 4 marks

**Question (Simple English):** Give a technical mitigation for the selected IoT attack.

**Answer (Simple English):**

Disable Telnet and use SSH if remote management is essential; change default credentials to strong unique passwords; update IoT firmware; segment IoT VLANs, restrict outbound traffic and monitor for botnet behaviour. Rate limiting/upstream DDoS protection helps defend the target.

## 2024 Paper

### 2024 Q1.1 — 5 marks

**Question (Simple English):** Explain the link among threat actor, asset, vulnerability, attack and impact.

**Answer (Simple English):**

A **threat actor** (person/group) targets an **asset** (valuable system/data), exploits a **vulnerability** (weakness), performs an **attack** (harmful action) and creates an **impact** (data loss, downtime or financial damage). Example: external criminal → outdated server → known flaw → remote compromise → outage.

### 2024 Q1.2(i) — 4 marks

**Question (Simple English):** Analyse administrator copying user passwords: actor, asset, vulnerability, mitigation.

**Answer (Simple English):**

**Actor:** internal privileged administrator. **Asset:** user credentials/account database. **Weakness:** excessive admin permissions and insufficient auditing. **Mitigation:** least privilege, separate duties, protected password hashing, privileged access management and audit alerts.

### 2024 Q1.2(ii) — 4 marks

**Question (Simple English):** Analyse botnet attack on an old online-store server.

**Answer (Simple English):**

**Actor:** external competing company/botnet operator. **Asset:** online store/availability. **Weakness:** aging, under-protected infrastructure and inadequate DDoS capacity. **Mitigation:** upstream DDoS mitigation/CDN, traffic scrubbing, rate limits and patched/modernized infrastructure.

## 2026 Paper

### 2026 Q1.1 — 7 marks

**Question (Simple English):** Define threat actor, asset, vulnerability, attack and impact; show their order and example.

**Answer (Simple English):**

**Threat actor:** entity able to cause harm. **Asset:** resource worth protecting. **Vulnerability:** exploitable weakness. **Attack:** exploitation attempt/action. **Impact:** resulting loss. Chain: Actor → targets Asset → exploits Vulnerability → Attack → Impact. Example: attacker → DNS server → missing patches → query flooding → service outage.

### 2026 Q1.2(i) — 4 marks

**Question (Simple English):** Contractor accessed management subnet and took switch backups: identify actor, asset, weakness and mitigation.

**Answer (Simple English):**

**Actor:** internal/authorized contractor abusing access (insider-type threat). **Asset:** management subnet and switch configuration backups. **Weakness:** incorrect routing/segmentation allowing contractor reachability. **Mitigation:** restrict management VLAN via ACL/NGFW, least privilege, verify routes, MFA and audit access.

### 2026 Q1.2(ii) — 4 marks

**Question (Simple English):** Compromised IoT devices overwhelm outdated DNS server: identify actor, asset, weakness and mitigation.

**Answer (Simple English):**

**Actor:** external malicious group controlling IoT botnet. **Asset:** DNS service and availability. **Weakness:** outdated DNS server and weak DDoS controls. **Mitigation:** patch DNS service and use upstream DDoS protection, DNS rate limiting, anycast/redundancy and monitoring.

