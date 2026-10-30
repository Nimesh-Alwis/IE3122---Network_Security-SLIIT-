# Sri Lanka Institute of Information Technology

B.Sc. Honours Degree in Information Technology

Specialized in Cyber Security

Final Examination  
Year 3, Semester 1&2 (2022)

IE3032 - Network Security

Duration: 2 Hours

June 2022

## Instructions to Candidates:

- This paper has 4 Questions.
- Answer all questions in the booklet given.
- The total mark for the paper is 100.
- This paper contains 6 pages, including the cover page.
- Electronic devices capable of storing and retrieving text, including calculators and mobile phones are not allowed.

---

> **Format:** Each complete main question is followed immediately by its Simple English answers.

---

## Q1. IOT and Related Case Study [15 marks]

1. IOT networks comprises of following three layers: Perception Layer (Data gathering layer) Network Layer, and Analysis Layer.

1.1. Discuss one important function by providing examples. (6 marks)

2. “IOT cyberattacks more than doubled year-on-year during the first half of 2021, according to anti-virus and computer security service provider Kaspersky. From January to June this year, some 1.51 billion breaches of Internet of Things (IOT) devices took place, Kaspersky reported, an increase from 639 million in 2020. Most attackers brokered access to IoT networks via the telnet protocol, a command line interface that enables remote communication with a device or server. Kaspersky found that more than 872 million of IoT cyberattacks - or 58% - leveraged telnet, many with the intent of cryptocurrency mining, distributed denial-of-service (DDoS) shutdowns or pilfering confidential data. The study was conducted using software honeypots, which emulate IoT devices as a proxy for vulnerable hardware endpoints, according to PYMTS.com. The findings confirm that the pandemic has exacerbated IoT vulnerabilities by prolonging device usage in household settings. Many of the devices - whether intended for enterprise or personal use - lack adequate security protocols. The spike in IoT cyberattacks comes at a sensitive time for the industry. New technologies such as artificial intelligence and edge computing have presented opportunities, but also complicate the cyber and data security landscape. Dan Demeter, security expert at Kaspersky, said: “We see that once users’ interest in smart devices rose, attacks also intensified.”

2.1. What are the common IoT attacks mentioned in the above report? (3 marks)

2.2. Select one attack and explain the vulnerability leads to that attack. (2 marks)

2.3. Create a solution to mitigate the attack and provide the technical measures that can be taken to avoid the vulnerability. (4 marks)

---

## Q1 Answers — IoT and Related Case Study

### 1.1 IoT layers (6 marks)

- **Perception layer:** Collects real-world data through sensors and devices. Example: a temperature sensor measures room heat.
- **Network layer:** Transfers collected data to a server or cloud through Wi-Fi, Zigbee, Ethernet or cellular networks.
- **Analysis layer:** Processes the data and produces useful decisions. Example: it sends an alert when temperature is too high.

### 2.1 Common IoT attacks (3 marks)

- Telnet-based device compromise.
- Cryptocurrency mining using compromised devices.
- Distributed Denial-of-Service (DDoS) attacks.
- Theft of confidential data.

### 2.2 Vulnerability leading to an attack (2 marks)

**Example—IoT DDoS:** Many IoT devices use default or weak passwords and expose Telnet. An attacker logs in, adds the device to a botnet and commands it to flood a target.

### 2.3 Mitigation (4 marks)

- Disable Telnet; use SSH only when remote administration is necessary.
- Replace default passwords with strong, unique passwords.
- Update device firmware and remove unused services.
- Put IoT devices in a separate VLAN and restrict traffic with ACLs/firewalls.
- Monitor unusual traffic and use rate limiting or upstream DDoS protection.

---

## Q2. Defending the Network [35 marks]

1. Explain what are the two categories of Endpoint security? Your answer should contain examples for each category (4 marks)

2. ISO-OSI reference model has 7 layers to ensure data delivery in computer networks. TCP/IP stack has been derived using the ISO-OSI reference model for Internet communication.

2.1. Explain about the DataLink Layer of ISO/OSI Ref. Model. Your answer should discuss about functionalities, addresses, security vulnerabilities, and attack (4 marks)

2.2. Illustrate what is an Overlapping Fragmentation Attack? You have to clearly mention all the necessary steps in the figure. (4 marks)

2.3. List 3 UDP attacks and explain one of the attacks. (4 marks)

3. A company is developing an online tutoring platform that allows registered students to seek help with their study and registered tutors to bid for a request. The platform is designed to work on both desktop computers and mobile devices. Students and tutors will be able to conduct one-on-one meeting and share their materials during a help session.

3.1. Describe three (3) requirements of the online platform that address the security goal Integrity. Your answer must be specific to this scenario and cover all aspects of the security goal. (3 Marks)

3.2. Due to the mal configuration of the password policy of the tutoring platform it was infected by “HermeticWizard” the data-wiper like a computer worm which is spreading across a local network.

3.2.1. List five components that should be considered in password policy. (5 Marks)

3.2.2. List down 4 phases that used when responding to a worm attack (4 Marks)

3.2.3. Compare two network testing tools that could have been used to eliminate the worm attack to the tutoring platform. (3 Marks)

4. Use one example and explain what is zero Trust (4 Marks)

---

## Q2 Answers — Defending the Network

### 1. Endpoint-security categories (4 marks)

- **Endpoint protection:** Prevents attacks. Examples: anti-malware, host firewall, application control and disk encryption.
- **Endpoint detection and response (EDR):** Detects suspicious activity, records events and helps isolate/respond to compromised devices.

### 2.1 Data Link Layer (4 marks)

- OSI **Layer 2** converts packets into frames and delivers them on the local network.
- It uses **MAC addresses**, controls access to the medium and detects errors using FCS.
- Switches, Ethernet and VLANs operate here.
- Weaknesses include trusting MAC/ARP information and insecure trunk negotiation.
- Attacks include MAC flooding, ARP spoofing, VLAN hopping and STP manipulation.

### 2.2 Overlapping fragmentation attack (4 marks)

```text
Original IP datagram
   ↓ split using the same IP identification value
Fragment 1: bytes 0–999
Fragment 2: bytes 800–1599
                 ↑ overlap: bytes 800–999
Firewall reassembly ≠ destination reassembly
   ↓
Malicious content may evade inspection or crash the host
```

The attacker sends fragments whose byte ranges overlap. If the firewall and destination choose different overlapping data, the firewall may accept safe data while the destination rebuilds malicious data. Drop overlapping fragments and use consistent fragment normalization.

### 2.3 Three UDP attacks (4 marks)

- UDP flood.
- DNS/NTP amplification.
- UDP port scan.

**UDP flood:** The attacker sends many UDP packets. The server wastes bandwidth and CPU processing them and may generate ICMP Port Unreachable replies. Use ACLs, rate limiting and DDoS filtering.

### 3.1 Integrity requirements (3 marks)

- Only the correct student or tutor may create or change a help request, bid or shared file.
- Protect messages/files in transit with TLS so attackers cannot modify them.
- Use hashes/digital signatures, access control and audit logs to detect unauthorized changes and identify who made each change.

### 3.2.1 Password-policy components (5 marks)

1. Minimum password length.
2. Complexity or blocked-password rules.
3. Password history/reuse restriction.
4. Maximum/minimum password age where required.
5. Account lockout or login throttling after failed attempts.

MFA should also protect important accounts.

### 3.2.2 Worm-response phases (4 marks)

1. **Preparation:** tools, backups and response roles.
2. **Detection and analysis:** confirm the worm and identify affected devices.
3. **Containment, eradication and recovery:** isolate devices, remove malware, patch and restore.
4. **Post-incident activity:** record lessons, improve controls and monitor recurrence.

### 3.2.3 Network-testing tools (3 marks)

- **Nmap:** Discovers hosts, ports, services and vulnerable exposure. It is fast for network-wide identification but does not deeply inspect every vulnerability.
- **Nessus/OpenVAS:** Scans for known vulnerabilities and missing patches. It gives detailed findings but may produce false positives and needs safe scheduling.

Use them only on authorized systems; patch findings and verify again.

### 4. Zero Trust (4 marks)

Zero Trust means **never trust automatically; always verify**. Every access request is checked using identity, device condition, location and least privilege. Example: a tutor already inside the network must still use MFA and can access only assigned sessions, not the complete student database.

---

## Q3. Firewall and AAA [20 marks]

1. A consultant firm recommended the ACME company to implement an ACL to its network infrastructure to curb illegal activities. What is an ACL and name the 4 areas (i.e., ports or addresses) where ACLs can be applied to? (4 Marks)

2. “A firewall is a network security device that monitors incoming and outgoing network traffic and decides whether to allow or block specific traffic based on a defined set of security rules.”

2.1. List 4 limitations of a Firewall and briefly explain them. (3 Marks)

2.2. List 4 Firewall best practices that can be used to secure Your Network (3 Marks)

3. Discuss why ACL and Stateful firewalls are not suitable to filter zoom traffic in a case of security threat. Hence, it is better we have a Next Generation firewall to filter the traffic. (5 Marks)

4. Compare Remote Authentication Dial-In User Service (RADIUS) and Terminal Access Controller Access Control System (TACACS+). Your comparison should explain the functionalities, advantages and disadvantages. (2 Marks)

5. Single sign-on (SSO) is an authentication scheme that allows a user to log in with a single ID and password. Discuss the biggest disadvantage of using SSO for authentication and suggest a solution to overcome that disadvantage? (3 Marks)

---

## Q3 Answers — Firewall and AAA

### 1. ACL and four matching areas (4 marks)

An **Access Control List (ACL)** is an ordered set of permit/deny rules applied to network traffic. Conditions can match:

1. Source IP address.
2. Destination IP address.
3. Source port.
4. Destination port.

### 2.1 Firewall limitations (3 marks)

- Cannot stop attacks that bypass it, such as direct mobile/hotspot connections.
- Cannot fully prevent insider misuse using permitted access.
- Encrypted traffic can hide threats unless inspected.
- Incorrect rules or unknown application attacks can still allow malicious traffic.

### 2.2 Firewall best practices (3 marks)

- Use default-deny and allow only required services.
- Review/remove unused rules and document every rule.
- Patch firewall software and restrict administration with MFA.
- Enable logging, alerts, backups and regular rule testing.

### 3. ACL/stateful firewall vs NGFW for Zoom (5 marks)

ACLs mainly see IP addresses, protocols and ports. Stateful firewalls also track connection state, but Zoom can use dynamic ports and encrypted traffic. Blocking a port may stop legitimate Zoom traffic while allowing threats inside permitted HTTPS traffic. An **NGFW** can identify the Zoom application/user, inspect permitted traffic where legally configured, use IPS/threat intelligence and apply application-specific policy.

### 4. RADIUS vs TACACS+ (2 marks)

| Feature | RADIUS | TACACS+ |
|---|---|---|
| Common use | Network access, Wi-Fi and VPN users | Network-device administration |
| Transport | UDP | TCP port 49 |
| Encryption | Encrypts password field | Encrypts most of packet body |
| AAA | Authentication/authorization often combined | Separates authentication, authorization and accounting |
| Strength | Broad support and efficient | Per-command authorization and detailed admin control |
| Limitation | Less detailed device-command control | Mainly used for device administration/Cisco environments |

### 5. SSO disadvantage and solution (3 marks)

The biggest disadvantage is a **single point of compromise**: if one SSO account is stolen, many services become accessible. Use MFA, conditional access, short sessions, monitoring and rapid account revocation.

---

## Q4. TCP/IP Stack and the related attacks [30 marks]

1. Write 4 basic characteristics of reliable networks, and explain one of them using Zoom as an example (5 marks)

2. When using the Zoom communication to have online lectures, as indicated in figure below, we can observe that Zoom uses both TCP and UDP ports to do the communication. First, Zoom initiates the connection with the Zoom servers, and then send Audio, Video and Static content (screen share) during the zoom session. Below figure shows the connections made by Zoom when conducing a lecture.

2.1. Analyze the above figure and explain why Zoom use both reliable and unreliable communication. Your explanation should have examples of services. (6 marks)

2.2. Above Figure displays three different UDP Source PORT numbers are assigned to the Zoom destination port.

2.2.1. What are those port numbers? (2 mark)

2.2.2. Below Wireshark output shows the Zoom packet captured during the lecture. State which UDP port is used to send which data (Video, Audio and Static content)? You must justify your answer. (5 marks)

3. In year 2022, the “Digital Marketing Ltd” company’s SDN based network suffered from a DOS attack making staff and clients unable to connect to the company network. Staff was not able to access their emails and other company resources, while clients were not able to access the e-market online buying platform. The “Digital Marketing Ltd” company lost over USD$15 million of sales during the attack.

3.1. Assuming that the above server was utilized TCP as the transport layer protocol, Use a diagram an discuss how TCP is Vulnerable to Dos attacks. You have to clearly show the TCP Queues, and TCP Messages used to give a Dos attack. (6 marks)

3.2. The Below Figure illustrates the Defense in depth. Select the best two layers can be used eliminate the DOs attack. You must compare those with examples. (6 Marks)

---

## Q4 Answers — TCP/IP and Related Attacks

### 1. Reliable-network characteristics (5 marks)

- Fault tolerance.
- Scalability.
- Quality of Service (QoS).
- Security.

**Zoom example—QoS:** Voice/video packets receive priority during congestion, reducing delay, jitter and packet loss.

### 2.1 Why Zoom uses TCP and UDP (6 marks)

- **TCP** provides reliable, ordered delivery and retransmission. It suits login/control, chat, files and web/static information.
- **UDP** avoids connection and retransmission delays. It suits live audio/video because receiving a late packet is often less useful than continuing in real time.
- Zoom uses each transport according to the service and may fall back when networks block UDP.

### 2.2.1 UDP source ports (2 marks)

Read the three exact source-port numbers from the original figure. They cannot be safely inferred from the question text alone.

### 2.2.2 Match captured streams (5 marks)

Use the supplied Wireshark graph:

- **Video:** normally the highest and most variable bandwidth with larger/frequent packets.
- **Audio:** usually smaller packets sent at regular short intervals.
- **Static/screen content:** normally bursty traffic when the screen changes.

State the exact port beside each stream from the figure and support it with packet size, rate and timing. Do not guess a port without the capture.

### 3.1 TCP SYN-flood DoS (6 marks)

```text
Attacker                         Server
SYN (often spoofed) ----------> SYN/half-open queue
             <----------------- SYN-ACK
No final ACK                    entry waits
Many more SYNs ---------------> queue becomes full
Legitimate SYN ---------------> delayed or dropped
```

TCP normally uses `SYN → SYN-ACK → ACK`. The attacker never sends the final ACK, so half-open connections consume the backlog. Use SYN cookies, rate/connection limits, larger protected backlogs and upstream DDoS filtering.

### 3.2 Two defense-in-depth layers (6 marks)

- **Perimeter/network layer:** ISP scrubbing, ACLs, NGFW and rate limiting stop traffic before it reaches servers. It protects several systems but cannot help if the upstream link is already saturated without ISP support.
- **Host/transport layer:** SYN cookies, TCP backlog tuning and per-source limits protect the server’s connection state. It is close to the asset but cannot recover bandwidth already exhausted.

Use both layers together because they solve different parts of the attack.
