# Lecture 02 – Networking Revision

## 📌 Lecture Overview

This lecture covers **Networking Revision** as presented in the supplied IE3122 slides. The notes follow the source order across 55 slides and retain the lecture's terminology, mechanisms, examples, and configuration details. They are organized for rapid MCQ, structured-answer, and scenario revision.

> **Source boundary:** Content below is derived from `IE3122_Week1_NetworkingRevision_Slides.pdf`. Generic exam prompts/examples are labelled as application material; no unsupported lecturer emphasis is claimed.

## 🎯 Learning Objectives

- Explain the principal concepts in Networking Revision.
- Relate vulnerabilities to their security impact and suitable mitigations.
- Apply the lecture concepts to exam and practical scenarios.

## 📚 Main Topics and Subtopics

### What We're Refreshing (Slide 2)

**Exam Answer:** Layered architecture (OSI & TCP/IP).

**Explanation:**

- Layered architecture (OSI & TCP/IP)
- Switching & routing fundamentals
- Ethernet & IP addressing
- DHCP & ARP
- TCP & UDP
- HTTP
- Why revisit this?
- Every attack and defense mechanism in this module
- sits on top of these fundamentals — you can't
- secure a layer you don't understand.
- This is a refresher, not first-time teaching — we
- move quickly and focus on what matters for
- security.

**සිංහලෙන්:** **What We're Refreshing** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Layered architecture (OSI & TCP/IP)
- Switching & routing fundamentals
- Ethernet & IP addressing
- DHCP & ARP

**🧠 Memory Tip:** Remember **What We're Refreshing** by linking its purpose → mechanism → result.

### How This Fits the Module (Slide 3)

**Exam Answer:** Underpins LO1 (describing vulnerabilities) and LO3 (analysing network/communication requirements).

**Explanation:**

- Underpins LO1 (describing vulnerabilities) and LO3 (analysing network/communication requirements).
- Weeks 3–5 build directly on this: Layer 2, 3, and 4 attacks all exploit gaps in the protocols we're reviewing today.
- If any of this feels shaky, flag it early — it only gets more security-focused from here.

**සිංහලෙන්:** **How This Fits the Module** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Underpins LO1 (describing vulnerabilities) and LO3 (analysing network/communication requirements).
- Weeks 3–5 build directly on this: Layer 2, 3, and 4 attacks all exploit gaps in the protocols we're reviewing today.
- If any of this feels shaky, flag it early — it only gets more security-focused from here.

**🧠 Memory Tip:** Remember **How This Fits the Module** by linking its purpose → mechanism → result.

### Layered Architecture (Slide 4)

**Exam Answer:** Why we split networking into layers.

**Explanation:**

- Why we split networking into layers

**සිංහලෙන්:** **Layered Architecture** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Why we split networking into layers

**🧠 Memory Tip:** Remember **Layered Architecture** by linking its purpose → mechanism → result.

### Why Layered Architecture? (Slide 5)

**Exam Answer:** CONCEPT.

**Explanation:**

- CONCEPT
- Breaks a complex problem (moving data across a network) into independent, manageable pieces.
- Each layer has one job and only talks to the layers directly above and below it.
- Vendors can innovate within a layer (e.g. a new Ethernet standard) without breaking the layers above.
- Security matters: attackers target specific layers, so defenders need layer-by-layer thinking.

**සිංහලෙන්:** **Why Layered Architecture?** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONCEPT
- Breaks a complex problem (moving data across a network) into independent, manageable pieces.
- Each layer has one job and only talks to the layers directly above and below it.
- Vendors can innovate within a layer (e.g. a new Ethernet standard) without breaking the layers above.

**🧠 Memory Tip:** Remember **Why Layered Architecture?** by linking its purpose → mechanism → result.

### The OSI 7-Layer Model (Slide 6)

**Exam Answer:** CONCEPT.

**Explanation:**

- CONCEPT
- 7 Application HTTP , DNS, SMTP
- 6 Presentation Encryption, encoding
- 5 Session Session mgmt
- 4 Transport TCP , UDP
- 3 Network IP , routing
- 2 Data Link Ethernet, MAC, ARP
- 1 Physical Cabling, signals

**සිංහලෙන්:** **The OSI 7-Layer Model** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONCEPT
- 7 Application HTTP , DNS, SMTP
- 6 Presentation Encryption, encoding
- 5 Session Session mgmt

**🧠 Memory Tip:** Remember **The OSI 7-Layer Model** by linking its purpose → mechanism → result.

### OSI vs TCP/IP Model (Slide 7)

**Exam Answer:** CONCEPT.

**Explanation:**

- CONCEPT
- OSI (7 layers) TCP/IP (4 layers)
- Application / Presentation / Session Application
- Transport Transport
- Network Internet
- Data Link / Physical Network Access
- TCP/IP is what's actually implemented on the Internet; OSI is the conceptual teaching model we use to reason about it.

**සිංහලෙන්:** **OSI vs TCP/IP Model** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONCEPT
- OSI (7 layers) TCP/IP (4 layers)
- Application / Presentation / Session Application
- Transport Transport

**🧠 Memory Tip:** Remember **OSI vs TCP/IP Model** by linking its purpose → mechanism → result.

### Encapsulation & Decapsulation (Slide 8)

**Exam Answer:** CONCEPT.

**Explanation:**

- CONCEPT
- Data + TCP/UDPHeader (Segment) + IPHeader (Packet) + EthernetHeader/Trailer (Frame)
- Encapsulation: as data moves down the stack (sender), each layer wraps it with its own header (and sometimes trailer).
- Decapsulation: as it moves up the stack (receiver), each layer strips off and reads its own header.
- Security relevance: many attacks (spoofing, injection) work by tampering with a specific layer's header.

**සිංහලෙන්:** **Encapsulation & Decapsulation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONCEPT
- Data + TCP/UDPHeader (Segment) + IPHeader (Packet) + EthernetHeader/Trailer (Frame)
- Encapsulation: as data moves down the stack (sender), each layer wraps it with its own header (and sometimes trailer).
- Decapsulation: as it moves up the stack (receiver), each layer strips off and reads its own header.

**🧠 Memory Tip:** Remember **Encapsulation & Decapsulation** by linking its purpose → mechanism → result.

### Switching Revision (Slide 9)

**Exam Answer:** Layer 2 forwarding fundamentals.

**Explanation:**

- Layer 2 forwarding fundamentals

**සිංහලෙන්:** **Switching Revision** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Layer 2 forwarding fundamentals

**🧠 Memory Tip:** Remember **Switching Revision** by linking its purpose → mechanism → result.

### What Switches Do (Slide 10)

**Exam Answer:** SWITCHING.

**Explanation:**

- SWITCHING
- Operate at Layer 2 — forward frames based on destination MAC address.
- Build and maintain a MAC address table by learning source MACs on incoming frames.
- Unknown destination → flood out all ports except the incoming one; known destination → forward out one port only.
- Each switch port is its own collision domain — this is why switches replaced hubs.

**සිංහලෙන්:** **What Switches Do** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SWITCHING
- Operate at Layer 2 — forward frames based on destination MAC address.
- Build and maintain a MAC address table by learning source MACs on incoming frames.
- Unknown destination → flood out all ports except the incoming one; known destination → forward out one port only.

**🧠 Memory Tip:** Remember **What Switches Do** by linking its purpose → mechanism → result.

### Domains & VLANs (Slide 11)

**Exam Answer:** SWITCHING.

**Explanation:**

- SWITCHING
- Collision domain: a segment where frames can collide — each switch port is its own collision domain.
- Broadcast domain: the set of devices that receive a broadcast — by default, all ports on a switch share one broadcast
- domain.
- VLANs (Virtual LANs) split a switch into multiple broadcast domains for segmentation — a core building block for later
- security topics like zone-based defenses.

**සිංහලෙන්:** **Domains & VLANs** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SWITCHING
- Collision domain: a segment where frames can collide — each switch port is its own collision domain.
- Broadcast domain: the set of devices that receive a broadcast — by default, all ports on a switch share one broadcast
- domain.

**🧠 Memory Tip:** Remember **Domains & VLANs** by linking its purpose → mechanism → result.

### Common Switching Issues (Slide 12)

**Exam Answer:** SWITCHING.

**Explanation:**

- SWITCHING
- Switching loops: redundant links can cause broadcast storms — prevented by Spanning Tree Protocol (STP).
- MAC table exhaustion / CAM overflow: an attacker floods fake MACs to force a switch into flooding all frames
- (foreshadows Week 4–5 Layer 2 attacks).
- We'll dig into these as attacks — and their defenses — later in the module.

**සිංහලෙන්:** **Common Switching Issues** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SWITCHING
- Switching loops: redundant links can cause broadcast storms — prevented by Spanning Tree Protocol (STP).
- MAC table exhaustion / CAM overflow: an attacker floods fake MACs to force a switch into flooding all frames
- (foreshadows Week 4–5 Layer 2 attacks).

**🧠 Memory Tip:** Remember **Common Switching Issues** by linking its purpose → mechanism → result.

### Routing Revision (Slide 13)

**Exam Answer:** Layer 3 forwarding fundamentals.

**Explanation:**

- Layer 3 forwarding fundamentals

**සිංහලෙන්:** **Routing Revision** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Layer 3 forwarding fundamentals

**🧠 Memory Tip:** Remember **Routing Revision** by linking its purpose → mechanism → result.

### What Routers Do (Slide 14)

**Exam Answer:** ROUTING.

**Explanation:**

- ROUTING
- Operate at Layer 3 — forward packets based on destination IP address.
- Maintain a routing table mapping networks to the best next-hop interface.
- Connect different networks/broadcast domains together — a router is a natural boundary for security policy.
- Every host needs a default gateway — the router it sends traffic to when the destination isn't on its local network.

**සිංහලෙන්:** **What Routers Do** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ROUTING
- Operate at Layer 3 — forward packets based on destination IP address.
- Maintain a routing table mapping networks to the best next-hop interface.
- Connect different networks/broadcast domains together — a router is a natural boundary for security policy.

**🧠 Memory Tip:** Remember **What Routers Do** by linking its purpose → mechanism → result.

### Static vs Dynamic Routing (Slide 15)

**Exam Answer:** ROUTING.

**Explanation:**

- ROUTING
- Static Routing Dynamic Routing
- Configuration Manually entered by admin Learned automatically via a routing protocol
- Best for Small, stable networks Larger networks with changing topology
- Security angle Predictable, smaller attack surface Vulnerable to route injection/spoofing if unauthenticated

**සිංහලෙන්:** **Static vs Dynamic Routing** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ROUTING
- Static Routing Dynamic Routing
- Configuration Manually entered by admin Learned automatically via a routing protocol
- Best for Small, stable networks Larger networks with changing topology

**🧠 Memory Tip:** Remember **Static vs Dynamic Routing** by linking its purpose → mechanism → result.

### Routing Protocols — Quick Overview (Slide 16)

**Exam Answer:** ROUTING.

**Explanation:**

- ROUTING
- Protocol Type Notes
- RIP Distance-vector Simple, hop-count based, limited scalability
- OSPF Link-state Fast convergence, widely used internally
- EIGRP Advanced distance-vector Cisco-developed, fast convergence
- BGP Path-vector Routes the Internet itself, between autonomous systems

**සිංහලෙන්:** **Routing Protocols — Quick Overview** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ROUTING
- Protocol Type Notes
- RIP Distance-vector Simple, hop-count based, limited scalability
- OSPF Link-state Fast convergence, widely used internally

**🧠 Memory Tip:** Remember **Routing Protocols — Quick Overview** by linking its purpose → mechanism → result.

### Ethernet (Slide 17)

**Exam Answer:** The dominant Layer 2 / Layer 1 technology.

**Explanation:**

- The dominant Layer 2 / Layer 1 technology

**සිංහලෙන්:** **Ethernet** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- The dominant Layer 2 / Layer 1 technology

**🧠 Memory Tip:** Remember **Ethernet** by linking its purpose → mechanism → result.

### The Ethernet Frame (Slide 18)

**Exam Answer:** ETHERNET.

**Explanation:**

- ETHERNET
- Preambl
- e
- Dest
- MAC
- Src
- MAC Type Payload (46–1500B) FCS
- Destination/Source MAC: 6-byte hardware addresses identifying sender and receiver on the local segment.
- Type: identifies the encapsulated protocol (e.g. IPv4, ARP).
- FCS (Frame Check Sequence): CRC checksum for error detection — not tamper protection.

**සිංහලෙන්:** **The Ethernet Frame** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ETHERNET
- Preambl
- e
- Dest

**🧠 Memory Tip:** Remember **The Ethernet Frame** by linking its purpose → mechanism → result.

### MAC Addressing (Slide 19)

**Exam Answer:** ETHERNET.

**Explanation:**

- ETHERNET
- 48-bit address, usually written as six hex pairs (e.g. 00:1A:2B:3C:4D:5E).
- First 3 bytes (OUI) identify the manufacturer; last 3 bytes are the device-specific identifier.
- Burned into hardware, but can be spoofed in software — a common Layer 2 attack technique we'll cover later.

**සිංහලෙන්:** **MAC Addressing** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ETHERNET
- 48-bit address, usually written as six hex pairs (e.g. 00:1A:2B:3C:4D:5E).
- First 3 bytes (OUI) identify the manufacturer; last 3 bytes are the device-specific identifier.
- Burned into hardware, but can be spoofed in software — a common Layer 2 attack technique we'll cover later.

**🧠 Memory Tip:** Remember **MAC Addressing** by linking its purpose → mechanism → result.

### Ethernet Standards & Speeds (Slide 20)

**Exam Answer:** ETHERNET.

**Explanation:**

- ETHERNET
- Standard Speed Common Use
- 10BASE-T 10 Mbps Legacy
- 100BASE-TX (Fast Ethernet) 100 Mbps Older LANs
- 1000BASE-T (Gigabit) 1 Gbps Standard LAN today
- 10GBASE-T and above 10 Gbps+ Data centers, backbones

**සිංහලෙන්:** **Ethernet Standards & Speeds** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ETHERNET
- Standard Speed Common Use
- 10BASE-T 10 Mbps Legacy
- 100BASE-TX (Fast Ethernet) 100 Mbps Older LANs

**🧠 Memory Tip:** Remember **Ethernet Standards & Speeds** by linking its purpose → mechanism → result.

### IP (Slide 21)

**Exam Answer:** Logical addressing and routing at Layer 3.

**Explanation:**

- Logical addressing and routing at Layer 3

**සිංහලෙන්:** **IP** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Logical addressing and routing at Layer 3

**🧠 Memory Tip:** Remember **IP** by linking its purpose → mechanism → result.

### IPv4 Addressing (Slide 22)

**Exam Answer:** IP.

**Explanation:**

- IP
- 32-bit address, written as 4 decimal octets (e.g. 192.168.1.10).
- Split into network and host portions, defined by a subnet mask (e.g. /24 = 255.255.255.0).
- Address classes (A, B, C) are largely historical — modern networks use CIDR (Classless Inter-Domain Routing).
- Private ranges (10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16) aren't routed on the public Internet — relevant to NAT and
- perimeter security.

**සිංහලෙන්:** **IPv4 Addressing** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IP
- 32-bit address, written as 4 decimal octets (e.g. 192.168.1.10).
- Split into network and host portions, defined by a subnet mask (e.g. /24 = 255.255.255.0).
- Address classes (A, B, C) are largely historical — modern networks use CIDR (Classless Inter-Domain Routing).

**🧠 Memory Tip:** Remember **IPv4 Addressing** by linking its purpose → mechanism → result.

### Subnetting Basics (Slide 23)

**Exam Answer:** IP.

**Explanation:**

- IP
- CIDR Subnet Mask Usable Hosts
- /24 255.255.255.0 254
- /25 255.255.255.128 126
- /26 255.255.255.192 62
- /30 255.255.255.252 2 (point-to-point links)
- Subnetting isn't just addressing — smaller subnets mean smaller broadcast domains and tighter security boundaries.

**සිංහලෙන්:** **Subnetting Basics** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IP
- CIDR Subnet Mask Usable Hosts
- /24 255.255.255.0 254
- /25 255.255.255.128 126

**🧠 Memory Tip:** Remember **Subnetting Basics** by linking its purpose → mechanism → result.

### IPv4 vs IPv6 (Slide 24)

**Exam Answer:** IP.

**Explanation:**

- IP
- IPv4 IPv6
- Address length 32-bit 128-bit
- Address space ~4.3 billion 3.4×10³⁸
- Built-in security None (IPSec optional) IPSec support built into the standard
- Notation 192.168.1.10 2001:0db8::1

**සිංහලෙන්:** **IPv4 vs IPv6** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IP
- IPv4 IPv6
- Address length 32-bit 128-bit
- Address space ~4.3 billion 3.4×10³⁸

**🧠 Memory Tip:** Remember **IPv4 vs IPv6** by linking its purpose → mechanism → result.

### IPv4 vs IPv6 Header (Slide 25)

**Exam Answer:** IP.

**Explanation:**

- IP

**සිංහලෙන්:** **IPv4 vs IPv6 Header** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IP

**🧠 Memory Tip:** Remember **IPv4 vs IPv6 Header** by linking its purpose → mechanism → result.

### IP Header — Key Fields (Slide 26)

**Exam Answer:** IP.

**Explanation:**

- IP
- TTL (Time to Live): limits how many hops a packet can traverse — prevents infinite routing loops.
- Protocol: identifies the transport-layer protocol carried (TCP=6, UDP=17, ICMP=1).
- Source/Destination IP: the addresses routers use to forward the packet.
- Fragmentation flags/offset: support splitting packets too large for a given link — also a historical attack vector
- (fragmentation attacks).

**සිංහලෙන්:** **IP Header — Key Fields** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IP
- TTL (Time to Live): limits how many hops a packet can traverse — prevents infinite routing loops.
- Protocol: identifies the transport-layer protocol carried (TCP=6, UDP=17, ICMP=1).
- Source/Destination IP: the addresses routers use to forward the packet.

**🧠 Memory Tip:** Remember **IP Header — Key Fields** by linking its purpose → mechanism → result.

### DHCP (Slide 27)

**Exam Answer:** Automatic IP address assignment.

**Explanation:**

- Automatic IP address assignment

**සිංහලෙන්:** **DHCP** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Automatic IP address assignment

**🧠 Memory Tip:** Remember **DHCP** by linking its purpose → mechanism → result.

### DHCP: DORA Process (Slide 28)

**Exam Answer:** DHCP.

**Explanation:**

- DHCP
- Discover
- Client broadcasts for a DHCP
- server
- Offer
- Server offers an available IP
- Request
- Client requests the offered IP
- Acknowledge
- Server confirms the lease

**සිංහලෙන්:** **DHCP: DORA Process** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DHCP
- Discover
- Client broadcasts for a DHCP
- server

**🧠 Memory Tip:** Remember **DHCP: DORA Process** by linking its purpose → mechanism → result.

### DHCP: DORA Process (Slide 29)

**Exam Answer:** DHCP.

**Explanation:**

- DHCP

**සිංහලෙන්:** **DHCP: DORA Process** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DHCP

**🧠 Memory Tip:** Remember **DHCP: DORA Process** by linking its purpose → mechanism → result.

### DHCP Details (Slide 30)

**Exam Answer:** DHCP.

**Explanation:**

- DHCP
- Uses UDP ports 67 (server) and 68 (client).
- Leases are time-limited — clients must renew before expiry or risk losing their address.
- DHCP options can also hand out gateway, DNS servers, and other config — not just an IP address.

**සිංහලෙන්:** **DHCP Details** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DHCP
- Uses UDP ports 67 (server) and 68 (client).
- Leases are time-limited — clients must renew before expiry or risk losing their address.
- DHCP options can also hand out gateway, DNS servers, and other config — not just an IP address.

**🧠 Memory Tip:** Remember **DHCP Details** by linking its purpose → mechanism → result.

### DHCP: A Security Preview (Slide 31)

**Exam Answer:** DHCP.

**Explanation:**

- DHCP
- DHCP has no built-in authentication — any device can respond to a Discover.
- Rogue DHCP server attack: an attacker's server races the real one to hand out a malicious gateway/DNS, redirecting
- victim traffic.
- Mitigation preview: DHCP snooping on switches (we'll cover this properly under Layer 2 attacks & network defense).

**සිංහලෙන්:** **DHCP: A Security Preview** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DHCP
- DHCP has no built-in authentication — any device can respond to a Discover.
- Rogue DHCP server attack: an attacker's server races the real one to hand out a malicious gateway/DNS, redirecting
- victim traffic.

**🧠 Memory Tip:** Remember **DHCP: A Security Preview** by linking its purpose → mechanism → result.

### ARP (Slide 32)

**Exam Answer:** Mapping IP addresses to MAC addresses.

**Explanation:**

- Mapping IP addresses to MAC addresses

**සිංහලෙන්:** **ARP** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Mapping IP addresses to MAC addresses

**🧠 Memory Tip:** Remember **ARP** by linking its purpose → mechanism → result.

### How ARP Works (Slide 33)

**Exam Answer:** ARP.

**Explanation:**

- ARP
- A host needs a destination's MAC address to build an Ethernet frame, but usually only knows its IP .
- ARP Request: broadcast — “Who has 192.168.1.5? Tell 192.168.1.10.”
- ARP Reply: unicast — the owner of that IP responds with its MAC address.
- The result is cached in the sender's ARP table to avoid repeating the broadcast for every packet.

**සිංහලෙන්:** **How ARP Works** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ARP
- A host needs a destination's MAC address to build an Ethernet frame, but usually only knows its IP .
- ARP Request: broadcast — “Who has 192.168.1.5? Tell 192.168.1.10.”
- ARP Reply: unicast — the owner of that IP responds with its MAC address.

**🧠 Memory Tip:** Remember **How ARP Works** by linking its purpose → mechanism → result.

### ARP Cache — Example (Slide 34)

**Exam Answer:** ARP.

**Explanation:**

- ARP
- IP Address MAC Address Type
- 192.168.1.1 AA:BB:CC:00:11:22 Dynamic
- 192.168.1.5 AA:BB:CC:00:33:44 Dynamic

**සිංහලෙන්:** **ARP Cache — Example** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ARP
- IP Address MAC Address Type
- 192.168.1.1 AA:BB:CC:00:11:22 Dynamic
- 192.168.1.5 AA:BB:CC:00:33:44 Dynamic

**🧠 Memory Tip:** Remember **ARP Cache — Example** by linking its purpose → mechanism → result.

### ARP Protocol (Slide 35)

**Exam Answer:** ARP.

**Explanation:**

- ARP

**සිංහලෙන්:** **ARP Protocol** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ARP

**🧠 Memory Tip:** Remember **ARP Protocol** by linking its purpose → mechanism → result.

### ARP: A Security Preview (Slide 36)

**Exam Answer:** ARP.

**Explanation:**

- ARP
- ARP has no authentication — a host will accept an unsolicited ARP reply and update its cache.
- ARP spoofing / poisoning: an attacker sends forged ARP replies to associate their own MAC with a victim's IP , enabling
- man-in-the-middle attacks.
- We'll cover detection and mitigation (e.g. dynamic ARP inspection) under Layer 2 attacks in Weeks 4–5.

**සිංහලෙන්:** **ARP: A Security Preview** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ARP
- ARP has no authentication — a host will accept an unsolicited ARP reply and update its cache.
- ARP spoofing / poisoning: an attacker sends forged ARP replies to associate their own MAC with a victim's IP , enabling
- man-in-the-middle attacks.

**🧠 Memory Tip:** Remember **ARP: A Security Preview** by linking its purpose → mechanism → result.

### TCP (Slide 37)

**Exam Answer:** Reliable, connection-oriented transport.

**Explanation:**

- Reliable, connection-oriented transport

**සිංහලෙන්:** **TCP** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Reliable, connection-oriented transport

**🧠 Memory Tip:** Remember **TCP** by linking its purpose → mechanism → result.

### TCP Characteristics (Slide 38)

**Exam Answer:** TCP.

**Explanation:**

- TCP
- Connection-oriented: a session is established before data flows (three-way handshake).
- Reliable: lost segments are detected (via sequence numbers/ACKs) and retransmitted.
- Ordered: segments are reassembled in the correct order at the destination.
- Used where correctness matters more than speed: web (HTTP), email, file transfer.

**සිංහලෙන්:** **TCP Characteristics** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TCP
- Connection-oriented: a session is established before data flows (three-way handshake).
- Reliable: lost segments are detected (via sequence numbers/ACKs) and retransmitted.
- Ordered: segments are reassembled in the correct order at the destination.

**🧠 Memory Tip:** Remember **TCP Characteristics** by linking its purpose → mechanism → result.

### TCP Communication (Slide 39)

**Exam Answer:** TCP.

**Explanation:**

- TCP
- This handshake establishes sequence numbers both sides will use to track delivery.
- Security relevance: SYN flood attacks abuse this by sending many SYNs and never completing the handshake, exhausting
- server resources.

**සිංහලෙන්:** **TCP Communication** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TCP
- This handshake establishes sequence numbers both sides will use to track delivery.
- Security relevance: SYN flood attacks abuse this by sending many SYNs and never completing the handshake, exhausting
- server resources.

**🧠 Memory Tip:** Remember **TCP Communication** by linking its purpose → mechanism → result.

### TCP Header — Key Fields (Slide 40)

**Exam Answer:** TCP.

**Explanation:**

- TCP
- Field Purpose
- Source / Destination Port Identify the sending and receiving application (socket)
- Sequence / Acknowledgment Number Track byte ordering and confirm receipt
- Flags (SYN, ACK, FIN, RST) Control connection setup, teardown, and reset
- Window Size Flow control — how much data the receiver can accept

**සිංහලෙන්:** **TCP Header — Key Fields** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TCP
- Field Purpose
- Source / Destination Port Identify the sending and receiving application (socket)
- Sequence / Acknowledgment Number Track byte ordering and confirm receipt

**🧠 Memory Tip:** Remember **TCP Header — Key Fields** by linking its purpose → mechanism → result.

### Ports & Sockets (Slide 41)

**Exam Answer:** TCP.

**Explanation:**

- TCP
- A port (0–65535) identifies a specific application/service on a host.
- Well-known ports (0– 1023): HTTP=80, HTTPS=443, SSH=22, DNS=53.
- A socket = IP address + port — uniquely identifies one end of a connection.
- Firewalls commonly filter traffic by port — a preview of Week 7.

**සිංහලෙන්:** **Ports & Sockets** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TCP
- A port (0–65535) identifies a specific application/service on a host.
- Well-known ports (0– 1023): HTTP=80, HTTPS=443, SSH=22, DNS=53.
- A socket = IP address + port — uniquely identifies one end of a connection.

**🧠 Memory Tip:** Remember **Ports & Sockets** by linking its purpose → mechanism → result.

### UDP (Slide 42)

**Exam Answer:** Fast, connectionless transport.

**Explanation:**

- Fast, connectionless transport

**සිංහලෙන්:** **UDP** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Fast, connectionless transport

**🧠 Memory Tip:** Remember **UDP** by linking its purpose → mechanism → result.

### UDP Characteristics (Slide 43)

**Exam Answer:** UDP.

**Explanation:**

- UDP
- Connectionless: no handshake, no session state — just send.
- No reliability guarantees: no retransmission, no ordering, no flow control.
- Lower overhead than TCP — used where speed matters more than perfection: DNS, DHCP , VoIP , video streaming.
- That same lack of state makes UDP an easy vector for spoofing and amplification attacks.

**සිංහලෙන්:** **UDP Characteristics** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- UDP
- Connectionless: no handshake, no session state — just send.
- No reliability guarantees: no retransmission, no ordering, no flow control.
- Lower overhead than TCP — used where speed matters more than perfection: DNS, DHCP , VoIP , video streaming.

**🧠 Memory Tip:** Remember **UDP Characteristics** by linking its purpose → mechanism → result.

### UDP Header — Much Simpler (Slide 44)

**Exam Answer:** UDP.

**Explanation:**

- UDP
- Field Purpose
- Source / Destination Port Identify sending and receiving application
- Length Size of header + data
- Checksum Basic error detection (optional in IPv4)

**සිංහලෙන්:** **UDP Header — Much Simpler** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- UDP
- Field Purpose
- Source / Destination Port Identify sending and receiving application
- Length Size of header + data

**🧠 Memory Tip:** Remember **UDP Header — Much Simpler** by linking its purpose → mechanism → result.

### UDP vs TCP Header (Slide 45)

**Exam Answer:** UDP.

**Explanation:**

- UDP

**සිංහලෙන්:** **UDP vs TCP Header** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- UDP

**🧠 Memory Tip:** Remember **UDP vs TCP Header** by linking its purpose → mechanism → result.

### TCP vs UDP (Slide 46)

**Exam Answer:** UDP.

**Explanation:**

- UDP
- TCP UDP
- Connection Connection-oriented Connectionless
- Reliability Guaranteed delivery, ordered Best-effort, no guarantees
- Speed Slower (handshake, ACKs) Faster, minimal overhead
- Typical use Web, email, file transfer DNS, DHCP , VoIP , streaming

**සිංහලෙන්:** **TCP vs UDP** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- UDP
- TCP UDP
- Connection Connection-oriented Connectionless
- Reliability Guaranteed delivery, ordered Best-effort, no guarantees

**🧠 Memory Tip:** Remember **TCP vs UDP** by linking its purpose → mechanism → result.

### TCP vs UDP (Slide 47)

**Exam Answer:** UDP.

**Explanation:**

- UDP

**සිංහලෙන්:** **TCP vs UDP** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- UDP

**🧠 Memory Tip:** Remember **TCP vs UDP** by linking its purpose → mechanism → result.

### HTTP (Slide 48)

**Exam Answer:** The protocol behind the web.

**Explanation:**

- The protocol behind the web

**සිංහලෙන්:** **HTTP** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- The protocol behind the web

**🧠 Memory Tip:** Remember **HTTP** by linking its purpose → mechanism → result.

### HTTP Basics (Slide 49)

**Exam Answer:** HTTP.

**Explanation:**

- HTTP
- Request/response protocol: a client sends a request, the server sends a response.
- Common methods: GET (retrieve), POST (submit data), PUT (update), DELETE (remove).
- Runs over TCP , traditionally on port 80.
- Stateless by design — each request is independent (cookies/sessions add state on top).

**සිංහලෙන්:** **HTTP Basics** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- HTTP
- Request/response protocol: a client sends a request, the server sends a response.
- Common methods: GET (retrieve), POST (submit data), PUT (update), DELETE (remove).
- Runs over TCP , traditionally on port 80.

**🧠 Memory Tip:** Remember **HTTP Basics** by linking its purpose → mechanism → result.

### HTTP Protocol (Slide 50)

**Exam Answer:** HTTP.

**Explanation:**

- HTTP

**සිංහලෙන්:** **HTTP Protocol** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- HTTP

**🧠 Memory Tip:** Remember **HTTP Protocol** by linking its purpose → mechanism → result.

### HTTP vs HTTPS (Slide 51)

**Exam Answer:** HTTP.

**Explanation:**

- HTTP
- HTTP HTTPS
- Port 80 443
- Encryption None — plaintext TLS/SSL encrypted
- Data exposed to eavesdroppers? Yes No (in transit)

**සිංහලෙන්:** **HTTP vs HTTPS** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- HTTP
- HTTP HTTPS
- Port 80 443
- Encryption None — plaintext TLS/SSL encrypted

**🧠 Memory Tip:** Remember **HTTP vs HTTPS** by linking its purpose → mechanism → result.

### HTTP: A Security Preview (Slide 52)

**Exam Answer:** HTTP.

**Explanation:**

- HTTP
- Plaintext HTTP exposes credentials, cookies, and content to anyone who can see the traffic — relevant to Layer 3/4
- attacks like sniffing.
- HTTPS (TLS) provides confidentiality and integrity, but the certificate trust model itself can be attacked (covered
- under Digital Certificates, Week 12).
- Common headers and misconfigurations here become relevant again when we reach cryptography and PKI.

**සිංහලෙන්:** **HTTP: A Security Preview** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- HTTP
- Plaintext HTTP exposes credentials, cookies, and content to anyone who can see the traffic — relevant to Layer 3/4
- attacks like sniffing.
- HTTPS (TLS) provides confidentiality and integrity, but the certificate trust model itself can be attacked (covered

**🧠 Memory Tip:** Remember **HTTP: A Security Preview** by linking its purpose → mechanism → result.

### Summary (Slide 53)

**Exam Answer:** Layered architecture (OSI/TCP-IP) gives us a shared vocabulary for where an attack or defense operates.

**Explanation:**

- Layered architecture (OSI/TCP-IP) gives us a shared vocabulary for where an attack or defense operates.
- Switching and routing move frames/packets — and every hop is a place security policy can be enforced.
- Ethernet, IP , DHCP , and ARP move data at Layers 1–3 — mostly without built-in authentication, which is why they're
- common attack targets.
- TCP and UDP shape how attacks like SYN floods and spoofing work at Layer 4.
- HTTP/HTTPS shows why encryption matters at the application layer.

**සිංහලෙන්:** **Summary** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Layered architecture (OSI/TCP-IP) gives us a shared vocabulary for where an attack or defense operates.
- Switching and routing move frames/packets — and every hop is a place security policy can be enforced.
- Ethernet, IP , DHCP , and ARP move data at Layers 1–3 — mostly without built-in authentication, which is why they're
- common attack targets.

**🧠 Memory Tip:** Remember **Summary** by linking its purpose → mechanism → result.

### This Week's Lab (Slide 54)

**Exam Answer:** Part A — Incident case studies: analyse real, recent network security breaches and answer scenario questions about.

**Explanation:**

- Part A — Incident case studies: analyse real, recent network security breaches and answer scenario questions about
- vulnerability, impact, and mitigation.
- Part B — Job market scan: review local and international entry-level cybersecurity job ads and tally how many require
- networking/network security skills.
- See the Week 1 Lab Guide for full instructions.

**සිංහලෙන්:** **This Week's Lab** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Part A — Incident case studies: analyse real, recent network security breaches and answer scenario questions about
- vulnerability, impact, and mitigation.
- Part B — Job market scan: review local and international entry-level cybersecurity job ads and tally how many require
- networking/network security skills.

**🧠 Memory Tip:** Remember **This Week's Lab** by linking its purpose → mechanism → result.


## 📊 Important Comparisons

| Comparison/topic | Source | Exam focus |
|---|---:|---|
| OSI vs TCP/IP Model | Slide 7 | CONCEPT. |
| Static vs Dynamic Routing | Slide 15 | ROUTING. |
| Routing Protocols — Quick Overview | Slide 16 | ROUTING. |
| IPv4 vs IPv6 | Slide 24 | IP. |
| IPv4 vs IPv6 Header | Slide 25 | IP. |
| UDP vs TCP Header | Slide 45 | UDP. |
| TCP vs UDP | Slide 46 | UDP. |
| TCP vs UDP | Slide 47 | UDP. |
| HTTP vs HTTPS | Slide 51 | HTTP. |
| Summary | Slide 53 | Layered architecture (OSI/TCP-IP) gives us a shared vocabulary for where an attack or defense operates. |

## 🛠️ Practical Knowledge

### Static vs Dynamic Routing (Slide 15)

- ROUTING
- Static Routing Dynamic Routing
- Configuration Manually entered by admin Learned automatically via a routing protocol
- Best for Small, stable networks Larger networks with changing topology
- Security angle Predictable, smaller attack surface Vulnerable to route injection/spoofing if unauthenticated

### Routing Protocols — Quick Overview (Slide 16)

- ROUTING
- Protocol Type Notes
- RIP Distance-vector Simple, hop-count based, limited scalability
- OSPF Link-state Fast convergence, widely used internally
- EIGRP Advanced distance-vector Cisco-developed, fast convergence
- BGP Path-vector Routes the Internet itself, between autonomous systems

### DHCP: DORA Process (Slide 28)

- DHCP
- Discover
- Client broadcasts for a DHCP
- server
- Offer
- Server offers an available IP
- Request
- Client requests the offered IP
- Acknowledge
- Server confirms the lease

### HTTP: A Security Preview (Slide 52)

- HTTP
- Plaintext HTTP exposes credentials, cookies, and content to anyone who can see the traffic — relevant to Layer 3/4
- attacks like sniffing.
- HTTPS (TLS) provides confidentiality and integrity, but the certificate trust model itself can be attacked (covered
- under Digital Certificates, Week 12).
- Common headers and misconfigurations here become relevant again when we reach cryptography and PKI.

### This Week's Lab (Slide 54)

- Part A — Incident case studies: analyse real, recent network security breaches and answer scenario questions about
- vulnerability, impact, and mitigation.
- Part B — Job market scan: review local and international entry-level cybersecurity job ads and tally how many require
- networking/network security skills.
- See the Week 1 Lab Guide for full instructions.

## ⭐ Important Exam Points

- ⭐ **What We're Refreshing (Slide 2):** Layered architecture (OSI & TCP/IP).
- ⭐ **How This Fits the Module (Slide 3):** Underpins LO1 (describing vulnerabilities) and LO3 (analysing network/communication requirements).
- ⭐ **Layered Architecture (Slide 4):** Why we split networking into layers.
- ⭐ **Why Layered Architecture? (Slide 5):** CONCEPT.
- ⭐ **The OSI 7-Layer Model (Slide 6):** CONCEPT.
- ⭐ **OSI vs TCP/IP Model (Slide 7):** CONCEPT.
- ⭐ **Encapsulation & Decapsulation (Slide 8):** CONCEPT.
- ⭐ **Switching Revision (Slide 9):** Layer 2 forwarding fundamentals.
- ⭐ **What Switches Do (Slide 10):** SWITCHING.
- ⭐ **Domains & VLANs (Slide 11):** SWITCHING.
- ⭐ **Common Switching Issues (Slide 12):** SWITCHING.
- ⭐ **Routing Revision (Slide 13):** Layer 3 forwarding fundamentals.
- ⭐ **What Routers Do (Slide 14):** ROUTING.
- ⭐ **Static vs Dynamic Routing (Slide 15):** ROUTING.
- ⭐ **Routing Protocols — Quick Overview (Slide 16):** ROUTING.

## ❓ Possible Exam Questions

### MCQs

1. Which statement best matches **Layered Architecture**?
   - A. It is unrelated to network security.
   - B. Why we split networking into layers.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

2. Which statement best matches **What Routers Do**?
   - A. It is unrelated to network security.
   - B. ROUTING.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

3. Which statement best matches **IPv4 vs IPv6**?
   - A. It is unrelated to network security.
   - B. IP.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

4. Which statement best matches **ARP Cache — Example**?
   - A. It is unrelated to network security.
   - B. ARP.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

5. Which statement best matches **UDP Header — Much Simpler**?
   - A. It is unrelated to network security.
   - B. UDP.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**


### Short Structured Questions

1. **Explain Layered Architecture.**
   - **Model answer:** Why we split networking into layers.

2. **Explain What Routers Do.**
   - **Model answer:** ROUTING.

3. **Explain IPv4 vs IPv6.**
   - **Model answer:** IP.

4. **Explain ARP Cache — Example.**
   - **Model answer:** ARP.

5. **Explain UDP Header — Much Simpler.**
   - **Model answer:** UDP.


### Scenario-Based Question

**Scenario:** An organization must apply the concepts from **Networking Revision** to improve its network security. Identify the relevant mechanism or risk, explain the likely impact, and recommend a layered response.

**Model-answer approach:** Identify the asset and trust boundary; name the relevant protocol/control; explain the mechanism using the lecture terminology; state confidentiality, integrity, or availability impact; then recommend the matching prevention, detection, and verification steps from the slides.

## ⚡ Last-Minute Quick Revision

- **What We're Refreshing:** Layered architecture (OSI & TCP/IP).
- **How This Fits the Module:** Underpins LO1 (describing vulnerabilities) and LO3 (analysing network/communication requirements).
- **Layered Architecture:** Why we split networking into layers.
- **Why Layered Architecture?:** CONCEPT.
- **The OSI 7-Layer Model:** CONCEPT.
- **OSI vs TCP/IP Model:** CONCEPT.
- **Encapsulation & Decapsulation:** CONCEPT.
- **Switching Revision:** Layer 2 forwarding fundamentals.
- **What Switches Do:** SWITCHING.
- **Domains & VLANs:** SWITCHING.
- **Common Switching Issues:** SWITCHING.
- **Routing Revision:** Layer 3 forwarding fundamentals.
- **What Routers Do:** ROUTING.
- **Static vs Dynamic Routing:** ROUTING.
- **Routing Protocols — Quick Overview:** ROUTING.
- **Ethernet:** The dominant Layer 2 / Layer 1 technology.
- **The Ethernet Frame:** ETHERNET.
- **MAC Addressing:** ETHERNET.
- **Ethernet Standards & Speeds:** ETHERNET.
- **IP:** Logical addressing and routing at Layer 3.

## Verification Notes

- Slide coverage: **55 of 55 slides processed**.
- Slide numbers refer to PDF page order.
- Any application example or scenario above extends the slide concept for revision and is not presented as a verbatim lecturer statement.
