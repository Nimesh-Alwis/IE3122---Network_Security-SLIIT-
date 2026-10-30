# Layer 2: Port Security, DHCP Snooping and VLANs

> **Study pack:** IE3032 Network Security final papers — June 2022, June 2023, June 2024 and May 2026.
> **Format:** Simplified exam question + **Simple English exam answer**. Original year, question ID and marks are retained.
> **Source:** Uploaded year-specific `.md` transcripts. Where the transcript lacks a diagram/packet capture or a requested ACL is technically inconsistent, the limitation is explicitly marked.
> **Cisco:** Command examples assume common Cisco IOS syntax; interface/feature support varies by platform. Passwords shown are **exam-provided example credentials**, not safe production passwords.

## 2023 Paper

### 2023 Q1.a(i) — 2 marks

**Question (Simple English):** Recommend a switch control to prevent CAM-table attacks and unauthorized MAC devices.

**Answer (Simple English):**

Enable **switch port security** on access ports; restrict learned MAC addresses and define a violation action. This reduces unauthorized connections and MAC flooding.

### 2023 Q1.a(ii) — 8 marks

**Question (Simple English):** Configure Fa0/1–2 port security (max 5, shutdown) and disable remaining Fa0/3–24 and Gi0/1–2.

**Answer (Simple English):**

```cisco
conf t
interface range fa0/1 - 2
 switchport mode access
 switchport port-security
 switchport port-security maximum 5
 switchport port-security violation shutdown
exit
interface range fa0/3 - 24
 shutdown
exit
interface range gi0/1 - 2
 shutdown
end
```
`shutdown` violation puts an offending port into err-disabled state; recover only after correcting the problem.

### 2023 Q1.b(i) — 2 marks

**Question (Simple English):** Recommend a control against unauthorized DHCP servers.

**Answer (Simple English):**

Enable **DHCP snooping**. Mark only legitimate DHCP-server-facing interfaces trusted; untrusted access ports cannot send server replies.

### 2023 Q1.b(ii) — 9 marks

**Question (Simple English):** Configure DHCP snooping globally, VLAN 1, trusted Fa0/4 and rate limit 20.

**Answer (Simple English):**

```cisco
conf t
ip dhcp snooping
ip dhcp snooping vlan 1
interface fa0/4
 ip dhcp snooping trust
 ip dhcp snooping limit rate 20
end
```
Use rate limit on the interface requested in the paper; in production, rate limiting is normally most useful on **untrusted access ports**, not DHCP-server uplinks.

### 2023 Q1.b(iii) — 4 marks

**Question (Simple English):** List methods to prevent VLAN hopping.

**Answer (Simple English):**

Configure user ports as static **access** (`switchport mode access`), disable dynamic trunk negotiation (DTP), restrict allowed VLANs on trunks, avoid using VLAN 1 as native VLAN and use an unused native VLAN.

## 2024 Paper

### 2024 Q1.3 — 6 marks

**Question (Simple English):** Configure port security Fa0/1–2 (max 3, restrict); disable Fa0/3–24 and Gi0/1–2.

**Answer (Simple English):**

```cisco
conf t
interface range fa0/1 - 2
 switchport mode access
 switchport port-security
 switchport port-security maximum 3
 switchport port-security violation restrict
exit
interface range fa0/3 - 24
 shutdown
exit
interface range gi0/1 - 2
 shutdown
end
```
`restrict`: drop frames from unauthorized MACs, increment counter/log, but keep port active.

### 2024 Q1.4 — 6 marks

**Question (Simple English):** Configure DHCP snooping VLAN 1, trust Fa0/23–24 and limit Fa0/1 to 15 packets/second.

**Answer (Simple English):**

```cisco
conf t
ip dhcp snooping
ip dhcp snooping vlan 1
interface range fa0/23 - 24
 ip dhcp snooping trust
exit
interface fa0/1
 ip dhcp snooping limit rate 15
end
```

## 2026 Paper

### 2026 Q1.3 — 5 marks

**Question (Simple English):** Configure port security on Fa0/3–4 (max 2, restrict); shut down Fa0/5–24 and Gi0/1–2.

**Answer (Simple English):**

```cisco
conf t
interface range fa0/3 - 4
 switchport mode access
 switchport port-security
 switchport port-security maximum 2
 switchport port-security violation restrict
exit
interface range fa0/5 - 24
 shutdown
exit
interface range gi0/1 - 2
 shutdown
end
```

### 2026 Q1.4 — 5 marks

**Question (Simple English):** Configure DHCP snooping on VLAN 10; trust Fa0/15–16; limit Fa0/1 to 15 packets/s.

**Answer (Simple English):**

```cisco
conf t
ip dhcp snooping
ip dhcp snooping vlan 10
interface range fa0/15 - 16
 ip dhcp snooping trust
exit
interface fa0/1
 ip dhcp snooping limit rate 15
end
```

