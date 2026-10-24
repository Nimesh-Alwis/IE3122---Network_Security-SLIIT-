<style>@page{size:A4 landscape;margin:4mm}body{font-size:5pt;line-height:1.06;column-count:2;column-gap:4mm}h1,h2{column-span:all;margin:2px 0}table{width:100%;border-collapse:collapse;break-inside:avoid}th,td{border:0;padding:1px 2px;vertical-align:top}th{background:#ddd}p{margin:2px 0}code{font-size:4.6pt}</style>

# IE3122 Reference 02 — Layer 2, Layer 3 & STP Attack–Defense Matrix

> Scope: Weeks 3–4. For fundamentals see Sheet 01; routing-protocol attacks are in Sheet 03; commands in Sheet 07.

## Layer 2 matrix

| Attack | Exploited condition & mechanism | Result / evidence | Best mitigation (and why) |
|---|---|---|---|
| MAC spoofing | MAC is easily changed and treated as identity; attacker copies authorized/victim MAC | Unauthorized access, impersonation, session disruption | 802.1X authenticates user/device; port security limits learned MACs but sticky MAC alone can be copied |
| CAM/MAC flooding | Finite CAM table; many fake source MACs fill it; switch may flood unknown unicasts (“fail open”) | Eavesdropping/MITM opportunity, CPU/bandwidth DoS, rapidly changing/full table | Port security maximum + restrict/shutdown; storm control; 802.1X; monitor MAC churn |
| Switch spoofing | DTP dynamically negotiates trunk with attacker pretending to be switch | Access to traffic from multiple allowed VLANs | Force access ports; hard-code trunks; `switchport nonegotiate`; restrict allowed VLAN list |
| Double tagging | Attacker on native VLAN sends outer native tag + inner target tag; first switch strips outer tag, next follows inner | One-way injection into target VLAN; return traffic not automatically delivered to attacker | Unused native VLAN ≠ VLAN 1; tag native VLAN where supported; never place users on native VLAN; prune trunks |
| DHCP starvation | Flood unique client IDs/MACs to consume address pool | Legitimate clients receive no lease; prepares rogue-server attack | DHCP Snooping rate limits/untrusted ports; port security; monitor exhaustion |
| DHCP spoofing | Rogue server answers first with malicious gateway/DNS | MITM, redirection, loss of connectivity | DHCP Snooping: only trusted uplink/server port may send server messages; bindings record IP/MAC/VLAN/port |
| ARP spoof/poison | Hosts accept unauthenticated/unsolicited ARP replies; attacker maps gateway/victim IP to attacker MAC | MITM, credential capture, alteration or DoS; duplicate/rapid ARP changes | DAI validates ARP against DHCP Snooping binding; static ARP for critical devices; segmentation/encryption |

**Dependencies/trade-offs:** DHCP Snooping must precede DAI because DAI needs trusted bindings; statically addressed hosts require ARP ACL/manual handling. Port-security `protect` silently drops, `restrict` drops+counts/logs, `shutdown` err-disables (strongest but most disruptive). VLAN segmentation limits scope but inter-VLAN policy is still required.

## Layer 3 matrix

| Attack | Mechanism / difference | Impact | Mitigation / caution |
|---|---|---|---|
| ICMP sweep | Echo requests across address range; replies reveal live hosts | Reconnaissance for later targeting | Rate-limit/log ICMP; IDS threshold; host firewall. Do not blindly block all ICMP—diagnostics, PMTUD and error reporting need selected types |
| Ping of Death | Oversized/malformed fragmented ICMP reassembles beyond limit on vulnerable legacy stack | Crash/reboot/DoS | Patch/modern stack; firewall malformed/oversized fragments; IDS |
| Ping flood | High-volume direct Echo traffic consumes victim/link/CPU | DoS; attacker cost roughly tracks traffic | Rate limit/police, upstream filtering, DDoS protection |
| Smurf | Spoof victim source; ICMP echo to directed broadcast; many hosts reply to victim | Reflected/amplified DDoS | Disable IP directed broadcasts; ingress anti-spoofing; filter/rate-limit; avoid amplifiers |
| IP spoofing | Forge source IP; IP provides addressing, not source authentication | Hide source, bypass naive source rule, reflection, blind injection | Ingress/egress filtering (BCP38), uRPF, authenticated protocols; stateful filtering |
| TTL expiry abuse | Send packets designed to expire; routers generate ICMP Time Exceeded and spend resources | Recon/path mapping or control-plane DoS | Control-plane policing, rate-limit ICMP errors; TTL security where applicable |
| IP fragmentation abuse | Tiny/overlapping/evasive fragments exploit reassembly differences or resource use | IDS/firewall evasion, crash/DoS | Normalize/reassemble consistently, drop invalid overlaps, patch, sensible fragment policy |

**Key comparison:** Ping flood is direct; Smurf adds spoofing + broadcast reflection/amplification. ICMP sweep seeks information; floods seek availability loss. Blocking every ICMP type trades security visibility for broken operations—permit necessary types with limits.

## STP essentials

| Stage | Selection rule |
|---|---|
| Root bridge | Lowest Bridge ID = priority then MAC; configure a known root with low priority |
| Root port (non-root switch) | Lowest total root path cost; ties: sender bridge ID, sender port ID, local port ID |
| Designated port (per segment) | Port offering lowest path to root; root’s ports are designated |
| Other redundant port | Blocking/discarding prevents loop |
| 802.1D states | Blocking → Listening → Learning → Forwarding (Disabled separate); slower convergence |
| RSTP roles/states | Root, designated, alternate/backup; Discarding/Learning/Forwarding; rapid proposal/agreement |

| STP attack | Mechanism / impact | Defense |
|---|---|---|
| Root bridge spoofing | Attacker sends superior BPDU (lower bridge ID), becomes root, attracts traffic | Explicit root priority; Root Guard on ports where root must never appear; authenticate/secure physical access |
| Topology-change flooding | Repeated topology-change indications force relearning/flushes | Instability, flooding, CPU load | PortFast on true edge ports; BPDU Guard shuts edge port receiving BPDU; storm/control-plane monitoring |
| STP DoS / BPDU manipulation | Malformed/excess BPDUs or induced loops/topology churn | Broadcast storm, MAC flapping, outage | BPDU Guard, Root Guard, Loop Guard, correct link type, monitoring |

## STP protection chooser

| Feature | Put it on | Trigger / action | Do not confuse |
|---|---|---|---|
| PortFast | End-host edge port only | Immediately forwarding; still participates if BPDU arrives | Unsafe on switch-to-switch link |
| BPDU Guard | PortFast/edge access port | Any BPDU → err-disable/shutdown | Protects edge from rogue switch |
| Root Guard | Downstream/designated port where root must not appear | Superior BPDU → root-inconsistent until gone | Does not disable permanently |
| Loop Guard | Non-designated/root redundant link | Missing expected BPDUs → loop-inconsistent | Prevents unidirectional-link false forwarding |
| BPDU Filter | Rare, deliberate edge use | Suppresses BPDUs; can create loop if misused | Not a safer BPDU Guard; hiding BPDUs removes protection |
| UplinkFast / BackboneFast | Legacy PVST enhancements | Faster access-uplink / indirect-failure recovery | RSTP largely supersedes them |

## High-yield diagnosis order

1. Identify layer and intended protocol behavior. 2. State unauthenticated/trust/finite-resource weakness. 3. Trace attacker input → device state/forwarding change → CIA effect. 4. Select prevention at the trust boundary. 5. Add detection/verification and state trade-off. Commands and `show` checks: Sheet 07.
