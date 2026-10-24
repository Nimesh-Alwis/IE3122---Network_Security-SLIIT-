<style>@page{size:A4 landscape;margin:4mm}body{font-size:5pt;line-height:1.06;column-count:2;column-gap:4mm}h1,h2{column-span:all;margin:2px 0}table{width:100%;border-collapse:collapse;break-inside:avoid}th,td{border:0;padding:1px 2px;vertical-align:top}th{background:#ddd}p,ol{margin:2px 0}</style>

# IE3122 Reference 08 — Structured-Essay Frameworks & Cross-Topic Comparisons

> Final: 2 hours, 4 structured essays; all lectures, tutorials and labs. Nominal pacing: 30 min/question. Use the question’s verb and scenario evidence—not a memorized data dump.

## Command words and answer architecture

| Verb | What earns marks | Compact structure |
|---|---|---|
| Define / state / list | Precise term/facts; no unnecessary story | Term → essential distinguishing property → tiny example |
| Describe | Ordered behavior/mechanism | Normal state → steps → resulting state/output |
| Explain | Cause-and-effect (“why/how”) | Claim → mechanism → consequence → scenario link |
| Compare / distinguish | Same criteria for both; similarities + differences | Table/paired paragraphs → decisive difference → implication |
| Evaluate | Benefits, limitations, assumptions/trade-offs; justified judgment | Criteria → evidence for/against → residual risk → conclusion |
| Recommend / design | Requirements-driven selection, alternatives rejected | Requirement → choice → how it works → why fit → trade-off → compensating control |
| Configure | Correct ordered syntax plus placement and verification | Preconditions → commands → where/direction → show/test → failure check |

## Four reusable essay skeletons

| Question family | High-scoring flow |
|---|---|
| Attack + defense | Define normal protocol → underlying trust/resource flaw → packet-by-packet attack → CIA impact/evidence → mechanism-specific prevention → detection → mitigation limitation |
| Compare technologies | Define both → compare operation, security service, deployment, performance, management, compatibility → map scenario requirements → choose explicitly → acknowledge trade-off |
| Design layered security | Assets/data flows/trust boundaries → threats/vulnerabilities → risk priority → preventive/detective/corrective controls at multiple layers → availability/recovery → verification/residual risk |
| Lab/configuration | State topology/goal → prerequisites/addressing → config in dependency order → explain each block → positive and negative tests/show output → deliberate fault/troubleshooting → security caveat |

## Cross-topic selection matrix

| Requirement / symptom | Likely best concept(s) | Why / caveat |
|---|---|---|
| Separate guests from staff | VLAN + inter-VLAN ACL/firewall | VLAN creates broadcast boundary; policy enforces trust boundary |
| Stop rogue DHCP and ARP MITM | DHCP Snooping then DAI | Snooping binding is DAI’s validation source |
| Prevent rogue switch becoming root | Fixed root priority + Root Guard; BPDU Guard at edges | Placement depends on expected BPDU behavior |
| Authenticate routing neighbor | OSPF/EIGRP auth | Stops outsiders without key, not malicious authorized route; add filters/monitoring |
| Validate global BGP origin | RPKI + prefix filtering | Directly addresses unauthorized origin, not every path-policy attack |
| Resist SYN flood state exhaustion | SYN cookies/proxy + rate/upstream controls | Cookies remove pre-ACK server-state commitment |
| Publish web service safely | DMZ + WAF/NGFW + strict DMZ→Inside policy | Perimeter/stateful firewall alone may miss SQLi |
| Branch-to-branch private network | Site-to-site IPsec tunnel; GRE over IPsec if GRE features needed | GRE alone only encapsulates |
| Contractor gets one web app | Clientless SSL VPN + app/identity policy | Least access; full IPsec network access is excessive |
| Administer routers centrally | TACACS+ + local emergency fallback + accounting | Per-command control; redundancy/recovery needed |
| Authenticate Wi-Fi/VPN users | RADIUS + MFA/802.1X | Broad network-access integration |
| Fast bulk confidentiality | Symmetric AEAD session cipher | Requires safe key/nonce management |
| Integrity between shared-key peers | HMAC/AEAD | Cannot provide non-repudiation |
| Vendor-authentic software update | Digital signature + validated certificate/key | Plain digest from same site can be replaced |
| Public-key MITM prevention | Certificate chain + name/time/revocation checks | Encryption alone does not authenticate whose key |

## Frequently confused pairs

| Pair | Decisive distinction |
|---|---|
| Vulnerability vs threat vs risk | Weakness vs potential cause of harm vs likelihood×impact of exploitation |
| Authentication vs authorization | Prove identity vs decide allowed actions |
| IDS vs IPS | Alert out-of-band vs block inline |
| Stateful firewall vs `established` ACL | Actual flow state vs TCP ACK/RST bit approximation |
| MAC spoof vs CAM flood | Copy/change one identity vs overflow table with many sources |
| DHCP starvation vs spoofing | Exhaust legitimate leases vs supply malicious configuration |
| Root Guard vs BPDU Guard | Blocks superior-root claim on designated/downstream port vs disables edge port on any BPDU |
| IP spoofing vs route hijack | Forge packet source vs alter selected path/prefix reachability |
| TCP hijack vs RST injection | Inject/control data vs terminate flow; both need accepted flow context |
| Tunnel vs VPN | Encapsulation/path vs cryptographic confidentiality/integrity/authentication |
| AH vs ESP | Integrity/authentication only vs confidentiality plus optional integrity/authentication |
| Hash vs HMAC vs signature | No key / shared key / private-public key and non-repudiation support |
| Encryption vs signature | Confidentiality (receiver key context) vs origin/integrity (sender private key) |
| Self-signed vs DV | Locally pre-trusted identity vs public CA validates domain control |

## Scenario evidence vocabulary

Translate clues into requirements: “hundreds/high volume”→throughput/scalability; “moving Wi-Fi/cellular”→mobile session continuity; “only one web app”→application granularity/least privilege; “always-on branches”→site-to-site; “limited budget/staff”→manageable UTM/simpler architecture; “highest assurance/budget”→dual-firewall/defence in depth; “public-facing”→DMZ/WAF/patching; “third party”→separate trust boundary, least privilege, MFA, vendor assurance/logging; “legacy simulator”→state lab limitation and production alternative.

## 30-minute execution plan

1. **3 min:** underline verb, entities, constraints, marks; jot requirements and sheet/topic. 2. **22 min:** lead with direct answer; use labeled table/sequence; connect every control to mechanism; include trade-off and verification. 3. **5 min:** ensure every subpart answered, correct direction/order/ports, conclusion present. If stuck, write the normal protocol sequence first—most attack explanations follow directly from the violated assumption.

## Quality checklist

- Did I answer the requested verb and make a judgment where required?
- Did I distinguish vulnerability, attack technique and outcome?
- Did I name CIA/AAA service precisely rather than saying “more secure”?
- Did I justify with facts from the scenario and reject a plausible alternative?
- Did I give layered mitigation plus limitation/residual risk?
- For configuration: correct order, interface/direction, implicit deny, verification and failure test?
