# Lecture 10 – VPN Technologies

## 📌 Lecture Overview

This lecture covers **VPN Technologies** as presented in the supplied IE3122 slides. The notes follow the source order across 31 slides and retain the lecture's terminology, mechanisms, examples, and configuration details. They are organized for rapid MCQ, structured-answer, and scenario revision.

> **Source boundary:** Content below is derived from `IE3122_Week9_VPNTechnologies_Slides.pdf`. Generic exam prompts/examples are labelled as application material; no unsupported lecturer emphasis is claimed.

## 🎯 Learning Objectives

- LO3
- Analyse security requirements and recommend appropriate technologies.
- LO4
- Evaluate different security technologies, compare them, and identify appropriate use cases.
- LO5
- Configure security technologies to satisfy specific requirements.

## 📚 Main Topics and Subtopics

### IPsec VPN (Slide 4)

**Exam Answer:** Securing the network layer itself.

**Explanation:**

- Securing the network layer itself

**සිංහලෙන්:** **IPsec VPN** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Securing the network layer itself

**🧠 Memory Tip:** Remember **IPsec VPN** by linking its purpose → mechanism → result.

### IPsec: Overview (Slide 5)

**Exam Answer:** IPSEC.

**Explanation:**

- IPSEC
- IPsec (Internet Protocol Security) operates at the network layer, securing IP packets themselves, regardless of which
- application generated them.
- It is not one fixed protocol but a modular framework: it deliberately does not mandate which specific algorithm you use for
- any given job, only which job needs doing.
- Because it protects at the IP layer, IPsec secures everything above it automatically. No individual application needs to be
- aware it's even running.

**සිංහලෙන්:** **IPsec: Overview** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IPSEC
- IPsec (Internet Protocol Security) operates at the network layer, securing IP packets themselves, regardless of which
- application generated them.
- It is not one fixed protocol but a modular framework: it deliberately does not mandate which specific algorithm you use for

**🧠 Memory Tip:** Remember **IPsec: Overview** by linking its purpose → mechanism → result.

### IPsec as a Modular Framework (Slide 6)

**Exam Answer:** IPSEC.

**Explanation:**

- IPSEC
- IPsec defines five separate functions, each with a menu of interchangeable choices rather than one mandatory answer. The firs t row matters most: AH
- authenticates only, with no encryption; ESP adds real confidentiality, which is why ESP or ESP+AH is used far more often.
- An actual configuration picks exactly one choice per row. The two examples on the right are both valid, built from that same menu.

**සිංහලෙන්:** **IPsec as a Modular Framework** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IPSEC
- IPsec defines five separate functions, each with a menu of interchangeable choices rather than one mandatory answer. The firs t row matters most: AH
- authenticates only, with no encryption; ESP adds real confidentiality, which is why ESP or ESP+AH is used far more often.
- An actual configuration picks exactly one choice per row. The two examples on the right are both valid, built from that same menu.

**🧠 Memory Tip:** Remember **IPsec as a Modular Framework** by linking its purpose → mechanism → result.

### Choosing Confidentiality and Integrity Algorithms (Slide 7)

**Exam Answer:** IPSEC.

**Explanation:**

- IPSEC
- Confidentiality and integrity are two separate rows in the same framework, each with its own menu, and each option carries a genuinely
- different security strength.

**සිංහලෙන්:** **Choosing Confidentiality and Integrity Algorithms** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IPSEC
- Confidentiality and integrity are two separate rows in the same framework, each with its own menu, and each option carries a genuinely
- different security strength.

**🧠 Memory Tip:** Remember **Choosing Confidentiality and Integrity Algorithms** by linking its purpose → mechanism → result.

### Peer Authentication Methods (Slide 8)

**Exam Answer:** IPSEC.

**Explanation:**

- IPSEC
- The Authentication row offers two choices: PSK (pre-shared key, the same secret configured manually on both peers) or RSA (certificate-based,
- using public-key cryptography instead).
- Either way, the mechanism is the same shape: each peer hashes its own authentication key together with its identity, and the two sides
- compare hashes to confirm they agree, without ever sending the key itself across the network.

**සිංහලෙන්:** **Peer Authentication Methods** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IPSEC
- The Authentication row offers two choices: PSK (pre-shared key, the same secret configured manually on both peers) or RSA (certificate-based,
- using public-key cryptography instead).
- Either way, the mechanism is the same shape: each peer hashes its own authentication key together with its identity, and the two sides

**🧠 Memory Tip:** Remember **Peer Authentication Methods** by linking its purpose → mechanism → result.

### Diffie-Hellman Group Choices (Slide 9)

**Exam Answer:** IPSEC.

**Explanation:**

- IPSEC
- The Diffie-Hellman row picks which mathematical group the key exchange itself uses. Higher-numbered groups generally mean larger, stronger
- keys.
- This is a genuinely live consideration, not just historical: DH14 is the realistic minimum for production networks today, butolder or simulated
- equipment doesn't always support it.

**සිංහලෙන්:** **Diffie-Hellman Group Choices** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IPSEC
- The Diffie-Hellman row picks which mathematical group the key exchange itself uses. Higher-numbered groups generally mean larger, stronger
- keys.
- This is a genuinely live consideration, not just historical: DH14 is the realistic minimum for production networks today, butolder or simulated

**🧠 Memory Tip:** Remember **Diffie-Hellman Group Choices** by linking its purpose → mechanism → result.

### IPsec: IKE's Two Phases (Slide 10)

**Exam Answer:** IPSEC.

**Explanation:**

- IPSEC
- IKE Phase 1 establishes a secure, authenticated channel between the two peers themselves, called the ISAKMP SA. This is the
- peers proving who they are to each other and agreeing on how to protect their own negotiation traffic.
- IKE Phase 2 then uses that secure channel to negotiate the actual IPsec Security Associations that will protect real data
- traffic, the specific encryption and authentication parameters applied to the traffic itself.
- Splitting negotiation into two phases means the peers only need to re-authenticate each other occasionally, in Phase 1, while
- Phase 2 can refresh the data-protection keys far more frequently without repeating full peer authentication every time.

**සිංහලෙන්:** **IPsec: IKE's Two Phases** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IPSEC
- IKE Phase 1 establishes a secure, authenticated channel between the two peers themselves, called the ISAKMP SA. This is the
- peers proving who they are to each other and agreeing on how to protect their own negotiation traffic.
- IKE Phase 2 then uses that secure channel to negotiate the actual IPsec Security Associations that will protect real data

**🧠 Memory Tip:** Remember **IPsec: IKE's Two Phases** by linking its purpose → mechanism → result.

### IPsec: Transport Mode vs Tunnel Mode (Slide 11)

**Exam Answer:** IPSEC.

**Explanation:**

- IPSEC
- Transport mode encrypts only the payload of the original IP packet, leaving the original IP header intact. This is typically used
- for direct host-to-host protection, where both ends are the actual communicating parties.
- Tunnel mode encrypts the entire original IP packet, including its header, and wraps it inside a new IP packet with new
- addressing. This is what site-to-site VPNs use, since it hides the original internal addressing entirely from the public network
- in between.
- The choice of mode is independent of whether you're using AH or ESP; either component can run in either mode, though ESP
- in tunnel mode is by far the most common real-world combination.

**සිංහලෙන්:** **IPsec: Transport Mode vs Tunnel Mode** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IPSEC
- Transport mode encrypts only the payload of the original IP packet, leaving the original IP header intact. This is typically used
- for direct host-to-host protection, where both ends are the actual communicating parties.
- Tunnel mode encrypts the entire original IP packet, including its header, and wraps it inside a new IP packet with new

**🧠 Memory Tip:** Remember **IPsec: Transport Mode vs Tunnel Mode** by linking its purpose → mechanism → result.

### IPsec: Strengths and Limitations (Slide 12)

**Exam Answer:** IPSEC.

**Explanation:**

- IPSEC
- Strengths: operates at the network layer, so it's completely application-transparent, protecting all IP traffic without needing
- any individual application to support it. It's a strong, mature, widely interoperable standard with robust authentication
- options.
- Limitations: configuration genuinely is complex, involving several distinct components, an ISAKMP policy, a transform set, and
- traffic-matching rules, that all have to agree correctly. AH in particular struggles to cross NAT devices, since NAT modifies the
- very IP header AH is protecting, breaking its integrity check; ESP needs a NAT Traversal extension to reliably cross NAT too.
- It's also generally less naturally suited to simple browser-based remote access than SSL VPN.

**සිංහලෙන්:** **IPsec: Strengths and Limitations** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IPSEC
- Strengths: operates at the network layer, so it's completely application-transparent, protecting all IP traffic without needing
- any individual application to support it. It's a strong, mature, widely interoperable standard with robust authentication
- options.

**🧠 Memory Tip:** Remember **IPsec: Strengths and Limitations** by linking its purpose → mechanism → result.

### SSL VPN (Slide 13)

**Exam Answer:** Built from interchangeable cryptographic building blocks.

**Explanation:**

- Built from interchangeable cryptographic building blocks

**සිංහලෙන්:** **SSL VPN** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Built from interchangeable cryptographic building blocks

**🧠 Memory Tip:** Remember **SSL VPN** by linking its purpose → mechanism → result.

### SSL VPN: Overview (Slide 14)

**Exam Answer:** SSL VPN.

**Explanation:**

- SSL VPN
- SSL VPN uses the same TLS/SSL protocol that secures ordinary HTTPS web traffic, rather than a dedicated network-layer
- protocol suite like IPsec.
- Because it rides on the same protocol as HTTPS, it often needs nothing more than a standard web browser, or at most a
- lightweight client, rather than dedicated VPN client software.
- It also tends to traverse firewalls and NAT more easily than IPsec in practice, simply because almost every corporate firewall
- already permits outbound HTTPS on port 443, so SSL VPN traffic blends straight into traffic that was already allowed.

**සිංහලෙන්:** **SSL VPN: Overview** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SSL VPN
- SSL VPN uses the same TLS/SSL protocol that secures ordinary HTTPS web traffic, rather than a dedicated network-layer
- protocol suite like IPsec.
- Because it rides on the same protocol as HTTPS, it often needs nothing more than a standard web browser, or at most a

**🧠 Memory Tip:** Remember **SSL VPN: Overview** by linking its purpose → mechanism → result.

### SSL VPN Has Interchangeable Building Blocks Too (Slide 15)

**Exam Answer:** SSL VPN.

**Explanation:**

- SSL VPN
- IPsec is the technology most commonly held up as the modular one, precisely because of the explicit, named framework you
- just saw. SSL/TLS is built the same underlying way, just negotiated differently: as a single named cipher suite chosen from a
- list, rather than assembled row by row.
- SSL/TLS is not one fixed algorithm. It's built from several independent functional building blocks, and the two peers negotiate
- which specific option fills each block at the start of every session.
- This matters directly for security: an SSL VPN configured to allow older, weaker options in any one of these blocks can be
- seriously weakened, even if every other block is configured well.
- The next slide breaks down exactly which functional block does what, and which real protocols and algorithms have
- historically filled each one.

**සිංහලෙන්:** **SSL VPN Has Interchangeable Building Blocks Too** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SSL VPN
- IPsec is the technology most commonly held up as the modular one, precisely because of the explicit, named framework you
- just saw. SSL/TLS is built the same underlying way, just negotiated differently: as a single named cipher suite chosen from a
- list, rather than assembled row by row.

**🧠 Memory Tip:** Remember **SSL VPN Has Interchangeable Building Blocks Too** by linking its purpose → mechanism → result.

### SSL VPN's Functional Blocks, Visually (Slide 16)

**Exam Answer:** SSL VPN.

**Explanation:**

- SSL VPN
- The same idea as IPsec's framework, laid out the same way: one row per function, each with a menu of choices. Greyed-out
- options are deprecated and should never be selected today.
- Protocol
- Version SSLv3 TLS 1.0 TLS 1.1 TLS 1.2 TLS 1.3
- Key
- Exchange RSA DHE ECDHE
- Bulk
- Encryption DES RC4 3DES AES-CBC AES-GCM ChaCha20
- Integrity
- / MAC MD5 SHA-1 SHA-256 in AEAD
- Identity
- / PKI X.509 Cert

**සිංහලෙන්:** **SSL VPN's Functional Blocks, Visually** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SSL VPN
- The same idea as IPsec's framework, laid out the same way: one row per function, each with a menu of choices. Greyed-out
- options are deprecated and should never be selected today.
- Protocol

**🧠 Memory Tip:** Remember **SSL VPN's Functional Blocks, Visually** by linking its purpose → mechanism → result.

### Building Two Example Cipher Suites (Slide 17)

**Exam Answer:** SSL VPN.

**Explanation:**

- SSL VPN
- Pick one option from each row and you get a real, nameable cipher suite. These two are both valid TLS configurations, but
- they are not remotely equivalent in strength.
- Weaker (avoid) Stronger (prefer)
- Protocol Version TLS 1.2 TLS 1.3
- Key Exchange RSA ECDHE
- Bulk Encryption AES-CBC AES-GCM
- Integrity / MAC SHA-1 built into cipher

**සිංහලෙන්:** **Building Two Example Cipher Suites** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SSL VPN
- Pick one option from each row and you get a real, nameable cipher suite. These two are both valid TLS configurations, but
- they are not remotely equivalent in strength.
- Weaker (avoid) Stronger (prefer)

**🧠 Memory Tip:** Remember **Building Two Example Cipher Suites** by linking its purpose → mechanism → result.

### SSL VPN's Building Blocks, Function by Function (Slide 18)

**Exam Answer:** SSL VPN.

**Explanation:**

- SSL VPN
- Function What it does Protocols/algorithms that can fill it
- Protocol version Which version of TLS governs the whole session SSLv3, TLS 1.0, TLS 1.1 (all deprecated); TLS 1.2 (widely used); TLS 1.3 (current)
- Key exchange How the two sides agree on a shared secret RSA (no forward secrecy); DHE; ECDHE (modern, provides forward secrecy)
- Bulk encryption The cipher actually protecting the data DES, RC4 (both insecure); 3DES (deprecated); AES-CBC; AES-GCM; ChaCha20
- Integrity/MAC Detecting if data was tampered with MD5, SHA-1 (both deprecated); SHA-256/384; built into AEAD ciphers like AES-GCM
- Identity/PKI Verifying the server's, and optionally the client's, identity X.509 certificates, validated through a Certificate Authority chain

**සිංහලෙන්:** **SSL VPN's Building Blocks, Function by Function** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SSL VPN
- Function What it does Protocols/algorithms that can fill it
- Protocol version Which version of TLS governs the whole session SSLv3, TLS 1.0, TLS 1.1 (all deprecated); TLS 1.2 (widely used); TLS 1.3 (current)
- Key exchange How the two sides agree on a shared secret RSA (no forward secrecy); DHE; ECDHE (modern, provides forward secrecy)

**🧠 Memory Tip:** Remember **SSL VPN's Building Blocks, Function by Function** by linking its purpose → mechanism → result.

### SSL VPN: Client Access Modes (Slide 19)

**Exam Answer:** SSL VPN.

**Explanation:**

- SSL VPN
- The cryptography isn't the only modular part of SSL VPN. How a client actually connects is also independently selectable.
- Clientless (portal) mode: an ordinary web browser only, reaching a limited set of internal web applications through a secure
- portal.
- A third mode, thin client (port-forwarding), sits between the two shown below: a small browser applet extends access to
- specific TCP applications without a full install.
- Full tunnel client mode: a complete agent, such as Cisco AnyConnect, providing full network-layer access, using TLS as the
- underlying transport.
- Figure 7-4, SSL VPN Options: the clientless browser path (A) and the AnyConnect full-tunnel path (B), both terminating at the same ASA.

**සිංහලෙන්:** **SSL VPN: Client Access Modes** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SSL VPN
- The cryptography isn't the only modular part of SSL VPN. How a client actually connects is also independently selectable.
- Clientless (portal) mode: an ordinary web browser only, reaching a limited set of internal web applications through a secure
- portal.

**🧠 Memory Tip:** Remember **SSL VPN: Client Access Modes** by linking its purpose → mechanism → result.

### IPsec vs SSL VPN (Slide 20)

**Exam Answer:** Two different answers to the same underlying problem.

**Explanation:**

- Two different answers to the same underlying problem

**සිංහලෙන්:** **IPsec vs SSL VPN** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Two different answers to the same underlying problem

**🧠 Memory Tip:** Remember **IPsec vs SSL VPN** by linking its purpose → mechanism → result.

### IPsec vs SSL VPN: Direct Comparison (Slide 21)

**Exam Answer:** COMPARISON.

**Explanation:**

- COMPARISON
- Aspect IPsec VPN SSL VPN
- Layer of operation Network layer (Layer 3) Built on TLS, above the transport layer
- Client requirement Often needs dedicated client software Often just a browser, in clientless mode
- Traffic scope Secures all IP traffic transparently Typically specific applications or resources, though full-tunnel mode approaches IPsec's scope
- NAT traversal Can struggle, especially AH; needs NAT-T Generally NAT-friendly, uses standard HTTPS
- Access granularity Network-level, largely all-or-nothing per tunnel Can be very granular, down to specific applications or URLs
- Typical use case Site-to-site links, full-network remote access Individual remote access, especially browser-based

**සිංහලෙන්:** **IPsec vs SSL VPN: Direct Comparison** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- COMPARISON
- Aspect IPsec VPN SSL VPN
- Layer of operation Network layer (Layer 3) Built on TLS, above the transport layer
- Client requirement Often needs dedicated client software Often just a browser, in clientless mode

**🧠 Memory Tip:** Remember **IPsec vs SSL VPN: Direct Comparison** by linking its purpose → mechanism → result.

### Configuring VPNs and Tunnels on Cisco (Slide 22)

**Exam Answer:** Devices.

**Explanation:**

- Devices
- Concept alongside the actual command templates

**සිංහලෙන්:** **Configuring VPNs and Tunnels on Cisco** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Devices
- Concept alongside the actual command templates

**🧠 Memory Tip:** Remember **Configuring VPNs and Tunnels on Cisco** by linking its purpose → mechanism → result.

### GRE Tunnel: Concept (Slide 23)

**Exam Answer:** CONFIGURATION.

**Explanation:**

- CONFIGURATION
- A GRE tunnel is configured as a logical Tunnel interface, entirely separate from any physical interface, with its own IP
- addressing for the virtual point-to-point link it creates.
- It needs a source, the local physical interface or address traffic will actually leave from, and a destination, the remote peer's
- real, public address.
- Remember from earlier: this alone provides no encryption whatsoever. GRE just gets traffic there, in the clear.
- interface Tunnel0
- ip address 10.10.10.1 255.255.255.252
- tunnel source GigabitEthernet0/0
- tunnel destination 203.0.113.10

**සිංහලෙන්:** **GRE Tunnel: Concept** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION
- A GRE tunnel is configured as a logical Tunnel interface, entirely separate from any physical interface, with its own IP
- addressing for the virtual point-to-point link it creates.
- It needs a source, the local physical interface or address traffic will actually leave from, and a destination, the remote peer's

**🧠 Memory Tip:** Remember **GRE Tunnel: Concept** by linking its purpose → mechanism → result.

### IPsec Site-to-Site: Step 1, the IKE Phase 1 Policy (Slide 24)

**Exam Answer:** CONFIGURATION.

**Explanation:**

- CONFIGURATION
- The first step defines how the two peers will authenticate each other and protect their own negotiation traffic, the ISAKMP
- policy from Phase 1 earlier in this deck.
- crypto isakmp policy 10
- encryption aes
- hash sha256
- authentication pre-share
- group 14
- lifetime 86400
- exit
- crypto isakmp key MySharedKey address 203.0.113.10

**සිංහලෙන්:** **IPsec Site-to-Site: Step 1, the IKE Phase 1 Policy** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION
- The first step defines how the two peers will authenticate each other and protect their own negotiation traffic, the ISAKMP
- policy from Phase 1 earlier in this deck.
- crypto isakmp policy 10

**🧠 Memory Tip:** Remember **IPsec Site-to-Site: Step 1, the IKE Phase 1 Policy** by linking its purpose → mechanism → result.

### IPsec Site-to-Site: Step 2, the Transform Set (Slide 25)

**Exam Answer:** CONFIGURATION.

**Explanation:**

- CONFIGURATION
- The transform set defines the Phase 2 parameters, the actual encryption and authentication that will protect real data traffic once
- negotiation is complete.
- crypto ipsec transform-set MYSET esp-aes esp-sha256-hmac

**සිංහලෙන්:** **IPsec Site-to-Site: Step 2, the Transform Set** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION
- The transform set defines the Phase 2 parameters, the actual encryption and authentication that will protect real data traffic once
- negotiation is complete.
- crypto ipsec transform-set MYSET esp-aes esp-sha256-hmac

**🧠 Memory Tip:** Remember **IPsec Site-to-Site: Step 2, the Transform Set** by linking its purpose → mechanism → result.

### IPsec Site-to-Site: Step 3, Defining Interesting Traffic (Slide 26)

**Exam Answer:** CONFIGURATION.

**Explanation:**

- CONFIGURATION
- An ACL identifies exactly which traffic should actually be sent through the VPN, commonly called interesting traffic. Only
- traffic matching this ACL gets encrypted; everything else follows normal routing.
- access-list 100 permit ip 192.168.10.0 0.0.0.255 192.168.20.0 0.0.0.255

**සිංහලෙන්:** **IPsec Site-to-Site: Step 3, Defining Interesting Traffic** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION
- An ACL identifies exactly which traffic should actually be sent through the VPN, commonly called interesting traffic. Only
- traffic matching this ACL gets encrypted; everything else follows normal routing.
- access-list 100 permit ip 192.168.10.0 0.0.0.255 192.168.20.0 0.0.0.255

**🧠 Memory Tip:** Remember **IPsec Site-to-Site: Step 3, Defining Interesting Traffic** by linking its purpose → mechanism → result.

### IPsec Site-to-Site: Step 4, the Crypto Map (Slide 27)

**Exam Answer:** CONFIGURATION.

**Explanation:**

- CONFIGURATION
- The crypto map ties everything together: which peer to protect traffic toward, which transform set to use, and which ACL
- defines interesting traffic, then applies the whole thing to the outbound interface.
- crypto map MYMAP 10 ipsec-isakmp
- set peer 203.0.113.10
- set transform-set MYSET
- match address 100
- exit
- interface GigabitEthernet0/0
- crypto map MYMAP

**සිංහලෙන්:** **IPsec Site-to-Site: Step 4, the Crypto Map** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION
- The crypto map ties everything together: which peer to protect traffic toward, which transform set to use, and which ACL
- defines interesting traffic, then applies the whole thing to the outbound interface.
- crypto map MYMAP 10 ipsec-isakmp

**🧠 Memory Tip:** Remember **IPsec Site-to-Site: Step 4, the Crypto Map** by linking its purpose → mechanism → result.

### GRE Over IPsec: Bringing Both Together (Slide 28)

**Exam Answer:** CONFIGURATION.

**Explanation:**

- CONFIGURATION
- Configure the GRE tunnel exactly as shown earlier, giving you a working but unencrypted logical link.
- Then configure IPsec exactly as in the previous four steps, with one key difference: the interesting-traffic ACL should match
- GRE traffic itself, protocol 47, between the tunnel endpoints, rather than the traffic riding inside the tunnel.
- The result carries the best of both: GRE's flexibility, including support for dynamic routing protocols and non-IP traffic across
- the tunnel, protected by IPsec's actual encryption. This is a genuinely common real-world design, not just a teaching exercise.

**සිංහලෙන්:** **GRE Over IPsec: Bringing Both Together** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION
- Configure the GRE tunnel exactly as shown earlier, giving you a working but unencrypted logical link.
- Then configure IPsec exactly as in the previous four steps, with one key difference: the interesting-traffic ACL should match
- GRE traffic itself, protocol 47, between the tunnel endpoints, rather than the traffic riding inside the tunnel.

**🧠 Memory Tip:** Remember **GRE Over IPsec: Bringing Both Together** by linking its purpose → mechanism → result.

### Summary (Slide 29)

**Exam Answer:** IPsec secures the network layer itself using a suite of cooperating protocols, AH for integrity alone, ESP for encryption, and.

**Explanation:**

- IPsec secures the network layer itself using a suite of cooperating protocols, AH for integrity alone, ESP for encryption, and
- IKE to negotiate it all in two phases.
- SSL VPN rides on the same TLS that secures HTTPS, and is genuinely modular: the protocol version, key exchange, bulk cipher,
- and integrity check are all independently negotiated, and the client access mode is a separate choice again.
- Neither is simply better than the other. IPsec suits full-network, always-on connections; SSL VPN suits individual, often
- browser-based remote access.
- GRE, IPsec, and GRE over IPsec each solve a different problem, plain transport, plain security, or both together, and the
- configuration for each builds directly on the last.

**සිංහලෙන්:** **Summary** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IPsec secures the network layer itself using a suite of cooperating protocols, AH for integrity alone, ESP for encryption, and
- IKE to negotiate it all in two phases.
- SSL VPN rides on the same TLS that secures HTTPS, and is genuinely modular: the protocol version, key exchange, bulk cipher,
- and integrity check are all independently negotiated, and the client access mode is a separate choice again.

**🧠 Memory Tip:** Remember **Summary** by linking its purpose → mechanism → result.

### This Week's Lab & Tutorial (Slide 30)

**Exam Answer:** Lab: to be planned in a follow-up discussion, once we've confirmed which of today's configurations are genuinely supported.

**Explanation:**

- Lab: to be planned in a follow-up discussion, once we've confirmed which of today's configurations are genuinely supported
- and testable in Packet Tracer.
- Tutorial worksheet: study-notes-style questions covering IPsec, SSL VPN's modular building blocks, and Cisco VPN
- configuration. Use it to prep for the mid-semester test.

**සිංහලෙන්:** **This Week's Lab & Tutorial** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Lab: to be planned in a follow-up discussion, once we've confirmed which of today's configurations are genuinely supported
- and testable in Packet Tracer.
- Tutorial worksheet: study-notes-style questions covering IPsec, SSL VPN's modular building blocks, and Cisco VPN
- configuration. Use it to prep for the mid-semester test.

**🧠 Memory Tip:** Remember **This Week's Lab & Tutorial** by linking its purpose → mechanism → result.


## 📊 Important Comparisons

| Comparison/topic | Source | Exam focus |
|---|---:|---|
| IPsec: Overview | Slide 5 | IPSEC. |
| IPsec: Transport Mode vs Tunnel Mode | Slide 11 | IPSEC. |
| SSL VPN: Overview | Slide 14 | SSL VPN. |
| IPsec vs SSL VPN | Slide 20 | Two different answers to the same underlying problem. |
| IPsec vs SSL VPN: Direct Comparison | Slide 21 | COMPARISON. |
| Summary | Slide 29 | IPsec secures the network layer itself using a suite of cooperating protocols, AH for integrity alone, ESP for encryption, and. |

## 🛠️ Practical Knowledge

### IPsec, SSL VPN, and Cisco Configuration (Slide 1)

- IE3122: Network Security | Week 9
- What's actually happening inside the two dominant VPN technologies

### Today's Agenda (Slide 2)

- IPsec: architecture, components, and modes
- SSL VPN: architecture, client access modes, and its modular cryptographic building blocks
- IPsec versus SSL VPN, compared directly
- Configuring tunnels and VPNs on Cisco devices: concept and template, for GRE, IPsec, and GRE over IPsec

### IPsec as a Modular Framework (Slide 6)

- IPSEC
- IPsec defines five separate functions, each with a menu of interchangeable choices rather than one mandatory answer. The firs t row matters most: AH
- authenticates only, with no encryption; ESP adds real confidentiality, which is why ESP or ESP+AH is used far more often.
- An actual configuration picks exactly one choice per row. The two examples on the right are both valid, built from that same menu.

### IPsec: Strengths and Limitations (Slide 12)

- IPSEC
- Strengths: operates at the network layer, so it's completely application-transparent, protecting all IP traffic without needing
- any individual application to support it. It's a strong, mature, widely interoperable standard with robust authentication
- options.
- Limitations: configuration genuinely is complex, involving several distinct components, an ISAKMP policy, a transform set, and
- traffic-matching rules, that all have to agree correctly. AH in particular struggles to cross NAT devices, since NAT modifies the
- very IP header AH is protecting, breaking its integrity check; ESP needs a NAT Traversal extension to reliably cross NAT too.
- It's also generally less naturally suited to simple browser-based remote access than SSL VPN.

### Building Two Example Cipher Suites (Slide 17)

- SSL VPN
- Pick one option from each row and you get a real, nameable cipher suite. These two are both valid TLS configurations, but
- they are not remotely equivalent in strength.
- Weaker (avoid) Stronger (prefer)
- Protocol Version TLS 1.2 TLS 1.3
- Key Exchange RSA ECDHE
- Bulk Encryption AES-CBC AES-GCM
- Integrity / MAC SHA-1 built into cipher

### Configuring VPNs and Tunnels on Cisco (Slide 22)

- Devices
- Concept alongside the actual command templates

### GRE Tunnel: Concept (Slide 23)

- CONFIGURATION
- A GRE tunnel is configured as a logical Tunnel interface, entirely separate from any physical interface, with its own IP
- addressing for the virtual point-to-point link it creates.
- It needs a source, the local physical interface or address traffic will actually leave from, and a destination, the remote peer's
- real, public address.
- Remember from earlier: this alone provides no encryption whatsoever. GRE just gets traffic there, in the clear.
- interface Tunnel0
- ip address 10.10.10.1 255.255.255.252
- tunnel source GigabitEthernet0/0
- tunnel destination 203.0.113.10

### IPsec Site-to-Site: Step 1, the IKE Phase 1 Policy (Slide 24)

- CONFIGURATION
- The first step defines how the two peers will authenticate each other and protect their own negotiation traffic, the ISAKMP
- policy from Phase 1 earlier in this deck.
- crypto isakmp policy 10
- encryption aes
- hash sha256
- authentication pre-share
- group 14
- lifetime 86400
- exit
- crypto isakmp key MySharedKey address 203.0.113.10

### IPsec Site-to-Site: Step 2, the Transform Set (Slide 25)

- CONFIGURATION
- The transform set defines the Phase 2 parameters, the actual encryption and authentication that will protect real data traffic once
- negotiation is complete.
- crypto ipsec transform-set MYSET esp-aes esp-sha256-hmac

### IPsec Site-to-Site: Step 3, Defining Interesting Traffic (Slide 26)

- CONFIGURATION
- An ACL identifies exactly which traffic should actually be sent through the VPN, commonly called interesting traffic. Only
- traffic matching this ACL gets encrypted; everything else follows normal routing.
- access-list 100 permit ip 192.168.10.0 0.0.0.255 192.168.20.0 0.0.0.255

### IPsec Site-to-Site: Step 4, the Crypto Map (Slide 27)

- CONFIGURATION
- The crypto map ties everything together: which peer to protect traffic toward, which transform set to use, and which ACL
- defines interesting traffic, then applies the whole thing to the outbound interface.
- crypto map MYMAP 10 ipsec-isakmp
- set peer 203.0.113.10
- set transform-set MYSET
- match address 100
- exit
- interface GigabitEthernet0/0
- crypto map MYMAP

### GRE Over IPsec: Bringing Both Together (Slide 28)

- CONFIGURATION
- Configure the GRE tunnel exactly as shown earlier, giving you a working but unencrypted logical link.
- Then configure IPsec exactly as in the previous four steps, with one key difference: the interesting-traffic ACL should match
- GRE traffic itself, protocol 47, between the tunnel endpoints, rather than the traffic riding inside the tunnel.
- The result carries the best of both: GRE's flexibility, including support for dynamic routing protocols and non-IP traffic across
- the tunnel, protected by IPsec's actual encryption. This is a genuinely common real-world design, not just a teaching exercise.

### Summary (Slide 29)

- IPsec secures the network layer itself using a suite of cooperating protocols, AH for integrity alone, ESP for encryption, and
- IKE to negotiate it all in two phases.
- SSL VPN rides on the same TLS that secures HTTPS, and is genuinely modular: the protocol version, key exchange, bulk cipher,
- and integrity check are all independently negotiated, and the client access mode is a separate choice again.
- Neither is simply better than the other. IPsec suits full-network, always-on connections; SSL VPN suits individual, often
- browser-based remote access.
- GRE, IPsec, and GRE over IPsec each solve a different problem, plain transport, plain security, or both together, and the
- configuration for each builds directly on the last.

### This Week's Lab & Tutorial (Slide 30)

- Lab: to be planned in a follow-up discussion, once we've confirmed which of today's configurations are genuinely supported
- and testable in Packet Tracer.
- Tutorial worksheet: study-notes-style questions covering IPsec, SSL VPN's modular building blocks, and Cisco VPN
- configuration. Use it to prep for the mid-semester test.

## ⭐ Important Exam Points

- ⭐ **IPsec VPN (Slide 4):** Securing the network layer itself.
- ⭐ **IPsec: Overview (Slide 5):** IPSEC.
- ⭐ **IPsec as a Modular Framework (Slide 6):** IPSEC.
- ⭐ **Choosing Confidentiality and Integrity Algorithms (Slide 7):** IPSEC.
- ⭐ **Peer Authentication Methods (Slide 8):** IPSEC.
- ⭐ **Diffie-Hellman Group Choices (Slide 9):** IPSEC.
- ⭐ **IPsec: IKE's Two Phases (Slide 10):** IPSEC.
- ⭐ **IPsec: Transport Mode vs Tunnel Mode (Slide 11):** IPSEC.
- ⭐ **IPsec: Strengths and Limitations (Slide 12):** IPSEC.
- ⭐ **SSL VPN (Slide 13):** Built from interchangeable cryptographic building blocks.
- ⭐ **SSL VPN: Overview (Slide 14):** SSL VPN.
- ⭐ **SSL VPN Has Interchangeable Building Blocks Too (Slide 15):** SSL VPN.
- ⭐ **SSL VPN's Functional Blocks, Visually (Slide 16):** SSL VPN.
- ⭐ **Building Two Example Cipher Suites (Slide 17):** SSL VPN.
- ⭐ **SSL VPN's Building Blocks, Function by Function (Slide 18):** SSL VPN.

## ❓ Possible Exam Questions

### MCQs

1. Which statement best matches **IPsec VPN**?
   - A. It is unrelated to network security.
   - B. Securing the network layer itself.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

2. Which statement best matches **Diffie-Hellman Group Choices**?
   - A. It is unrelated to network security.
   - B. IPSEC.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

3. Which statement best matches **SSL VPN: Overview**?
   - A. It is unrelated to network security.
   - B. SSL VPN.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

4. Which statement best matches **SSL VPN: Client Access Modes**?
   - A. It is unrelated to network security.
   - B. SSL VPN.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

5. Which statement best matches **IPsec Site-to-Site: Step 1, the IKE Phase 1 Policy**?
   - A. It is unrelated to network security.
   - B. CONFIGURATION.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**


### Short Structured Questions

1. **Explain IPsec VPN.**
   - **Model answer:** Securing the network layer itself.

2. **Explain Diffie-Hellman Group Choices.**
   - **Model answer:** IPSEC.

3. **Explain SSL VPN: Overview.**
   - **Model answer:** SSL VPN.

4. **Explain SSL VPN: Client Access Modes.**
   - **Model answer:** SSL VPN.

5. **Explain IPsec Site-to-Site: Step 1, the IKE Phase 1 Policy.**
   - **Model answer:** CONFIGURATION.


### Scenario-Based Question

**Scenario:** An organization must apply the concepts from **VPN Technologies** to improve its network security. Identify the relevant mechanism or risk, explain the likely impact, and recommend a layered response.

**Model-answer approach:** Identify the asset and trust boundary; name the relevant protocol/control; explain the mechanism using the lecture terminology; state confidentiality, integrity, or availability impact; then recommend the matching prevention, detection, and verification steps from the slides.

## ⚡ Last-Minute Quick Revision

- **IPsec VPN:** Securing the network layer itself.
- **IPsec: Overview:** IPSEC.
- **IPsec as a Modular Framework:** IPSEC.
- **Choosing Confidentiality and Integrity Algorithms:** IPSEC.
- **Peer Authentication Methods:** IPSEC.
- **Diffie-Hellman Group Choices:** IPSEC.
- **IPsec: IKE's Two Phases:** IPSEC.
- **IPsec: Transport Mode vs Tunnel Mode:** IPSEC.
- **IPsec: Strengths and Limitations:** IPSEC.
- **SSL VPN:** Built from interchangeable cryptographic building blocks.
- **SSL VPN: Overview:** SSL VPN.
- **SSL VPN Has Interchangeable Building Blocks Too:** SSL VPN.
- **SSL VPN's Functional Blocks, Visually:** SSL VPN.
- **Building Two Example Cipher Suites:** SSL VPN.
- **SSL VPN's Building Blocks, Function by Function:** SSL VPN.
- **SSL VPN: Client Access Modes:** SSL VPN.
- **IPsec vs SSL VPN:** Two different answers to the same underlying problem.
- **IPsec vs SSL VPN: Direct Comparison:** COMPARISON.
- **Configuring VPNs and Tunnels on Cisco:** Devices.
- **GRE Tunnel: Concept:** CONFIGURATION.

## Verification Notes

- Slide coverage: **31 of 31 slides processed**.
- Slide numbers refer to PDF page order.
- Any application example or scenario above extends the slide concept for revision and is not presented as a verbatim lecturer statement.
