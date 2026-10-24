<style>@page{size:A4 landscape;margin:4mm}body{font-size:5pt;line-height:1.08;column-count:2;column-gap:4mm}h1,h2,h3{column-span:all;margin:2px 0}table{width:100%;border-collapse:collapse;break-inside:avoid}th,td{border:0;padding:1px 3px;vertical-align:top}th{background:#ddd}p,ul{margin:2px 0}code{font-size:4.7pt}</style>

# IE3122 Reference 01 — Core Networking & Security Foundations

> Scope: Weeks 1–2 lectures/tutorials/labs. Print: A4 landscape, 5 pt, no table borders. Detailed attacks/configurations are in Sheets 02–07.

## Models, encapsulation and devices

| Layer | PDU / addressing | Main work | Security observation |
|---|---|---|---|
| 7 Application | Data; names/URLs | HTTP, DNS, DHCP, user services | Input abuse, phishing, malware; HTTPS adds TLS, not application correctness |
| 6 Presentation | Data | Format, compression, encryption | Bad crypto/encoding can expose or alter data |
| 5 Session | Data | Establish/manage sessions | Token/session theft |
| 4 Transport | Segment/datagram; ports | TCP reliability/state; UDP low overhead | Scans, hijack/RST, SYN/UDP floods |
| 3 Network | Packet; IP | Routing across networks | Spoofing, ICMP abuse, route manipulation |
| 2 Data Link | Frame; MAC | Local delivery, switching, VLAN/STP | MAC/CAM/VLAN/DHCP/ARP/STP attacks |
| 1 Physical | Bits | Signals/media | Cable/device theft, jamming, tapping |

| Concept | Compact answer |
|---|---|
| Why layers? | Modularity, interoperability and fault isolation: change/troubleshoot one function without redesigning all others. Analysts locate the attacked function and inspect the matching headers. |
| Encapsulation | App data → TCP/UDP header → IP header → Ethernet header+trailer → bits. Receiver reverses it. Each header creates fields that can be trusted, filtered, logged or spoofed. |
| TCP/IP mapping | Application ≈ OSI 5–7; Transport=4; Internet=3; Network Access=1–2. |
| Switch | Learns source MAC→port; forwards using destination MAC. Each port is a collision domain; a VLAN is a broadcast domain. |
| Router | Selects next hop by routing table; separates broadcast domains; default gateway handles off-subnet traffic. |
| VLAN security | Separates staff/server/guest broadcasts and limits lateral movement; inter-VLAN traffic becomes enforceable at router/firewall. VLAN alone is not encryption or authentication. |

## Ethernet, IP and subnetting

| Item | Essential facts / method |
|---|---|
| Ethernet fields | Destination MAC, Source MAC, Type/Length, payload, FCS. FCS detects accidental errors; attacker can modify data and recompute FCS, so it is not cryptographic integrity. |
| IPv4 | 32 bits; network prefix + host portion. Private: `10/8`, `172.16/12`, `192.168/16`; not publicly routed. |
| Hosts | For prefix `/p`: addresses=`2^(32-p)`; conventional usable hosts=`2^(32-p)-2`; mask is first `p` bits 1. Example `/26`=`255.255.255.192`, block 64, usable 62. |
| Security via subnetting | Smaller trust zones reduce broadcast reach and lateral movement; ACL/firewall policy can control traffic between zones. It does not itself stop attacks inside a subnet. |
| Socket / flow | Endpoint=`IP:port`; TCP flow identified by source IP+port and destination IP+port (plus protocol). |

## Core protocols and sequences

| Protocol/process | Sequence / choice | Security connection |
|---|---|---|
| ARP | Broadcast request “who has IP?” → owner unicasts reply → cache IP↔MAC | No authentication; forged/unsolicited replies enable MITM/DoS. DAI validates using DHCP Snooping bindings. |
| DHCP DORA | Discover → Offer → Request → Acknowledge | No native server authentication: rogue DHCP supplies attacker gateway/DNS; starvation exhausts pool. |
| TCP open | SYN → SYN-ACK → ACK; server reserves half-open state after SYN | SYN flood fills backlog with spoofed/incomplete handshakes. SYN cookies avoid early allocation. |
| TCP close | FIN/ACK exchanges; active closer enters TIME_WAIT to absorb delayed segments and prevent tuple reuse confusion | Many states consume resources operationally. RST aborts immediately. |
| TCP vs UDP | TCP: connection-oriented, ordered, reliable, flow/congestion control, more overhead. UDP: connectionless, best effort, low latency/overhead | File backup→TCP; live voice→UDP. UDP flood needs no handshake; scan silence is ambiguous. |
| HTTP | Stateless request/response; GET retrieves, POST submits. State added using cookies/tokens | Plain HTTP exposes credentials/content and permits alteration. HTTPS=HTTP over TLS: confidentiality, integrity, server authentication (when certificate validated). |

## Security vocabulary and threat model

| Term | Meaning | Connected example |
|---|---|---|
| Asset | Anything valuable | Student-record database |
| Vulnerability | Weakness | Unpatched public server |
| Threat / threat actor | Potential cause / entity capable of harm | Criminal exploiting remotely |
| Exploit | Technique/code using weakness | Crafted request triggers flaw |
| Risk | Likelihood × impact of threat exploiting vulnerability | Data theft/service loss; rate using evidence and business effect |
| Attack surface | All reachable people, devices, software, interfaces and suppliers | Cloud/mobile/IoT enlarge entry points and trust relationships |

**Threat-model chain:** define scope/assets → actors/motives → entry points/trust boundaries → vulnerabilities → likelihood & impact → prioritize risk → controls → residual risk/monitoring. Never list a control without tying it to a risk.

| Security property | Question / examples |
|---|---|
| Confidentiality | Who may read? Encryption, ACL, segmentation |
| Integrity | Was it altered? Hash/MAC/signature, validation |
| Availability | Is it usable? Redundancy, rate limits, backups |
| Authentication | Is identity genuine? MFA, certificates |
| Authorization | What may authenticated identity do? Least privilege/RBAC |
| Non-repudiation | Can origin later credibly deny? Digital signature + identity/key governance |

## Actors, attacks and controls

| Category | Distinction / defence emphasis |
|---|---|
| White / black / grey hat | Authorized defender / malicious unauthorized / unauthorized but not primarily malicious. Authorization, not claimed intent, is decisive. |
| Script kiddie, insider, organized crime, nation-state, hacktivist | Skill/motive differ: curiosity/status; trusted access; profit; espionage/disruption; ideology. Controls must match capability and access. |
| Virus / worm / Trojan | Virus attaches and needs execution; worm self-propagates; Trojan disguises itself. Use patching/segmentation for worms, endpoint controls and user education for execution/deception. |
| Ransomware / spyware | Ransomware encrypts/disrupts and extorts; spyware covertly collects. Offline tested backups aid recovery but do not prevent exfiltration. |
| Phishing / pretexting / baiting | Deceptive message / fabricated story-role / attractive lure. Verify through independent channel, MFA, awareness, help-desk procedure. |
| Recon / access / DoS-DDoS | Recon discovers targets; access gains unauthorized capability; DoS disrupts one/few sources while DDoS uses distributed/botnet sources, complicating filtering. |

| Control class | Examples | Limitation |
|---|---|---|
| Administrative | Policy, training, vendor review, incident plan, separation of duties | Depends on enforcement and people |
| Technical | MFA, firewall, EDR, segmentation, encryption, logging | Can be misconfigured/bypassed; patch continuously |
| Physical | Locks, CCTV, guards, UPS | Does not stop remote/logical abuse |

**Defence in depth:** preventive + detective + corrective controls at identity, endpoint, network, application, data, people/vendor and physical layers. A firewall cannot fix stolen credentials, vulnerable apps, malicious insiders or trusted-supplier compromise. Apply least privilege, zero/default-deny trust, MFA, segmentation, patching, immutable/offline backups, centralized logs and rehearsed response.

## Structured-answer micro-template

`Recommendation → mechanism → scenario evidence → benefit/property → limitation/trade-off → complementary control/verification.` For a risk: `asset → threat → vulnerability → exploit path → CIA impact → likelihood/impact rating → prioritized layered controls → residual risk`.
