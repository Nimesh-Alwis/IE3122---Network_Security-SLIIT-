<style>@page{size:A4 landscape;margin:4mm}body{font-size:5pt;line-height:1.06;column-count:2;column-gap:4mm}h1,h2{column-span:all;margin:2px 0}table{width:100%;border-collapse:collapse;break-inside:avoid}th,td{border:0;padding:1px 2px;vertical-align:top}th{background:#ddd}p{margin:2px 0}code{font-size:4.6pt}</style>

# IE3122 Reference 03 — Routing & Layer 4 Attack–Defense Matrix

## Routing protocols

| Protocol | Type / algorithm | Metric & behavior | Security-relevant point |
|---|---|---|---|
| RIP | IGP, distance vector | Hop count; max 15, 16 unreachable; periodic whole-table updates | Simple/slow; fake low-hop routes and unauthorized updates if unauthenticated |
| OSPF | IGP, link state | Cost (bandwidth-derived); LSAs build LSDB, SPF computes path; areas | Authenticate neighbors/updates; rogue adjacency/LSA can alter topology |
| EIGRP | IGP, advanced distance vector | Composite metric (bandwidth/delay by default); DUAL; partial bounded updates | Key-chain MD5 lab configuration; mismatched auth breaks adjacency |
| BGP | EGP, path vector | Policy attributes including AS_PATH; inter-AS prefix reachability | Trust/policy at Internet scale; origin error/abuse enables prefix hijack; use RPKI filtering |

## Routing attack matrix

| Attack | Mechanism | Outcome / distinction | Primary defenses & limits |
|---|---|---|---|
| Routing-table poisoning | Send false/worse/better route information so peers install corrupt paths | Misroute, loop, intercept or outage; general category | Neighbor authentication, passive interfaces, route filters, least-trust peering, monitoring. Auth proves sender/key, not truth of an authorized insider’s route |
| Unauthorized route injection | Non-neighbor/rogue neighbor advertises a route it should not originate | Traffic attraction or bypass | Authentication + prefix/distribute policies + infrastructure ACLs |
| Route/prefix hijacking | BGP AS announces another owner’s prefix (often more-specific, therefore selected) | Blackhole or interception/sinkhole; 2008 YouTube: Pakistan route leaked globally | RPKI Route Origin Validation, prefix/max-prefix filters, monitoring/rapid withdrawal |
| Blackhole | Selected route deliberately/accidentally drops traffic | Availability loss | Route validation, monitoring, redundancy |
| Sinkhole | Selected route attracts traffic to observe/filter/redirect | Confidentiality/integrity risk; can be legitimate defensive sinkhole | Authenticate/validate origin; monitor path changes |

**OSPF vs EIGRP authentication:** OSPF can enable message-digest authentication per area, then key per participating interface. EIGRP configures a reusable key chain and attaches it per interface for an AS—flexible rotation but more objects. Every neighbor-facing link must match algorithm/key; mismatch intentionally demonstrates adjacency loss. A distribute-list controls accepted/advertised routes, not who formed adjacency or whether all false information is impossible.

## TCP mechanics and reconnaissance

| Item | Exact meaning / observable result |
|---|---|
| 3-way handshake | Client SYN(x) → server SYN-ACK(y, ack x+1; half-open state) → client ACK(y+1; established). Initial sequence numbers support ordering and injection resistance. |
| Close | Each direction FIN then ACK; RST aborts. TIME_WAIT retains tuple/state to absorb old duplicates and ensure final ACK can be retransmitted. |
| Full-connect scan | Completes handshake; reliable but more logs/state. |
| SYN/half-open scan | SYN; SYN-ACK=open, RST=closed; scanner sends RST instead of completing. Faster/less application logging, still visible to network controls. |
| FIN/Xmas/NULL scans | Abnormal flags exploit RFC response differences: closed often RST, open often silence; may slip naive “block SYN only” stateless rule. Modern stateful IDS/firewalls detect them. |
| OS fingerprinting | Infers TCP/IP stack from TTL, window, options, flags/responses; narrows likely exploits and evasion choices, but NAT/middleboxes distort evidence. |
| TCP host sweep | Probe chosen port(s) across many IPs; finds hosts even if ICMP blocked. |
| UDP scan | ICMP Port Unreachable→closed; UDP reply→open; silence→open/filtered/lost, so retries make it slow/ambiguous. |

## Layer 4 attack matrix

| Attack | Shared weakness / mechanism | Goal & effect | Mitigation strategy |
|---|---|---|---|
| TCP hijacking | If attacker observes/predicts valid 4-tuple + sequence/ACK numbers, injects accepted segments | Take over/alter established session | TLS/SSH, unpredictable ISNs, anti-spoofing, segmentation, stateful IDS; encryption prevents useful content injection |
| TCP RST injection | Forge acceptable RST with correct flow/sequence context | Terminate connection (availability), not control it | Authentication/encryption, tight RST validation, anti-spoofing, monitoring |
| SYN flood | Many SYNs (often spoofed); server commits half-open TCB/backlog before client proof | Backlog/memory exhausted; legitimate handshakes fail | SYN cookies (encode state; remove early allocation), rate limiting, proxy/SYN cache, shorter timeout, upstream DDoS defense. Bigger backlog only tolerates more load |
| TCP flood | High connection/packet volume, possibly completed handshakes | CPU/state/bandwidth/application exhaustion | Stateful rate limits, load balancing/CDN/scrubbing, behavioral detection |
| UDP flood | Connectionless datagrams require no setup; spoofed traffic/response work consumes link/host | Cheap high-rate DoS; reflection possible | Rate limit by service, ACL unused ports, anti-spoofing, upstream mitigation; preserve required UDP |
| Port/host scan | Protocol responses reveal reachability/services | Recon, not necessarily compromise | Close unused services, firewall/default deny, IDS threshold/tarpit carefully, scan logs |

## Critical comparisons and evaluation

| Claim | Exam-ready evaluation |
|---|---|
| “Block ICMP and recon stops” | False: TCP/UDP host sweeps and application probes still work; blanket blocking can break PMTUD/diagnostics. Filter/rate-limit purposefully and reduce exposed services. |
| “Increase SYN backlog solves SYN flood” | It raises tolerance but retains the vulnerable early allocation. SYN cookies create state only after a valid ACK, addressing the mechanism. |
| TCP vs UDP weakness | Both historically trust unauthenticated network metadata. TCP abuse manipulates state/sequence/resource reservation; UDP abuse exploits stateless immediate processing and spoofability. |
| Low-cost priorities | Patch/disable unused services; host/network firewall default deny; anti-spoofing; rate limits/SYN cookies; secure protocols; centralized logs. Explain risk reduced and residual limitation. |

## Scenario answer pattern

Name the protocol normal behavior → identify violated assumption → trace packet/state change → distinguish reconnaissance/access/DoS → map CIA impact → choose mechanism-specific prevention → detection/verification → cost/availability trade-off. Routing/Cisco verification commands are in Sheet 07.
