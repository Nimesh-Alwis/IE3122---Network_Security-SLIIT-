# Lecture 07 – Routing Attacks and Defenses

## 📌 Lecture Overview

This lecture covers **Routing Attacks and Defenses** as presented in the supplied IE3122 slides. The notes follow the source order across 45 slides and retain the lecture's terminology, mechanisms, examples, and configuration details. They are organized for rapid MCQ, structured-answer, and scenario revision.

> **Source boundary:** Content below is derived from `IE3122_Week5_RoutingAttacks_Slides_1.pdf`. Generic exam prompts/examples are labelled as application material; no unsupported lecturer emphasis is claimed.

## 🎯 Learning Objectives

- LO1
- Describe common network vulnerabilities and attacks, today specifically at the routing layer.
- LO2
- Evaluate different mitigation techniques for vulnerabilities and make recommendations.
- By the end of this session you should be able to explain how a routing protocol decides what to trust, how that trust can be
- abused, and which defense actually closes the gap.

## 📚 Main Topics and Subtopics

### Routing Protocol Fundamentals (Slide 4)

**Exam Answer:** How routers learn to trust each other.

**Explanation:**

- How routers learn to trust each other

**සිංහලෙන්:** **Routing Protocol Fundamentals** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- How routers learn to trust each other

**🧠 Memory Tip:** Remember **Routing Protocol Fundamentals** by linking its purpose → mechanism → result.

### Why Routing Protocols Matter (Slide 5)

**Exam Answer:** FUNDAMENTALS.

**Explanation:**

- FUNDAMENTALS
- Recall Week 1: a router forwards packets based on its routing table. Routing protocols exist so routers can build that
- table automatically, by exchanging information with their neighbors instead of relying on manual configuration alone.
- This automation is powerful at scale. Large networks and the Internet itself simply couldn't run on manually
- maintained routes.
- But it means every router is placing real trust in whatever its neighbors tell it. Everything in this lecture follows from
- asking: what happens when that trust is misplaced?

**සිංහලෙන්:** **Why Routing Protocols Matter** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FUNDAMENTALS
- Recall Week 1: a router forwards packets based on its routing table. Routing protocols exist so routers can build that
- table automatically, by exchanging information with their neighbors instead of relying on manual configuration alone.
- This automation is powerful at scale. Large networks and the Internet itself simply couldn't run on manually

**🧠 Memory Tip:** Remember **Why Routing Protocols Matter** by linking its purpose → mechanism → result.

### RIP: Routing Information Protocol (Slide 6)

**Exam Answer:** FUNDAMENTALS.

**Explanation:**

- FUNDAMENTALS
- Type: distance-vector. Each router only knows what its direct neighbors tell it, and picks the path with the fewest
- hops.
- Simple to configure, but scales poorly and converges slowly on larger networks.
- No authentication in RIPv1 at all; RIPv2 added optional plaintext or MD5 authentication, but it's frequently left
- disabled in practice.

**සිංහලෙන්:** **RIP: Routing Information Protocol** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FUNDAMENTALS
- Type: distance-vector. Each router only knows what its direct neighbors tell it, and picks the path with the fewest
- hops.
- Simple to configure, but scales poorly and converges slowly on larger networks.

**🧠 Memory Tip:** Remember **RIP: Routing Information Protocol** by linking its purpose → mechanism → result.

### RIP: Metric and Messages (Slide 7)

**Exam Answer:** FUNDAMENTALS.

**Explanation:**

- FUNDAMENTALS
- Metric: hop count only. Every link counts as 1 hop regardless of its actual bandwidth or reliability, capped at a
- maximum of 15. A route needing 16 hops is treated as unreachable, which is part of why RIP struggles on larger
- networks.
- Messages: RIP Request (a router asking for routing information) and RIP Response (the reply, also sent unsolicited
- every 30 seconds by default to advertise the full routing table).
- Transport: runs directly over UDP , port 520, using broadcast in RIPv1 and multicast (224.0.0.9) in RIPv2.
- Security angle: because full routing table updates go out every 30 seconds to anyone listening on the segment, an
- attacker doesn't need to do anything sophisticated to see the whole picture, or to inject a convincing-looking
- Response of their own.

**සිංහලෙන්:** **RIP: Metric and Messages** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FUNDAMENTALS
- Metric: hop count only. Every link counts as 1 hop regardless of its actual bandwidth or reliability, capped at a
- maximum of 15. A route needing 16 hops is treated as unreachable, which is part of why RIP struggles on larger
- networks.

**🧠 Memory Tip:** Remember **RIP: Metric and Messages** by linking its purpose → mechanism → result.

### OSPF: Open Shortest Path First (Slide 8)

**Exam Answer:** FUNDAMENTALS.

**Explanation:**

- FUNDAMENTALS
- Type: link-state. Every router builds a full map of the network topology (within its area) and calculates the best path
- itself, rather than trusting a neighbor's summary.
- Organised into areas for scalability, with Area 0 (the backbone) connecting all others.
- Supports MD5 authentication between neighbors. This is one of the two protocols you'll actually configure and
- harden in this week's lab.

**සිංහලෙන්:** **OSPF: Open Shortest Path First** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FUNDAMENTALS
- Type: link-state. Every router builds a full map of the network topology (within its area) and calculates the best path
- itself, rather than trusting a neighbor's summary.
- Organised into areas for scalability, with Area 0 (the backbone) connecting all others.

**🧠 Memory Tip:** Remember **OSPF: Open Shortest Path First** by linking its purpose → mechanism → result.

### OSPF: Metric and Messages (Slide 9)

**Exam Answer:** FUNDAMENTALS.

**Explanation:**

- FUNDAMENTALS
- Metric: cost, calculated from interface bandwidth (a reference bandwidth divided by the interface's actual
- bandwidth). Faster links get a lower cost, so OSPF's path selection reflects real link speed, unlike RIP's flat hop count.
- Messages: Hello (discovers and maintains neighbor relationships), Database Description or DBD (summarises the link-
- state database during initial sync), Link State Request or LSR (asks for missing details), Link State Update or LSU
- (carries the actual Link State Advertisements), and Link State Acknowledgment or LSAck.
- Transport: runs directly over IP , protocol number 89 (not over UDP or TCP), using multicast addresses 224.0.0.5 (all
- OSPF routers) and 224.0.0.6 (designated routers).
- Security angle: because Hello packets are how OSPF forms a neighbor relationship in the first place, that's exactly the
- message MD5 authentication has to protect before any topology information is ever exchanged.

**සිංහලෙන්:** **OSPF: Metric and Messages** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FUNDAMENTALS
- Metric: cost, calculated from interface bandwidth (a reference bandwidth divided by the interface's actual
- bandwidth). Faster links get a lower cost, so OSPF's path selection reflects real link speed, unlike RIP's flat hop count.
- Messages: Hello (discovers and maintains neighbor relationships), Database Description or DBD (summarises the link-

**🧠 Memory Tip:** Remember **OSPF: Metric and Messages** by linking its purpose → mechanism → result.

### EIGRP: Enhanced Interior Gateway Routing Protocol (Slide 10)

**Exam Answer:** FUNDAMENTALS.

**Explanation:**

- FUNDAMENTALS
- Type: advanced distance-vector (Cisco calls it ‘hybrid’). Uses the DUAL algorithm to converge faster than classic
- distance-vector protocols like RIP , while staying simpler to configure than OSPF.
- Metric factors in bandwidth and delay, not just hop count, giving more realistic path selection.
- Also supports MD5 authentication between neighbors: the second protocol you'll configure and harden this week.

**සිංහලෙන්:** **EIGRP: Enhanced Interior Gateway Routing Protocol** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FUNDAMENTALS
- Type: advanced distance-vector (Cisco calls it ‘hybrid’). Uses the DUAL algorithm to converge faster than classic
- distance-vector protocols like RIP , while staying simpler to configure than OSPF.
- Metric factors in bandwidth and delay, not just hop count, giving more realistic path selection.

**🧠 Memory Tip:** Remember **EIGRP: Enhanced Interior Gateway Routing Protocol** by linking its purpose → mechanism → result.

### EIGRP: Metric and Messages (Slide 11)

**Exam Answer:** FUNDAMENTALS.

**Explanation:**

- FUNDAMENTALS
- Metric: a composite value combining bandwidth and delay by default (reliability and load are also part of the formula
- but disabled by default). This gives EIGRP a more realistic picture of path quality than a simple hop count.
- Messages: Hello (maintains neighbor adjacency, similar role to OSPF's), Update (carries actual routing information),
- Query and Reply (used by the DUAL algorithm to find a new loop-free path when a route fails), and Acknowledgment.
- Transport: runs directly over IP , protocol number 88, using multicast address 224.0.0.10.
- Security angle: DUAL's Query/Reply exchange is exactly what an attacker's false advertisements interact with during
- Routing Table Poisoning, since a convincing false route can trigger the same recalculation process a genuine link
- failure would.

**සිංහලෙන්:** **EIGRP: Metric and Messages** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FUNDAMENTALS
- Metric: a composite value combining bandwidth and delay by default (reliability and load are also part of the formula
- but disabled by default). This gives EIGRP a more realistic picture of path quality than a simple hop count.
- Messages: Hello (maintains neighbor adjacency, similar role to OSPF's), Update (carries actual routing information),

**🧠 Memory Tip:** Remember **EIGRP: Metric and Messages** by linking its purpose → mechanism → result.

### BGP: Border Gateway Protocol (Slide 12)

**Exam Answer:** FUNDAMENTALS.

**Explanation:**

- FUNDAMENTALS
- Type: path-vector. The only exterior gateway protocol in this list, used to route between Autonomous Systems (AS),
- not within one. This is the protocol that holds the entire Internet together.
- A router advertises which prefixes (address blocks) it can reach and via which AS path; neighbors largely take that
- advertisement on trust.
- Supports MD5 authentication (a password per neighbor session), but Packet Tracer's BGP support is limited enough
- that we won't rely on configuring it hands-on this week.

**සිංහලෙන්:** **BGP: Border Gateway Protocol** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FUNDAMENTALS
- Type: path-vector. The only exterior gateway protocol in this list, used to route between Autonomous Systems (AS),
- not within one. This is the protocol that holds the entire Internet together.
- A router advertises which prefixes (address blocks) it can reach and via which AS path; neighbors largely take that

**🧠 Memory Tip:** Remember **BGP: Border Gateway Protocol** by linking its purpose → mechanism → result.

### BGP: Metric and Messages (Slide 13)

**Exam Answer:** FUNDAMENTALS.

**Explanation:**

- FUNDAMENTALS
- Metric: BGP doesn't use a single simple metric the way the other three do. Path selection runs through an ordered list
- of path attributes (weight, local preference, AS-path length, origin, and others), with AS-path length being the
- simplest to reason about: a shorter path through fewer Autonomous Systems is generally preferred.
- Messages: OPEN (establishes a session with a neighbor), UPDATE (advertises new routes or withdraws ones no longer
- valid, exactly the message type involved in a prefix hijack), KEEPALIVE (confirms the session is still alive), and
- NOTIFICATION (reports an error and closes the session).
- Transport: unlike the other three protocols, BGP runs over TCP , port 179, rather than directly over IP or UDP . This is
- also why BGP's MD5 authentication is technically a TCP-level protection (an MD5 signature carried in the TCP header),
- not a routing-protocol-level one.
- Security angle: the UPDATE message is the entire attack surface for prefix hijacking. Whoever can get an UPDATE
- accepted, truthfully or not, controls where that traffic goes next.

**සිංහලෙන්:** **BGP: Metric and Messages** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FUNDAMENTALS
- Metric: BGP doesn't use a single simple metric the way the other three do. Path selection runs through an ordered list
- of path attributes (weight, local preference, AS-path length, origin, and others), with AS-path length being the
- simplest to reason about: a shorter path through fewer Autonomous Systems is generally preferred.

**🧠 Memory Tip:** Remember **BGP: Metric and Messages** by linking its purpose → mechanism → result.

### The Four Protocols at a Glance (Slide 14)

**Exam Answer:** FUNDAMENTALS.

**Explanation:**

- FUNDAMENTALS
- Protocol Type Metric Transport Authentication
- RIP Distance-vector Hop count (max 15) UDP 520 Optional, rarely enabled
- OSPF Link-state Cost (bandwidth-based) IP protocol 89 MD5, well supported
- EIGRP Advanced distance-vector Bandwidth + delay composite IP protocol 88 MD5, well supported
- BGP Path-vector AS-path length + attributes TCP 179 MD5 possible, limited adoption
- Notice BGP is the only one running over TCP rather than directly over IP or UDP, which is exactly why its MD5 authentication works differently to the others.

**සිංහලෙන්:** **The Four Protocols at a Glance** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FUNDAMENTALS
- Protocol Type Metric Transport Authentication
- RIP Distance-vector Hop count (max 15) UDP 520 Optional, rarely enabled
- OSPF Link-state Cost (bandwidth-based) IP protocol 89 MD5, well supported

**🧠 Memory Tip:** Remember **The Four Protocols at a Glance** by linking its purpose → mechanism → result.

### Why Routing Trust Is Exploitable (Slide 15)

**Exam Answer:** FUNDAMENTALS.

**Explanation:**

- FUNDAMENTALS
- Same theme as every week so far: by default, none of these protocols verify that a neighbor advertising routes is
- actually authorised to do so.
- A router that accepts a routing update has no built-in way to check whether the advertised route is truthful, current,
- or even physically plausible.
- The consequences scale with the protocol's reach: a bad RIP route affects one small network, while a bad BGP
- announcement can affect the global Internet, as today's real-world example will show.

**සිංහලෙන්:** **Why Routing Trust Is Exploitable** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FUNDAMENTALS
- Same theme as every week so far: by default, none of these protocols verify that a neighbor advertising routes is
- actually authorised to do so.
- A router that accepts a routing update has no built-in way to check whether the advertised route is truthful, current,

**🧠 Memory Tip:** Remember **Why Routing Trust Is Exploitable** by linking its purpose → mechanism → result.

### Routing Attacks (Slide 16)

**Exam Answer:** Five ways trust in a routing protocol can be abused.

**Explanation:**

- Five ways trust in a routing protocol can be abused

**සිංහලෙන්:** **Routing Attacks** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Five ways trust in a routing protocol can be abused

**🧠 Memory Tip:** Remember **Routing Attacks** by linking its purpose → mechanism → result.

### Five Attacks at a Glance (Slide 17)

**Exam Answer:** ATTACKS OVERVIEW.

**Explanation:**

- ATTACKS OVERVIEW
- Attack What it targets
- Routing Table Poisoning Injecting false routes into a distance-vector protocol
- Unauthorised Route Injection A rogue router joining the routing domain uninvited
- Route/Prefix Hijacking Advertising ownership of address space that isn't yours (BGP)
- Blackhole / Sinkhole Attack Redirecting traffic to a dead end or attacker-controlled device
- Routing DoS / Instability Attack Flooding updates to force constant recalculation

**සිංහලෙන්:** **Five Attacks at a Glance** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACKS OVERVIEW
- Attack What it targets
- Routing Table Poisoning Injecting false routes into a distance-vector protocol
- Unauthorised Route Injection A rogue router joining the routing domain uninvited

**🧠 Memory Tip:** Remember **Five Attacks at a Glance** by linking its purpose → mechanism → result.

### Routing Table Poisoning: Overview & Technique (Slide 18)

**Exam Answer:** ATTACK 1.

**Explanation:**

- ATTACK 1
- Overview: the attacker injects false route advertisements into a distance-vector protocol, convincing routers to
- update their tables with incorrect paths.
- Vulnerability exploited: distance-vector protocols like RIP propagate route information hop-by-hop based on what a
- neighbor claims, with no independent way to verify the claim.
- Technique: a compromised or rogue device connected to the network advertises a very attractive-looking (low hop
- count) but false route to a target network, and legitimate routers propagate it further.
- Impact: traffic intended for the real destination gets misrouted, enabling denial of service, interception, or both,
- depending on where the false route actually points.

**සිංහලෙන්:** **Routing Table Poisoning: Overview & Technique** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACK 1
- Overview: the attacker injects false route advertisements into a distance-vector protocol, convincing routers to
- update their tables with incorrect paths.
- Vulnerability exploited: distance-vector protocols like RIP propagate route information hop-by-hop based on what a

**🧠 Memory Tip:** Remember **Routing Table Poisoning: Overview & Technique** by linking its purpose → mechanism → result.

### Routing Table Poisoning: Mitigation (Slide 19)

**Exam Answer:** ATTACK 1.

**Explanation:**

- ATTACK 1
- Route authentication (MD5) on neighbor relationships stops an unauthenticated device from having its
- advertisements accepted at all.
- Route filtering / distribute-lists: explicitly define which routes are acceptable to learn or advertise on a given
- interface, rejecting anything implausible.
- Passive-interface on any interface that doesn't need to participate in the routing protocol at all removes the attack
- surface outright on those links.

**සිංහලෙන්:** **Routing Table Poisoning: Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACK 1
- Route authentication (MD5) on neighbor relationships stops an unauthenticated device from having its
- advertisements accepted at all.
- Route filtering / distribute-lists: explicitly define which routes are acceptable to learn or advertise on a given

**🧠 Memory Tip:** Remember **Routing Table Poisoning: Mitigation** by linking its purpose → mechanism → result.

### Unauthorised Route Injection: Overview & Technique (Slide 20)

**Exam Answer:** ATTACK 2.

**Explanation:**

- ATTACK 2
- Overview: an attacker connects a rogue router (or a device impersonating one) directly into the routing domain and
- forms a full neighbor relationship, not just a single false advertisement.
- Vulnerability exploited: without authentication, any device speaking the right routing protocol on the right network
- segment can become a fully trusted neighbor.
- Technique: the rogue router advertises itself as a legitimate participant, then either injects false routes continuously
- or simply gains visibility into the entire routing domain's topology.
- Impact: broader and more persistent than a single poisoning attempt: the attacker has an ongoing foothold, not a
- one-time injection.

**සිංහලෙන්:** **Unauthorised Route Injection: Overview & Technique** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACK 2
- Overview: an attacker connects a rogue router (or a device impersonating one) directly into the routing domain and
- forms a full neighbor relationship, not just a single false advertisement.
- Vulnerability exploited: without authentication, any device speaking the right routing protocol on the right network

**🧠 Memory Tip:** Remember **Unauthorised Route Injection: Overview & Technique** by linking its purpose → mechanism → result.

### Unauthorised Route Injection: Mitigation (Slide 21)

**Exam Answer:** ATTACK 2.

**Explanation:**

- ATTACK 2
- Neighbor authentication (MD5) is the direct fix: a rogue device without the correct key simply cannot form a neighbor
- relationship in the first place.
- Passive-interface on access-layer and other non-router-facing interfaces prevents a rogue device plugged into the
- wrong port from ever seeing routing traffic at all.
- Physical port security (recall Week 3) is a genuine complementary control here. If the rogue device can't reach a
- routing-capable interface physically, it can't attempt this attack regardless of protocol-level defenses.

**සිංහලෙන්:** **Unauthorised Route Injection: Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACK 2
- Neighbor authentication (MD5) is the direct fix: a rogue device without the correct key simply cannot form a neighbor
- relationship in the first place.
- Passive-interface on access-layer and other non-router-facing interfaces prevents a rogue device plugged into the

**🧠 Memory Tip:** Remember **Unauthorised Route Injection: Mitigation** by linking its purpose → mechanism → result.

### Route/Prefix Hijacking: Overview & Technique (Slide 22)

**Exam Answer:** ATTACK 3.

**Explanation:**

- ATTACK 3
- Overview: an AS advertises a route for an IP prefix it doesn't actually own or isn't authorised to originate. A BGP-
- specific attack, given BGP is what governs address space ownership across the Internet.
- Vulnerability exploited: BGP has no built-in mechanism to verify that an AS advertising a prefix is its legitimate owner.
- Neighbors, and their neighbors in turn, largely accept advertisements on trust.
- Technique: the attacker (or a misconfigured legitimate network) announces a route for someone else's address block,
- often a more specific prefix, since BGP prefers the most specific match available.
- Impact: traffic meant for the real owner gets redirected globally, not just locally, exactly what happened in a well-
- documented real-world incident, next.

**සිංහලෙන්:** **Route/Prefix Hijacking: Overview & Technique** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACK 3
- Overview: an AS advertises a route for an IP prefix it doesn't actually own or isn't authorised to originate. A BGP-
- specific attack, given BGP is what governs address space ownership across the Internet.
- Vulnerability exploited: BGP has no built-in mechanism to verify that an AS advertising a prefix is its legitimate owner.

**🧠 Memory Tip:** Remember **Route/Prefix Hijacking: Overview & Technique** by linking its purpose → mechanism → result.

### Real-World Example: The 2008 YouTube Hijack (Slide 23)

**Exam Answer:** ATTACK 3.

**Explanation:**

- ATTACK 3
- On 24 February 2008, Pakistan Telecom (AS17557) was ordered by its government to block YouTube domestically, and
- attempted this by advertising a route for part of YouTube's address block (208.65.153.0/24, a more specific slice of
- YouTube's actual 208.65.152.0/22).
- This was only ever meant to be visible inside Pakistan, but Pakistan Telecom's upstream provider, PCCW (AS3491), did
- not validate the advertisement and propagated it to the rest of the Internet.
- Because BGP prefers more specific routes, most of the global Internet started sending YouTube-bound traffic to
- Pakistan Telecom instead, effectively taking YouTube offline worldwide for roughly two hours, until PCCW
- disconnected Pakistan Telecom.
- This wasn't even a deliberate global attack. It was a local censorship attempt with no malicious intent to hijack
- anything outside Pakistan. That's exactly what makes it such a powerful illustration of how little verification BGP does
- by default.

**සිංහලෙන්:** **Real-World Example: The 2008 YouTube Hijack** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACK 3
- On 24 February 2008, Pakistan Telecom (AS17557) was ordered by its government to block YouTube domestically, and
- attempted this by advertising a route for part of YouTube's address block (208.65.153.0/24, a more specific slice of
- YouTube's actual 208.65.152.0/22).

**🧠 Memory Tip:** Remember **Real-World Example: The 2008 YouTube Hijack** by linking its purpose → mechanism → result.

### Route/Prefix Hijacking: Mitigation (Slide 24)

**Exam Answer:** ATTACK 3.

**Explanation:**

- ATTACK 3
- RPKI (Resource Public Key Infrastructure) lets an address block's legitimate owner cryptographically sign a Route
- Origin Authorisation (ROA), so other networks can verify an advertisement before accepting it. This is the real-world
- fix that emerged after incidents like the YouTube hijack.
- Route filtering at provider boundaries: an upstream provider should only accept the specific prefixes it has agreed a
- customer is authorised to announce, exactly the validation PCCW skipped in 2008.
- This is theory-only for our purposes: RPKI and provider-level BGP filtering aren't things we can configure in Packet
- Tracer, but understanding why they exist is directly relevant to LO2's evaluation skill.

**සිංහලෙන්:** **Route/Prefix Hijacking: Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACK 3
- RPKI (Resource Public Key Infrastructure) lets an address block's legitimate owner cryptographically sign a Route
- Origin Authorisation (ROA), so other networks can verify an advertisement before accepting it. This is the real-world
- fix that emerged after incidents like the YouTube hijack.

**🧠 Memory Tip:** Remember **Route/Prefix Hijacking: Mitigation** by linking its purpose → mechanism → result.

### Blackhole / Sinkhole Attack: Overview & Technique (Slide 25)

**Exam Answer:** ATTACK 4.

**Explanation:**

- ATTACK 4
- Overview: the attacker manipulates routing so that traffic for a target is directed to a dead end (blackholed: silently
- dropped) or to a device they control (sinkholed: captured for analysis or further attack).
- Vulnerability exploited: the same lack of route verification as the other attacks in this section. The difference here is
- entirely in what the attacker does with the misdirected traffic, not in how they achieve the misdirection.
- Technique: often achieved via the same mechanisms as poisoning or unauthorised injection, just aimed specifically at
- creating a non-existent or attacker-controlled next hop for a target network.
- Impact: a blackhole is a denial of service; a sinkhole additionally lets the attacker inspect (and potentially tamper
- with) traffic before optionally forwarding it on, which can make the attack harder to notice.

**සිංහලෙන්:** **Blackhole / Sinkhole Attack: Overview & Technique** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACK 4
- Overview: the attacker manipulates routing so that traffic for a target is directed to a dead end (blackholed: silently
- dropped) or to a device they control (sinkholed: captured for analysis or further attack).
- Vulnerability exploited: the same lack of route verification as the other attacks in this section. The difference here is

**🧠 Memory Tip:** Remember **Blackhole / Sinkhole Attack: Overview & Technique** by linking its purpose → mechanism → result.

### Blackhole / Sinkhole Attack: Mitigation (Slide 26)

**Exam Answer:** ATTACK 4.

**Explanation:**

- ATTACK 4
- The same core defenses apply as for the attacks that enable it: route authentication, route filtering, and passive-
- interface all reduce the attacker's ability to influence next-hop selection in the first place.
- Monitoring for unexpected traffic drops or unusual latency/path changes is a useful detective control: a legitimate
- destination silently becoming unreachable is a strong signal worth alerting on.
- This attack is a good reminder that a single root cause (unverified routing trust) can be aimed at different outcomes,
- echoing Week 3's multi-function attack discussion.

**සිංහලෙන්:** **Blackhole / Sinkhole Attack: Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACK 4
- The same core defenses apply as for the attacks that enable it: route authentication, route filtering, and passive-
- interface all reduce the attacker's ability to influence next-hop selection in the first place.
- Monitoring for unexpected traffic drops or unusual latency/path changes is a useful detective control: a legitimate

**🧠 Memory Tip:** Remember **Blackhole / Sinkhole Attack: Mitigation** by linking its purpose → mechanism → result.

### Routing DoS / Instability Attack: Overview & Technique (Slide 27)

**Exam Answer:** ATTACK 5.

**Explanation:**

- ATTACK 5
- Overview: rather than trying to redirect traffic anywhere specific, the attacker floods the network with routing
- updates to force constant recalculation, degrading or breaking routing entirely.
- Vulnerability exploited: routers must process every routing update they receive from a trusted neighbor. Without
- authentication, an attacker can generate a high volume of updates cheaply.
- Technique: repeatedly advertising and withdrawing routes, or flooding a high volume of route changes, keeps
- affected routers permanently busy recalculating instead of forwarding traffic.
- Impact: a routing-layer denial of service, the same underlying goal as Week 4's STP DoS attack, just aimed at the
- routing protocol instead of the spanning tree.

**සිංහලෙන්:** **Routing DoS / Instability Attack: Overview & Technique** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACK 5
- Overview: rather than trying to redirect traffic anywhere specific, the attacker floods the network with routing
- updates to force constant recalculation, degrading or breaking routing entirely.
- Vulnerability exploited: routers must process every routing update they receive from a trusted neighbor. Without

**🧠 Memory Tip:** Remember **Routing DoS / Instability Attack: Overview & Technique** by linking its purpose → mechanism → result.

### Routing DoS / Instability Attack: Mitigation (Slide 28)

**Exam Answer:** ATTACK 5.

**Explanation:**

- ATTACK 5
- Route authentication remains the primary fix: an unauthenticated flood of updates is simply rejected before it can
- force any recalculation at all.
- Route dampening (suppressing a route that flaps repeatedly, so it's temporarily ignored instead of triggering fresh
- recalculation every time) is a standard operational defense on protocols like BGP .
- Rate-limiting how frequently routing updates are processed provides a backstop even when authentication is
- somehow bypassed or misconfigured.

**සිංහලෙන්:** **Routing DoS / Instability Attack: Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACK 5
- Route authentication remains the primary fix: an unauthenticated flood of updates is simply rejected before it can
- force any recalculation at all.
- Route dampening (suppressing a route that flaps repeatedly, so it's temporarily ignored instead of triggering fresh

**🧠 Memory Tip:** Remember **Routing DoS / Instability Attack: Mitigation** by linking its purpose → mechanism → result.

### Which Attacks Apply to Which Protocols (Slide 29)

**Exam Answer:** ATTACKS OVERVIEW.

**Explanation:**

- ATTACKS OVERVIEW
- Attack RIP OSPF EIGRP BGP
- Routing Table
- Poisoning
- False Response,
- low hop count
- Rogue LSA
- flooded domain-wide
- False Update,
- attractive metric
- False UPDATE,
- favourable attributes
- Unauthorised
- Route Injection
- No adjacency
- needed, just send
- Hello-based
- adjacency, then flood
- Hello-based
- adjacency, then send
- Must spoof a
- configured neighbor
- Route/Prefix
- Hijacking
- Local scope
- only
- Local scope
- only
- Local scope
- only
- Primary case:
- UPDATE claims a prefix
- Blackhole /
- Sinkhole
- Via poisoning
- above
- Via poisoning
- above
- Via poisoning
- above
- Via hijacking
- above
- Routing DoS /
- Instability
- Response flood,
- repeated recalc
- LSA flood/flap,
- repeated SPF runs
- Query flood,
- repeated DUAL runs
- Route flapping,
- global recalc
- Prefix hijacking is the one attack that's genuinely BGP-specific; the other four have an analog on every protocol, just via a different exact mechanism.

**සිංහලෙන්:** **Which Attacks Apply to Which Protocols** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACKS OVERVIEW
- Attack RIP OSPF EIGRP BGP
- Routing Table
- Poisoning

**🧠 Memory Tip:** Remember **Which Attacks Apply to Which Protocols** by linking its purpose → mechanism → result.

### Defenses in Detail (Slide 30)

**Exam Answer:** The mechanisms behind this week's mitigations.

**Explanation:**

- The mechanisms behind this week's mitigations

**සිංහලෙන්:** **Defenses in Detail** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- The mechanisms behind this week's mitigations

**🧠 Memory Tip:** Remember **Defenses in Detail** by linking its purpose → mechanism → result.

### A Note on Scope (Slide 31)

**Exam Answer:** DEFENSES.

**Explanation:**

- DEFENSES
- From here, implementation detail focuses specifically on two protocols: OSPF and EIGRP .
- This isn't an arbitrary choice. These are the two protocols with confirmed, reliable MD5 authentication support in
- Packet Tracer, which is exactly what you'll configure hands-on in this week's lab.
- RIPv2's authentication support is inconsistent across Packet Tracer versions, and BGP's overall protocol support in
- Packet Tracer is limited enough that we won't rely on it. Both remain relevant in theory, but neither is something we'll
- configure and verify this week.
- Where a defense mechanism behaves differently between OSPF and EIGRP specifically, the following slides call that
- out explicitly, since spotting that kind of difference is exactly the LO2 evaluation skill this module is building.

**සිංහලෙන්:** **A Note on Scope** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEFENSES
- From here, implementation detail focuses specifically on two protocols: OSPF and EIGRP .
- This isn't an arbitrary choice. These are the two protocols with confirmed, reliable MD5 authentication support in
- Packet Tracer, which is exactly what you'll configure hands-on in this week's lab.

**🧠 Memory Tip:** Remember **A Note on Scope** by linking its purpose → mechanism → result.

### Neighbor Authentication (MD5) (Slide 32)

**Exam Answer:** DEFENSES.

**Explanation:**

- DEFENSES
- The core defense across almost every attack this week: routers only form a neighbor relationship, and only accept
- routing updates, from a device that can prove it holds the correct shared key.
- This is exactly what you'll configure hands-on in this week's lab, on both OSPF and EIGRP .

**සිංහලෙන්:** **Neighbor Authentication (MD5)** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEFENSES
- The core defense across almost every attack this week: routers only form a neighbor relationship, and only accept
- routing updates, from a device that can prove it holds the correct shared key.
- This is exactly what you'll configure hands-on in this week's lab, on both OSPF and EIGRP .

**🧠 Memory Tip:** Remember **Neighbor Authentication (MD5)** by linking its purpose → mechanism → result.

### Authentication: OSPF vs EIGRP Implementation (Slide 33)

**Exam Answer:** DEFENSES.

**Explanation:**

- DEFENSES
- OSPF: authentication is enabled per area (area 0 authentication message-digest) or per interface, with a single MD5
- key configured directly on that interface. Straightforward, but only one active key at a time.
- EIGRP: authentication requires defining a key chain first (a named object holding one or more keys), then applying
- both the authentication mode and the key chain to an interface. More setup steps, but key chains support multiple
- keys with defined lifetimes, enabling scheduled key rotation without downtime.
- The LO2 takeaway: EIGRP's extra configuration complexity buys a real operational capability (key rotation) that OSPF's
- simpler mechanism doesn't offer out of the box. That's a genuine cost/capability trade-off, not just implementation
- trivia.

**සිංහලෙන්:** **Authentication: OSPF vs EIGRP Implementation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEFENSES
- OSPF: authentication is enabled per area (area 0 authentication message-digest) or per interface, with a single MD5
- key configured directly on that interface. Straightforward, but only one active key at a time.
- EIGRP: authentication requires defining a key chain first (a named object holding one or more keys), then applying

**🧠 Memory Tip:** Remember **Authentication: OSPF vs EIGRP Implementation** by linking its purpose → mechanism → result.

### Passive-Interface (Slide 34)

**Exam Answer:** DEFENSES.

**Explanation:**

- DEFENSES
- Stops a router from sending (and in most implementations, also processing received) routing protocol traffic out a
- specific interface, while that interface's network is still advertised to the rest of the routing domain.
- Ideal for interfaces facing end users or other non-router devices. There's no legitimate reason for a routing update to
- arrive from a printer or a PC.
- A simple, low-cost control that directly removes the attack surface on interfaces that never needed to participate in
- routing in the first place.
- OSPF and EIGRP implementation is essentially identical here: the passive-interface command sits under the routing
- process and names the interface, in both cases. This is one control where there's no meaningful difference to
- evaluate between the two.

**සිංහලෙන්:** **Passive-Interface** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEFENSES
- Stops a router from sending (and in most implementations, also processing received) routing protocol traffic out a
- specific interface, while that interface's network is still advertised to the rest of the routing domain.
- Ideal for interfaces facing end users or other non-router devices. There's no legitimate reason for a routing update to

**🧠 Memory Tip:** Remember **Passive-Interface** by linking its purpose → mechanism → result.

### Route Filtering / Distribute-Lists (Slide 35)

**Exam Answer:** DEFENSES.

**Explanation:**

- DEFENSES
- Explicitly defines which specific routes are acceptable to learn from, or advertise to, a given neighbor, rather than
- trusting everything a neighbor sends.
- Directly stops implausible or out-of-scope advertisements even from an authenticated neighbor. Authentication
- proves who's talking; filtering controls what they're allowed to say.
- This is exactly the control PCCW should have had in place in the 2008 YouTube hijack: filtering Pakistan Telecom's
- advertisements to only the prefixes they were actually authorised to announce.

**සිංහලෙන්:** **Route Filtering / Distribute-Lists** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEFENSES
- Explicitly defines which specific routes are acceptable to learn from, or advertise to, a given neighbor, rather than
- trusting everything a neighbor sends.
- Directly stops implausible or out-of-scope advertisements even from an authenticated neighbor. Authentication

**🧠 Memory Tip:** Remember **Route Filtering / Distribute-Lists** by linking its purpose → mechanism → result.

### Route Filtering: A Protocol-Type Caveat (Slide 36)

**Exam Answer:** DEFENSES.

**Explanation:**

- DEFENSES
- EIGRP: because it's distance-vector, a distribute-list directly controls what actually goes into the Update messages
- sent to, or accepted from, a neighbor. Filtering here genuinely stops a route from propagating further.
- OSPF: because it's link-state, every router in an area needs an identical copy of the link-state database to calculate
- correct paths. A distribute-list on OSPF only filters what gets installed into the local routing table, not what's flooded
- on to other routers via LSAs.
- The LO2 takeaway: the same control name (‘distribute-list’) does a meaningfully different job depending on the
- protocol's type. On OSPF, actually stopping propagation needs a different tool (e.g. an area filter-list at an area
- boundary), not a plain distribute-list.

**සිංහලෙන්:** **Route Filtering: A Protocol-Type Caveat** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEFENSES
- EIGRP: because it's distance-vector, a distribute-list directly controls what actually goes into the Update messages
- sent to, or accepted from, a neighbor. Filtering here genuinely stops a route from propagating further.
- OSPF: because it's link-state, every router in an area needs an identical copy of the link-state database to calculate

**🧠 Memory Tip:** Remember **Route Filtering: A Protocol-Type Caveat** by linking its purpose → mechanism → result.

### RPKI (Resource Public Key Infrastructure) (Slide 37)

**Exam Answer:** DEFENSES.

**Explanation:**

- DEFENSES
- A cryptographic system letting the legitimate holder of an IP address block publish a signed Route Origin
- Authorisation (ROA), stating which AS is allowed to originate routes for it.
- Other networks can then validate a BGP advertisement against the ROA before accepting it, directly closing the gap
- that made the YouTube hijack possible.
- BGP-specific, and adopted unevenly across the real Internet even today. Theory-only for this module, since it isn't
- something Packet Tracer can demonstrate.

**සිංහලෙන්:** **RPKI (Resource Public Key Infrastructure)** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEFENSES
- A cryptographic system letting the legitimate holder of an IP address block publish a signed Route Origin
- Authorisation (ROA), stating which AS is allowed to originate routes for it.
- Other networks can then validate a BGP advertisement against the ROA before accepting it, directly closing the gap

**🧠 Memory Tip:** Remember **RPKI (Resource Public Key Infrastructure)** by linking its purpose → mechanism → result.

### RPKI: How the Trust Chain Works (Slide 38)

**Exam Answer:** DEFENSES.

**Explanation:**

- DEFENSES
- RIR
- (e.g. RIPE NCC)
- Resource
- Certificate ROA RPKIRepository
- Trust anchor Issued to the prefix holder Signed by prefix holder Published, downloadable
- RIRs (Regional Internet Registries, e.g. RIPE NCC, ARIN, APNIC) act as trust anchors. Each one issues an X.509 resource certificate that
- cryptographically binds an IP prefix to whichever organisation was legitimately allocated it.
- The prefix holder then creates and signs a Route Origin Authorisation (ROA): a small, specific statement declaring exactly which AS number is
- authorised to originate routes for that prefix, and the maximum prefix length allowed.
- ROAs are published into a distributed set of RPKI repositories that any network operator can download and cryptographically verify, using the RIR's
- certificate as the root of trust.
- This is genuinely different from just trusting a BGP announcement: a ROA is a signed, independently verifiable statement madein advance, not
- something an attacker can fake without the real prefix holder's private key.

**සිංහලෙන්:** **RPKI: How the Trust Chain Works** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEFENSES
- RIR
- (e.g. RIPE NCC)
- Resource

**🧠 Memory Tip:** Remember **RPKI: How the Trust Chain Works** by linking its purpose → mechanism → result.

### RPKI: Route Origin Validation in Action (Slide 39)

**Exam Answer:** DEFENSES.

**Explanation:**

- DEFENSES
- A router (or dedicated validator software feeding it) checks every incoming BGP announcement against its local cache of validated ROAs,
- producing one of three outcomes.
- Valid
- Announced AS and prefix length both match a ROA
- Accepted normally
- Invalid
- A ROA exists, but the AS or length doesn't match it
- Rejected. This is exactly what a hijack looks like
- NotFound
- No ROA exists for this prefix at all
- Treated as normal, unvalidated routing
- Applied to 2008: had PCCW validated Pakistan Telecom's announcement of 208.65.153.0/24 against a ROA showing AS36561 as the o nly authorised
- origin, the announcement would have come back Invalid and simply been dropped, never reaching the rest of the Internet.
- Two honest limitations: RPKI only validates the origin AS, not the full AS-path, so it doesn't stop every possible manipulation. And it only works where
- operators have both registered ROAs and actually enabled validation, adoption remains uneven across the real Internet even today.

**සිංහලෙන්:** **RPKI: Route Origin Validation in Action** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEFENSES
- A router (or dedicated validator software feeding it) checks every incoming BGP announcement against its local cache of validated ROAs,
- producing one of three outcomes.
- Valid

**🧠 Memory Tip:** Remember **RPKI: Route Origin Validation in Action** by linking its purpose → mechanism → result.

### Attack Summary: Vulnerability, Exploit, Impact, and Mitigation (Slide 40)

**Exam Answer:** ATTACKS OVERVIEW.

**Explanation:**

- ATTACKS OVERVIEW
- Attack Vulnerability Exploit Impact(s) Mitigations
- Routing Table
- Poisoning
- No verification
- of neighbor route
- claims
- False advertisement
- with an attractive
- (low) metric
- Misrouted traffic;
- denial of service;
- interception
- MD5 authentication;
- route filtering;
- passive-interface
- Unauthorised
- Route Injection
- No authentication
- required to form
- a neighbor adjacency
- Rogue device joins
- as a full,
- trusted neighbor
- Persistent foothold;
- topology visibility;
- ongoing false routes
- MD5 authentication;
- passive-interface;
- physical port security
- Route/Prefix
- Hijacking
- No verification of
- prefix ownership
- (BGP-specific)
- Advertise an
- unowned, often more
- specific, prefix
- Global traffic
- redirection; denial
- of service; interception
- RPKI; provider-level
- route filtering
- Blackhole /
- Sinkhole
- Same lack of route
- verification as
- poisoning/injection
- Redirect traffic via
- manipulated routing
- information
- Denial of service
- (blackhole); interception
- and tampering (sinkhole)
- MD5 authentication;
- filtering; passive-interface;
- traffic monitoring
- Routing DoS /
- Instability
- No authentication;
- must process every
- received update
- Flood routing updates,
- or repeatedly advertise
- and withdraw routes
- Router CPU exhaustion;
- network-wide DoS;
- unstable forwarding
- MD5 authentication;
- route dampening;
- rate-limiting

**සිංහලෙන්:** **Attack Summary: Vulnerability, Exploit, Impact, and Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACKS OVERVIEW
- Attack Vulnerability Exploit Impact(s) Mitigations
- Routing Table
- Poisoning

**🧠 Memory Tip:** Remember **Attack Summary: Vulnerability, Exploit, Impact, and Mitigation** by linking its purpose → mechanism → result.

### Full Mitigation Comparison (Slide 41)

**Exam Answer:** DEFENSES.

**Explanation:**

- DEFENSES
- Attack Primary mitigation
- Routing Table Poisoning Neighbor authentication (MD5), route filtering
- Unauthorised Route Injection Neighbor authentication (MD5), passive-interface
- Route/Prefix Hijacking RPKI, provider-level route filtering (theory only)
- Blackhole / Sinkhole Attack Same as injection/poisoning, plus traffic monitoring
- Routing DoS / Instability Attack Neighbor authentication (MD5), route dampening, rate-limiting

**සිංහලෙන්:** **Full Mitigation Comparison** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEFENSES
- Attack Primary mitigation
- Routing Table Poisoning Neighbor authentication (MD5), route filtering
- Unauthorised Route Injection Neighbor authentication (MD5), passive-interface

**🧠 Memory Tip:** Remember **Full Mitigation Comparison** by linking its purpose → mechanism → result.

### Layered Defense for Routing (Slide 42)

**Exam Answer:** DEFENSES.

**Explanation:**

- DEFENSES
- Notice how much weight neighbor authentication alone carries here: it's the single control that meaningfully
- addresses four of the five attacks covered today.
- But authentication alone doesn't stop everything: it proves who's talking, not that what they're saying is plausible.
- That's what filtering adds on top.
- Same layered-defense principle from every week so far: authentication, filtering, and passive-interface each close a
- different gap, and a real network needs more than one of them.

**සිංහලෙන්:** **Layered Defense for Routing** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEFENSES
- Notice how much weight neighbor authentication alone carries here: it's the single control that meaningfully
- addresses four of the five attacks covered today.
- But authentication alone doesn't stop everything: it proves who's talking, not that what they're saying is plausible.

**🧠 Memory Tip:** Remember **Layered Defense for Routing** by linking its purpose → mechanism → result.

### Summary (Slide 43)

**Exam Answer:** Routing protocols automate what would otherwise be manual configuration, but that automation runs entirely on trust between.

**Explanation:**

- Routing protocols automate what would otherwise be manual configuration, but that automation runs entirely on trust between
- neighbors.
- RIP , OSPF, EIGRP , and BGP each build that trust differently, but none of them verify it by default.
- Five attacks (poisoning, unauthorised injection, hijacking, blackhole/sinkhole, and routing DoS) all trace back to that same unverified
- trust, aimed at different outcomes.
- The 2008 YouTube hijack shows this isn't hypothetical: a local censorship attempt with no malicious global intent still took down a
- major service worldwide for two hours.
- Neighbor authentication (MD5) is this week's strongest single control, and the one you'll actually configure on OSPF and EIGRP in the
- lab.

**සිංහලෙන්:** **Summary** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Routing protocols automate what would otherwise be manual configuration, but that automation runs entirely on trust between
- neighbors.
- RIP , OSPF, EIGRP , and BGP each build that trust differently, but none of them verify it by default.
- Five attacks (poisoning, unauthorised injection, hijacking, blackhole/sinkhole, and routing DoS) all trace back to that same unverified

**🧠 Memory Tip:** Remember **Summary** by linking its purpose → mechanism → result.

### This Week's Lab & Tutorial (Slide 44)

**Exam Answer:** Lab (runs in the Week 6 session): configure and verify MD5 neighbor authentication on both OSPF and EIGRP in.

**Explanation:**

- Lab (runs in the Week 6 session): configure and verify MD5 neighbor authentication on both OSPF and EIGRP in
- Packet Tracer, the two protocols confirmed to support this reliably.
- Tutorial worksheet: study-notes-style questions covering the four protocols, all five attacks, and their mitigations. Use
- it to prep for the mid-semester test.

**සිංහලෙන්:** **This Week's Lab & Tutorial** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Lab (runs in the Week 6 session): configure and verify MD5 neighbor authentication on both OSPF and EIGRP in
- Packet Tracer, the two protocols confirmed to support this reliably.
- Tutorial worksheet: study-notes-style questions covering the four protocols, all five attacks, and their mitigations. Use
- it to prep for the mid-semester test.

**🧠 Memory Tip:** Remember **This Week's Lab & Tutorial** by linking its purpose → mechanism → result.


## 📊 Important Comparisons

| Comparison/topic | Source | Exam focus |
|---|---:|---|
| Routing Table Poisoning: Overview & Technique | Slide 18 | ATTACK 1. |
| Unauthorised Route Injection: Overview & Technique | Slide 20 | ATTACK 2. |
| Route/Prefix Hijacking: Overview & Technique | Slide 22 | ATTACK 3. |
| Blackhole / Sinkhole Attack: Overview & Technique | Slide 25 | ATTACK 4. |
| Routing DoS / Instability Attack: Overview & Technique | Slide 27 | ATTACK 5. |
| Authentication: OSPF vs EIGRP Implementation | Slide 33 | DEFENSES. |
| Attack Summary: Vulnerability, Exploit, Impact, and Mitigation | Slide 40 | ATTACKS OVERVIEW. |
| Full Mitigation Comparison | Slide 41 | DEFENSES. |
| Summary | Slide 43 | Routing protocols automate what would otherwise be manual configuration, but that automation runs entirely on trust between. |

## 🛠️ Practical Knowledge

### Why Routing Protocols Matter (Slide 5)

- FUNDAMENTALS
- Recall Week 1: a router forwards packets based on its routing table. Routing protocols exist so routers can build that
- table automatically, by exchanging information with their neighbors instead of relying on manual configuration alone.
- This automation is powerful at scale. Large networks and the Internet itself simply couldn't run on manually
- maintained routes.
- But it means every router is placing real trust in whatever its neighbors tell it. Everything in this lecture follows from
- asking: what happens when that trust is misplaced?

### OSPF: Open Shortest Path First (Slide 8)

- FUNDAMENTALS
- Type: link-state. Every router builds a full map of the network topology (within its area) and calculates the best path
- itself, rather than trusting a neighbor's summary.
- Organised into areas for scalability, with Area 0 (the backbone) connecting all others.
- Supports MD5 authentication between neighbors. This is one of the two protocols you'll actually configure and
- harden in this week's lab.

### BGP: Border Gateway Protocol (Slide 12)

- FUNDAMENTALS
- Type: path-vector. The only exterior gateway protocol in this list, used to route between Autonomous Systems (AS),
- not within one. This is the protocol that holds the entire Internet together.
- A router advertises which prefixes (address blocks) it can reach and via which AS path; neighbors largely take that
- advertisement on trust.
- Supports MD5 authentication (a password per neighbor session), but Packet Tracer's BGP support is limited enough
- that we won't rely on configuring it hands-on this week.

### Route/Prefix Hijacking: Overview & Technique (Slide 22)

- ATTACK 3
- Overview: an AS advertises a route for an IP prefix it doesn't actually own or isn't authorised to originate. A BGP-
- specific attack, given BGP is what governs address space ownership across the Internet.
- Vulnerability exploited: BGP has no built-in mechanism to verify that an AS advertising a prefix is its legitimate owner.
- Neighbors, and their neighbors in turn, largely accept advertisements on trust.
- Technique: the attacker (or a misconfigured legitimate network) announces a route for someone else's address block,
- often a more specific prefix, since BGP prefers the most specific match available.
- Impact: traffic meant for the real owner gets redirected globally, not just locally, exactly what happened in a well-
- documented real-world incident, next.

### A Note on Scope (Slide 31)

- DEFENSES
- From here, implementation detail focuses specifically on two protocols: OSPF and EIGRP .
- This isn't an arbitrary choice. These are the two protocols with confirmed, reliable MD5 authentication support in
- Packet Tracer, which is exactly what you'll configure hands-on in this week's lab.
- RIPv2's authentication support is inconsistent across Packet Tracer versions, and BGP's overall protocol support in
- Packet Tracer is limited enough that we won't rely on it. Both remain relevant in theory, but neither is something we'll
- configure and verify this week.
- Where a defense mechanism behaves differently between OSPF and EIGRP specifically, the following slides call that
- out explicitly, since spotting that kind of difference is exactly the LO2 evaluation skill this module is building.

### Neighbor Authentication (MD5) (Slide 32)

- DEFENSES
- The core defense across almost every attack this week: routers only form a neighbor relationship, and only accept
- routing updates, from a device that can prove it holds the correct shared key.
- This is exactly what you'll configure hands-on in this week's lab, on both OSPF and EIGRP .

### Authentication: OSPF vs EIGRP Implementation (Slide 33)

- DEFENSES
- OSPF: authentication is enabled per area (area 0 authentication message-digest) or per interface, with a single MD5
- key configured directly on that interface. Straightforward, but only one active key at a time.
- EIGRP: authentication requires defining a key chain first (a named object holding one or more keys), then applying
- both the authentication mode and the key chain to an interface. More setup steps, but key chains support multiple
- keys with defined lifetimes, enabling scheduled key rotation without downtime.
- The LO2 takeaway: EIGRP's extra configuration complexity buys a real operational capability (key rotation) that OSPF's
- simpler mechanism doesn't offer out of the box. That's a genuine cost/capability trade-off, not just implementation
- trivia.

### Passive-Interface (Slide 34)

- DEFENSES
- Stops a router from sending (and in most implementations, also processing received) routing protocol traffic out a
- specific interface, while that interface's network is still advertised to the rest of the routing domain.
- Ideal for interfaces facing end users or other non-router devices. There's no legitimate reason for a routing update to
- arrive from a printer or a PC.
- A simple, low-cost control that directly removes the attack surface on interfaces that never needed to participate in
- routing in the first place.
- OSPF and EIGRP implementation is essentially identical here: the passive-interface command sits under the routing
- process and names the interface, in both cases. This is one control where there's no meaningful difference to
- evaluate between the two.

### Route Filtering: A Protocol-Type Caveat (Slide 36)

- DEFENSES
- EIGRP: because it's distance-vector, a distribute-list directly controls what actually goes into the Update messages
- sent to, or accepted from, a neighbor. Filtering here genuinely stops a route from propagating further.
- OSPF: because it's link-state, every router in an area needs an identical copy of the link-state database to calculate
- correct paths. A distribute-list on OSPF only filters what gets installed into the local routing table, not what's flooded
- on to other routers via LSAs.
- The LO2 takeaway: the same control name (‘distribute-list’) does a meaningfully different job depending on the
- protocol's type. On OSPF, actually stopping propagation needs a different tool (e.g. an area filter-list at an area
- boundary), not a plain distribute-list.

### Summary (Slide 43)

- Routing protocols automate what would otherwise be manual configuration, but that automation runs entirely on trust between
- neighbors.
- RIP , OSPF, EIGRP , and BGP each build that trust differently, but none of them verify it by default.
- Five attacks (poisoning, unauthorised injection, hijacking, blackhole/sinkhole, and routing DoS) all trace back to that same unverified
- trust, aimed at different outcomes.
- The 2008 YouTube hijack shows this isn't hypothetical: a local censorship attempt with no malicious global intent still took down a
- major service worldwide for two hours.
- Neighbor authentication (MD5) is this week's strongest single control, and the one you'll actually configure on OSPF and EIGRP in the
- lab.

### This Week's Lab & Tutorial (Slide 44)

- Lab (runs in the Week 6 session): configure and verify MD5 neighbor authentication on both OSPF and EIGRP in
- Packet Tracer, the two protocols confirmed to support this reliably.
- Tutorial worksheet: study-notes-style questions covering the four protocols, all five attacks, and their mitigations. Use
- it to prep for the mid-semester test.

## ⭐ Important Exam Points

- ⭐ **Routing Protocol Fundamentals (Slide 4):** How routers learn to trust each other.
- ⭐ **Why Routing Protocols Matter (Slide 5):** FUNDAMENTALS.
- ⭐ **RIP: Routing Information Protocol (Slide 6):** FUNDAMENTALS.
- ⭐ **RIP: Metric and Messages (Slide 7):** FUNDAMENTALS.
- ⭐ **OSPF: Open Shortest Path First (Slide 8):** FUNDAMENTALS.
- ⭐ **OSPF: Metric and Messages (Slide 9):** FUNDAMENTALS.
- ⭐ **EIGRP: Enhanced Interior Gateway Routing Protocol (Slide 10):** FUNDAMENTALS.
- ⭐ **EIGRP: Metric and Messages (Slide 11):** FUNDAMENTALS.
- ⭐ **BGP: Border Gateway Protocol (Slide 12):** FUNDAMENTALS.
- ⭐ **BGP: Metric and Messages (Slide 13):** FUNDAMENTALS.
- ⭐ **The Four Protocols at a Glance (Slide 14):** FUNDAMENTALS.
- ⭐ **Why Routing Trust Is Exploitable (Slide 15):** FUNDAMENTALS.
- ⭐ **Routing Attacks (Slide 16):** Five ways trust in a routing protocol can be abused.
- ⭐ **Five Attacks at a Glance (Slide 17):** ATTACKS OVERVIEW.
- ⭐ **Routing Table Poisoning: Overview & Technique (Slide 18):** ATTACK 1.

## ❓ Possible Exam Questions

### MCQs

1. Which statement best matches **Routing Protocol Fundamentals**?
   - A. It is unrelated to network security.
   - B. How routers learn to trust each other.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

2. Which statement best matches **BGP: Border Gateway Protocol**?
   - A. It is unrelated to network security.
   - B. FUNDAMENTALS.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

3. Which statement best matches **Unauthorised Route Injection: Overview & Technique**?
   - A. It is unrelated to network security.
   - B. ATTACK 2.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

4. Which statement best matches **Routing DoS / Instability Attack: Mitigation**?
   - A. It is unrelated to network security.
   - B. ATTACK 5.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

5. Which statement best matches **Route Filtering: A Protocol-Type Caveat**?
   - A. It is unrelated to network security.
   - B. DEFENSES.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**


### Short Structured Questions

1. **Explain Routing Protocol Fundamentals.**
   - **Model answer:** How routers learn to trust each other.

2. **Explain BGP: Border Gateway Protocol.**
   - **Model answer:** FUNDAMENTALS.

3. **Explain Unauthorised Route Injection: Overview & Technique.**
   - **Model answer:** ATTACK 2.

4. **Explain Routing DoS / Instability Attack: Mitigation.**
   - **Model answer:** ATTACK 5.

5. **Explain Route Filtering: A Protocol-Type Caveat.**
   - **Model answer:** DEFENSES.


### Scenario-Based Question

**Scenario:** An organization must apply the concepts from **Routing Attacks and Defenses** to improve its network security. Identify the relevant mechanism or risk, explain the likely impact, and recommend a layered response.

**Model-answer approach:** Identify the asset and trust boundary; name the relevant protocol/control; explain the mechanism using the lecture terminology; state confidentiality, integrity, or availability impact; then recommend the matching prevention, detection, and verification steps from the slides.

## ⚡ Last-Minute Quick Revision

- **Routing Protocol Fundamentals:** How routers learn to trust each other.
- **Why Routing Protocols Matter:** FUNDAMENTALS.
- **RIP: Routing Information Protocol:** FUNDAMENTALS.
- **RIP: Metric and Messages:** FUNDAMENTALS.
- **OSPF: Open Shortest Path First:** FUNDAMENTALS.
- **OSPF: Metric and Messages:** FUNDAMENTALS.
- **EIGRP: Enhanced Interior Gateway Routing Protocol:** FUNDAMENTALS.
- **EIGRP: Metric and Messages:** FUNDAMENTALS.
- **BGP: Border Gateway Protocol:** FUNDAMENTALS.
- **BGP: Metric and Messages:** FUNDAMENTALS.
- **The Four Protocols at a Glance:** FUNDAMENTALS.
- **Why Routing Trust Is Exploitable:** FUNDAMENTALS.
- **Routing Attacks:** Five ways trust in a routing protocol can be abused.
- **Five Attacks at a Glance:** ATTACKS OVERVIEW.
- **Routing Table Poisoning: Overview & Technique:** ATTACK 1.
- **Routing Table Poisoning: Mitigation:** ATTACK 1.
- **Unauthorised Route Injection: Overview & Technique:** ATTACK 2.
- **Unauthorised Route Injection: Mitigation:** ATTACK 2.
- **Route/Prefix Hijacking: Overview & Technique:** ATTACK 3.
- **Real-World Example: The 2008 YouTube Hijack:** ATTACK 3.

## Verification Notes

- Slide coverage: **45 of 45 slides processed**.
- Slide numbers refer to PDF page order.
- Any application example or scenario above extends the slide concept for revision and is not presented as a verbatim lecturer statement.
