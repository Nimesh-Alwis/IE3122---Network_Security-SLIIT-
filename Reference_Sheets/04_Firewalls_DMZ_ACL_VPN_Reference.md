<style>@page{size:A4 landscape;margin:4mm}body{font-size:5pt;line-height:1.05;column-count:2;column-gap:4mm}h1,h2{column-span:all;margin:2px 0}table{width:100%;border-collapse:collapse;break-inside:avoid}th,td{border:0;padding:1px 2px;vertical-align:top}th{background:#ddd}p{margin:2px 0}code{font-size:4.5pt}</style>

# IE3122 Reference 04 — Firewalls, DMZ, ACLs & VPN

## Firewall selection

| Control/type | Decision basis | Strength | Limitation / best fit |
|---|---|---|---|
| Firewall / IDS / IPS | Firewall enforces policy; IDS detects+alerts; IPS detects+blocks inline | Complementary prevention/detection | IPS can add latency/false-positive disruption; IDS alone does not stop traffic |
| Software vs hardware | Endpoint-local vs network gateway/appliance | Host context/mobile protection vs centralized throughput/segmentation | Deploy both for layered coverage |
| Stateless packet filter | Per-packet L3/L4 fields, no flow memory | Fast/simple/cheap | Cannot know if return packet belongs to legitimate session |
| Stateful inspection | Tracks connection state; dynamically admits valid return traffic | Better context/security | State table exhaustion; limited application meaning |
| Circuit gateway | Validates session/handshake, relays connection | Hides internal endpoints/session policy | Does not inspect malicious application content |
| Application proxy | Terminates/proxies and understands protocol/content | Deep filtering, user anonymization | More latency/resources/configuration |
| WAF | HTTP/S application semantics | SQLi/XSS/web attack focus | Only web apps, not full network control |
| UTM | Multiple broad controls in one appliance | Affordable/simple for small team | Bottleneck/single vendor/less depth |
| NGFW | Stateful + application/user awareness, IPS, often TLS inspection | Granular modern app policy at scale | Cost/skills/performance/privacy trade-offs |

Evolution trades decreasing simplicity/throughput for increasing context, visibility and precision. Port 443 no longer identifies a single trustworthy application; encrypted/multiplexed traffic drove application/user-aware controls.

## DMZ, zones and placement

| Design | Security/operations trade-off |
|---|---|
| DMZ | Separate subnet for public services. Outside→DMZ permits required services; DMZ→Inside default deny/strict exceptions; Inside→DMZ/Outside controlled. Compromised DMZ host is contained only if inter-zone rules enforce it. |
| ZBF | Policy/configuration model grouping interfaces into zones and applying directional zone-pair policy; not a distinct inspection technology. INSIDE→OUTSIDE and reverse are separate trust decisions. |
| Firewall behind border router | Router exposed; router can prefilter before firewall; common and simple. |
| Firewall before border router | Firewall directly protects router; firewall itself fully Internet-facing. |
| Dual firewall, router before both (screened subnet) | Strong defence in depth; distinct outer/inner barriers around DMZ; cost/management and possible bottlenecks. Best high-value/budget-rich choice, ideally diverse controls. |
| Dual firewall, router between | Layered but compromise/misconfiguration of middle router can bridge/undermine separation; more complex. |

## ACL logic

ACLs process top-down, first match wins, and end with implicit `deny any`/`deny ip any any`. Put specific exceptions before broad rules; add explicit final permit only if policy demands it. Standard ACL matches source only → near destination to avoid overblocking. Extended ACL matches protocol, source, destination, ports → near source to discard unwanted traffic early. `in/out` is relative to the router interface.

| Need | Pattern |
|---|---|
| Standard numbered | `access-list 10 permit 192.168.50.0 0.0.0.15` then apply `ip access-group 10 in|out` |
| Extended numbered | `access-list 110 deny tcp 10.10.30.0 0.0.0.255 host 172.16.5.10 eq 23`; then `permit ip any any` |
| Named extended | `ip access-list extended DENY_FTP_ADMIN` → `deny tcp 192.168.40.0 0.0.0.255 host 10.0.0.50 eq 21` → `permit ip any any` |
| Permit return TCP only | `permit tcp ... established` checks ACK/RST; useful stateless approximation, not true stateful inspection |
| Wildcard | `0` bit must match, `1` ignores. Wildcard=`255.255.255.255 - subnet mask`; `/24`→`0.0.0.255`, `/28`→`0.0.0.15`, host→`host x` |

## VPN purpose and classification

VPN combines tunneling/encapsulation + encryption/confidentiality + integrity/authentication over an untrusted network. A tunnel alone changes carriage/outer addressing; it does not necessarily protect payload. GRE supports routed/multicast protocols but has no encryption—GRE over IPsec adds protection.

| Axis/type | Choose when | Trade-off / trust |
|---|---|---|
| Software vs hardware gateway | Flexibility/low cost vs dedicated throughput/scalability | Independent of connection purpose |
| Remote access | Individual user securely reaches organization | Client/user authentication and endpoint security matter |
| Personal VPN | Individual routes Internet traffic through provider | Trust shifts from local ISP/network to VPN provider; not organizational access |
| Mobile VPN | Endpoint roams Wi-Fi/cellular while session persists | Logistics/field devices; handles address/network changes |
| Site-to-site | Always-on gateway-to-gateway LAN connection | Branches; scalable central policy, no per-user tunnel |
| Cloud VPN | Site-to-site variant connecting on-premises/VPC/cloud networks | Provider-managed virtual gateway; no physical cloud-side appliance |

## IPsec framework

| Choice | Function / decision |
|---|---|
| AH | Integrity, origin authentication, anti-replay; no confidentiality; NAT-unfriendly because protected header changes |
| ESP | Confidentiality plus optional integrity/authentication; dominant practical choice; NAT-T commonly UDP 4500 |
| IKE Phase 1 | Authenticate peers and create protected IKE/ISAKMP management channel (policy, DH, PSK/cert) |
| IKE Phase 2 | Negotiate IPsec SAs/transform set and keys for protected data; reuses Phase-1 channel |
| Transport mode | Protects IP payload; original IP header remains; host-to-host |
| Tunnel mode | Protects entire original packet inside new outer IP packet; site-to-site/gateway use |
| Interesting-traffic ACL | Selects traffic that triggers/is protected by IPsec; nonmatching legitimate traffic routes normally, not encrypted. GRE-over-IPsec ACL matches GRE between WAN peers because IPsec sees the already encapsulated packet |
| DH choice | Higher modern group generally stronger but costs compute/needs support. Lecture production baseline: Group 14; Packet Tracer lab limit uses Group 5—compatibility is not a claim of production strength |

## SSL/TLS VPN and direct comparison

| Dimension | IPsec VPN | SSL/TLS VPN |
|---|---|---|
| Layer/access | Network-layer, broad subnet/full-network access | Application/transport oriented; clientless portal or full-tunnel client |
| Traversal | ESP/AH and IKE can face NAT/firewall issues; NAT-T helps | Common TCP/UDP 443 generally traverses easily |
| Granularity | Often network/subnet policy | Fine per-user/per-application access |
| Best scenario | Branch/site link; employees needing office-like network access | Contractor needing one web app→clientless portal; remote user broad access→full-tunnel client |
| Management | Strong gateway/device config; transparent to site users | Browser convenience or client software; application compatibility varies |

TLS functional blocks: version (prefer TLS 1.3; retire SSL/old TLS), key agreement (ephemeral ECDHE; retire static RSA key exchange), bulk encryption (AES-GCM/ChaCha20-Poly1305; retire RC4/3DES), integrity (AEAD; retire MD5/SHA-1 constructions), identity (CA certificate/signature; validate chain/name/time/revocation). TLS 1.3 separates authentication/key exchange from a smaller AEAD cipher-suite choice.

Configuration sequence and complete command patterns: Sheet 07.
