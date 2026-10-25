# IE3032 — Network Security Final Examination

| Field | Details |
|---|---|
| Academic period | Year 3, Semester 1 & 2 (2026) |
| Date / duration | May 2026 / 2 hours + 10 minutes reading |
| Questions / marks | 4 compulsory questions / 100 marks |
| Exam aid | One single-sided A4 paper permitted |
| Source | [Original PDF](IE3032_Network_Security_Final_2026_May.pdf) |

## Question 1 — Network Attacks and Security [25 marks]

1. Define threat actor, asset, vulnerability, attack, and impact; explain their sequential relationship in a network-security incident lifecycle; and give one generic example. **(7 marks)**

2. For each scenario, identify the internal/external actor, asset, vulnerability, and one most effective mitigation: **(8 marks)**
   1. A contractor reaches the management subnet because of incorrect routing and retrieves switch-configuration backups.
   2. A malicious group uses compromised IoT devices to overwhelm an outdated DNS server with bogus queries.

3. Write Cisco IOS commands to enable port security on `Fa0/3–4`, set maximum MAC addresses to 2, use `restrict`, and disable `Fa0/5–24` and `Gi0/1–2`. **(5 marks)**

4. Write Cisco IOS commands to enable DHCP Snooping globally and for VLAN 10, trust `Fa0/15–16`, and rate-limit `Fa0/1` to 15 packets/second. **(5 marks)**

## Question 2 — ACL and Firewalls [25 marks]

1. A financial-services company is deploying an Internet-facing payment portal while keeping authentication and transaction-verification systems isolated.
   1. Analyze the strengths of ZBFW, NGFW, and API/Application-Layer Gateway Firewall. **(6 marks)**
   2. Recommend one firewall type for external-application protection, internal segmentation, and traffic visibility, with scenario-specific justification. **(6 marks)**

2. Write Cisco IOS commands on Router 2 to create zones `CAMPUS` and `WAN-EDGE`, assigning `Gi0/0` to `CAMPUS` and `S0/1/0` to `WAN-EDGE`. **(6 marks)**

3. A repository at `10.5.200.20` stores encryption keys and transaction logs; only `10.5.50.10` and `10.5.100.5` may access it. Write commands to: **(7 marks)**
   - Create standard named ACL `SECURE-ACCESS` on Router A.
   - Permit the two hosts and deny all others.
   - Apply it inbound on `Gi0/1`.
   - On Router B, create numbered ACL 12 denying access to `10.5.200.0/24` from any source except the approved hosts.

## Question 3 — VPN and AAA [25 marks]

1. An international logistics company has overseas distribution centers and travelling employees connecting from airports and hotels. Explain site-to-site versus remote-access VPNs, then recommend and justify secure approaches for both groups. **(6 marks)**

2. A three-branch engineering firm has unreliable WAN connections. Addresses include R6 LAN `172.20.20.1`, R7 LAN `172.20.30.1`, TACACS+ `172.20.20.50`, and RADIUS `172.20.30.60`. Write complete commands to: **(9 marks)**
   - Create R6 local backup user `NetAdmin` with secret `engPwd11`.
   - Configure R6 TACACS+ with key `tacLocal44` and console AAA login.
   - Configure R7 RADIUS with key `radLocal99`.
   - Apply the defined AAA method to the console line.

3. Evaluate local versus server-based AAA for branch devices, list advantages/disadvantages, and justify your recommendation. **(5 marks)**

4. Employees entering the correct portal address are redirected to a fake login page; investigation shows manipulation of domain-name resolution. Identify and explain the attack and give two practical preventive steps. **(5 marks)**

## Question 4 — Network Defence [25 marks]

1. Identify each attack and recommend/justify the most appropriate mitigation: **(9 marks)**
   1. Devices automatically connect to a network using the company SSID but weaker encryption; traffic is intercepted.
   2. An external attacker changes shared-project files by injecting malicious commands into unvalidated input fields.
   3. High-volume ICMP traffic overwhelms the public web server.

2. Identify two policy documents that strengthen security governance, DR, and BCP in response to these weaknesses. For each, explain purpose, coverage, and two specific rules. **(8 marks)**

3. Design an upgraded HQ architecture for an Internet-reachable cloud analytics platform, internal HR/Finance servers, departmental VLANs, and stronger filtering for sensitive VLANs.
   1. Draw a secured perimeter, analytics DMZ, internal VLANs, and inter-VLAN filtering/inspection layer. **(4 marks)**
   2. Recommend and justify the best firewall architecture. **(4 marks)**
