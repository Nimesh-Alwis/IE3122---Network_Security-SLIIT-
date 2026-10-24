<style>@page{size:A4 landscape;margin:3.5mm}body{font-size:5pt;line-height:1.02;column-count:3;column-gap:3mm}h1,h2{column-span:all;margin:1px 0}table{width:100%;border-collapse:collapse;break-inside:avoid}th,td{border:0;padding:1px;vertical-align:top}th{background:#ddd}p{margin:1px 0}</style>

# IE3122 Reference 09 — Master Last-Minute Sheet

> Use as index/trigger sheet; details are intentionally not repeated. `S01…S08` refer to the other reference files.

## One-line recall grid

| Topic | Trigger fact | Detail |
|---|---|---|
| OSI | Data→segment/datagram→packet→frame→bits; inspect each header/trust field | S01 |
| Subnet | addresses `2^(32−p)`; usable normally −2; `/26` mask `.192`, 62 hosts | S01 |
| DHCP/ARP/TCP | DORA; ARP request/reply; SYN→SYN-ACK→ACK | S01 |
| Threat model | Asset→threat→vulnerability→exploit path→likelihood×impact→controls→residual risk | S01 |
| CIA+ | Confidentiality, Integrity, Availability + Authentication, Authorization, Non-repudiation | S01 |
| L2 defenses | Port security; fixed access/trunks+nonegotiate; unused native VLAN; DHCP Snooping→DAI | S02/S07 |
| STP chooser | Root Guard=superior BPDU; BPDU Guard=any BPDU on edge; Loop Guard=missing BPDU | S02/S07 |
| L3 | Sweep=recon; flood=direct DoS; Smurf=spoofed reflected amplification; BCP38/uRPF | S02 |
| Routing | RIP hop; OSPF cost/link-state; EIGRP composite/DUAL; BGP path/policy | S03 |
| BGP hijack | Unauthorized/more-specific prefix → blackhole/sinkhole; RPKI+filters | S03 |
| TCP attack | Hijack injects; RST kills; SYN flood consumes half-open state; cookies defer state | S03 |
| UDP | No handshake; flood cheap; scan silence=open/filtered/lost | S03 |
| Firewall | Stateless fields; stateful flow; proxy app; WAF web; UTM breadth; NGFW app/user context | S04 |
| ACL | Top-down first match + implicit deny; standard near destination, extended near source | S04/S07 |
| DMZ/ZBF | DMZ isolates public hosts; ZBF is directional policy model, not new technology | S04 |
| VPN | Tunnel encapsulates; VPN adds crypto. GRE readable; GRE+IPsec protected | S04/S07 |
| IPsec | Phase 1 secure management channel; Phase 2 IPsec SAs; tunnel wraps whole packet | S04 |
| Remote choice | Branch→site-to-site; roaming device→mobile; one web app→clientless SSL; cloud network→cloud VPN | S04 |
| AAA | Authenticate identity; Authorize action; Account event | S05 |
| RADIUS/TACACS+ | RADIUS UDP/network access; TACACS+ TCP/device admin/per-command | S05/S07 |
| Fallback | Next method on ERROR/timeout, not explicit FAIL/reject | S05 |
| Crypto | Symmetric fast bulk; asymmetric identity/key exchange; hybrid uses both | S06 |
| Key count | Pairwise symmetric `n(n−1)/2`; 200→19,900 | S06 |
| Mode | ECB patterns; CBC chained+IV; CTR unique nonce; GCM/AEAD encrypts+authenticates | S06 |
| Hash/MAC/signature | no key / shared key / private-public; signature supports non-repudiation | S06 |
| PKI | Validate chain, SAN/name, time, usage, revocation, strength; protect root | S06 |
| Essay | Recommendation→mechanism→scenario evidence→benefit→trade-off→verification | S08 |

## Attack → primary control

| Attack | First mechanism-specific response |
|---|---|
| MAC/CAM abuse | 802.1X + port-security/max MAC |
| Switch spoof / double tag | Static access/trunk + nonegotiate / unused non-user native VLAN |
| DHCP spoof/starvation | DHCP Snooping trust/rate/binding |
| ARP poison | DAI after DHCP Snooping |
| Rogue STP root | Set root priority + Root Guard; BPDU Guard at host edges |
| Smurf/IP spoof | Disable directed broadcast + ingress/egress anti-spoofing |
| Route injection | Neighbor auth + prefix/distribute filters + monitoring |
| BGP prefix hijack | RPKI origin validation + prefix/max-prefix filter |
| SYN flood | SYN cookies/proxy + rate/upstream DDoS controls |
| TCP injection | TLS/SSH + anti-spoofing/stateful monitoring |
| SQL injection through firewall | Secure coding/input parameterization + WAF; firewall alone insufficient |
| Stolen password | MFA, secure reset/help-desk verification, anomaly detection |
| Password database theft | Unique salt + memory-hard KDF, optional pepper |
| Public-key MITM | Authenticated certificates/signatures + full validation |

## Numbers, ports and flags

| Item | Recall |
|---|---|
| VLAN | 802.1Q; native frames typically untagged; move native off VLAN 1 and keep users off it |
| TCP flags | SYN open; ACK acknowledgment; FIN graceful direction close; RST abort; Xmas FIN+PSH+URG; NULL none |
| Telnet / SSH / HTTP / HTTPS | TCP 23 / 22 / 80 / 443 |
| TACACS+ | TCP 49 |
| RADIUS | UDP 1812 AuthN/AuthZ, 1813 accounting |
| GRE / ESP / AH | IP protocol 47 / 50 / 51 |
| IKE / NAT-T | UDP 500 / 4500 |
| RIP limit | 15 usable hops; 16 unreachable |
| ACL wildcard | inverse mask; `/24` `.255`; `/30` `.3`; `/28` `.15`; exact host all zeros |

## Configuration dependency order

| Task | Order |
|---|---|
| L2 secure VLAN | VLANs/access/trunks/native → router subinterfaces/DHCP → port security → DHCP Snooping/trust → DAI/trust → show/test |
| STP | Observe/elect intended root → RSTP/priority → PortFast+BPDU Guard edges → Root/Loop Guard selected links → verify/fault test |
| Routing auth | Establish adjacency/routes → enable compatible authentication all participating links → verify → deliberately mismatch → restore |
| ACL | Translate policy → most specific first → explicit intended remainder → correct interface/direction → counters + permit/deny matrix |
| GRE/IPsec | WAN routing → GRE → route LAN via tunnel → IKE Phase 1 → transform/Phase 2 → interesting ACL → crypto map on WAN → trigger/show SAs |
| AAA | Local safety account/test → enable AAA → server definition/key → ordered method list → attach line → remote test → outage fallback test |
| Certificate | Key/trustpoint prerequisites → authenticate CA → enroll → verify chain/revocation |

## Final-answer safety net

When uncertain, write: **normal behavior → exploited assumption → exact outcome → CIA impact → targeted prevention → detection/verification → limitation + second layer.** For comparisons, use identical criteria and finish with a scenario-specific choice. For labs, include where a command is applied and one `show`/positive/negative test. Do not claim: FCS is cryptographic integrity; VLAN/GRE/hash alone provides authentication; AH encrypts; firewall stops every attack; local fallback follows an explicit server reject; Packet Tracer DH5 is a modern production recommendation.
