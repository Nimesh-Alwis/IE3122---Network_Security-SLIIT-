# IE3032 — Network Security Final Examination

| Field | Details |
|---|---|
| Institute | Sri Lanka Institute of Information Technology |
| Degree | B.Sc. Honours Degree in Information Technology, Specialized in Cyber Security |
| Academic period | Year 3, Semester 1 & 2 (2022) |
| Date | June 2022 |
| Duration | 2 hours |
| Questions / marks | 4 compulsory questions / 100 marks |
| Source | [Original PDF](IE3032_Network_Security_Final_2022_June.pdf) |

> Transcribed from the source PDF. Figures and packet-capture details referenced by questions remain available in the original PDF.

## Question 1 — IoT and Related Case Study [15 marks]

1. IoT networks comprise three layers: Perception Layer (data-gathering layer), Network Layer, and Analysis Layer. Discuss one important function of each layer, providing examples. **(6 marks)**

2. A report describes 1.51 billion IoT-device breaches during January–June 2021, more than double the 639 million recorded in 2020. It states that approximately 58% leveraged Telnet, commonly for cryptocurrency mining, DDoS attacks, or stealing confidential data. Many enterprise and personal IoT devices lack adequate security protocols, while AI and edge computing increase both opportunities and security complexity.

   1. What common IoT attacks are mentioned in the report? **(3 marks)**
   2. Select one attack and explain the vulnerability that leads to it. **(2 marks)**
   3. Create a mitigation solution and provide technical measures that can prevent the vulnerability. **(4 marks)**

## Question 2 — Defending the Network [35 marks]

1. Explain the two categories of endpoint security, giving examples for each. **(4 marks)**

2. The ISO/OSI model has seven layers, while the TCP/IP stack was derived for Internet communication.

   1. Explain the Data Link Layer, including its functions, addresses, security vulnerabilities, and attacks. **(4 marks)**
   2. Illustrate an overlapping fragmentation attack, clearly identifying every necessary step in the figure. **(4 marks)**
   3. List three UDP attacks and explain one of them. **(4 marks)**

3. An online tutoring platform lets registered students request help, registered tutors bid for requests, and both parties hold one-to-one meetings and share materials using desktop and mobile devices.

   1. Describe three scenario-specific requirements that address integrity, covering all aspects of that security goal. **(3 marks)**
   2. A misconfigured password policy allows the platform to be infected by “HermeticWizard,” a data-wiper-like worm spreading across the local network.
      1. List five components that should be included in a password policy. **(5 marks)**
      2. List four phases used when responding to a worm attack. **(4 marks)**
      3. Compare two network-testing tools that could have been used to eliminate the worm attack. **(3 marks)**

4. Use one example to explain Zero Trust. **(4 marks)**

## Question 3 — Firewall and AAA [20 marks]

1. Define an ACL and name the four areas—ports or addresses—where ACL conditions can be applied. **(4 marks)**

2. A firewall monitors incoming and outgoing network traffic and allows or blocks it according to security rules.

   1. List and briefly explain four firewall limitations. **(3 marks)**
   2. List four firewall best practices that can secure a network. **(3 marks)**

3. Discuss why ACLs and stateful firewalls are unsuitable for filtering Zoom traffic during a security threat, and why a Next-Generation Firewall is preferable. **(5 marks)**

4. Compare RADIUS and TACACS+, including functionality, advantages, and disadvantages. **(2 marks)**

5. Single Sign-On permits login using one identity and password. Discuss its greatest disadvantage and recommend a solution. **(3 marks)**

## Question 4 — TCP/IP Stack and Related Attacks [30 marks]

1. State four basic characteristics of reliable networks and explain one using Zoom as an example. **(5 marks)**

2. A Zoom lecture uses both TCP and UDP for connection initiation, audio, video, and static content/screen sharing. Refer to the figure in the source PDF.

   1. Explain why Zoom uses both reliable and unreliable communication, giving service examples. **(6 marks)**
   2. The figure shows three UDP source-port numbers assigned to the Zoom destination port.
      1. State those port numbers. **(2 marks)**
      2. Using the Wireshark output, identify which UDP port carries video, audio, and static content, and justify each answer. **(5 marks)**

3. In 2022, Digital Marketing Ltd’s SDN network suffered a DoS attack that prevented staff and customers from reaching email, company resources, and its online store, resulting in more than USD 15 million in lost sales.

   1. Assuming the server uses TCP, use a diagram to explain how TCP is vulnerable to DoS. Clearly show TCP queues and the TCP messages used in the attack. **(6 marks)**
   2. From the defence-in-depth figure, select and compare the best two layers for eliminating the DoS attack, giving examples. **(6 marks)**
