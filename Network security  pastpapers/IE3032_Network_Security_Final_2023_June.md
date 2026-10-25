# IE3032 — Network Security Final Examination

| Field | Details |
|---|---|
| Academic period | Year 3, Semester 1 & 2 (2023) |
| Date / duration | June 2023 / 2 hours |
| Questions / marks | 4 compulsory questions / 100 marks |
| Exam aid | One handwritten A4 paper permitted |
| Source | [Original PDF](IE3032_Network_Security_Final_2023_June.pdf) |

> Clean transcription of the paper. Consult the PDF for the original layout and topology context.

## Question 1 — Layer 2 Security [25 marks]

### a. Port security

A medium-sized company uses Cisco Catalyst switches and must allow only authorized devices, prevent CAM-table attacks, restrict MAC addresses per port, set a maximum, and define violation actions.

1. Recommend the most suitable switch-security measure. **(2 marks)**
2. Write commands to: **(8 marks)**
   - Enable port security on `Fa0/1` and `Fa0/2`.
   - Set the maximum allowed MAC addresses to 5.
   - Set the violation action to `shutdown`.
   - Disable unused ports `Fa0/3–24` and `Gi0/1–2`.

### b. DHCP security

The company uses multiple VLANs and a DHCP server in a trusted VLAN, and must prevent unauthorized devices from distributing rogue IP configuration.

1. Recommend the most suitable switch-security measure. **(2 marks)**
2. Write commands to enable DHCP Snooping globally, enable it for trusted VLAN 1, trust `Fa0/4`, and set a rate limit of 20 on `Fa0/4`. **(9 marks)**
3. State the best methods for preventing VLAN-hopping attacks. **(4 marks)**

## Question 2 — ACL and Firewalls [25 marks]

1. A public web application serves customers while internal servers handle inventory, shipping, and backend operations.
   1. Recommend the most suitable approach between a zone-based firewall and a DMZ. **(2 marks)**
   2. Write commands on Router 3 to create `IN-ZONE` and `OUT-ZONE`, assigning `G0/1` to the inside zone and `S0/0/1` to the outside zone. **(6 marks)**

2. Create access controls so that only PC1 (`192.168.20.4`) and the web server (`192.168.100.100`) can access the file server. Write commands to: **(12 marks)**
   - Create a standard named ACL called `File Server Restrictions` on R1.
   - Permit the two hosts and deny all other traffic.
   - Apply it outbound on `Fa0/1`.
   - Create numbered ACL 1 with a statement denying access to `192.168.20.0/24` from `192.168.11.0/24`.

3. Explain a Next-Generation Firewall and compare it with traditional firewalls. **(5 marks)**

## Question 3 — VPN and AAA [25 marks]

1. A global financial-data company has remote employees, partners, and clients. Justify deploying both site-to-site and remote-access VPNs against these requirements. **(6 marks)**

2. A multi-office company needs centralized device administration and audit records. The topology includes R2 (`192.168.2.1`), R3 (`192.168.3.1`), a TACACS+ server (`192.168.2.2`), and a RADIUS server (`192.168.3.2`).
   1. Write commands to: **(9 marks)**
      - Create local backup user `Admin2` with secret `admin2pa55` on R2.
      - Configure the TACACS+ server and key `tacacspa55` on R2.
      - Configure AAA login authentication for R2 console access.
      - Configure the RADIUS server and key `radiuspa55` on R3.
      - Apply the defined AAA method to the console line.
   2. Compare server-based AAA with local AAA, recommend one, and explain benefits, drawbacks, and security improvement. **(5 marks)**

3. Define a replay attack, explain its operation, and state steps that prevent future replay attacks. **(5 marks)**

## Question 4 — Network Attacks and Defence [25 marks]

1. Identify each attack and justify the best mitigation: **(9 marks)**
   - The switch MAC table is filled with addresses not connected to the network.
   - A Windows XP web server crashes after receiving a fragmented ICMP Echo Request.
   - A server spends resources returning ICMP messages for UDP datagrams sent from many addresses to inactive ports.

2. Identify two key policy documents for current threats, describe what each should cover, and write two rules for each document. **(8 marks)**

3. Recommend and justify the best solution for each scenario: **(8 marks)**
   1. Replace expensive, insufficient leased lines with secure use of cheaper public fibre while continuing secure work-from-home access.
   2. Bring a public website/server in-house while controlling traffic among many internal subnetworks with different security requirements; recommend a topology and firewall type.
