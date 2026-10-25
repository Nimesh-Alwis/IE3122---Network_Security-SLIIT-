# IE3032 — Network Security Final Examination

| Field | Details |
|---|---|
| Academic period | Year 3, Semester 1 & 2 (2024) |
| Date / duration | June 2024 / 2 hours + 10 minutes reading |
| Questions / marks | 4 compulsory questions / 100 marks |
| Exam aid | One A4 paper permitted |
| Source | [Original PDF](IE3032_Network_Security_Final_2024_June.pdf) |

## Question 1 — Network Attacks and Security [25 marks]

1. Analyze and describe the relationship among a threat actor, asset, vulnerability, attack, and impact. **(5 marks)**

2. For each scenario, identify the threat actor and whether internal/external, targeted asset, exploited vulnerability, and best mitigation: **(8 marks)**
   1. A network administrator abuses unlimited system access to copy regular users’ passwords.
   2. Another company uses a botnet to overwhelm an online-store web server running on seven-year-old hardware.

3. Write Cisco commands to enable port security on `Fa0/1–2`, allow a maximum of 3 MAC addresses, use `restrict` violation mode, and shut down unused `Fa0/3–24` and `G0/1–2`. **(6 marks)**

4. Write Cisco commands to enable DHCP Snooping globally and for VLAN 1, trust `Fa0/23–24`, and rate-limit `Fa0/1` to 15 packets per second. **(6 marks)**

## Question 2 — ACL and Firewalls [25 marks]

1. A public web application handles orders, product details, and support tickets while internal servers handle inventory, shipping, and backend operations.
   1. Analyze the strengths of a zone-based firewall, NGFW, and WAF in this context.
   2. Recommend and justify the most suitable firewall type. **(12 marks total)**

2. Write Cisco commands on Router 3 to create zones `INTERNAL` and `EXTERNAL`, assigning `Fa0/1` to `INTERNAL` and `S0/0/1` to `EXTERNAL`. **(6 marks)**

3. Write commands to: **(7 marks)**
   - Create standard named ACL `Rule1` on R1.
   - Permit hosts `192.168.20.1` and `192.168.100.1`; deny all others.
   - Apply it outbound on `Fa0/1`.
   - Create numbered ACL 1 denying access to `192.168.20.0/24` from any other network.

## Question 3 — VPN and AAA [25 marks]

1. For a medical-data company with global remote employees and branches: **(6 marks)**
   1. Explain site-to-site versus remote-access VPN functionality and differences. **(2 marks)**
   2. Identify and justify the best secure-communications approach for branches and remote employees. **(4 marks)**

2. Given R2 (`192.168.2.1`), R3 (`192.168.3.1`), TACACS+ server (`192.168.2.2`), and RADIUS server (`192.168.3.2`), write commands to: **(9 marks)**
   - Create R2 local backup user `Admin` with secret `pwd1234`.
   - Configure R2 TACACS+ server/key `tcspwd` and console AAA login.
   - Configure R3 RADIUS server/key `rdspwd`.
   - Apply the defined method to the console line.

3. Compare server-based and local AAA, recommend one, and justify the security effect. **(5 marks)**

4. Define an eavesdropping attack, explain it, and recommend future prevention steps. **(5 marks)**

## Question 4 — Network Defence [25 marks]

1. Identify each attack and justify its best mitigation: **(9 marks)**
   1. A DHCP pool is exhausted despite having far more addresses than legitimate devices.
   2. An unknown person gains account access after trying many passwords.
   3. A server holds many TCP connections whose handshakes never finish.

2. Identify two key security-policy documents supporting DR and BCP, describe their coverage, and write two rules for each. **(8 marks)**

3. Design an optimal HQ security topology for public email/web servers, growing internal VLANs, and inter-subnet filtering. Draw the topology **(3 marks)** and recommend/justify a firewall type **(5 marks)**.
