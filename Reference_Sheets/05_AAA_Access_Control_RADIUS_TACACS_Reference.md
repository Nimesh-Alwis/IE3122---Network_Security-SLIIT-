<style>@page{size:A4 landscape;margin:4mm}body{font-size:5pt;line-height:1.06;column-count:2;column-gap:4mm}h1,h2{column-span:all;margin:2px 0}table{width:100%;border-collapse:collapse;break-inside:avoid}th,td{border:0;padding:1px 2px;vertical-align:top}th{background:#ddd}p{margin:2px 0}code{font-size:4.6pt}</style>

# IE3122 Reference 05 — AAA, Access Control, RADIUS & TACACS+

## AAA chain

| Function | Question | Inputs / outputs | Failure example |
|---|---|---|---|
| Authentication | Who are you; can you prove it? | Credentials/factors → verified identity | Stolen/replayed password, unavailable identity server |
| Authorization | What may that identity do? | Identity, role, policy, context → permissions/commands/resources | Overprivileged admin/user; confused AuthN with permission |
| Accounting | What happened, by whom, when, where, outcome? | Start/stop/events/commands → audit/billing/forensics records | No traceability; logs tampered or time unsynchronized |

**Factors:** knowledge (password/PIN), possession (token/phone/key), inherence (physical biometric), sometimes behavioral biometric/context. MFA requires different factors; two passwords are not MFA. Biometrics are probabilistic and difficult to revoke; protect templates. Apply least privilege, separation of duties, periodic review, secure logs/NTP and break-glass recovery.

## Access-control models

| Model | Who/what decides | Strength | Weakness / example |
|---|---|---|---|
| DAC | Resource owner grants permissions | Flexible/collaborative | Permission sprawl/owner mistakes; file sharing |
| MAC | Central labels/classifications and clearances | Strong information-flow enforcement | Rigid/admin-heavy; military classified data |
| RBAC | Job role → permissions; users assigned roles | Scalable, least privilege, easy review | Role explosion/stale memberships |
| Rule-based (RuBAC) | Global conditional rules (time, network, state, attributes) | Dynamic/context enforcement | Rule complexity/conflicts; firewall/time policy |

## Deployment decisions

| Choice | Advantages | Limitations / correct use |
|---|---|---|
| Local AAA | Works without server/network; simple for few devices; emergency fallback | Duplicate accounts, weak central audit/revocation, poor scale |
| Server-based AAA | Central users/policy/logs, consistent revocation, scalable | Server/network dependency and shared infrastructure become critical; deploy redundancy + local emergency fallback |
| Device administration | Controls administrators logging into router/switch/firewall and commands | TACACS+ commonly preferred for per-command control/separation |
| Network access | Controls users/devices joining VPN, Wi-Fi, 802.1X/network | RADIUS commonly preferred and widely integrated |

## RADIUS vs TACACS+

| Dimension | RADIUS | TACACS+ |
|---|---|---|
| Transport | UDP 1812 authentication/authorization, 1813 accounting (legacy 1645/1646) | TCP 49 |
| AAA separation | Authentication and authorization commonly combined; accounting separate | Cleanly separates authentication, authorization and accounting |
| Protection | Password field protected; much of packet/header visible (use secure transport variants where available) | Encrypts TACACS+ payload/body; header remains visible |
| Command authorization | Limited compared with TACACS+ | Granular per-command authorization/accounting |
| Typical fit | Network access: 802.1X, Wi-Fi, VPN; multivendor ecosystem | Administrative access to network devices |
| Transport trade-off | Low overhead/no connection; app manages retries | Reliable ordered delivery but TCP state/overhead |

## Cisco method-list logic

`aaa authentication login <list-name|default> <method1> <method2>...` tries methods in order. Next method is normally attempted when earlier method returns **ERROR/no response**, not when it actively returns **FAIL/reject**—a reject must not become a local-password bypass. Named list must be attached to the relevant line; `default` applies where configured/expected. Always build/test local fallback before changing remote access, keep an active recovery session, and secure management with SSH rather than Telnet outside the teaching lab.

| Lab purpose | Essential configuration | Expected observation |
|---|---|---|
| Local baseline | `username localadmin privilege 15 secret ...`; `aaa new-model`; `aaa authentication login default local`; under `line vty 0 4`: `login authentication default` | Local login succeeds before server dependency |
| TACACS+ first | PT syntax: `tacacs-server host 192.168.1.2`; `tacacs-server key ...`; `aaa authentication login default group tacacs+ local` | Server user works; if server is unreachable, local fallback works |
| RADIUS first | `radius-server host 192.168.2.2`; `radius-server key ...`; `aaa authentication login default group radius local` | Same reachability/fallback logic |
| Deliberate failure | Disable/unreach server, then retry with local account | Demonstrates resilience, not fallback after an explicit bad-password reject |

> Lab DOCX visually inserts spaces around hyphens/plus signs in some extracted text. Use valid IOS tokens `tacacs-server` and `tacacs+`. Packet Tracer uses legacy server syntax; modern IOS often uses named `tacacs server NAME` / `radius server NAME` objects.

## Secure design / troubleshooting

| Symptom | Check in order |
|---|---|
| Server login fails | IP reachability/routes → client/NAS entry uses correct router source IP → UDP/TCP port → identical shared secret → username/password → method list attached to VTY/console → server logs |
| Local fallback does not run | Determine server reject vs timeout/error; check method order and whether local user exists before `aaa new-model` |
| Lockout risk | Console/out-of-band access, active privileged session, local emergency account, configuration checkpoint, redundant servers |
| Accounting unreliable | NTP/timezone, server reachability/storage, start-stop vs command records, integrity/access controls and retention |

## Scenario recommendation formula

State users and access type → choose local/central (usually central + emergency local) → choose RADIUS for network access or TACACS+ for device command control → require MFA/least privilege → redundant servers and protected management path → accounting/SIEM/NTP → test rejection, timeout and recovery separately → note protocol/legacy-security limitation.
