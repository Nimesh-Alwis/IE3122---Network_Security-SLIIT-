# Lecture 05 – Layer 3 Attacks and Defenses

## 📌 Lecture Overview

This lecture covers **Layer 3 Attacks and Defenses** as presented in the supplied IE3122 slides. The notes follow the source order across 34 slides and retain the lecture's terminology, mechanisms, examples, and configuration details. They are organized for rapid MCQ, structured-answer, and scenario revision.

> **Source boundary:** Content below is derived from `IE3122_Week4_Layer3Attacks_Slides.pdf`. Generic exam prompts/examples are labelled as application material; no unsupported lecturer emphasis is claimed.

## 🎯 Learning Objectives

- LO1
- Describe common network vulnerabilities and attacks — today, specifically at Layer 3.
- LO2
- Evaluate different mitigation techniques for vulnerabilities and make recommendations.
- By the end of this session you should be able to explain how each attack abuses ICMP or the IP header, and recommend a
- specific hardening measure for each.

## 📚 Main Topics and Subtopics

### ICMP: A Quick Overview (Slide 4)

**Exam Answer:** The protocol behind ping, traceroute — and several attacks.

**Explanation:**

- The protocol behind ping, traceroute — and several attacks

**සිංහලෙන්:** **ICMP: A Quick Overview** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- The protocol behind ping, traceroute — and several attacks

**🧠 Memory Tip:** Remember **ICMP: A Quick Overview** by linking its purpose → mechanism → result.

### What ICMP Is For (Slide 5)

**Exam Answer:** ICMP.

**Explanation:**

- ICMP
- Internet Control Message Protocol (ICMP) is IP's built-in diagnostic and error-reporting mechanism — it doesn't carry
- application data, it carries information about the network itself.
- Recall Week 1: ping uses ICMP Echo Request/Reply; traceroute uses ICMP alongside manipulated TTL values.
- Routers and hosts generate ICMP messages automatically in response to conditions like an unreachable destination, a
- packet that's expired, or a message too large to forward.
- Like ARP and DHCP , ICMP has no authentication — anything on the network can send it, and hosts are designed to
- trust and respond to it by default.

**සිංහලෙන්:** **What ICMP Is For** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ICMP
- Internet Control Message Protocol (ICMP) is IP's built-in diagnostic and error-reporting mechanism — it doesn't carry
- application data, it carries information about the network itself.
- Recall Week 1: ping uses ICMP Echo Request/Reply; traceroute uses ICMP alongside manipulated TTL values.

**🧠 Memory Tip:** Remember **What ICMP Is For** by linking its purpose → mechanism → result.

### Common ICMP Message Types (Slide 6)

**Exam Answer:** ICMP.

**Explanation:**

- ICMP
- Type Purpose
- Echo Request / Echo Reply Used by ping to test reachability
- Destination Unreachable Sent when a packet can't be delivered (host, network, port, or protocol unreachable)
- Time Exceeded Sent when a packet's TTL reaches zero before arriving — what traceroute relies on
- Redirect A router telling a host a better route exists for a given destination

**සිංහලෙන්:** **Common ICMP Message Types** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ICMP
- Type Purpose
- Echo Request / Echo Reply Used by ping to test reachability
- Destination Unreachable Sent when a packet can't be delivered (host, network, port, or protocol unreachable)

**🧠 Memory Tip:** Remember **Common ICMP Message Types** by linking its purpose → mechanism → result.

### Why ICMP Is an Attractive Target (Slide 7)

**Exam Answer:** ICMP.

**Explanation:**

- ICMP
- Hosts are designed to respond to ICMP automatically — that automatic, trusting response is exactly what several
- attacks exploit.
- ICMP messages are small and cheap to generate, making them ideal for both reconnaissance (many quick probes) and
- volume-based denial of service.
- Because ICMP operates below the application layer, many of these attacks succeed without ever touching a
- vulnerable application — the network stack itself is the target.

**සිංහලෙන්:** **Why ICMP Is an Attractive Target** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ICMP
- Hosts are designed to respond to ICMP automatically — that automatic, trusting response is exactly what several
- attacks exploit.
- ICMP messages are small and cheap to generate, making them ideal for both reconnaissance (many quick probes) and

**🧠 Memory Tip:** Remember **Why ICMP Is an Attractive Target** by linking its purpose → mechanism → result.

### ICMP-Based Attacks (Slide 8)

**Exam Answer:** ICMP Sweep, Ping of Death, Ping Flood, Smurf.

**Explanation:**

- ICMP Sweep, Ping of Death, Ping Flood, Smurf

**සිංහලෙන්:** **ICMP-Based Attacks** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ICMP Sweep, Ping of Death, Ping Flood, Smurf

**🧠 Memory Tip:** Remember **ICMP-Based Attacks** by linking its purpose → mechanism → result.

### ICMP Sweep: Overview, Vulnerability & Technique (Slide 9)

**Exam Answer:** INFO GATHERING.

**Explanation:**

- INFO GATHERING
- Overview: a reconnaissance technique — the attacker sends ICMP Echo Requests to every address in a target IP range
- to discover which hosts are actually alive, before attempting anything else.
- Vulnerability exploited: hosts reply to ICMP Echo Requests by default, with no authentication or rate limiting, happily
- confirming their own existence to anyone who asks.
- Attack technique: automated tools (e.g. nmap's ping sweep) send Echo Requests across an entire subnet in seconds;
- every host that replies is added to a target list for further, more specific attacks.
- This is exactly the reconnaissance phase previewed back in Week 2 — access & reconnaissance attacks are usually
- step one, not the whole attack.

**සිංහලෙන්:** **ICMP Sweep: Overview, Vulnerability & Technique** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- INFO GATHERING
- Overview: a reconnaissance technique — the attacker sends ICMP Echo Requests to every address in a target IP range
- to discover which hosts are actually alive, before attempting anything else.
- Vulnerability exploited: hosts reply to ICMP Echo Requests by default, with no authentication or rate limiting, happily

**🧠 Memory Tip:** Remember **ICMP Sweep: Overview, Vulnerability & Technique** by linking its purpose → mechanism → result.

### ICMP Sweep: Mitigation (Slide 10)

**Exam Answer:** INFO GATHERING.

**Explanation:**

- INFO GATHERING
- Block or rate-limit inbound ICMP Echo Requests at the network perimeter, especially from untrusted external sources
- — most organisations don't need to be pingable from the public Internet at all.
- Where ICMP is needed for legitimate diagnostics, restrict it to specific trusted source addresses rather than allowing
- it from anywhere.
- Detective control: a burst of ICMP Echo Requests hitting a large sequential range of internal addresses in a short time
- is a strong signal for an IDS to flag as reconnaissance.

**සිංහලෙන්:** **ICMP Sweep: Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- INFO GATHERING
- Block or rate-limit inbound ICMP Echo Requests at the network perimeter, especially from untrusted external sources
- — most organisations don't need to be pingable from the public Internet at all.
- Where ICMP is needed for legitimate diagnostics, restrict it to specific trusted source addresses rather than allowing

**🧠 Memory Tip:** Remember **ICMP Sweep: Mitigation** by linking its purpose → mechanism → result.

### Ping of Death: Overview, Vulnerability & Technique (Slide 11)

**Exam Answer:** DOS.

**Explanation:**

- DOS
- Overview: an attack that sends a malformed, oversized ICMP packet designed to crash or destabilise the target when
- it's reassembled.
- Vulnerability exploited: the maximum legal IP packet size is 65,535 bytes — older or poorly written network stacks
- didn't properly handle a packet that arrived, via fragmentation, appearing to exceed that limit.
- Attack technique: the attacker sends a ping whose fragments, when reassembled by the target, produce a packet
- larger than the maximum allowed size, overflowing the reassembly buffer.
- Impact: historically caused crashes, freezes, or reboots on vulnerable systems — largely a legacy attack against
- modern patched operating systems, but still relevant on unpatched embedded or IoT devices.

**සිංහලෙන්:** **Ping of Death: Overview, Vulnerability & Technique** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DOS
- Overview: an attack that sends a malformed, oversized ICMP packet designed to crash or destabilise the target when
- it's reassembled.
- Vulnerability exploited: the maximum legal IP packet size is 65,535 bytes — older or poorly written network stacks

**🧠 Memory Tip:** Remember **Ping of Death: Overview, Vulnerability & Technique** by linking its purpose → mechanism → result.

### Ping of Death: Mitigation (Slide 12)

**Exam Answer:** DOS.

**Explanation:**

- DOS
- Keep operating systems and network device firmware patched — this exact vulnerability was fixed industry-wide
- decades ago, so patching alone eliminates the risk on modern systems.
- Configure firewalls to enforce maximum packet size limits and drop malformed or illegally fragmented ICMP packets
- before they reach internal hosts.
- A reminder that legacy attacks don't disappear — they just move to whatever's still unpatched, which is often IoT and
- embedded devices with long deployment lifespans.

**සිංහලෙන්:** **Ping of Death: Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DOS
- Keep operating systems and network device firmware patched — this exact vulnerability was fixed industry-wide
- decades ago, so patching alone eliminates the risk on modern systems.
- Configure firewalls to enforce maximum packet size limits and drop malformed or illegally fragmented ICMP packets

**🧠 Memory Tip:** Remember **Ping of Death: Mitigation** by linking its purpose → mechanism → result.

### Ping Flood: Overview, Vulnerability & Technique (Slide 13)

**Exam Answer:** DOS.

**Explanation:**

- DOS
- Overview: the simplest possible ICMP attack — overwhelm the target with a high volume of Echo Requests,
- exhausting its bandwidth or processing capacity.
- Vulnerability exploited: a host must process every ICMP Echo Request it receives and generate a reply — there's no
- built-in limit on how many it can be sent per second.
- Attack technique: the attacker (or a botnet, recall Week 2's Mirai example) sends a continuous, high-rate stream of
- Echo Requests directly at the target.
- Impact: legitimate traffic is crowded out by the flood — a straightforward Denial of Service on Availability, one of the
- three CIA properties.

**සිංහලෙන්:** **Ping Flood: Overview, Vulnerability & Technique** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DOS
- Overview: the simplest possible ICMP attack — overwhelm the target with a high volume of Echo Requests,
- exhausting its bandwidth or processing capacity.
- Vulnerability exploited: a host must process every ICMP Echo Request it receives and generate a reply — there's no

**🧠 Memory Tip:** Remember **Ping Flood: Overview, Vulnerability & Technique** by linking its purpose → mechanism → result.

### Ping Flood: Mitigation (Slide 14)

**Exam Answer:** DOS.

**Explanation:**

- DOS
- Rate-limit ICMP traffic at the perimeter firewall/router — cap how many ICMP packets per second are allowed from a
- single source.
- Use IPS/IDS to detect abnormal spikes in ICMP volume and trigger automatic blocking.
- For large-scale floods, a dedicated DDoS-protection service (recall Week 2's GitHub example) absorbs volume that on-
- premises equipment simply can't handle alone.

**සිංහලෙන්:** **Ping Flood: Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DOS
- Rate-limit ICMP traffic at the perimeter firewall/router — cap how many ICMP packets per second are allowed from a
- single source.
- Use IPS/IDS to detect abnormal spikes in ICMP volume and trigger automatic blocking.

**🧠 Memory Tip:** Remember **Ping Flood: Mitigation** by linking its purpose → mechanism → result.

### Smurf Attack: Overview & Vulnerability (Slide 15)

**Exam Answer:** DOS — AMPLIFICATION.

**Explanation:**

- DOS — AMPLIFICATION
- Overview: an amplification attack — the attacker gets an entire network of innocent hosts to unknowingly flood the
- real victim on their behalf.
- Vulnerability exploited: two things combine here — IP allows a source address to be spoofed, and many networks
- historically allowed ICMP Echo Requests sent to a broadcast address to be answered by every host on that network.
- This combination turns a single small request into a massive multiplied response — exactly the kind of amplification
- that makes volumetric DoS attacks so dangerous.

**සිංහලෙන්:** **Smurf Attack: Overview & Vulnerability** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DOS — AMPLIFICATION
- Overview: an amplification attack — the attacker gets an entire network of innocent hosts to unknowingly flood the
- real victim on their behalf.
- Vulnerability exploited: two things combine here — IP allows a source address to be spoofed, and many networks

**🧠 Memory Tip:** Remember **Smurf Attack: Overview & Vulnerability** by linking its purpose → mechanism → result.

### Smurf Attack: The Technique (Slide 16)

**Exam Answer:** DOS — AMPLIFICATION.

**Explanation:**

- DOS — AMPLIFICATION
- Attacker Broadcast Address(entire subnet) Spoofed ICMP Echo Request: source = victim's IP
- Host 1
- Host 2
- Host 3
- Victim Every host replies — all at once — straight to the victim
- One spoofed request
- → many hosts reply
- → victim is flooded with replies it never asked for

**සිංහලෙන්:** **Smurf Attack: The Technique** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DOS — AMPLIFICATION
- Attacker Broadcast Address(entire subnet) Spoofed ICMP Echo Request: source = victim's IP
- Host 1
- Host 2

**🧠 Memory Tip:** Remember **Smurf Attack: The Technique** by linking its purpose → mechanism → result.

### Smurf Attack: Mitigation (Slide 17)

**Exam Answer:** DOS — AMPLIFICATION.

**Explanation:**

- DOS — AMPLIFICATION
- Disable directed broadcast forwarding on routers (no ip directed-broadcast) — this single setting is why Smurf attacks
- are largely historical on modern, correctly configured networks.
- Ingress/egress filtering (BCP 38) at network boundaries drops packets with obviously spoofed source addresses
- before they can be used in an amplification attack at all.
- Rate-limit ICMP responses at the network edge as a defence-in-depth backstop, even if broadcast forwarding is
- already disabled.

**සිංහලෙන්:** **Smurf Attack: Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DOS — AMPLIFICATION
- Disable directed broadcast forwarding on routers (no ip directed-broadcast) — this single setting is why Smurf attacks
- are largely historical on modern, correctly configured networks.
- Ingress/egress filtering (BCP 38) at network boundaries drops packets with obviously spoofed source addresses

**🧠 Memory Tip:** Remember **Smurf Attack: Mitigation** by linking its purpose → mechanism → result.

### IP-Based Attacks (Slide 18)

**Exam Answer:** Abusing the IP header itself — IP Spoofing, TTL, and fragmentation.

**Explanation:**

- Abusing the IP header itself — IP Spoofing, TTL, and fragmentation

**සිංහලෙන්:** **IP-Based Attacks** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Abusing the IP header itself — IP Spoofing, TTL, and fragmentation

**🧠 Memory Tip:** Remember **IP-Based Attacks** by linking its purpose → mechanism → result.

### Why the IP Header Can Be Abused (Slide 19)

**Exam Answer:** IP HEADER.

**Explanation:**

- IP HEADER
- Recall Week 1: the IP header carries the source and destination address, TTL, and fragmentation control fields — all of
- it set by the sender, with nothing on the wire to verify any of it is honest.
- Routers and hosts largely trust what the header claims and act on it — forward toward the claimed destination,
- decrement the claimed TTL, reassemble according to the claimed fragmentation flags.
- Every attack in this section works by crafting header values that are technically valid but deliberately misleading.

**සිංහලෙන්:** **Why the IP Header Can Be Abused** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- IP HEADER
- Recall Week 1: the IP header carries the source and destination address, TTL, and fragmentation control fields — all of
- it set by the sender, with nothing on the wire to verify any of it is honest.
- Routers and hosts largely trust what the header claims and act on it — forward toward the claimed destination,

**🧠 Memory Tip:** Remember **Why the IP Header Can Be Abused** by linking its purpose → mechanism → result.

### IP Spoofing: Overview, Vulnerability & Technique (Slide 20)

**Exam Answer:** HEADER ABUSE.

**Explanation:**

- HEADER ABUSE
- Overview: the attacker sends packets with a forged source IP address — one that isn't actually theirs.
- Vulnerability exploited: IP has no built-in mechanism to verify that a packet's claimed source address is genuine —
- routers forward based on destination only.
- Attack technique: simply set the source address field to whatever the attacker wants — a trusted internal address (to
- bypass source-based access controls), or a victim's address (to redirect responses toward them, as in the Smurf
- attack).
- Impact: enables amplification attacks, bypasses naive IP-based trust/filtering, and makes attributing an attack back to
- its real source significantly harder.

**සිංහලෙන්:** **IP Spoofing: Overview, Vulnerability & Technique** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- HEADER ABUSE
- Overview: the attacker sends packets with a forged source IP address — one that isn't actually theirs.
- Vulnerability exploited: IP has no built-in mechanism to verify that a packet's claimed source address is genuine —
- routers forward based on destination only.

**🧠 Memory Tip:** Remember **IP Spoofing: Overview, Vulnerability & Technique** by linking its purpose → mechanism → result.

### IP Spoofing: Mitigation (Slide 21)

**Exam Answer:** HEADER ABUSE.

**Explanation:**

- HEADER ABUSE
- Ingress filtering: block inbound traffic on an external interface that claims to come from your own internal address
- ranges — no legitimate packet would ever arrive that way.
- Egress filtering: block outbound traffic that doesn't carry a source address from your own assigned range — stops
- your own network being used to spoof addresses in an attack on someone else (BCP 38, the same principle behind
- Smurf mitigation).
- Unicast Reverse Path Forwarding (uRPF) on routers: verify that a packet's source address is reachable via the interface
- it arrived on, dropping it if the path doesn't make sense.

**සිංහලෙන්:** **IP Spoofing: Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- HEADER ABUSE
- Ingress filtering: block inbound traffic on an external interface that claims to come from your own internal address
- ranges — no legitimate packet would ever arrive that way.
- Egress filtering: block outbound traffic that doesn't carry a source address from your own assigned range — stops

**🧠 Memory Tip:** Remember **IP Spoofing: Mitigation** by linking its purpose → mechanism → result.

### TTL-Based Attacks: A Quick Recap of TTL (Slide 22)

**Exam Answer:** HEADER ABUSE.

**Explanation:**

- HEADER ABUSE
- Recall Week 1: Time To Live (TTL) limits how many router hops a packet can traverse — each router decrements it by
- one, and a router that decrements it to zero discards the packet and returns an ICMP Time Exceeded message.
- TTL was designed to prevent packets looping forever due to routing errors — but its predictable, inspectable
- behaviour also makes it something attackers can exploit deliberately.
- Two distinct attacks abuse this: one targets network devices directly, the other targets the security tools meant to
- inspect the traffic.

**සිංහලෙන්:** **TTL-Based Attacks: A Quick Recap of TTL** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- HEADER ABUSE
- Recall Week 1: Time To Live (TTL) limits how many router hops a packet can traverse — each router decrements it by
- one, and a router that decrements it to zero discards the packet and returns an ICMP Time Exceeded message.
- TTL was designed to prevent packets looping forever due to routing errors — but its predictable, inspectable

**🧠 Memory Tip:** Remember **TTL-Based Attacks: A Quick Recap of TTL** by linking its purpose → mechanism → result.

### TTL Expiry Attack: Overview, Vulnerability & Technique (Slide 23)

**Exam Answer:** HEADER ABUSE.

**Explanation:**

- HEADER ABUSE
- Overview: the attacker deliberately sends packets with very low TTL values so that they expire at a router, forcing that
- router to generate an ICMP Time Exceeded reply.
- Vulnerability exploited: generating an ICMP error message costs the router CPU cycles — something it must do for
- every expiring packet, with no default limit on how often.
- Attack technique: flood a router with a high volume of deliberately low-TTL packets; each one forces a fresh Time
- Exceeded message, consuming processing capacity that should be spent forwarding real traffic.
- Impact: a denial of service aimed specifically at network infrastructure (routers) rather than end hosts — a variation
- on the same theme as the STP DoS attack from earlier this week.

**සිංහලෙන්:** **TTL Expiry Attack: Overview, Vulnerability & Technique** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- HEADER ABUSE
- Overview: the attacker deliberately sends packets with very low TTL values so that they expire at a router, forcing that
- router to generate an ICMP Time Exceeded reply.
- Vulnerability exploited: generating an ICMP error message costs the router CPU cycles — something it must do for

**🧠 Memory Tip:** Remember **TTL Expiry Attack: Overview, Vulnerability & Technique** by linking its purpose → mechanism → result.

### TTL-Based Evasion Attack: Overview, Vulnerability & Technique (Slide 24)

**Exam Answer:** HEADER ABUSE.

**Explanation:**

- HEADER ABUSE
- Overview: an attacker crafts a TTL value so that a packet is seen differently by a security device (like an IDS) than by
- the actual destination host — designed to sneak malicious traffic past inspection.
- Vulnerability exploited: an IDS sitting between the attacker and the target is at a different number of hops from the
- target than the attacker's packet accounts for — if the TTL is tuned precisely, the packet can expire right after the IDS
- sees it but the IDS doesn't realise it never reached the real destination (or vice versa).
- Attack technique: the attacker sends a sequence where some packets are crafted to be processed by the IDS but
- silently dropped before reaching the host, while the packets the host actually assembles differ from what the IDS
- believes it inspected — letting disguised malicious content through undetected.
- Impact: this is a foundational IDS/IPS evasion technique — not a direct attack on availability, but a way to defeat
- detection entirely so a different attack can proceed unnoticed.

**සිංහලෙන්:** **TTL-Based Evasion Attack: Overview, Vulnerability & Technique** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- HEADER ABUSE
- Overview: an attacker crafts a TTL value so that a packet is seen differently by a security device (like an IDS) than by
- the actual destination host — designed to sneak malicious traffic past inspection.
- Vulnerability exploited: an IDS sitting between the attacker and the target is at a different number of hops from the

**🧠 Memory Tip:** Remember **TTL-Based Evasion Attack: Overview, Vulnerability & Technique** by linking its purpose → mechanism → result.

### TTL Evasion: Why It Works (Slide 25)

**Exam Answer:** HEADER ABUSE.

**Explanation:**

- HEADER ABUSE
- Attacker IDS Sensor Real Destination
- Packet's TTL expires here — never actually arrives
- The IDS inspects the packet and, seeing nothing wrong, allows it through — but the packet's TTL was crafted to expire in the
- network segment between the IDS and the real destination.
- The destination host never actually receives that packet at all — yet the IDS's picture of the conversation now doesn't match
- what the destination actually experiences.
- Attackers exploit this mismatch (in either direction) to slip malicious payloads past inspection while keeping the IDS's logs
- looking clean.

**සිංහලෙන්:** **TTL Evasion: Why It Works** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- HEADER ABUSE
- Attacker IDS Sensor Real Destination
- Packet's TTL expires here — never actually arrives
- The IDS inspects the packet and, seeing nothing wrong, allows it through — but the packet's TTL was crafted to expire in the

**🧠 Memory Tip:** Remember **TTL Evasion: Why It Works** by linking its purpose → mechanism → result.

### TTL-Based Attacks: Mitigation (Slide 26)

**Exam Answer:** HEADER ABUSE.

**Explanation:**

- HEADER ABUSE
- Rate-limit ICMP Time Exceeded generation on routers to blunt TTL expiry-based CPU exhaustion, the same principle
- used against Ping Flood.
- For evasion: deploy IDS/IPS sensors as close to the protected host as possible (minimising the hop-count gap an
- attacker could exploit), and use IDS technology that actively tracks and normalises TTL rather than passively trusting
- it.
- Keep IDS/IPS signature and inspection engines updated — TTL evasion is a known, well-documented technique, and
- modern IDS platforms include specific countermeasures for it.

**සිංහලෙන්:** **TTL-Based Attacks: Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- HEADER ABUSE
- Rate-limit ICMP Time Exceeded generation on routers to blunt TTL expiry-based CPU exhaustion, the same principle
- used against Ping Flood.
- For evasion: deploy IDS/IPS sensors as close to the protected host as possible (minimising the hop-count gap an

**🧠 Memory Tip:** Remember **TTL-Based Attacks: Mitigation** by linking its purpose → mechanism → result.

### Teardrop Attack (Fragmentation): Overview, Vulnerability & (Slide 27)

**Exam Answer:** Technique.

**Explanation:**

- Technique
- HEADER ABUSE
- Overview: an attack that sends deliberately malformed, overlapping IP fragments designed to break the reassembly
- process on the target.
- Vulnerability exploited: when a large packet is fragmented, each fragment carries an offset telling the receiver where
- it belongs during reassembly — older or poorly written IP stacks didn't properly validate that these offsets made
- sense.
- Attack technique: the attacker crafts fragments with overlapping, contradictory offsets. When the target tries to
- reassemble them, the reassembly logic can crash, hang, or corrupt memory.
- Impact: like Ping of Death, this is largely a legacy attack against modern patched systems — but the same
- fragmentation-based logic still appears in evasion techniques against firewalls and IDS today.

**සිංහලෙන්:** **Teardrop Attack (Fragmentation): Overview, Vulnerability &** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Technique
- HEADER ABUSE
- Overview: an attack that sends deliberately malformed, overlapping IP fragments designed to break the reassembly
- process on the target.

**🧠 Memory Tip:** Remember **Teardrop Attack (Fragmentation): Overview, Vulnerability &** by linking its purpose → mechanism → result.

### Teardrop Attack: Mitigation (Slide 28)

**Exam Answer:** HEADER ABUSE.

**Explanation:**

- HEADER ABUSE
- Keep operating systems patched — modern IP stacks correctly validate fragment offsets and simply discard
- malformed fragments instead of crashing.
- Configure firewalls to perform fragment reassembly and validation before packets reach internal hosts, dropping
- anything with impossible or overlapping offsets.
- Where policy allows, block fragmented traffic entirely at the perimeter for services that never legitimately need it —
- removes the attack surface outright.

**සිංහලෙන්:** **Teardrop Attack: Mitigation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- HEADER ABUSE
- Keep operating systems patched — modern IP stacks correctly validate fragment offsets and simply discard
- malformed fragments instead of crashing.
- Configure firewalls to perform fragment reassembly and validation before packets reach internal hosts, dropping

**🧠 Memory Tip:** Remember **Teardrop Attack: Mitigation** by linking its purpose → mechanism → result.

### Bringing It Together (Slide 29)

**Exam Answer:** Comparing mitigations across all eight attacks.

**Explanation:**

- Comparing mitigations across all eight attacks

**සිංහලෙන්:** **Bringing It Together** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Comparing mitigations across all eight attacks

**🧠 Memory Tip:** Remember **Bringing It Together** by linking its purpose → mechanism → result.

### Full Mitigation Comparison (Slide 30)

**Exam Answer:** SUMMARY.

**Explanation:**

- SUMMARY
- Attack Primary mitigation
- ICMP Sweep Block/rate-limit inbound ICMP Echo at the perimeter
- Ping of Death Patching; firewall packet-size/fragment validation
- Ping Flood ICMP rate limiting; IPS detection; DDoS protection service
- Smurf Attack Disable directed broadcast; ingress/egress filtering (BCP 38)
- IP Spoofing Ingress/egress filtering; uRPF
- TTL Expiry Attack Rate-limit ICMP Time Exceeded generation on routers
- TTL-Based Evasion IDS placement close to the host; TTL-aware inspection
- Teardrop (Fragmentation) Patching; firewall fragment reassembly/validation

**සිංහලෙන්:** **Full Mitigation Comparison** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SUMMARY
- Attack Primary mitigation
- ICMP Sweep Block/rate-limit inbound ICMP Echo at the perimeter
- Ping of Death Patching; firewall packet-size/fragment validation

**🧠 Memory Tip:** Remember **Full Mitigation Comparison** by linking its purpose → mechanism → result.

### Layered Defense at Layer 3 (Slide 31)

**Exam Answer:** SUMMARY.

**Explanation:**

- SUMMARY
- Notice the repeating themes: ingress/egress filtering stops multiple attacks at once (Spoofing, Smurf) — exactly the
- control-minimisation principle from Week 2's layered security plan.
- Patching alone neutralises several legacy attacks (Ping of Death, Teardrop) — a reminder that not every mitigation
- needs to be a piece of dedicated security hardware.
- No single control here covers everything: filtering doesn't stop a flood, rate limiting doesn't stop evasion — the same
- layered-defense principle from Week 2 applies just as much at Layer 3 as it did at Layer 2.

**සිංහලෙන්:** **Layered Defense at Layer 3** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SUMMARY
- Notice the repeating themes: ingress/egress filtering stops multiple attacks at once (Spoofing, Smurf) — exactly the
- control-minimisation principle from Week 2's layered security plan.
- Patching alone neutralises several legacy attacks (Ping of Death, Teardrop) — a reminder that not every mitigation

**🧠 Memory Tip:** Remember **Layered Defense at Layer 3** by linking its purpose → mechanism → result.

### Summary (Slide 32)

**Exam Answer:** ICMP is a trusted, unauthenticated diagnostic protocol — exactly what makes ICMP Sweep, Ping of Death, Ping Flood, and Smurf all.

**Explanation:**

- ICMP is a trusted, unauthenticated diagnostic protocol — exactly what makes ICMP Sweep, Ping of Death, Ping Flood, and Smurf all
- possible.
- The IP header itself — source address, TTL, fragmentation fields — is entirely sender-controlled and largely trusted, enabling IP
- Spoofing, TTL-based attacks, and Teardrop.
- Smurf and IP Spoofing share a common root cause (an unverifiable source address) and a common family of fixes (ingress/egress
- filtering).
- Legacy attacks like Ping of Death and Teardrop are mostly solved by patching — but their underlying techniques (fragmentation
- abuse, malformed packets) still show up in modern evasion methods.
- Layered defense applies at every layer we've studied so far — Layer 2 in Weeks 3–4, and now Layer 3 today.

**සිංහලෙන්:** **Summary** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ICMP is a trusted, unauthenticated diagnostic protocol — exactly what makes ICMP Sweep, Ping of Death, Ping Flood, and Smurf all
- possible.
- The IP header itself — source address, TTL, fragmentation fields — is entirely sender-controlled and largely trusted, enabling IP
- Spoofing, TTL-based attacks, and Teardrop.

**🧠 Memory Tip:** Remember **Summary** by linking its purpose → mechanism → result.

### This Week's Lab & Tutorial (Slide 33)

**Exam Answer:** Lab (runs in the Week 5 session): builds on this week's 3-tier STP topology, adding STP hardening plus Layer 3.

**Explanation:**

- Lab (runs in the Week 5 session): builds on this week's 3-tier STP topology, adding STP hardening plus Layer 3
- defensive configuration.
- Tutorial worksheet: study-notes-style questions covering ICMP fundamentals, both attack categories, and their
- mitigations — use it to prep for the mid-semester test.

**සිංහලෙන්:** **This Week's Lab & Tutorial** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Lab (runs in the Week 5 session): builds on this week's 3-tier STP topology, adding STP hardening plus Layer 3
- defensive configuration.
- Tutorial worksheet: study-notes-style questions covering ICMP fundamentals, both attack categories, and their
- mitigations — use it to prep for the mid-semester test.

**🧠 Memory Tip:** Remember **This Week's Lab & Tutorial** by linking its purpose → mechanism → result.


## 📊 Important Comparisons

| Comparison/topic | Source | Exam focus |
|---|---:|---|
| ICMP: A Quick Overview | Slide 4 | The protocol behind ping, traceroute — and several attacks. |
| ICMP Sweep: Overview, Vulnerability & Technique | Slide 9 | INFO GATHERING. |
| Ping of Death: Overview, Vulnerability & Technique | Slide 11 | DOS. |
| Ping Flood: Overview, Vulnerability & Technique | Slide 13 | DOS. |
| Smurf Attack: Overview & Vulnerability | Slide 15 | DOS — AMPLIFICATION. |
| IP Spoofing: Overview, Vulnerability & Technique | Slide 20 | HEADER ABUSE. |
| TTL Expiry Attack: Overview, Vulnerability & Technique | Slide 23 | HEADER ABUSE. |
| TTL-Based Evasion Attack: Overview, Vulnerability & Technique | Slide 24 | HEADER ABUSE. |
| Teardrop Attack (Fragmentation): Overview, Vulnerability & | Slide 27 | Technique. |
| Full Mitigation Comparison | Slide 30 | SUMMARY. |
| Summary | Slide 32 | ICMP is a trusted, unauthenticated diagnostic protocol — exactly what makes ICMP Sweep, Ping of Death, Ping Flood, and Smurf all. |

## 🛠️ Practical Knowledge

### ICMP Sweep: Overview, Vulnerability & Technique (Slide 9)

- INFO GATHERING
- Overview: a reconnaissance technique — the attacker sends ICMP Echo Requests to every address in a target IP range
- to discover which hosts are actually alive, before attempting anything else.
- Vulnerability exploited: hosts reply to ICMP Echo Requests by default, with no authentication or rate limiting, happily
- confirming their own existence to anyone who asks.
- Attack technique: automated tools (e.g. nmap's ping sweep) send Echo Requests across an entire subnet in seconds;
- every host that replies is added to a target list for further, more specific attacks.
- This is exactly the reconnaissance phase previewed back in Week 2 — access & reconnaissance attacks are usually
- step one, not the whole attack.

### Ping Flood: Overview, Vulnerability & Technique (Slide 13)

- DOS
- Overview: the simplest possible ICMP attack — overwhelm the target with a high volume of Echo Requests,
- exhausting its bandwidth or processing capacity.
- Vulnerability exploited: a host must process every ICMP Echo Request it receives and generate a reply — there's no
- built-in limit on how many it can be sent per second.
- Attack technique: the attacker (or a botnet, recall Week 2's Mirai example) sends a continuous, high-rate stream of
- Echo Requests directly at the target.
- Impact: legitimate traffic is crowded out by the flood — a straightforward Denial of Service on Availability, one of the
- three CIA properties.

### TTL-Based Attacks: A Quick Recap of TTL (Slide 22)

- HEADER ABUSE
- Recall Week 1: Time To Live (TTL) limits how many router hops a packet can traverse — each router decrements it by
- one, and a router that decrements it to zero discards the packet and returns an ICMP Time Exceeded message.
- TTL was designed to prevent packets looping forever due to routing errors — but its predictable, inspectable
- behaviour also makes it something attackers can exploit deliberately.
- Two distinct attacks abuse this: one targets network devices directly, the other targets the security tools meant to
- inspect the traffic.

### TTL-Based Evasion Attack: Overview, Vulnerability & Technique (Slide 24)

- HEADER ABUSE
- Overview: an attacker crafts a TTL value so that a packet is seen differently by a security device (like an IDS) than by
- the actual destination host — designed to sneak malicious traffic past inspection.
- Vulnerability exploited: an IDS sitting between the attacker and the target is at a different number of hops from the
- target than the attacker's packet accounts for — if the TTL is tuned precisely, the packet can expire right after the IDS
- sees it but the IDS doesn't realise it never reached the real destination (or vice versa).
- Attack technique: the attacker sends a sequence where some packets are crafted to be processed by the IDS but
- silently dropped before reaching the host, while the packets the host actually assembles differ from what the IDS
- believes it inspected — letting disguised malicious content through undetected.
- Impact: this is a foundational IDS/IPS evasion technique — not a direct attack on availability, but a way to defeat
- detection entirely so a different attack can proceed unnoticed.

### This Week's Lab & Tutorial (Slide 33)

- Lab (runs in the Week 5 session): builds on this week's 3-tier STP topology, adding STP hardening plus Layer 3
- defensive configuration.
- Tutorial worksheet: study-notes-style questions covering ICMP fundamentals, both attack categories, and their
- mitigations — use it to prep for the mid-semester test.

## ⭐ Important Exam Points

- ⭐ **ICMP: A Quick Overview (Slide 4):** The protocol behind ping, traceroute — and several attacks.
- ⭐ **What ICMP Is For (Slide 5):** ICMP.
- ⭐ **Common ICMP Message Types (Slide 6):** ICMP.
- ⭐ **Why ICMP Is an Attractive Target (Slide 7):** ICMP.
- ⭐ **ICMP-Based Attacks (Slide 8):** ICMP Sweep, Ping of Death, Ping Flood, Smurf.
- ⭐ **ICMP Sweep: Overview, Vulnerability & Technique (Slide 9):** INFO GATHERING.
- ⭐ **ICMP Sweep: Mitigation (Slide 10):** INFO GATHERING.
- ⭐ **Ping of Death: Overview, Vulnerability & Technique (Slide 11):** DOS.
- ⭐ **Ping of Death: Mitigation (Slide 12):** DOS.
- ⭐ **Ping Flood: Overview, Vulnerability & Technique (Slide 13):** DOS.
- ⭐ **Ping Flood: Mitigation (Slide 14):** DOS.
- ⭐ **Smurf Attack: Overview & Vulnerability (Slide 15):** DOS — AMPLIFICATION.
- ⭐ **Smurf Attack: The Technique (Slide 16):** DOS — AMPLIFICATION.
- ⭐ **Smurf Attack: Mitigation (Slide 17):** DOS — AMPLIFICATION.
- ⭐ **IP-Based Attacks (Slide 18):** Abusing the IP header itself — IP Spoofing, TTL, and fragmentation.

## ❓ Possible Exam Questions

### MCQs

1. Which statement best matches **ICMP: A Quick Overview**?
   - A. It is unrelated to network security.
   - B. The protocol behind ping, traceroute — and several attacks.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

2. Which statement best matches **ICMP Sweep: Mitigation**?
   - A. It is unrelated to network security.
   - B. INFO GATHERING.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

3. Which statement best matches **Smurf Attack: The Technique**?
   - A. It is unrelated to network security.
   - B. DOS — AMPLIFICATION.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

4. Which statement best matches **TTL-Based Attacks: A Quick Recap of TTL**?
   - A. It is unrelated to network security.
   - B. HEADER ABUSE.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

5. Which statement best matches **Teardrop Attack: Mitigation**?
   - A. It is unrelated to network security.
   - B. HEADER ABUSE.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**


### Short Structured Questions

1. **Explain ICMP: A Quick Overview.**
   - **Model answer:** The protocol behind ping, traceroute — and several attacks.

2. **Explain ICMP Sweep: Mitigation.**
   - **Model answer:** INFO GATHERING.

3. **Explain Smurf Attack: The Technique.**
   - **Model answer:** DOS — AMPLIFICATION.

4. **Explain TTL-Based Attacks: A Quick Recap of TTL.**
   - **Model answer:** HEADER ABUSE.

5. **Explain Teardrop Attack: Mitigation.**
   - **Model answer:** HEADER ABUSE.


### Scenario-Based Question

**Scenario:** An organization must apply the concepts from **Layer 3 Attacks and Defenses** to improve its network security. Identify the relevant mechanism or risk, explain the likely impact, and recommend a layered response.

**Model-answer approach:** Identify the asset and trust boundary; name the relevant protocol/control; explain the mechanism using the lecture terminology; state confidentiality, integrity, or availability impact; then recommend the matching prevention, detection, and verification steps from the slides.

## ⚡ Last-Minute Quick Revision

- **ICMP: A Quick Overview:** The protocol behind ping, traceroute — and several attacks.
- **What ICMP Is For:** ICMP.
- **Common ICMP Message Types:** ICMP.
- **Why ICMP Is an Attractive Target:** ICMP.
- **ICMP-Based Attacks:** ICMP Sweep, Ping of Death, Ping Flood, Smurf.
- **ICMP Sweep: Overview, Vulnerability & Technique:** INFO GATHERING.
- **ICMP Sweep: Mitigation:** INFO GATHERING.
- **Ping of Death: Overview, Vulnerability & Technique:** DOS.
- **Ping of Death: Mitigation:** DOS.
- **Ping Flood: Overview, Vulnerability & Technique:** DOS.
- **Ping Flood: Mitigation:** DOS.
- **Smurf Attack: Overview & Vulnerability:** DOS — AMPLIFICATION.
- **Smurf Attack: The Technique:** DOS — AMPLIFICATION.
- **Smurf Attack: Mitigation:** DOS — AMPLIFICATION.
- **IP-Based Attacks:** Abusing the IP header itself — IP Spoofing, TTL, and fragmentation.
- **Why the IP Header Can Be Abused:** IP HEADER.
- **IP Spoofing: Overview, Vulnerability & Technique:** HEADER ABUSE.
- **IP Spoofing: Mitigation:** HEADER ABUSE.
- **TTL-Based Attacks: A Quick Recap of TTL:** HEADER ABUSE.
- **TTL Expiry Attack: Overview, Vulnerability & Technique:** HEADER ABUSE.

## Verification Notes

- Slide coverage: **34 of 34 slides processed**.
- Slide numbers refer to PDF page order.
- Any application example or scenario above extends the slide concept for revision and is not presented as a verbatim lecturer statement.
