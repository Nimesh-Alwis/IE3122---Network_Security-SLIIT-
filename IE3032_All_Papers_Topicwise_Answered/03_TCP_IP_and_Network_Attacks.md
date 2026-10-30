# TCP/IP Stack and Network Attacks

> **Study pack:** IE3032 Network Security final papers — June 2022, June 2023, June 2024 and May 2026.
> **Format:** Simplified exam question + **Simple English exam answer**. Original year, question ID and marks are retained.
> **Source:** Uploaded year-specific `.md` transcripts. Where the transcript lacks a diagram/packet capture or a requested ACL is technically inconsistent, the limitation is explicitly marked.
> **Cisco:** Command examples assume common Cisco IOS syntax; interface/feature support varies by platform. Passwords shown are **exam-provided example credentials**, not safe production passwords.

## 2022 Paper

### 2022 Q2.2.1 — 4 marks

**Question (Simple English):** Explain Data Link Layer functions, addressing, vulnerabilities and attacks.

**Answer (Simple English):**

OSI **Layer 2** frames data, uses **MAC addresses**, controls media access, detects link errors (FCS) and supports switching/VLANs. Common vulnerabilities: unauthenticated ARP/trunks, trusting MAC addresses. Attacks: ARP spoofing, MAC/CAM flooding, VLAN hopping and STP manipulation.

### 2022 Q2.2.2 — 4 marks

**Question (Simple English):** Illustrate an overlapping fragmentation attack.

**Answer (Simple English):**

```text
1. Sender creates IP fragments for same IP datagram (same ID).
2. Fragment A: offset=0, payload covers bytes 0–999.
3. Fragment B: offset=800, payload covers bytes 800–1599.
4. Overlap: bytes 800–999 conflict.
5. A firewall and destination may reassemble differently.
6. An attacker exploits inconsistent validation to evade inspection
   or cause denial of service.
```
Mitigate with consistent fragment reassembly/normalization, drop suspicious overlaps and patch end systems. **Illustrative values**; the PDF figure is not reproduced.

### 2022 Q2.2.3 — 4 marks

**Question (Simple English):** Name three UDP attacks and explain one.

**Answer (Simple English):**

**UDP flood**, **DNS/NTP amplification**, and **UDP port scanning/probing**. Example UDP flood: attacker sends numerous UDP packets to ports, consuming bandwidth/CPU and triggering ICMP Port Unreachable on closed ports. Defend via rate limits, ACLs and upstream DDoS filtering.

### 2022 Q4.1 — 5 marks

**Question (Simple English):** List four reliable-network characteristics and explain one using Zoom.

**Answer (Simple English):**

**Fault tolerance, scalability, Quality of Service (QoS), security.** Example QoS: prioritizing Zoom voice/video minimizes delay, jitter and packet loss during congestion. These are standard network-design characteristics, not four guarantees provided by TCP.

### 2022 Q4.2.1 — 6 marks

**Question (Simple English):** Why does Zoom use both reliable and unreliable transport? Give examples.

**Answer (Simple English):**

**TCP:** reliable, ordered delivery for login/control, chat, files and some web content; retransmits lost data. **UDP:** low-latency delivery for live audio/video, where waiting for old packets hurts real-time quality. Zoom can adapt transport depending on network conditions; actual screen-sharing transport varies.

### 2022 Q4.2.2(i) — 2 marks

**Question (Simple English):** State the three UDP source-port numbers shown in the original capture.

**Answer (Simple English):**

**Not available in the uploaded Markdown transcription.** The question refers to packet-capture details/figure in the original 2022 PDF. Do not guess exact ports; read labels from that figure.

### 2022 Q4.2.2(ii) — 5 marks

**Question (Simple English):** Match UDP streams to Zoom video, audio and static content using Wireshark and justify.

**Answer (Simple English):**

**Cannot assign specific source ports without the actual capture/figure.** Method: compare bitrate, packet size and packet timing. Video usually higher and more variable bandwidth; voice smaller near-periodic packets; static/screen content burstier and content-dependent. These clues are heuristic, not definitive; use the provided graph.

### 2022 Q4.3.1 — 6 marks

**Question (Simple English):** Draw TCP SYN-flood DoS using TCP queues and messages.

**Answer (Simple English):**

```text
Attacker                     Server
  SYN (spoofed IP) --------> [SYN queue: HALF-OPEN] 
  <-------- SYN-ACK           [await final ACK]
  (no ACK)                   [queue entries accumulate]
  SYN SYN SYN ----------->   [backlog fills]
Legitimate SYN ---------->   [connections may time out/drop]
```
TCP normally uses SYN → SYN-ACK → ACK. Attackers send many SYNs but do not finish handshakes. Defenses: SYN cookies, backlog/connection limits, rate limiting and upstream DDoS protection.

### 2022 Q4.3.2 — 6 marks

**Question (Simple English):** Pick two defense-in-depth layers against TCP DoS and compare.

**Answer (Simple English):**

**Network/perimeter layer:** upstream filtering, rate limiting, DDoS scrubbing; absorbs traffic early and protects bandwidth, but filtering may miss sophisticated floods. **Host/transport layer:** SYN cookies, tuned TCP backlog and per-source connection limits; protects server connection state, but cannot solve a saturated upstream link. **Note:** Specific diagram labels in the original paper are not preserved by the transcription.

## 2023 Paper

### 2023 Q4.1(i) — 3 marks

**Question (Simple English):** MAC table is filled with fake addresses: name attack and best defense.

**Answer (Simple English):**

**CAM/MAC flooding.** Many spoofed source MAC addresses fill the switch forwarding table, causing excessive flooding. **Defend:** enable port security with maximum/sticky MAC addresses, disable unused ports and monitor violations.

### 2023 Q4.1(ii) — 3 marks

**Question (Simple English):** Windows XP server crashes after fragmented ICMP Echo: name attack and defense.

**Answer (Simple English):**

**Ping of Death / malformed fragmented ICMP packet attack.** Improper reassembly of oversized/malformed IP fragments can crash old network stacks. **Defend:** upgrade/patch old OS, drop malformed/reassembled oversized packets at the perimeter.

### 2023 Q4.1(iii) — 3 marks

**Question (Simple English):** UDP datagrams to inactive ports make server send ICMP errors: attack and defense.

**Answer (Simple English):**

**UDP flood.** Many UDP packets arrive at closed ports; server spends resources generating ICMP Destination Unreachable replies. **Defend:** rate limiting, firewall drop rules for unnecessary UDP, traffic scrubbing and DDoS mitigation.

## 2024 Paper

### 2024 Q4.1(i) — 3 marks

**Question (Simple English):** DHCP pool exhausted although few legitimate devices: identify attack and mitigate.

**Answer (Simple English):**

**DHCP starvation.** Attacker sends requests with many spoofed MAC/client identifiers to exhaust leases. **Defend:** DHCP snooping, per-port DHCP rate limits, port security and monitoring.

### 2024 Q4.1(ii) — 3 marks

**Question (Simple English):** Unknown person gained access after trying many passwords: attack and mitigation.

**Answer (Simple English):**

**Password brute force / credential guessing.** **Defend:** MFA, login throttling/account lockout, strong unique passwords and alerts.

### 2024 Q4.1(iii) — 3 marks

**Question (Simple English):** Many TCP connections never finish handshake: attack and mitigation.

**Answer (Simple English):**

**TCP SYN flood.** Half-open connections exhaust the SYN backlog. **Defend:** SYN cookies, rate limiting, connection limits and upstream DDoS protection.

## 2026 Paper

### 2026 Q4.1(i) — 3 marks

**Question (Simple English):** Device joins company-like Wi-Fi SSID with weak encryption; traffic intercepted.

**Answer (Simple English):**

**Evil twin / rogue access point.** Attacker broadcasts an SSID imitating company Wi-Fi and tricks devices into joining. **Defend:** WPA2/3-Enterprise with server-certificate validation, disable unsafe auto-join, wireless IDS.

### 2026 Q4.1(ii) — 3 marks

**Question (Simple English):** Shared-project files changed via commands entered in unvalidated fields.

**Answer (Simple English):**

**Injection attack (e.g., command injection, depending on application).** Inputs are trusted as executable commands and alter files. **Defend:** strict input validation, parameterized interfaces/no shell execution, least-privilege application accounts, WAF as extra defense.

### 2026 Q4.1(iii) — 3 marks

**Question (Simple English):** High-volume ICMP traffic overwhelms public server.

**Answer (Simple English):**

**ICMP flood / ping flood DoS.** Excess ICMP consumes bandwidth/CPU. **Defend:** ICMP rate limiting, upstream DDoS protection, traffic filtering; preserve essential diagnostic/PMTU ICMP where needed.

