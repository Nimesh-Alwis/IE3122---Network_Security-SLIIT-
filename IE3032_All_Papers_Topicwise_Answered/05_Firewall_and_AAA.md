# Firewall, ACL and AAA

> **Study pack:** IE3032 Network Security final papers — June 2022, June 2023, June 2024 and May 2026.
> **Format:** Simplified exam question + **Simple English exam answer**. Original year, question ID and marks are retained.
> **Source:** Uploaded year-specific `.md` transcripts. Where the transcript lacks a diagram/packet capture or a requested ACL is technically inconsistent, the limitation is explicitly marked.
> **Cisco:** Command examples assume common Cisco IOS syntax; interface/feature support varies by platform. Passwords shown are **exam-provided example credentials**, not safe production passwords.

## 2022 Paper

### 2022 Q3.1 — 4 marks

**Question (Simple English):** What is an ACL? Name four packet fields it can filter.

**Answer (Simple English):**

An **Access Control List (ACL)** is an ordered set of permit/deny rules that filters network traffic. Four common extended-ACL fields: **source IP, destination IP, source TCP/UDP port and destination TCP/UDP port**. Standard ACLs mainly match source IP.

### 2022 Q3.2.1 — 3 marks

**Question (Simple English):** List four firewall limitations with short explanations.

**Answer (Simple English):**

**Insider threats:** traffic inside protected segments may bypass perimeter checks. **Encrypted traffic:** payload threats may be hidden without authorized decryption. **Malware/allowed traffic:** a legitimate permitted connection may carry an exploit. **Misconfiguration:** overly broad policies can expose services.

### 2022 Q3.2.2 — 3 marks

**Question (Simple English):** List four firewall best practices.

**Answer (Simple English):**

**Default deny/least privilege**; **patch and update firmware/signatures**; **periodically review rules/remove unused permits**; **enable centralized logging/monitoring and alerting**.

### 2022 Q3.3 — 5 marks

**Question (Simple English):** Why are ACL/stateful firewalls insufficient for Zoom threats? Why prefer NGFW?

**Answer (Simple English):**

**ACL:** decides mainly from IPs, protocols and ports, not Zoom application behaviour. **Stateful firewall:** tracks established flows but may allow malicious application traffic within an allowed session. **NGFW:** adds application identification, deep packet inspection, IPS and granular policies. It can distinguish Zoom from other traffic sharing TCP 443. **Caveat:** encrypted payload inspection may require lawful/authorized decryption and Zoom end-to-end encryption may limit visibility.

### 2022 Q3.4 — 2 marks

**Question (Simple English):** Compare RADIUS and TACACS+ by function, pros and cons.

**Answer (Simple English):**

**RADIUS:** centralized network-access AAA (Wi-Fi/802.1X/VPN), commonly UDP 1812 auth and 1813 accounting; scalable but less fine-grained command authorization. **TACACS+:** centralized administrator/device access using TCP 49, separates authentication/authorization/accounting and supports per-command policy; richer control but requires compatible server/device support. Both need secure configuration.

### 2022 Q3.5 — 3 marks

**Question (Simple English):** What is SSO’s greatest disadvantage and how can it be reduced?

**Answer (Simple English):**

**Single point of compromise:** a stolen SSO credential/session can give access to many applications; IdP outage can also affect many services. **Mitigate:** phishing-resistant MFA, short/managed sessions, risk-based checks, account monitoring and redundant identity-provider infrastructure.

## 2023 Paper

### 2023 Q2.1(i) — 2 marks

**Question (Simple English):** For a public web server plus protected internal servers, choose between DMZ and ZBF.

**Answer (Simple English):**

Use a **DMZ** for the public-facing web server to separate it from backend systems, and **zone-based firewall policies** to restrict Internet↔DMZ↔internal flows. They are complementary: DMZ is a network segment, ZBF is a policy/configuration approach. If required to name one for placing the public server, choose DMZ.

### 2023 Q2.1(ii) — 6 marks

**Question (Simple English):** Configure R3 zones IN-ZONE/OUT-ZONE and assign G0/1, S0/0/1.

**Answer (Simple English):**

```cisco
conf t
zone security IN-ZONE
zone security OUT-ZONE
interface g0/1
 zone-member security IN-ZONE
exit
interface s0/0/1
 zone-member security OUT-ZONE
end
```
To **allow** inter-zone traffic, a separate zone-pair, class-map and policy-map are also needed; the question requests only zones and memberships.

### 2023 Q2.2 — 12 marks

**Question (Simple English):** Set standard named ACL for only 192.168.20.4 and 192.168.100.100; outbound Fa0/1; numbered ACL 1 for source 192.168.11.0/24.

**Answer (Simple English):**

```cisco
conf t
// Enter global configuration mode
ip access-list standard File_Server_Restrictions
// Create a standard named ACL
 permit host 192.168.20.4 // Allow PC1
 permit host 192.168.100.100 // Allow Web Server
 deny any // Block all other source IP addresses
exit// Exit ACL configuration mode
interface fa0/1
// Select FastEthernet 0/1 interface
 ip access-group File_Server_Restrictions out
 // Apply ACL to outgoing traffic
exit// Exit interface configuration mode
access-list 1 deny 192.168.11.0 0.0.0.255
// Deny source network 192.168.11.0/24
access-list 1 permit any
// Allow all other source IP addresses
end// Exit configuration mode
```
**Important source inconsistency:** a standard ACL cannot match destination network `192.168.20.0/24`; it matches **source only**. The original request to deny traffic **to** that subnet **from** `192.168.11.0/24` requires an **extended** ACL (below) on an appropriate interface. Cisco ACL names cannot contain spaces; underscores used above.
```cisco
ip access-list extended BLOCK_TO_20
 deny ip 192.168.11.0 0.0.0.255 192.168.20.0 0.0.0.255
 permit ip any any
```
Place it on the correct interface/direction for the topology.

### 2023 Q2.3 — 5 marks

**Question (Simple English):** What is NGFW? Compare with a traditional firewall.

**Answer (Simple English):**

**Traditional firewall:** packet/IP/port filtering or stateful flow tracking; often limited application context. **NGFW:** adds application/user awareness, integrated IPS, DPI, and threat intelligence (product-dependent). NGFW can block malicious web activity within a permitted HTTPS connection more selectively, subject to encryption visibility and configuration.

### 2023 Q3.2(i) — 9 marks

**Question (Simple English):** Configure R2 TACACS+ and local backup; R3 RADIUS; apply console AAA.

**Answer (Simple English):**

```cisco
! Router R2
conf t
aaa new-model
username Admin2 privilege 15 secret admin2pa55
tacacs server TAC_R2
 address ipv4 192.168.2.2
 key tacacspa55
exit
aaa group server tacacs+ T_GROUP
 server name TAC_R2
exit
aaa authentication login default group T_GROUP local
line con 0
 login authentication default
exit
end
! Router R3
conf t
aaa new-model
radius server RAD_R3
 address ipv4 192.168.3.2 auth-port 1812 acct-port 1813
 key radiuspa55
exit
aaa group server radius R_GROUP
 server name RAD_R3
exit
aaa authentication login default group R_GROUP local
line con 0
 login authentication default
end
```
`local` fallback normally applies on server error/unreachability, not rejection of incorrect credentials. IOS releases may use older `tacacs-server host` / `radius-server host` syntax.

### 2023 Q3.2(ii) — 5 marks

**Question (Simple English):** Compare local and server-based AAA and recommend one.

**Answer (Simple English):**

**Local AAA:** device-stored users; works offline but hard to manage across many routers and has fragmented logs. **Server-based AAA:** central user policy, immediate revocation and audit trails; depends on reachable AAA servers. **Recommendation:** central TACACS+ for device administration/RADIUS for network access **with a tested local emergency account** and redundant servers.

## 2024 Paper

### 2024 Q2.1(i) — 6 marks

**Question (Simple English):** Compare strengths of ZBFW, NGFW and WAF for customer-facing web app plus internal servers.

**Answer (Simple English):**

**ZBFW:** policies between INSIDE/OUTSIDE/DMZ zones, useful for segmentation. **NGFW:** application/user-aware filtering, IPS and centralized visibility for threats traversing zones. **WAF:** inspects HTTP(S) requests for web-specific attacks such as SQL injection/XSS and protects the web application. A WAF is specialized, not a substitute for network segmentation.

### 2024 Q2.1(ii) — 6 marks

**Question (Simple English):** Recommend the best firewall type for public web app and internal segmentation.

**Answer (Simple English):**

**NGFW** is the strongest single choice for combining network segmentation, application-level visibility and IPS. Place public-facing servers in a DMZ, isolate internal inventory/backend VLANs and allow only necessary flows. Add WAF for focused web-application protection where possible. A ZBFW also provides good policy organization.

### 2024 Q2.2 — 6 marks

**Question (Simple English):** Configure R3 zones INTERNAL/EXTERNAL and assign Fa0/1, S0/0/1.

**Answer (Simple English):**

```cisco
conf t
zone security INTERNAL
zone security EXTERNAL
interface fa0/1
 zone-member security INTERNAL
exit
interface s0/0/1
 zone-member security EXTERNAL
end
```
Zone-pair and service-policy are additionally needed to pass traffic across zones.

### 2024 Q2.3 — 7 marks

**Question (Simple English):** Create standard named ACL Rule1, allow two IPs, deny rest, outbound Fa0/1 and numbered ACL 1.

**Answer (Simple English):**

```cisco
conf t
ip access-list standard Rule1
 permit host 192.168.20.1
 permit host 192.168.100.1
 deny any
exit
interface fa0/1
 ip access-group Rule1 out
exit
access-list 1 deny any
end
```
**Exam-source ambiguity:** the additional numbered **standard** ACL 1 cannot selectively block only traffic **to** `192.168.20.0/24` while allowing other destinations. Use an **extended** ACL when both source and destination are needed. `access-list 1 deny any` is only a literal block-all demonstration, **not a correct destination-selective solution**; do not apply it for that goal. A practical correct extended example is:
```cisco
ip access-list extended BLOCK_OTHER_TO_20
 permit ip host 192.168.20.1 192.168.20.0 0.0.0.255
 permit ip host 192.168.100.1 192.168.20.0 0.0.0.255
 deny ip any 192.168.20.0 0.0.0.255
 permit ip any any
```

### 2024 Q3.2 — 9 marks

**Question (Simple English):** Configure R2 Admin and TACACS+ (192.168.2.2, key tcspwd); R3 RADIUS (192.168.3.2, key rdspwd); console AAA.

**Answer (Simple English):**

```cisco
! R2
conf t
aaa new-model
username Admin privilege 15 secret pwd1234
tacacs server TAC_R2
 address ipv4 192.168.2.2
 key tcspwd
exit
aaa group server tacacs+ T_GROUP
 server name TAC_R2
exit
aaa authentication login default group T_GROUP local
line con 0
 login authentication default
end
! R3
conf t
aaa new-model
radius server RAD_R3
 address ipv4 192.168.3.2 auth-port 1812 acct-port 1813
 key rdspwd
exit
aaa group server radius R_GROUP
 server name RAD_R3
exit
aaa authentication login default group R_GROUP local
line con 0
 login authentication default
end
```
R3 also needs a configured local user if its `local` fallback is to succeed.

### 2024 Q3.3 — 5 marks

**Question (Simple English):** Compare local AAA with server-based AAA and make a recommendation.

**Answer (Simple English):**

**Local:** independent of server, simple for small deployments; difficult user lifecycle and decentralized auditing. **Server-based:** central control/audits and consistent policy; server/connectivity dependency. **Recommend** redundant centralized AAA plus local break-glass fallback.

## 2026 Paper

### 2026 Q2.1(i) — 6 marks

**Question (Simple English):** Strengths of ZBFW, NGFW and API/Application-Layer Gateway for an Internet payment portal.

**Answer (Simple English):**

**ZBFW:** enforces controlled traffic paths between Internet, DMZ and internal finance zones. **NGFW:** application-aware inspection, IPS, threat visibility and segmentation. **API/application-layer gateway:** inspects and controls application/API requests, validates allowed methods and routes calls; can help enforce API-specific rules depending on product.

### 2026 Q2.1(ii) — 6 marks

**Question (Simple English):** Recommend one firewall type for external portal, isolated finance backends and visibility.

**Answer (Simple English):**

Choose an **NGFW**: segment portal/DMZ from authentication and verification servers; allow only approved API/transaction flows; use IPS, application visibility, logging and least-privilege rules. Add an API gateway/WAF as specialized application protection where feasible.

### 2026 Q2.2 — 6 marks

**Question (Simple English):** Create zones CAMPUS/WAN-EDGE on R2, assign Gi0/0 and S0/1/0.

**Answer (Simple English):**

```cisco
conf t
zone security CAMPUS
zone security WAN-EDGE
interface gi0/0
 zone-member security CAMPUS
exit
interface s0/1/0
 zone-member security WAN-EDGE
end
```
A zone pair/policy would be needed to permit inter-zone traffic.

### 2026 Q2.3 — 7 marks

**Question (Simple English):** Secure key/log repository: standard named SECURE-ACCESS, two permitted hosts, inbound Gi0/1; ACL 12 to deny others from key subnet.

**Answer (Simple English):**

```cisco
conf t
ip access-list standard SECURE-ACCESS
 permit host 10.5.50.10
 permit host 10.5.100.5
 deny any
exit
interface gi0/1
 ip access-group SECURE-ACCESS in
exit
end
```
**Directional warning:** this only works as intended if `Gi0/1 in` receives packets from those **source** hosts; if it is the repository-facing interface, use the correct direction/topology. The requested **numbered standard ACL 12** cannot filter by **destination subnet** or combine source and destination exceptions. Correct extended-ACL logic is:
```cisco
ip access-list extended REPO_PROTECT
 permit ip host 10.5.50.10 10.5.200.0 0.0.0.255
 permit ip host 10.5.100.5 10.5.200.0 0.0.0.255
 deny ip any 10.5.200.0 0.0.0.255
 permit ip any any
```
Apply where the traffic actually crosses. The paper ACL 12 requirement is technically under-specified/inconsistent for destination filtering.

### 2026 Q3.2 — 9 marks

**Question (Simple English):** Configure R6 local NetAdmin, TACACS+ 172.20.20.50 key tacLocal44; R7 RADIUS 172.20.30.60 key radLocal99; console AAA.

**Answer (Simple English):**

```cisco
! R6
conf t
aaa new-model
username NetAdmin privilege 15 secret engPwd11
tacacs server TAC_R6
 address ipv4 172.20.20.50
 key tacLocal44
exit
aaa group server tacacs+ T_GROUP
 server name TAC_R6
exit
aaa authentication login default group T_GROUP local
line con 0
 login authentication default
end
! R7
conf t
aaa new-model
radius server RAD_R7
 address ipv4 172.20.30.60 auth-port 1812 acct-port 1813
 key radLocal99
exit
aaa group server radius R_GROUP
 server name RAD_R7
exit
aaa authentication login default group R_GROUP local
line con 0
 login authentication default
end
```
For unreliable WAN, add a **local account on R7** and test emergency access before deployment.

### 2026 Q3.3 — 5 marks

**Question (Simple English):** Evaluate local vs server-based AAA for branch devices with unreliable WAN.

**Answer (Simple English):**

**Local:** keeps admins able to log in during WAN failure; harder to revoke/update across branches. **Server-based:** centralized authentication/authorization/accounting and audit trails; requires server availability. **Choose** central TACACS+/RADIUS plus redundant reachability and local emergency backup, tested for outages.

