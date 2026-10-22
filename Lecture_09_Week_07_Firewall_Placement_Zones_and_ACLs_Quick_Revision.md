# Lecture 09 – Firewall Placement, Zones, and ACLs

## 📌 Lecture Overview

This lecture covers **Firewall Placement, Zones, and ACLs** as presented in the supplied IE3122 slides. The notes follow the source order across 28 slides and retain the lecture's terminology, mechanisms, examples, and configuration details. They are organized for rapid MCQ, structured-answer, and scenario revision.

> **Source boundary:** Content below is derived from `IE3122_Week7_FirewallPlacementACLs_Slides.pdf`. Generic exam prompts/examples are labelled as application material; no unsupported lecturer emphasis is claimed.

## 🎯 Learning Objectives

- LO3
- Analyse security requirements and recommend appropriate technologies.
- LO4
- Evaluate different security technologies, compare them, and identify appropriate use cases.
- LO5
- Configure security technologies to satisfy specific requirements.
- By the end of this session you should be able to recommend a placement architecture for a given scenario, and correctly configure and place an
- ACL to enforce it.

## 📚 Main Topics and Subtopics

### The DMZ and the Zone-Based Model (Slide 4)

**Exam Answer:** A buffer network, and a way of thinking about policy.

**Explanation:**

- A buffer network, and a way of thinking about policy

**සිංහලෙන්:** **The DMZ and the Zone-Based Model** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- A buffer network, and a way of thinking about policy

**🧠 Memory Tip:** Remember **The DMZ and the Zone-Based Model** by linking its purpose → mechanism → result.

### What Is a DMZ? (Slide 5)

**Exam Answer:** CONCEPT.

**Explanation:**

- CONCEPT
- Internet DMZ(public-facing servers) Internal Network
- blocked or tightly restricted
- A DMZ (Demilitarised Zone) is a buffer network segment sitting between a trusted internal network and an untrusted external one,
- usually the Internet.
- It hosts services that genuinely need to be reachable from outside, such as web, email, or DNS servers, without exposing the internal
- network directly to that same exposure.
- The key principle: if a DMZ-hosted server is compromised, the attacker still doesn't have a direct path into the internal network. The DMZ
- contains the damage rather than preventing it entirely.

**සිංහලෙන්:** **What Is a DMZ?** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONCEPT
- Internet DMZ(public-facing servers) Internal Network
- blocked or tightly restricted
- A DMZ (Demilitarised Zone) is a buffer network segment sitting between a trusted internal network and an untrusted external one,

**🧠 Memory Tip:** Remember **What Is a DMZ?** by linking its purpose → mechanism → result.

### Zone-Based Firewall: A Configuration Model, Not a New Technology (Slide 6)

**Exam Answer:** CONFIGURATION MODEL.

**Explanation:**

- CONFIGURATION MODEL
- Recall Deck A's seven types: those are inspection technologies, answering the question of how a decision gets made.
- Zone-Based Firewall (ZBF) answers a different question entirely: how do you organize policy across many interfaces as a
- network grows? Any of the seven types could sit underneath a ZBF configuration.
- Interfaces are assigned to logical zones, such as INSIDE, OUTSIDE, and DMZ, rather than writing policy per individual interface
- pair.
- Traffic is only permitted between two different zones if an explicit zone-pair policy allows it. By default, traffic between
- different zones is denied unless stated, while traffic within the same zone is typically allowed by default.
- A zone-pair policy is directional and doesn't have to be symmetric: an INSIDE-to-OUTSIDE policy can be broad, while the
- OUTSIDE-to-INSIDE policy for the same two zones can be far stricter.

**සිංහලෙන්:** **Zone-Based Firewall: A Configuration Model, Not a New Technology** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION MODEL
- Recall Deck A's seven types: those are inspection technologies, answering the question of how a decision gets made.
- Zone-Based Firewall (ZBF) answers a different question entirely: how do you organize policy across many interfaces as a
- network grows? Any of the seven types could sit underneath a ZBF configuration.

**🧠 Memory Tip:** Remember **Zone-Based Firewall: A Configuration Model, Not a New Technology** by linking its purpose → mechanism → result.

### How DMZ and ZBF Fit Together (Slide 7)

**Exam Answer:** CONFIGURATION MODEL.

**Explanation:**

- CONFIGURATION MODEL
- The DMZ concept from the previous slide maps directly onto ZBF: a three-zone design (INSIDE, OUTSIDE, DMZ) is one of the
- most common real-world ZBF configurations.
- Each zone-pair gets its own tailored policy: OUTSIDE-to-DMZ permits specific public services; DMZ-to-INSIDE is denied or
- extremely restricted; INSIDE-to-OUTSIDE and INSIDE-to-DMZ are generally permitted.
- The advantage over configuring ACLs per interface directly: as the network grows, you reason about policy in terms of which
- zones may talk to which, not by tracking every individual interface pairing by hand. This scales far better and is much easier
- to audit.

**සිංහලෙන්:** **How DMZ and ZBF Fit Together** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION MODEL
- The DMZ concept from the previous slide maps directly onto ZBF: a three-zone design (INSIDE, OUTSIDE, DMZ) is one of the
- most common real-world ZBF configurations.
- Each zone-pair gets its own tailored policy: OUTSIDE-to-DMZ permits specific public services; DMZ-to-INSIDE is denied or

**🧠 Memory Tip:** Remember **How DMZ and ZBF Fit Together** by linking its purpose → mechanism → result.

### Four Placement Architectures (Slide 8)

**Exam Answer:** Where the firewall (or firewalls) actually sit relative to the border router.

**Explanation:**

- Where the firewall (or firewalls) actually sit relative to the border router

**සිංහලෙන්:** **Four Placement Architectures** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Where the firewall (or firewalls) actually sit relative to the border router

**🧠 Memory Tip:** Remember **Four Placement Architectures** by linking its purpose → mechanism → result.

### Architecture 1: Single Firewall Behind the Border Router (Slide 9)

**Exam Answer:** PLACEMENT.

**Explanation:**

- PLACEMENT
- Internet BorderRouter Firewall
- DMZ
- Internal Network
- Strengths
- Simple, single point of policy management
- Lower cost, only one security device to buy and maintain
- Weaknesses
- Single point of failure for the whole network
- DMZ and internal traffic compete for the same device's rules
- and processing

**සිංහලෙන්:** **Architecture 1: Single Firewall Behind the Border Router** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- PLACEMENT
- Internet BorderRouter Firewall
- DMZ
- Internal Network

**🧠 Memory Tip:** Remember **Architecture 1: Single Firewall Behind the Border Router** by linking its purpose → mechanism → result.

### Architecture 2: Single Firewall In Front of the Border Router (Slide 10)

**Exam Answer:** PLACEMENT.

**Explanation:**

- PLACEMENT
- Internet Firewall BorderRouter
- Internal Network
- Strengths
- The firewall inspects and filters all traffic before it even
- reaches the router, protecting the router itself
- Simpler conceptual flow for a small network where the firewall
- doubles as the primary gateway
- Weaknesses
- Non-standard design, so less documented best practice and
- vendor guidance
- The router's own management and routing-protocol traffic
- must all pass through firewall policy, adding complexity

**සිංහලෙන්:** **Architecture 2: Single Firewall In Front of the Border Router** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- PLACEMENT
- Internet Firewall BorderRouter
- Internal Network
- Strengths

**🧠 Memory Tip:** Remember **Architecture 2: Single Firewall In Front of the Border Router** by linking its purpose → mechanism → result.

### Architecture 3: Dual Firewall, Router Before Both (Screened Subnet) (Slide 11)

**Exam Answer:** PLACEMENT.

**Explanation:**

- PLACEMENT
- Internet Router Firewall 1
- DMZ
- Firewall 2
- Internal
- Strengths
- Strong defence in depth: an attacker must compromise two
- separate firewalls to reach the internal network
- The DMZ is genuinely isolated between two distinct security
- boundaries
- Each firewall's policy can be tailored specifically to its position
- Weaknesses
- Higher cost, two firewall devices to buy, license, and maintain
- More complex configuration and management overhead
- Real risk of policy inconsistency between the two devices if not
- carefully coordinated

**සිංහලෙන්:** **Architecture 3: Dual Firewall, Router Before Both (Screened Subnet)** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- PLACEMENT
- Internet Router Firewall 1
- DMZ
- Firewall 2

**🧠 Memory Tip:** Remember **Architecture 3: Dual Firewall, Router Before Both (Screened Subnet)** by linking its purpose → mechanism → result.

### Architecture 4: Dual Firewall, Router Between the Two (Slide 12)

**Exam Answer:** PLACEMENT.

**Explanation:**

- PLACEMENT
- Internet Firewall 1 Router
- DMZ
- Firewall 2
- Internal
- Strengths
- Firewall 1 filters all inbound internet traffic before it even reaches
- the router, protecting the router directly
- The router can focus purely on routing and NAT for the DMZ
- segment, without also being a security boundary
- Weaknesses
- If Firewall 1 is bypassed, the router sits exposed with no second
- firewall immediately in front of it
- Less common, less standardised design pattern with less vendor
- documentation
- The router becomes a dependency sitting between two security
- devices, a potential chokepoint

**සිංහලෙන්:** **Architecture 4: Dual Firewall, Router Between the Two** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- PLACEMENT
- Internet Firewall 1 Router
- DMZ
- Firewall 2

**🧠 Memory Tip:** Remember **Architecture 4: Dual Firewall, Router Between the Two** by linking its purpose → mechanism → result.

### Architecture Comparison (Slide 13)

**Exam Answer:** SUMMARY.

**Explanation:**

- SUMMARY
- Architecture Firewalls Router Position Key Trade-off
- Single, Behind Router 1 Before the firewall Simple and cheap, but a single point of failure
- Single, In Front of Router 1 After the firewall Protects the router, but non-standard
- Dual, Router Before Both 2 Before both firewalls Strong defence in depth, higher cost and complexity
- Dual, Router Between 2 Between the two firewalls Protects the router directly, but the router itself is exposed if Firewall 1 is bypassed

**සිංහලෙන්:** **Architecture Comparison** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SUMMARY
- Architecture Firewalls Router Position Key Trade-off
- Single, Behind Router 1 Before the firewall Simple and cheap, but a single point of failure
- Single, In Front of Router 1 After the firewall Protects the router, but non-standard

**🧠 Memory Tip:** Remember **Architecture Comparison** by linking its purpose → mechanism → result.

### Access Control Lists (Slide 14)

**Exam Answer:** The hands-on configuration you'll use in this week's lab.

**Explanation:**

- The hands-on configuration you'll use in this week's lab

**සිංහලෙන්:** **Access Control Lists** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- The hands-on configuration you'll use in this week's lab

**🧠 Memory Tip:** Remember **Access Control Lists** by linking its purpose → mechanism → result.

### ACL Fundamentals (Slide 15)

**Exam Answer:** ACLS.

**Explanation:**

- ACLS
- An ACL is an ordered list of permit and deny statements applied to an interface. Statements are evaluated strictly top to
- bottom.
- The first statement that matches a given packet wins, and processing stops there. Statements further down the list are never
- even checked for that packet.
- Every ACL ends with an implicit deny, even though it's invisible in the configuration. If no statement matches, the traffic is
- dropped by default.
- An ACL is applied per interface and per direction, inbound or outbound, so the same list can behave completely differently
- depending on where and which way you apply it.

**සිංහලෙන්:** **ACL Fundamentals** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACLS
- An ACL is an ordered list of permit and deny statements applied to an interface. Statements are evaluated strictly top to
- bottom.
- The first statement that matches a given packet wins, and processing stops there. Statements further down the list are never

**🧠 Memory Tip:** Remember **ACL Fundamentals** by linking its purpose → mechanism → result.

### Standard ACLs (Slide 16)

**Exam Answer:** ACLS.

**Explanation:**

- ACLS
- Filters based only on source IP address. Nothing else about the packet is considered, not the destination, not the protocol,
- not the port.
- Numbered in the ranges 1 to 99 and 1300 to 1999.
- Because a Standard ACL can't distinguish by destination, applying it too early in the network risks blocking traffic to
- destinations you never intended to affect.
- Best practice, covered in detail shortly: place a Standard ACL as close to the destination as possible.

**සිංහලෙන්:** **Standard ACLs** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACLS
- Filters based only on source IP address. Nothing else about the packet is considered, not the destination, not the protocol,
- not the port.
- Numbered in the ranges 1 to 99 and 1300 to 1999.

**🧠 Memory Tip:** Remember **Standard ACLs** by linking its purpose → mechanism → result.

### Extended ACLs (Slide 17)

**Exam Answer:** ACLS.

**Explanation:**

- ACLS
- Filters based on source and destination IP address, the protocol (TCP , UDP , ICMP , and others), and source and destination
- port numbers.
- Numbered in the ranges 100 to 199 and 2000 to 2699.
- Because an Extended ACL can match precisely on both source and destination together, it can safely be applied much earlier
- without the same risk of over-blocking that a Standard ACL carries.
- Best practice, covered in detail shortly: place an Extended ACL as close to the source as possible.

**සිංහලෙන්:** **Extended ACLs** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACLS
- Filters based on source and destination IP address, the protocol (TCP , UDP , ICMP , and others), and source and destination
- port numbers.
- Numbered in the ranges 100 to 199 and 2000 to 2699.

**🧠 Memory Tip:** Remember **Extended ACLs** by linking its purpose → mechanism → result.

### Named ACLs (Slide 18)

**Exam Answer:** ACLS.

**Explanation:**

- ACLS
- Functionally identical to a Standard or Extended ACL. The only difference is that a Named ACL is identified by a descriptive
- name instead of a number.
- A single Named ACL is still either standard-style or extended-style underneath. Naming it doesn't add new matching
- capability.
- The practical advantage is readability and maintainability: a name like BLOCK_TELNET_FROM_GUEST documents its own
- purpose, and individual lines can be added or removed without recreating the whole list.

**සිංහලෙන්:** **Named ACLs** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACLS
- Functionally identical to a Standard or Extended ACL. The only difference is that a Named ACL is identified by a descriptive
- name instead of a number.
- A single Named ACL is still either standard-style or extended-style underneath. Naming it doesn't add new matching

**🧠 Memory Tip:** Remember **Named ACLs** by linking its purpose → mechanism → result.

### Standard ACL: Command Format in Detail (Slide 19)

**Exam Answer:** ACL SYNTAX.

**Explanation:**

- ACL SYNTAX
- access-list {1-99 | 1300-1999} {permit | deny} {source} [source-wildcard] [log]
- Number: 1 to 99, or the expanded range 1300 to 1999. This is what tells the router the list is a Standard ACL.
- permit or deny: the action taken when a packet matches this line.
- Source: the address to match. This can be a specific host, a network combined with a wildcard mask, or the keyword any to match every address.
- Source wildcard: the inverse of a subnet mask, marking which bits must match exactly (0) and which can be anything (1). The keyword host is shorthand
- for a wildcard of 0.0.0.0, an exact single-address match.
- log (optional): records a message whenever this line is matched, useful for monitoring without changing the action taken.
- Example: access-list 10 permit 192.168.100.0 0.0.0.31
- Example: access-list 10 permit host 192.168.100.5
- Applied to an interface the same way as any ACL: interface GigabitEthernet0/0, then ip access -group 10 out.

**සිංහලෙන්:** **Standard ACL: Command Format in Detail** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACL SYNTAX
- access-list {1-99 | 1300-1999} {permit | deny} {source} [source-wildcard] [log]
- Number: 1 to 99, or the expanded range 1300 to 1999. This is what tells the router the list is a Standard ACL.
- permit or deny: the action taken when a packet matches this line.

**🧠 Memory Tip:** Remember **Standard ACL: Command Format in Detail** by linking its purpose → mechanism → result.

### Extended ACL: Command Format in Detail (Slide 20)

**Exam Answer:** ACL SYNTAX.

**Explanation:**

- ACL SYNTAX
- access-list {100-199 | 2000-2699} {permit | deny} {protocol}
- {source} [source-wildcard] [operator port]
- {destination} [destination-wildcard] [operator port] [established] [log]
- Number: 100 to 199, or the expanded range 2000 to 2699, identifying this as an Extended ACL.
- Protocol: ip for all traffic, or a specific protocol such as tcp, udp, or icmp. Port matching only applies when the protocol is tcp or udp.
- Source and destination: each specified the same way as a Standard ACL, host, network plus wildcard, or any, but here both ends of the conversation are
- matched, not just the source.
- Operator port: an optional comparison (eq, gt, lt, neq, or range) followed by a port number or name, applied separately to so urce and destination.
- established (TCP only, optional): matches only packets that are part of an already-established session, meaning the ACK or RST flag is set. This directly reflects
- Week 6's TCP handshake: a fresh SYN with no ACK will not match this keyword.
- Example: access-list 101 deny tcp 192.168.10.0 0.0.0.255 host 192.168.20.5 eq 23

**සිංහලෙන්:** **Extended ACL: Command Format in Detail** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACL SYNTAX
- access-list {100-199 | 2000-2699} {permit | deny} {protocol}
- {source} [source-wildcard] [operator port]
- {destination} [destination-wildcard] [operator port] [established] [log]

**🧠 Memory Tip:** Remember **Extended ACL: Command Format in Detail** by linking its purpose → mechanism → result.

### Named ACL: Command Format in Detail (Slide 21)

**Exam Answer:** ACL SYNTAX.

**Explanation:**

- ACL SYNTAX
- ip access-list {standard | extended} {name}
- [sequence-number] {permit | deny} { ...rest is identical to the matching
- Standard or Extended syntax above, just without repeating the name... }
- The first line enters a dedicated configuration sub-mode for that one list, rather than repeating access-list and a number on every line.
- Inside that sub-mode, every subsequent line is just permit or deny, matched exactly like the Standard or Extended syntax already covered, since a Named ACL
- is either type underneath, never a third kind of matching logic.
- An optional sequence number at the start of a line (for example 10, 20, 30) lets you insert a new line at a specific position later, without deleting and retyping
- the whole list.
- The name itself must start with a letter, cannot contain spaces, is case-sensitive, and must be unique among all ACLs of that sa me type.
- Example: ip access-list extended BLOCK_TELNET_TO_SERVER
- 10 deny tcp 192.168.10.0 0.0.0.255 host 192.168.20.5 eq 23
- 20 permit ip any any

**සිංහලෙන්:** **Named ACL: Command Format in Detail** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACL SYNTAX
- ip access-list {standard | extended} {name}
- [sequence-number] {permit | deny} { ...rest is identical to the matching
- Standard or Extended syntax above, just without repeating the name... }

**🧠 Memory Tip:** Remember **Named ACL: Command Format in Detail** by linking its purpose → mechanism → result.

### ACL Placement Rules (Slide 22)

**Exam Answer:** ACLS.

**Explanation:**

- ACLS
- Standard ACL: place it close to the destination. Since it can only filter by source address, placing it near the destination avoids
- accidentally blocking that source's traffic to other, unintended destinations elsewhere in the network.
- Extended ACL: place it close to the source. Since it can already match precisely on destination, protocol, and port, there's no
- benefit to letting unwanted traffic travel further into the network first. Stop it as early as possible instead.
- This connects directly back to the placement architectures you just saw: deciding where a firewall or router sits in the
- topology, and deciding where within that device's interfaces to apply a specific ACL, are both the same underlying question.
- Match traffic as early and as precisely as the tool allows, without over-blocking.

**සිංහලෙන්:** **ACL Placement Rules** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACLS
- Standard ACL: place it close to the destination. Since it can only filter by source address, placing it near the destination avoids
- accidentally blocking that source's traffic to other, unintended destinations elsewhere in the network.
- Extended ACL: place it close to the source. Since it can already match precisely on destination, protocol, and port, there's no

**🧠 Memory Tip:** Remember **ACL Placement Rules** by linking its purpose → mechanism → result.

### Worked Example: Extended ACL (Slide 23)

**Exam Answer:** CONFIGURATION.

**Explanation:**

- CONFIGURATION
- Scenario: block Telnet (port 23) from the 192.168.10.0/24 subnet to a specific server at 192.168.20.5, while permitting everything
- else.
- access-list 101 deny tcp 192.168.10.0 0.0.0.255 host 192.168.20.5 eq 23
- access-list 101 permit ip any any
- interface GigabitEthernet0/1
- ip access-group 101 in
- Applied close to the source (the 192.168.10.0/24 subnet's own gateway interface), exactly matching the Extended ACL placementrule from
- the previous slide.
- The explicit permit ip any any at the end matters. Without it, the ACL's implicit deny would silently block every other kind of traffic too, not just
- Telnet.

**සිංහලෙන්:** **Worked Example: Extended ACL** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION
- Scenario: block Telnet (port 23) from the 192.168.10.0/24 subnet to a specific server at 192.168.20.5, while permitting everything
- else.
- access-list 101 deny tcp 192.168.10.0 0.0.0.255 host 192.168.20.5 eq 23

**🧠 Memory Tip:** Remember **Worked Example: Extended ACL** by linking its purpose → mechanism → result.

### Worked Example: Named ACL (Same Policy, Named Style) (Slide 24)

**Exam Answer:** CONFIGURATION.

**Explanation:**

- CONFIGURATION
- ip access-list extended BLOCK_TELNET_TO_SERVER
- deny tcp 192.168.10.0 0.0.0.255 host 192.168.20.5 eq 23
- permit ip any any
- interface GigabitEthernet0/1
- ip access-group BLOCK_TELNET_TO_SERVER in
- Identical behaviour to the numbered version on the previous slide. The only difference is the self-documenting name in place of the
- number 101.
- In modern IOS, a specific line inside this named list can be removed or a new one inserted at a specific sequence number, without
- deleting and rebuilding the entire list.

**සිංහලෙන්:** **Worked Example: Named ACL (Same Policy, Named Style)** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION
- ip access-list extended BLOCK_TELNET_TO_SERVER
- deny tcp 192.168.10.0 0.0.0.255 host 192.168.20.5 eq 23
- permit ip any any

**🧠 Memory Tip:** Remember **Worked Example: Named ACL (Same Policy, Named Style)** by linking its purpose → mechanism → result.

### ACL Summary (Slide 25)

**Exam Answer:** SUMMARY.

**Explanation:**

- SUMMARY
- ACL Type Filters On Number Range Best Placement
- Standard Source IP address only 1-99, 1300-1999 Close to the destination
- Extended Source/destination IP , protocol, port 100-199, 2000-2699 Close to the source
- Named Same as Standard or Extended underneath N/A, identified by name Same as its underlying type

**සිංහලෙන්:** **ACL Summary** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SUMMARY
- ACL Type Filters On Number Range Best Placement
- Standard Source IP address only 1-99, 1300-1999 Close to the destination
- Extended Source/destination IP , protocol, port 100-199, 2000-2699 Close to the source

**🧠 Memory Tip:** Remember **ACL Summary** by linking its purpose → mechanism → result.

### Summary (Slide 26)

**Exam Answer:** A DMZ exists to contain damage: if a public-facing server is compromised, the internal network still isn't directly reachable from there.

**Explanation:**

- A DMZ exists to contain damage: if a public-facing server is compromised, the internal network still isn't directly reachable from there.
- Zone-Based Firewall is a way of organising policy, not a new inspection technology. Any firewall type from Deck A can sit underneath a ZBF
- configuration.
- All four placement architectures trade the same two things against each other: cost and management complexity versus depth of
- defence, whether that's one firewall or two, or where exactly the router sits relative to them.
- Standard ACLs filter on source address alone and belong close to the destination. Extended ACLs can match precisely and belong close to
- the source. Named ACLs are either of those, just easier to read and maintain.

**සිංහලෙන්:** **Summary** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- A DMZ exists to contain damage: if a public-facing server is compromised, the internal network still isn't directly reachable from there.
- Zone-Based Firewall is a way of organising policy, not a new inspection technology. Any firewall type from Deck A can sit underneath a ZBF
- configuration.
- All four placement architectures trade the same two things against each other: cost and management complexity versus depth of

**🧠 Memory Tip:** Remember **Summary** by linking its purpose → mechanism → result.

### This Week's Lab & Tutorial (Slide 27)

**Exam Answer:** Lab: hands-on Standard, Extended, and Named ACL configuration in Packet Tracer, including verifying placement and.

**Explanation:**

- Lab: hands-on Standard, Extended, and Named ACL configuration in Packet Tracer, including verifying placement and
- confirming the implicit deny behaves as expected.
- Tutorial worksheet: study-notes-style questions covering the DMZ, Zone-Based Firewall, the four placement architectures,
- and ACL configuration and placement. Use it to prep for the mid-semester test.

**සිංහලෙන්:** **This Week's Lab & Tutorial** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Lab: hands-on Standard, Extended, and Named ACL configuration in Packet Tracer, including verifying placement and
- confirming the implicit deny behaves as expected.
- Tutorial worksheet: study-notes-style questions covering the DMZ, Zone-Based Firewall, the four placement architectures,
- and ACL configuration and placement. Use it to prep for the mid-semester test.

**🧠 Memory Tip:** Remember **This Week's Lab & Tutorial** by linking its purpose → mechanism → result.


## 📊 Important Comparisons

| Comparison/topic | Source | Exam focus |
|---|---:|---|
| Architecture Comparison | Slide 13 | SUMMARY. |
| ACL Summary | Slide 25 | SUMMARY. |
| Summary | Slide 26 | A DMZ exists to contain damage: if a public-facing server is compromised, the internal network still isn't directly reachable from there. |

## 🛠️ Practical Knowledge

### Today's Agenda (Slide 2)

- What a DMZ is, and why it exists
- Zone-Based Firewall as a configuration model, not a new technology
- Four firewall placement architectures, compared for strengths and weaknesses
- Access Control Lists: Standard, Extended, and Named
- ACL placement rules, and a worked configuration example

### Zone-Based Firewall: A Configuration Model, Not a New Technology (Slide 6)

- CONFIGURATION MODEL
- Recall Deck A's seven types: those are inspection technologies, answering the question of how a decision gets made.
- Zone-Based Firewall (ZBF) answers a different question entirely: how do you organize policy across many interfaces as a
- network grows? Any of the seven types could sit underneath a ZBF configuration.
- Interfaces are assigned to logical zones, such as INSIDE, OUTSIDE, and DMZ, rather than writing policy per individual interface
- pair.
- Traffic is only permitted between two different zones if an explicit zone-pair policy allows it. By default, traffic between
- different zones is denied unless stated, while traffic within the same zone is typically allowed by default.
- A zone-pair policy is directional and doesn't have to be symmetric: an INSIDE-to-OUTSIDE policy can be broad, while the
- OUTSIDE-to-INSIDE policy for the same two zones can be far stricter.

### How DMZ and ZBF Fit Together (Slide 7)

- CONFIGURATION MODEL
- The DMZ concept from the previous slide maps directly onto ZBF: a three-zone design (INSIDE, OUTSIDE, DMZ) is one of the
- most common real-world ZBF configurations.
- Each zone-pair gets its own tailored policy: OUTSIDE-to-DMZ permits specific public services; DMZ-to-INSIDE is denied or
- extremely restricted; INSIDE-to-OUTSIDE and INSIDE-to-DMZ are generally permitted.
- The advantage over configuring ACLs per interface directly: as the network grows, you reason about policy in terms of which
- zones may talk to which, not by tracking every individual interface pairing by hand. This scales far better and is much easier
- to audit.

### Architecture 3: Dual Firewall, Router Before Both (Screened Subnet) (Slide 11)

- PLACEMENT
- Internet Router Firewall 1
- DMZ
- Firewall 2
- Internal
- Strengths
- Strong defence in depth: an attacker must compromise two
- separate firewalls to reach the internal network
- The DMZ is genuinely isolated between two distinct security
- boundaries
- Each firewall's policy can be tailored specifically to its position
- Weaknesses
- Higher cost, two firewall devices to buy, license, and maintain
- More complex configuration and management overhead
- Real risk of policy inconsistency between the two devices if not
- carefully coordinated

### Access Control Lists (Slide 14)

- The hands-on configuration you'll use in this week's lab

### ACL Fundamentals (Slide 15)

- ACLS
- An ACL is an ordered list of permit and deny statements applied to an interface. Statements are evaluated strictly top to
- bottom.
- The first statement that matches a given packet wins, and processing stops there. Statements further down the list are never
- even checked for that packet.
- Every ACL ends with an implicit deny, even though it's invisible in the configuration. If no statement matches, the traffic is
- dropped by default.
- An ACL is applied per interface and per direction, inbound or outbound, so the same list can behave completely differently
- depending on where and which way you apply it.

### Standard ACL: Command Format in Detail (Slide 19)

- ACL SYNTAX
- access-list {1-99 | 1300-1999} {permit | deny} {source} [source-wildcard] [log]
- Number: 1 to 99, or the expanded range 1300 to 1999. This is what tells the router the list is a Standard ACL.
- permit or deny: the action taken when a packet matches this line.
- Source: the address to match. This can be a specific host, a network combined with a wildcard mask, or the keyword any to match every address.
- Source wildcard: the inverse of a subnet mask, marking which bits must match exactly (0) and which can be anything (1). The keyword host is shorthand
- for a wildcard of 0.0.0.0, an exact single-address match.
- log (optional): records a message whenever this line is matched, useful for monitoring without changing the action taken.
- Example: access-list 10 permit 192.168.100.0 0.0.0.31
- Example: access-list 10 permit host 192.168.100.5
- Applied to an interface the same way as any ACL: interface GigabitEthernet0/0, then ip access -group 10 out.

### Extended ACL: Command Format in Detail (Slide 20)

- ACL SYNTAX
- access-list {100-199 | 2000-2699} {permit | deny} {protocol}
- {source} [source-wildcard] [operator port]
- {destination} [destination-wildcard] [operator port] [established] [log]
- Number: 100 to 199, or the expanded range 2000 to 2699, identifying this as an Extended ACL.
- Protocol: ip for all traffic, or a specific protocol such as tcp, udp, or icmp. Port matching only applies when the protocol is tcp or udp.
- Source and destination: each specified the same way as a Standard ACL, host, network plus wildcard, or any, but here both ends of the conversation are
- matched, not just the source.
- Operator port: an optional comparison (eq, gt, lt, neq, or range) followed by a port number or name, applied separately to so urce and destination.
- established (TCP only, optional): matches only packets that are part of an already-established session, meaning the ACK or RST flag is set. This directly reflects
- Week 6's TCP handshake: a fresh SYN with no ACK will not match this keyword.
- Example: access-list 101 deny tcp 192.168.10.0 0.0.0.255 host 192.168.20.5 eq 23

### Named ACL: Command Format in Detail (Slide 21)

- ACL SYNTAX
- ip access-list {standard | extended} {name}
- [sequence-number] {permit | deny} { ...rest is identical to the matching
- Standard or Extended syntax above, just without repeating the name... }
- The first line enters a dedicated configuration sub-mode for that one list, rather than repeating access-list and a number on every line.
- Inside that sub-mode, every subsequent line is just permit or deny, matched exactly like the Standard or Extended syntax already covered, since a Named ACL
- is either type underneath, never a third kind of matching logic.
- An optional sequence number at the start of a line (for example 10, 20, 30) lets you insert a new line at a specific position later, without deleting and retyping
- the whole list.
- The name itself must start with a letter, cannot contain spaces, is case-sensitive, and must be unique among all ACLs of that sa me type.
- Example: ip access-list extended BLOCK_TELNET_TO_SERVER
- 10 deny tcp 192.168.10.0 0.0.0.255 host 192.168.20.5 eq 23
- 20 permit ip any any

### ACL Placement Rules (Slide 22)

- ACLS
- Standard ACL: place it close to the destination. Since it can only filter by source address, placing it near the destination avoids
- accidentally blocking that source's traffic to other, unintended destinations elsewhere in the network.
- Extended ACL: place it close to the source. Since it can already match precisely on destination, protocol, and port, there's no
- benefit to letting unwanted traffic travel further into the network first. Stop it as early as possible instead.
- This connects directly back to the placement architectures you just saw: deciding where a firewall or router sits in the
- topology, and deciding where within that device's interfaces to apply a specific ACL, are both the same underlying question.
- Match traffic as early and as precisely as the tool allows, without over-blocking.

### Worked Example: Extended ACL (Slide 23)

- CONFIGURATION
- Scenario: block Telnet (port 23) from the 192.168.10.0/24 subnet to a specific server at 192.168.20.5, while permitting everything
- else.
- access-list 101 deny tcp 192.168.10.0 0.0.0.255 host 192.168.20.5 eq 23
- access-list 101 permit ip any any
- interface GigabitEthernet0/1
- ip access-group 101 in
- Applied close to the source (the 192.168.10.0/24 subnet's own gateway interface), exactly matching the Extended ACL placementrule from
- the previous slide.
- The explicit permit ip any any at the end matters. Without it, the ACL's implicit deny would silently block every other kind of traffic too, not just
- Telnet.

### Worked Example: Named ACL (Same Policy, Named Style) (Slide 24)

- CONFIGURATION
- ip access-list extended BLOCK_TELNET_TO_SERVER
- deny tcp 192.168.10.0 0.0.0.255 host 192.168.20.5 eq 23
- permit ip any any
- interface GigabitEthernet0/1
- ip access-group BLOCK_TELNET_TO_SERVER in
- Identical behaviour to the numbered version on the previous slide. The only difference is the self-documenting name in place of the
- number 101.
- In modern IOS, a specific line inside this named list can be removed or a new one inserted at a specific sequence number, without
- deleting and rebuilding the entire list.

### Summary (Slide 26)

- A DMZ exists to contain damage: if a public-facing server is compromised, the internal network still isn't directly reachable from there.
- Zone-Based Firewall is a way of organising policy, not a new inspection technology. Any firewall type from Deck A can sit underneath a ZBF
- configuration.
- All four placement architectures trade the same two things against each other: cost and management complexity versus depth of
- defence, whether that's one firewall or two, or where exactly the router sits relative to them.
- Standard ACLs filter on source address alone and belong close to the destination. Extended ACLs can match precisely and belong close to
- the source. Named ACLs are either of those, just easier to read and maintain.

### This Week's Lab & Tutorial (Slide 27)

- Lab: hands-on Standard, Extended, and Named ACL configuration in Packet Tracer, including verifying placement and
- confirming the implicit deny behaves as expected.
- Tutorial worksheet: study-notes-style questions covering the DMZ, Zone-Based Firewall, the four placement architectures,
- and ACL configuration and placement. Use it to prep for the mid-semester test.

## ⭐ Important Exam Points

- ⭐ **The DMZ and the Zone-Based Model (Slide 4):** A buffer network, and a way of thinking about policy.
- ⭐ **What Is a DMZ? (Slide 5):** CONCEPT.
- ⭐ **Zone-Based Firewall: A Configuration Model, Not a New Technology (Slide 6):** CONFIGURATION MODEL.
- ⭐ **How DMZ and ZBF Fit Together (Slide 7):** CONFIGURATION MODEL.
- ⭐ **Four Placement Architectures (Slide 8):** Where the firewall (or firewalls) actually sit relative to the border router.
- ⭐ **Architecture 1: Single Firewall Behind the Border Router (Slide 9):** PLACEMENT.
- ⭐ **Architecture 2: Single Firewall In Front of the Border Router (Slide 10):** PLACEMENT.
- ⭐ **Architecture 3: Dual Firewall, Router Before Both (Screened Subnet) (Slide 11):** PLACEMENT.
- ⭐ **Architecture 4: Dual Firewall, Router Between the Two (Slide 12):** PLACEMENT.
- ⭐ **Architecture Comparison (Slide 13):** SUMMARY.
- ⭐ **Access Control Lists (Slide 14):** The hands-on configuration you'll use in this week's lab.
- ⭐ **ACL Fundamentals (Slide 15):** ACLS.
- ⭐ **Standard ACLs (Slide 16):** ACLS.
- ⭐ **Extended ACLs (Slide 17):** ACLS.
- ⭐ **Named ACLs (Slide 18):** ACLS.

## ❓ Possible Exam Questions

### MCQs

1. Which statement best matches **The DMZ and the Zone-Based Model**?
   - A. It is unrelated to network security.
   - B. A buffer network, and a way of thinking about policy.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

2. Which statement best matches **Four Placement Architectures**?
   - A. It is unrelated to network security.
   - B. Where the firewall (or firewalls) actually sit relative to the border router.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

3. Which statement best matches **Architecture 4: Dual Firewall, Router Between the Two**?
   - A. It is unrelated to network security.
   - B. PLACEMENT.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

4. Which statement best matches **Standard ACLs**?
   - A. It is unrelated to network security.
   - B. ACLS.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

5. Which statement best matches **Extended ACL: Command Format in Detail**?
   - A. It is unrelated to network security.
   - B. ACL SYNTAX.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**


### Short Structured Questions

1. **Explain The DMZ and the Zone-Based Model.**
   - **Model answer:** A buffer network, and a way of thinking about policy.

2. **Explain Four Placement Architectures.**
   - **Model answer:** Where the firewall (or firewalls) actually sit relative to the border router.

3. **Explain Architecture 4: Dual Firewall, Router Between the Two.**
   - **Model answer:** PLACEMENT.

4. **Explain Standard ACLs.**
   - **Model answer:** ACLS.

5. **Explain Extended ACL: Command Format in Detail.**
   - **Model answer:** ACL SYNTAX.


### Scenario-Based Question

**Scenario:** An organization must apply the concepts from **Firewall Placement, Zones, and ACLs** to improve its network security. Identify the relevant mechanism or risk, explain the likely impact, and recommend a layered response.

**Model-answer approach:** Identify the asset and trust boundary; name the relevant protocol/control; explain the mechanism using the lecture terminology; state confidentiality, integrity, or availability impact; then recommend the matching prevention, detection, and verification steps from the slides.

## ⚡ Last-Minute Quick Revision

- **The DMZ and the Zone-Based Model:** A buffer network, and a way of thinking about policy.
- **What Is a DMZ?:** CONCEPT.
- **Zone-Based Firewall: A Configuration Model, Not a New Technology:** CONFIGURATION MODEL.
- **How DMZ and ZBF Fit Together:** CONFIGURATION MODEL.
- **Four Placement Architectures:** Where the firewall (or firewalls) actually sit relative to the border router.
- **Architecture 1: Single Firewall Behind the Border Router:** PLACEMENT.
- **Architecture 2: Single Firewall In Front of the Border Router:** PLACEMENT.
- **Architecture 3: Dual Firewall, Router Before Both (Screened Subnet):** PLACEMENT.
- **Architecture 4: Dual Firewall, Router Between the Two:** PLACEMENT.
- **Architecture Comparison:** SUMMARY.
- **Access Control Lists:** The hands-on configuration you'll use in this week's lab.
- **ACL Fundamentals:** ACLS.
- **Standard ACLs:** ACLS.
- **Extended ACLs:** ACLS.
- **Named ACLs:** ACLS.
- **Standard ACL: Command Format in Detail:** ACL SYNTAX.
- **Extended ACL: Command Format in Detail:** ACL SYNTAX.
- **Named ACL: Command Format in Detail:** ACL SYNTAX.
- **ACL Placement Rules:** ACLS.
- **Worked Example: Extended ACL:** CONFIGURATION.

## Verification Notes

- Slide coverage: **28 of 28 slides processed**.
- Slide numbers refer to PDF page order.
- Any application example or scenario above extends the slide concept for revision and is not presented as a verbatim lecturer statement.
