# Sri Lanka Institute of Information Technology

B.Sc. Honours Degree in Information Technology

Specialized in Cyber Security

Final Examination  
Year 3, Semester 1&2 (2023)

IE3032 - Network Security

Duration: 2 Hours

June 2023

## Instructions to Candidates:

- This paper has 4 Questions.
- Answer all questions in the booklet given.
- The total marks for the paper is 100.
- This paper contains 8 pages, including the cover page.
- One handwritten A4 paper can be brought into exam hall

---

> **Format:** Each complete main question is followed immediately by its Simple English answers.

---

## Question 01 — Layer 2 Security [25 marks]

a. You are the network administrator for a medium-sized company. The company has sensitive data that needs to be protected from unauthorized access. The network infrastructure includes Cisco Catalyst switches that connect various devices, such as computers, servers, and printers. The company wants to ensure that only authorized devices are allowed to connect to the network, prevent CAM table attacks, restrict the number of allowed MAC addresses on each switch port, set a maximum limit for the number of allowed MAC addresses, and configure violation actions.

i. Analyze the scenario and suggest which security measure you think is most suitable to enhance the security of the switches. (2 marks)

ii. The company had the following requirements to be implemented in the switch. Please mention the appropriate commands that must be used (8 marks)

1. Enable port security on interface Fast Ethernet ports 0/1 and 0/2
2. Set the maximum allowed MAC addresses to 5 on the interface.
3. Configure the violation action to be “shutdown” on the interface.
4. Disable all the remaining unused ports. (Interface Range f0/3 - 24, g0/1 - 2)

b. Now the company has a large number of devices that obtain IP addresses from the DHCP server. The network infrastructure includes Cisco Catalyst switches that are connected to multiple VLANs, and the DHCP server is in a trusted VLAN. The company wants to prevent unauthorized devices from acting as DHCP servers and distributing rogue IP addresses to other devices on the network.

i. Analyze the scenario and suggest which security measure you think is most suitable to enhance the security of the switches. (2 marks)

ii. The company had the following requirements to be implemented in the switch. Please mention the appropriate commands that has to be used. (9 marks)

1. Enable DHCP snooping globally.
2. Configure the trusted VLANs where the DHCP server is located. (VLAN 1)
3. Enable DHCP snooping on interface Fa0/4
4. Rate limit on the Fa0/4 interface for 20

iii. What is the best methods that can be used to thwart VLAN hopping attacks? (4 marks)

---

## Question 01 Answers — Layer 2 Security

### a(i) Suitable switch-security measure (2 marks)

Use **switch port security**. It limits the MAC addresses learned on an access port and performs a configured action when an unauthorized MAC appears. This reduces unauthorized access and CAM-table flooding.

### a(ii) Port-security commands (8 marks)

```cisco
enable
configure terminal
interface range fastethernet 0/1 - 2
 switchport mode access
 switchport port-security
 switchport port-security maximum 5
 switchport port-security violation shutdown
exit
interface range fastethernet 0/3 - 24
 shutdown
exit
interface range gigabitethernet 0/1 - 2
 shutdown
end
```

### b(i) DHCP-security measure (2 marks)

Use **DHCP snooping**. Only trusted server-facing ports may send DHCP server messages, so a rogue server on an access port is blocked.

### b(ii) DHCP-snooping commands (9 marks)

```cisco
enable
configure terminal
ip dhcp snooping
ip dhcp snooping vlan 1
interface fastethernet 0/4
 ip dhcp snooping trust
 ip dhcp snooping limit rate 20
end
```

The paper requests both trust and rate limit on Fa0/4. In a real network, rate limiting is normally most important on untrusted client ports.

### b(iii) Prevent VLAN hopping (4 marks)

- Configure user ports with `switchport mode access`.
- Disable DTP using `switchport nonegotiate` where supported.
- Use an unused native VLAN instead of VLAN 1 and tag the native VLAN where supported.
- Allow only required VLANs on trunks and shut down unused ports.

---

## Question 02 — ACL and Firewalls [25 marks]

a. A company is planning to deploy a new web application that will be accessible from the Internet. The web application will allow customers to place orders, view product details, and submit support tickets. The company's internal network contains servers that handle inventory management, shipping, and other backend operations. The company is more concerned with securing the internal network and wants to have more control over traffic between different parts of the network.

i. As a network administrator, analyze the situation and recommend the most suitable firewall between using a zone-based firewall or a DMZ? (2 marks)

ii. You are instructed to configure a Zone based policy firewall on Router 3. Please mention the appropriate commands that has to be used. (6 marks)

1. Create a zone named IN-ZONE
2. Create a zone named OUT-ZONE
3. Assign interfaces G0/1 to IN-ZONE security zone and S0/0/1 to OUT-ZONE security zone.

b. The senior network administrator has asked you to create a standard named ACL to prevent access to a file server. The file server contains the data base for the web applications. Only the Web Manager workstation PC1 and the Web Server need to access the File Server. All other traffic to the File Server should be denied. You are required to fulfill the below requirement on R1 and R2. Please mention the appropriate commands that has to be used. (12 marks)

i. Configure a named ACL on R1 called “File Server Restrictions”  
ii. Permit the hosts 192.168.20.4 and 192.168.100.100  
iii. Deny any other traffic.  
iv. Apply the named ACL outbound on the Fast Ethernet 0/1 interface.  
v. Create an numbered ACL using the number 1 on R1 with a statement that denies access to the 192.168.20.0/24 network from the 192.168.11.0/24 network

c. Explain the concept of a Next Generation Firewall and compare it to Traditional Firewalls. (5 Marks)

---

## Question 02 Answers — ACL and Firewalls

### a(i) Zone-based firewall or DMZ (2 marks)

Use a **DMZ topology controlled by a zone-based firewall**. Place the public web server in the DMZ, keep backend servers inside and allow only necessary flows. The DMZ prevents a compromised web server from directly reaching the internal network, while zone policies control traffic between OUTSIDE, DMZ and INSIDE.

### a(ii) Zone commands (6 marks)

```cisco
enable
configure terminal
zone security IN-ZONE
zone security OUT-ZONE
interface gigabitethernet 0/1
 zone-member security IN-ZONE
exit
interface serial 0/0/1
 zone-member security OUT-ZONE
end
```

A complete working ZBFW also needs class maps, policy maps, a zone pair and a service policy.

### b. ACL commands (12 marks)

```cisco
! R1 - named standard ACL
configure terminal
ip access-list standard File_Server_Restrictions
 permit host 192.168.20.4
 permit host 192.168.100.100
 deny any
exit
interface fastethernet 0/1
 ip access-group File_Server_Restrictions out
exit

! Literal numbered standard ACL requested by the paper
access-list 1 deny 192.168.11.0 0.0.0.255
access-list 1 permit any
end
```

Important: a standard ACL matches only the **source**. To specifically deny traffic from `192.168.11.0/24` **to** `192.168.20.0/24`, use an extended ACL:

```cisco
ip access-list extended BLOCK_TO_20
 deny ip 192.168.11.0 0.0.0.255 192.168.20.0 0.0.0.255
 permit ip any any
```

Apply it close to the source in the correct direction.

### c. NGFW vs traditional firewall (5 marks)

- A traditional packet-filter firewall mainly checks IP addresses, ports and protocols.
- A stateful traditional firewall also tracks connection state.
- An **NGFW** adds application/user awareness, deep packet inspection, IPS, malware/threat intelligence and better centralized visibility.
- Therefore, an NGFW can distinguish applications using the same port and block malicious activity inside an otherwise permitted flow.
- It costs more, needs skilled configuration and may need TLS inspection to see encrypted threats.

---

## Question 03 — VPN and AAA [25 marks]

a. You are the network administrator for a large company that handles sensitive financial data. Your company has recently expanded and now has remote employees working from different locations around the world. In addition, the company's partners and clients need to access the company's network to collaborate on projects and share information. Your company is concerned about the security of its network and wants to implement measures to control access and protect its data. As a network administrator, you have decided to implement both site-to-site VPN and remote access VPN for a company's network. Justify your selection by providing a detailed analysis of the company's requirements and how each type of VPN meets those requirements. (6 Marks)

b. A medium-sized company has multiple offices across the country, and each office has its own network devices, such as switches, routers, and firewalls. The company wants to implement a centralized authentication and authorization system for all network devices to enhance security and simplify management. The company has two main requirements: first, network administrators should be able to manage all network devices from a central location using a single set of credentials; second, the company wants to keep track of who is accessing the network and what actions they are taking, so it can monitor and audit network activity. As the network administrator, you have decided to implement TACACS+ and RADIUS as the authentication and authorization protocols for the network devices.

| Device | Interface | IP Address | Subnet Mask | Default Gateway | Switch Port |
|---|---|---|---|---|---|
| R1 | G0/1 | 192.168.1.1 | 255.255.255.0 | N/A | S1 F0/1 |
| R1 | S0/0/0 (DCE) | 10.1.1.2 | 255.255.255.252 | N/A | N/A |
| R2 | G0/0 | 192.168.2.1 | 255.255.255.0 | N/A | S2 F0/2 |
| R2 | S0/0/0 | 10.1.1.1 | 255.255.255.252 | N/A | N/A |
| R2 | S0/0/1 (DCE) | 10.2.2.1 | 255.255.255.252 | N/A | N/A |
| R3 | G0/1 | 192.168.3.1 | 255.255.255.0 | N/A | S3 F0/5 |
| R3 | S0/0/1 | 10.2.2.2 | 255.255.255.252 | N/A | N/A |
| TACACS+ Server | NIC | 192.168.2.2 | 255.255.255.0 | 192.168.2.1 | S2 F0/6 |
| RADIUS Server | NIC | 192.168.3.2 | 255.255.255.0 | 192.168.3.1 | S3 F0/1 |
| PC-A | NIC | 192.168.1.3 | 255.255.255.0 | 192.168.1.1 | S1 F0/2 |
| PC-B | NIC | 192.168.2.3 | 255.255.255.0 | 192.168.2.1 | S2 F0/1 |
| PC-C | NIC | 192.168.3.3 | 255.255.255.0 | 192.168.3.1 | S3 F0/18 |

i. Refer the above table and you are required to fulfill the below requirements. Please mention the appropriate commands that has to be used. (9 Marks)

1. For backup purposes, configure a local username of Admin2 and a secret password of admin2pa55 on R2.
2. Configure the AAA TACACS server IP address and secret key (tacacspa55) on R2.
3. Configure AAA login authentication for console access on R2.
4. Configure the AAA RADIUS server IP address and secret key (radiuspa55) on R3.
5. Configure the line console to use the defined AAA authentication method.

ii. The upper management has asked you to select two options: implementing server-based AAA authentication or local AAA authentication. analyze the situation and recommend the most suitable AAA authentication method between server-based AAA and local AAA authentication. What are the benefits and drawbacks of each method, and how will your recommendation improve network security? (5 Marks)

c. A large e-commerce company recently experienced a security breach, which resulted in the theft of customer data such as names, email addresses, and credit card information. The company's security team suspects that the attackers used a replay attack to gain access to the company's network. (5 Marks)

i. What is a Replay attack and how does it work?

ii. As the network administrator, what steps would you take to prevent replay attacks from occurring in the future?

---

## Question 03 Answers — VPN and AAA

### a. Site-to-site and remote-access VPN (6 marks)

- **Site-to-site IPsec VPN:** Creates an always-on encrypted gateway-to-gateway tunnel between company/partner networks. Local users normally need no VPN client.
- **Remote-access VPN:** Creates an encrypted user/device-to-company tunnel for home or travelling workers. Use MFA and device checks.
- The company needs both because branches/partners require network-to-network connectivity while individual remote employees require user-specific access.
- Apply least privilege and log all VPN activity.

### b(i) AAA configuration (9 marks)

```cisco
! R2 - TACACS+ with local backup
configure terminal
aaa new-model
username Admin2 privilege 15 secret admin2pa55
tacacs server TAC_R2
 address ipv4 192.168.2.2
 key tacacspa55
exit
aaa group server tacacs+ TAC_GROUP
 server name TAC_R2
exit
aaa authentication login default group TAC_GROUP local
line console 0
 login authentication default
exit
end

! R3 - RADIUS
configure terminal
aaa new-model
radius server RAD_R3
 address ipv4 192.168.3.2 auth-port 1812 acct-port 1813
 key radiuspa55
exit
aaa group server radius RAD_GROUP
 server name RAD_R3
exit
aaa authentication login default group RAD_GROUP local
line console 0
 login authentication default
end
```

Older IOS versions may use `tacacs-server host` and `radius-server host`. R3 needs a local user for successful local fallback.

### b(ii) Local vs server-based AAA (5 marks)

| Local AAA | Server-based AAA |
|---|---|
| Works if WAN/server fails | Central users and policies |
| Simple for one device | Central accounting/audit logs |
| Hard to update many devices | Immediate account revocation |
| Separate, incomplete logs | Depends on network/server availability |

Recommend **centralized TACACS+ for administrator access and RADIUS for network access**, with redundant servers and a protected local emergency account.

### c. Replay attack (5 marks)

A replay attack occurs when an attacker captures a valid authentication message, token or transaction and sends it again later. The receiver accepts the old message as new. Prevent it with nonces/challenge-response, sequence numbers, timestamps and short expiry, authenticated secure sessions and server-side anti-replay checks. Encryption alone may not stop replay.

---

## Question 04 — Network Attacks and Defense [25 marks]

a. Imagine you have been hired as a senior security engineer at a company which has been struggling with its information security posture. Due to new regulatory requirements the senior management has decided that an overall audit and revision of its cybersecurity capability and requirements is needed. Below are the details of the findings after 3 successful attacks on the company's network. Analyze the below scenarios and identify the attack that has taken place and identify and justify what is the best form of mitigation that can be used to stop such attacks in the future. (9 Marks)

i. After employees complained of connectivity issues further investigation showed that switch MAC address tables were filled with MAC addresses not connected to the network.

ii. After a few days in which the company web server crashed frequently the network logs were examined. It was found that that each time the webserver crashed after a fragmented ICMP echo request was received and processed by the server. It was also found that due to budgetary issues the OS used on the server was windows XP.

iii. After complaints about the website being unresponsive it was found that the server was using many resources to respond with ICMP messages to UDP packets meant for non-active ports. Further investigation revealed that the UDP datagrams originated from different IP addresses.

b. The company has now decided to improve its security posture by implementing an overarching security policy and developing DR and BCP plans. Based on the current threats faced by companies, identify 2 key policy documents that should be developed and what areas each should cover. For each document identify and write 2 key rules you will include. (8 Marks)

c. The company is now in the process of updating its security infrastructure. Identify and justify the best option for the below scenarios. (8 Marks)

i. The company has been using a dedicated leased line to connect its branches and the main HQ. Due to network expansion the currently available leased lines are not sufficient to handle the required traffic and a new one is extremely costly. The ISP has public fiber lines which are sufficient at much cheaper rates but security over the public network is not provided. Also, some workers are still working with work from home contracts, and they also require secure access to the internal networks. What solution do you recommend being used for this situation.

ii. The HQ is now thinking of bringing its previously outsourced website and server in-house. In addition, due to company expansion the number of internal sub-networks has significantly grown, and the security requirements of each network are different. Therefore, it has been decided that there need to be rules for what traffic can pass between even the external sub-networks. What topology and type of firewall would you recommend being used?

---

## Question 04 Answers — Network Attacks and Defense

### a(i) Filled MAC table (3 marks)

**Attack:** CAM/MAC flooding. Fake source MAC addresses fill the switch table, causing frames to be flooded. **Mitigation:** port security with maximum/sticky MACs, disable unused ports and alert on violations.

### a(ii) Fragmented ICMP crashes Windows XP (3 marks)

**Attack:** Ping of Death/malformed fragmented ICMP attack. The old OS fails while reassembling oversized or malformed fragments. **Mitigation:** replace/patch Windows XP and drop invalid fragments at the firewall/IPS.

### a(iii) UDP packets cause many ICMP replies (3 marks)

**Attack:** UDP flood. Packets target inactive ports, making the server generate ICMP errors and consume CPU/bandwidth. **Mitigation:** firewall unnecessary UDP, rate-limit ICMP/UDP and use upstream DDoS filtering.

### b. Two policy documents (8 marks)

**1. Information Security Policy**

- Covers access control, authentication, data classification, encryption and acceptable use.
- Rule 1: Privileged users must use MFA and least privilege.
- Rule 2: Confidential data must use approved encryption in transit and at rest.

**2. Incident Response Policy/Plan**

- Covers reporting, roles, triage, containment, evidence, recovery and lessons learned.
- Rule 1: Suspected incidents must be reported immediately to the security team.
- Rule 2: Confirmed infected devices must be isolated while logs/evidence are preserved.

### c(i) Public fibre, branches and home workers (4 marks)

Use **site-to-site IPsec VPNs over public fibre** for branches. Use **remote-access SSL/IPsec VPN with MFA** for home workers. Encryption, integrity checks and peer authentication protect public-network traffic. Use backup links/endpoints for availability.

### c(ii) In-house public server and many subnetworks (4 marks)

```text
Internet → Edge router → HA NGFW
                         ├── DMZ: public web server
                         └── Internal core
                             ├── User VLAN
                             ├── Server VLAN
                             └── Management VLAN
```

Use an **NGFW with OUTSIDE, DMZ and INSIDE zones**. Permit only necessary Internet-to-DMZ and DMZ-to-internal traffic. Apply application-aware IPS/logging and explicit inter-VLAN policies. High availability reduces the firewall single point of failure.
