# IE3122 – Network Security
## Week 01 | Networking Revision — Quick Exam Notes 🔐

> **Source:** Week 1 lecture slides (55 pages). Focus: layers, switching, routing, Ethernet/IP, DHCP, ARP, TCP/UDP, HTTP/HTTPS.

## 1. Layered Architecture ⭐
**Exam answer:** Layered architecture divides network communication into manageable layers, each with a specific responsibility. It supports interoperability, troubleshooting, and layer-specific security.

**සිංහලෙන්:** Network එකේ data යවන වැඩේ layers වලට වෙන් කරනවා. Attack එකක් වෙන්නේ කුමන layer එකේද කියලා තේරුම් ගන්න ලේසි.

| OSI Layer | Responsibility / Examples |
|---|---|
| 7 Application | HTTP, DNS, SMTP |
| 6 Presentation | Encoding, encryption |
| 5 Session | Session management |
| 4 Transport | TCP, UDP |
| 3 Network | IP addressing, routing |
| 2 Data Link | Ethernet, MAC, ARP |
| 1 Physical | Cables, signals |

**TCP/IP model (4 layers):** Application (OSI 5–7) → Transport (4) → Internet (3) → Network Access (1–2).

**Encapsulation:** Sender adds headers while moving *down* the layers: `Data → Segment (TCP/UDP) → Packet (IP) → Frame (Ethernet)`. **Decapsulation:** Receiver removes them moving *up*.

## 2. Switching & VLANs ⭐
**Exam answer:** A switch operates at OSI Layer 2 and forwards Ethernet frames using destination MAC addresses.

- Learns **source MAC → switch port** in its MAC/CAM table.
- Known destination MAC → forward to corresponding port.
- Unknown destination MAC → flood to all ports except incoming port.
- **Collision domain:** each switch port is a separate collision domain.
- **Broadcast domain:** one by default; **VLANs** split it into multiple logical broadcast domains.
- **Switching loop** → broadcast storm; **STP** helps prevent loops.
- **CAM table overflow** → fake MAC addresses fill table, potentially causing excessive flooding.

**සිංහලෙන්:** Switch එක MAC address බලලා frame forward කරනවා. VLAN දාලා එකම switch එකේ networks වෙන් කරගන්න පුළුවන්.

## 3. Routing ⭐
**Exam answer:** A router operates at Layer 3 and forwards packets between networks based on destination IP addresses and routing tables.

- **Routing table:** destination network → next hop/interface.
- **Default gateway:** local network එකෙන් පිටතට traffic යවන්න host එක භාවිතා කරන router.
- **Static routing:** manually configured; good for small/stable networks.
- **Dynamic routing:** routes learned using protocols; can be vulnerable to forged routing updates if unauthenticated.

| Protocol | Type | Remember |
|---|---|---|
| RIP | Distance-vector | Hop count |
| OSPF | Link-state | Fast convergence, internal networks |
| EIGRP | Advanced distance-vector | Cisco-developed |
| BGP | Path-vector | Routing between autonomous systems |

**Memory:** **Switch = MAC = L2; Router = IP = L3.**

## 4. Ethernet & MAC Addressing
- **Ethernet frame:** `Preamble | Destination MAC | Source MAC | Type | Payload | FCS`.
- **MAC:** 48 bits (6 bytes), e.g. `00:1A:2B:3C:4D:5E`; first 3 bytes identify manufacturer (OUI), in the traditional format.
- **FCS:** CRC-based accidental error detection; **not** protection from malicious tampering.
- **MAC spoofing:** software can change the presented MAC address.

| Standard | Speed |
|---|---|
| 10BASE-T | 10 Mbps |
| 100BASE-TX | 100 Mbps |
| 1000BASE-T | 1 Gbps |
| 10GBASE-T | 10 Gbps |

## 5. IP Addressing & Subnetting ⭐
**IPv4:** 32-bit logical address, e.g. `192.168.1.10`. Subnet mask separates **network** and **host** portions. Modern addressing uses **CIDR**, e.g. `/24`.

**Private IPv4 ranges:**
- `10.0.0.0/8`
- `172.16.0.0/12`
- `192.168.0.0/16`

| CIDR | Mask | Usable hosts (conventional subnet) |
|---|---|---|
| /24 | 255.255.255.0 | 254 |
| /25 | 255.255.255.128 | 126 |
| /26 | 255.255.255.192 | 62 |
| /30 | 255.255.255.252 | 2 |

**Formula:** usable IPv4 hosts = `2^(32 – prefix) – 2` for these conventional subnets.

**IPv6:** 128-bit address (e.g. `2001:db8::1`) vs IPv4's 32 bits. IPv6 supports IPsec in its standards, but **is not automatically encrypted**.

**IPv4 header fields:**
- **TTL:** limits hops, prevents infinite routing loops.
- **Protocol:** TCP=`6`, UDP=`17`, ICMP=`1`.
- **Source/Destination IP:** logical endpoints used for routing.
- **Fragmentation flags/offset:** support splitting/reassembling IPv4 packets; possible attack surface.

## 6. DHCP — Dynamic Host Configuration Protocol ⭐
**Exam answer:** DHCP automatically assigns IP configuration to network clients, including IP address, default gateway, and DNS server settings.

**DORA process:** `Discover → Offer → Request → Acknowledge`
1. **Discover:** Client broadcasts looking for a server.
2. **Offer:** Server offers an IP address.
3. **Request:** Client requests that address.
4. **Acknowledge:** Server confirms a time-limited lease.

- **UDP ports:** `67` server, `68` client.
- **Risk:** rogue DHCP server can provide malicious DNS or default gateway.
- **Defense:** **DHCP Snooping** on switches.

**සිංහලෙන්:** DHCP එකෙන් IP එක manually දාන්නේ නැතුව automatically ලැබෙනවා. Rogue DHCP server එකකින් වැරදි gateway/DNS දිය හැක.

## 7. ARP — Address Resolution Protocol ⭐
**Exam answer:** ARP resolves an IPv4 address to a MAC address on the local network.

1. **ARP Request:** Broadcast — “Who has `192.168.1.5`?”
2. **ARP Reply:** Owner responds with its MAC address (normally unicast).
3. Result is stored in the **ARP cache**.

- **Risk:** ARP lacks authentication → forged ARP replies may poison caches → **Man-in-the-Middle (MITM)**.
- **Defense:** **Dynamic ARP Inspection (DAI)**.

**Remember:** `ARP = IP → MAC`; `DHCP = get IP configuration`.

## 8. TCP — Transmission Control Protocol ⭐
**Exam answer:** TCP is a connection-oriented transport protocol that provides reliable, ordered data delivery with acknowledgments and retransmissions.

**Three-way handshake:** `SYN → SYN-ACK → ACK`.

| TCP header field | Purpose |
|---|---|
| Source/Destination port | Identify applications/services |
| Sequence number | Track transmitted bytes |
| Acknowledgment number | Confirm received data |
| SYN, ACK, FIN, RST | Connection control |
| Window size | Flow control |

- TCP header: normally **20 bytes minimum**, up to 60 with options.
- **SYN flood:** many unfinished handshakes can exhaust server resources.
- **Socket endpoint:** IP address + port.

## 9. UDP — User Datagram Protocol ⭐
**Exam answer:** UDP is a connectionless transport protocol with low overhead but no built-in delivery, ordering, or retransmission guarantees.

- No three-way handshake.
- Header **8 bytes**: source port, destination port, length, checksum.
- Examples in slides: DNS, DHCP, VoIP, video streaming.
- **Security risk:** spoofing and amplification attacks.

| Feature | TCP | UDP |
|---|---|---|
| Connection | Connection-oriented | Connectionless |
| Delivery | Reliable, ordered | Best effort |
| Handshake | Yes | No |
| Minimum header | 20 bytes | 8 bytes |
| Typical use | Web, email, file transfer | DNS, DHCP, VoIP |

**Memory:** `TCP = Reliability`; `UDP = Low overhead` (not inherently secure/insecure).

## 10. HTTP vs HTTPS ⭐
**Exam answer:** HTTP is a stateless request-response application protocol. HTTPS protects HTTP traffic with TLS encryption and integrity protection.

**Methods:**
- **GET:** retrieve a resource.
- **POST:** submit data.
- **PUT:** update/replace a resource.
- **DELETE:** remove a resource.

| Feature | HTTP | HTTPS |
|---|---|---|
| Default port | 80 | 443 |
| Encryption | No | TLS |
| Traffic contents | Plaintext | Protected in transit |

- HTTP requests are stateless; cookies/sessions add application-level state.
- **Risk:** HTTP may expose credentials, cookies and content to network eavesdroppers.
- HTTPS helps protect confidentiality and integrity, but correct certificate validation remains important.

## 11. Quick Security Connections 🔐
| Target/protocol | Vulnerability/attack | Defense from lecture |
|---|---|---|
| Switching | Loop/broadcast storm | STP |
| Switching MAC table | CAM overflow | Covered in later Layer 2 security lectures |
| DHCP | Rogue DHCP server | DHCP Snooping |
| ARP | ARP poisoning / MITM | Dynamic ARP Inspection |
| TCP | SYN flood | Exam focus: incomplete handshake exhaustion |
| UDP | Spoofing/amplification | Exam focus: connectionless protocol risk |
| HTTP | Traffic sniffing / plaintext exposure | HTTPS/TLS |

## ⚡ 60-Second Final Revision
- **OSI:** 7 layers; **TCP/IP:** 4 layers.
- **L2 switch:** MAC, frames; **L3 router:** IP, packets.
- **VLAN:** broadcast domain segmentation; **STP:** loop prevention.
- **IPv4:** 32-bit; **IPv6:** 128-bit.
- **DHCP:** DORA, UDP 67/68; **ARP:** IP → MAC.
- **TCP:** SYN → SYN-ACK → ACK; ordered/reliable.
- **UDP:** connectionless, lightweight, 8-byte header.
- **HTTP 80:** plaintext; **HTTPS 443:** TLS.
- **Attack connections:** CAM overflow, rogue DHCP, ARP poisoning, SYN flood, UDP amplification, HTTP sniffing.

---
**Lecture coverage:** IE3122 Week 01, slides 1–55. The slide deck also previews Week 1 Lab Part A (incident case studies) and Part B (cybersecurity job-market scan); consult its separate Lab Guide for full lab instructions.
