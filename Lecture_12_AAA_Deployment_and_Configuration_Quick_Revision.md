# Lecture 12 – AAA Deployment and Configuration

## 📌 Lecture Overview

This lecture covers **AAA Deployment and Configuration** as presented in the supplied IE3122 slides. The notes follow the source order across 28 slides and retain the lecture's terminology, mechanisms, examples, and configuration details. They are organized for rapid MCQ, structured-answer, and scenario revision.

> **Source boundary:** Content below is derived from `IE3122_Week10_AAADeploymentConfig_Slides.pdf`. Generic exam prompts/examples are labelled as application material; no unsupported lecturer emphasis is claimed.

## 🎯 Learning Objectives

- LO3
- Analyse security requirements and recommend appropriate technologies.
- LO4
- Evaluate different security technologies, compare them, and identify appropriate use cases.
- LO5
- Configure security technologies to satisfy specific requirements.

## 📚 Main Topics and Subtopics

### Local vs. Server-Based AAA (Slide 4)

**Exam Answer:** Where the decision actually gets made.

**Explanation:**

- Where the decision actually gets made

**සිංහලෙන්:** **Local vs. Server-Based AAA** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Where the decision actually gets made

**🧠 Memory Tip:** Remember **Local vs. Server-Based AAA** by linking its purpose → mechanism → result.

### Local AAA (Slide 5)

**Exam Answer:** DEPLOYMENT.

**Explanation:**

- DEPLOYMENT
- Mechanism: each device, a router or switch, keeps its own username and password database and makes its own authentication decisions entirely
- independently.
- Example use case: a small office with two or three routers managed directly by one administrator, or a fallback method configured on every device
- in case a central server later becomes unreachable.
- Strengths: no external server or network dependency, so it works even if the rest of the network is completely down; simple to set up with no extra
- infrastructure; takes effect immediately, with nothing else that needs to be reachable first.
- Weaknesses: doesn't scale. With many devices, adding, removing, or updating a single user means logging into and changing every device
- individually, and each device's own logs stay separate rather than forming one consistent audit trail.

**සිංහලෙන්:** **Local AAA** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEPLOYMENT
- Mechanism: each device, a router or switch, keeps its own username and password database and makes its own authentication decisions entirely
- independently.
- Example use case: a small office with two or three routers managed directly by one administrator, or a fallback method configured on every device

**🧠 Memory Tip:** Remember **Local AAA** by linking its purpose → mechanism → result.

### Server-Based (Centralised) AAA (Slide 6)

**Exam Answer:** DEPLOYMENT.

**Explanation:**

- DEPLOYMENT
- Mechanism: devices forward authentication and authorization requests to a dedicated AAA server, running RADIUS or TACACS+, which makes the
- decision and reports back.
- Example use case: a large enterprise with hundreds of routers, switches, and VPN concentrators all authenticating against one central TACACS+ server, or
- a university campus where every WiFi access point authenticates students and staff against one RADIUS server tied to the inst itution's directory.
- Strengths: one consistent user database and one place to manage accounts; one centralised audit log across the entire network ; scales cleanly to large
- networks without per-device administrative overhead.
- Weaknesses: introduces a genuine new dependency, since an unreachable AAA server means devices can't authenticate anyone agai nst it unless a
- fallback is configured; adds infrastructure cost and complexity; and becomes a single, high-value target, since compromising the AAA server could
- compromise authentication for the whole network.

**සිංහලෙන්:** **Server-Based (Centralised) AAA** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEPLOYMENT
- Mechanism: devices forward authentication and authorization requests to a dedicated AAA server, running RADIUS or TACACS+, which makes the
- decision and reports back.
- Example use case: a large enterprise with hundreds of routers, switches, and VPN concentrators all authenticating against one central TACACS+ server, or

**🧠 Memory Tip:** Remember **Server-Based (Centralised) AAA** by linking its purpose → mechanism → result.

### Local vs. Server-Based: Comparison (Slide 7)

**Exam Answer:** DEPLOYMENT.

**Explanation:**

- DEPLOYMENT
- Aspect Local AAA Server-Based AAA
- Consistency Managed per device, inconsistent at scale One central database, consistent everywhere
- Scalability Poor, doesn't scale beyond a few devices Strong, scales to large networks
- Dependency None, entirely self-contained Depends on the AAA server being reachable
- Typical use Small networks, or as a fallback method Enterprise networks

**සිංහලෙන්:** **Local vs. Server-Based: Comparison** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DEPLOYMENT
- Aspect Local AAA Server-Based AAA
- Consistency Managed per device, inconsistent at scale One central database, consistent everywhere
- Scalability Poor, doesn't scale beyond a few devices Strong, scales to large networks

**🧠 Memory Tip:** Remember **Local vs. Server-Based: Comparison** by linking its purpose → mechanism → result.

### Device Administration AAA vs. Network (Slide 8)

**Exam Answer:** Access AAA.

**Explanation:**

- Access AAA
- What is actually being protected

**සිංහලෙන්:** **Device Administration AAA vs. Network** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Access AAA
- What is actually being protected

**🧠 Memory Tip:** Remember **Device Administration AAA vs. Network** by linking its purpose → mechanism → result.

### Device Administration AAA (Slide 9)

**Exam Answer:** TWO KINDS OF ACCESS.

**Explanation:**

- TWO KINDS OF ACCESS
- Controls who can log into the network's own infrastructure devices, a router or switch's CLI, and once in, exactly which
- commands they're allowed to run.
- The stakes here are can this person reconfigure the network, and the natural granularity is per command.
- This is TACACS+'s traditional home ground, covered in detail shortly.

**සිංහලෙන්:** **Device Administration AAA** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TWO KINDS OF ACCESS
- Controls who can log into the network's own infrastructure devices, a router or switch's CLI, and once in, exactly which
- commands they're allowed to run.
- The stakes here are can this person reconfigure the network, and the natural granularity is per command.

**🧠 Memory Tip:** Remember **Device Administration AAA** by linking its purpose → mechanism → result.

### Network Access AAA (Slide 10)

**Exam Answer:** TWO KINDS OF ACCESS.

**Explanation:**

- TWO KINDS OF ACCESS
- Controls who or what can get onto the network in the first place: WiFi association, a VPN connection (recall Week 9), or
- wired 802.1X port authentication.
- The stakes here are can this device or user reach the network at all. There's no equivalent of per-command granularity, since
- an end user connecting to WiFi isn't issuing router commands.
- This is RADIUS's traditional home ground, built for fast, high-volume, simultaneous connection handling rather than fine-
- grained command control.

**සිංහලෙන්:** **Network Access AAA** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TWO KINDS OF ACCESS
- Controls who or what can get onto the network in the first place: WiFi association, a VPN connection (recall Week 9), or
- wired 802.1X port authentication.
- The stakes here are can this device or user reach the network at all. There's no equivalent of per-command granularity, since

**🧠 Memory Tip:** Remember **Network Access AAA** by linking its purpose → mechanism → result.

### Why This Distinction Actually Matters (Slide 11)

**Exam Answer:** TWO KINDS OF ACCESS.

**Explanation:**

- TWO KINDS OF ACCESS
- TACACS+'s full-packet encryption and its clean separation of all three AAA functions matches device administration's need for
- fine-grained, secure command control.
- RADIUS's lighter design, encrypting only the password, and bundling authentication with authorization matches network
- access's need for fast, high-volume connection handling.
- Neither protocol is simply better overall. Each is well suited to the specific stakes and scale of its own traditional use case,
- which is exactly why both still exist side by side today.

**සිංහලෙන්:** **Why This Distinction Actually Matters** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TWO KINDS OF ACCESS
- TACACS+'s full-packet encryption and its clean separation of all three AAA functions matches device administration's need for
- fine-grained, secure command control.
- RADIUS's lighter design, encrypting only the password, and bundling authentication with authorization matches network

**🧠 Memory Tip:** Remember **Why This Distinction Actually Matters** by linking its purpose → mechanism → result.

### RADIUS vs. TACACS+ (Slide 12)

**Exam Answer:** Two protocols, two different jobs.

**Explanation:**

- Two protocols, two different jobs

**සිංහලෙන්:** **RADIUS vs. TACACS+** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Two protocols, two different jobs

**🧠 Memory Tip:** Remember **RADIUS vs. TACACS+** by linking its purpose → mechanism → result.

### RADIUS: Mechanism and Use Cases (Slide 13)

**Exam Answer:** RADIUS.

**Explanation:**

- RADIUS
- Remote Authentication Dial-In User Service. Despite the dated name, it's the dominant protocol for modern network access
- AAA.
- Transport: UDP , on ports 1812 for authentication and authorization and 1813 for accounting.
- Encrypts only the password field in the packet. The rest, including the username, travels unencrypted, and it bundles
- authentication and authorization into a single response rather than treating them as separate exchanges.
- Use cases: WiFi authentication via 802.1X, VPN remote access (recall Week 9), and its original historical role authenticating
- ISP dial-up and broadband customers, anywhere many simultaneous connections need fast, lightweight handling.

**සිංහලෙන්:** **RADIUS: Mechanism and Use Cases** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- RADIUS
- Remote Authentication Dial-In User Service. Despite the dated name, it's the dominant protocol for modern network access
- AAA.
- Transport: UDP , on ports 1812 for authentication and authorization and 1813 for accounting.

**🧠 Memory Tip:** Remember **RADIUS: Mechanism and Use Cases** by linking its purpose → mechanism → result.

### RADIUS: Strengths and Weaknesses (Slide 14)

**Exam Answer:** RADIUS.

**Explanation:**

- RADIUS
- Strengths: an open, multi-vendor standard (RFC 2865 and 2866) supported broadly across many manufacturers' equipment,
- not locked to one vendor. Lightweight and fast, since UDP and its combined authentication-authorization response suit high-
- volume, simultaneous connection handling well. Straightforward to deploy across a mixed-vendor environment.
- Weaknesses: only the password is encrypted, so usernames and other attributes cross the network in plain text, a genuine
- security gap compared to TACACS+. UDP itself gives no guaranteed delivery, unlike TCP . Bundling authentication and
- authorization together also means less flexibility to control each independently.

**සිංහලෙන්:** **RADIUS: Strengths and Weaknesses** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- RADIUS
- Strengths: an open, multi-vendor standard (RFC 2865 and 2866) supported broadly across many manufacturers' equipment,
- not locked to one vendor. Lightweight and fast, since UDP and its combined authentication-authorization response suit high-
- volume, simultaneous connection handling well. Straightforward to deploy across a mixed-vendor environment.

**🧠 Memory Tip:** Remember **RADIUS: Strengths and Weaknesses** by linking its purpose → mechanism → result.

### TACACS+: Mechanism and Use Cases (Slide 15)

**Exam Answer:** TACACS+.

**Explanation:**

- TACACS+
- Terminal Access Controller Access-Control System Plus. Cisco's own protocol for device administration AAA.
- Transport: TCP , on port 49, giving reliable delivery that UDP doesn't guarantee.
- Encrypts the entire packet body, not just the password, and cleanly separates all three AAA functions into genuinely
- independent exchanges rather than bundling them.
- Use cases: administering Cisco routers and switches, controlling exactly which CLI commands a given administrator can run,
- and any enterprise environment needing a detailed, per-command audit trail for its own infrastructure.

**සිංහලෙන්:** **TACACS+: Mechanism and Use Cases** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TACACS+
- Terminal Access Controller Access-Control System Plus. Cisco's own protocol for device administration AAA.
- Transport: TCP , on port 49, giving reliable delivery that UDP doesn't guarantee.
- Encrypts the entire packet body, not just the password, and cleanly separates all three AAA functions into genuinely

**🧠 Memory Tip:** Remember **TACACS+: Mechanism and Use Cases** by linking its purpose → mechanism → result.

### TACACS+: Strengths and Weaknesses (Slide 16)

**Exam Answer:** TACACS+.

**Explanation:**

- TACACS+
- Strengths: full-packet encryption gives meaningfully stronger confidentiality than RADIUS. Genuinely separating
- authentication, authorization, and accounting allows fine-grained control over each independently, including command-level
- authorization. TCP provides reliable delivery.
- Weaknesses: Cisco-proprietary, so it isn't natively supported across other vendors' equipment the way RADIUS is. Carries
- heavier protocol overhead than RADIUS, since it encrypts the full packet and rides on TCP , making it less suited to very high-
- volume simultaneous-connection scenarios such as thousands of WiFi clients.

**සිංහලෙන්:** **TACACS+: Strengths and Weaknesses** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TACACS+
- Strengths: full-packet encryption gives meaningfully stronger confidentiality than RADIUS. Genuinely separating
- authentication, authorization, and accounting allows fine-grained control over each independently, including command-level
- authorization. TCP provides reliable delivery.

**🧠 Memory Tip:** Remember **TACACS+: Strengths and Weaknesses** by linking its purpose → mechanism → result.

### RADIUS vs. TACACS+: Full Comparison (Slide 17)

**Exam Answer:** COMPARISON.

**Explanation:**

- COMPARISON
- Aspect RADIUS TACACS+
- Transport UDP TCP
- Reliability No built-in retransmission Reliable delivery via TCP
- Encryption Password only Entire packet
- AAA separation Authentication and authorization combined All three functions fully separate
- Vendor support Open, multi-vendor (RFC 2865/2866) Cisco-proprietary
- Overhead Lower, suited to high connection volume Higher, justified by finer administrative control
- Typical use Network access (WiFi, VPN) Device administration (router/switch CLI)

**සිංහලෙන්:** **RADIUS vs. TACACS+: Full Comparison** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- COMPARISON
- Aspect RADIUS TACACS+
- Transport UDP TCP
- Reliability No built-in retransmission Reliable delivery via TCP

**🧠 Memory Tip:** Remember **RADIUS vs. TACACS+: Full Comparison** by linking its purpose → mechanism → result.

### AAA Method Lists (Slide 18)

**Exam Answer:** What happens when the first choice isn't available.

**Explanation:**

- What happens when the first choice isn't available

**සිංහලෙන්:** **AAA Method Lists** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- What happens when the first choice isn't available

**🧠 Memory Tip:** Remember **AAA Method Lists** by linking its purpose → mechanism → result.

### What a Method List Actually Is (Slide 19)

**Exam Answer:** METHOD LISTS.

**Explanation:**

- METHOD LISTS
- A method list defines an ordered sequence of AAA methods to try, one after another, until one of them succeeds or the
- whole list is exhausted.
- A typical example: try TACACS+ first, and if the TACACS+ server doesn't respond at all, fall back to the local username and
- password database.
- This directly solves server-based AAA's single point of failure from earlier. If the central server becomes unreachable, the
- device doesn't simply lock everyone out, it falls back to a still-functioning local option instead.

**සිංහලෙන්:** **What a Method List Actually Is** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- METHOD LISTS
- A method list defines an ordered sequence of AAA methods to try, one after another, until one of them succeeds or the
- whole list is exhausted.
- A typical example: try TACACS+ first, and if the TACACS+ server doesn't respond at all, fall back to the local username and

**🧠 Memory Tip:** Remember **What a Method List Actually Is** by linking its purpose → mechanism → result.

### The Same Logic as an ACL, Applied to AAA (Slide 20)

**Exam Answer:** METHOD LISTS.

**Explanation:**

- METHOD LISTS
- Recall Week 7: an ACL is processed top to bottom, and the first matching statement wins, with everything below it never
- even evaluated for that packet.
- A method list works the same way. Each method is tried in the order it's listed, and the first one that actually produces a
- usable result, success or a definitive deny, is what gets applied.
- Fall-through to the next method only happens when a method is unavailable, such as the server not responding at all, not
- simply because it denied the request.

**සිංහලෙන්:** **The Same Logic as an ACL, Applied to AAA** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- METHOD LISTS
- Recall Week 7: an ACL is processed top to bottom, and the first matching statement wins, with everything below it never
- even evaluated for that packet.
- A method list works the same way. Each method is tried in the order it's listed, and the first one that actually produces a

**🧠 Memory Tip:** Remember **The Same Logic as an ACL, Applied to AAA** by linking its purpose → mechanism → result.

### Configuring AAA on Cisco Devices (Slide 21)

**Exam Answer:** Concept alongside the actual command templates.

**Explanation:**

- Concept alongside the actual command templates

**සිංහලෙන්:** **Configuring AAA on Cisco Devices** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Concept alongside the actual command templates

**🧠 Memory Tip:** Remember **Configuring AAA on Cisco Devices** by linking its purpose → mechanism → result.

### Step 1, Enable AAA (Slide 22)

**Exam Answer:** CONFIGURATION.

**Explanation:**

- CONFIGURATION
- Before any AAA command works at all, AAA itself must be explicitly enabled on the device.
- aaa new-model

**සිංහලෙන්:** **Step 1, Enable AAA** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION
- Before any AAA command works at all, AAA itself must be explicitly enabled on the device.
- aaa new-model

**🧠 Memory Tip:** Remember **Step 1, Enable AAA** by linking its purpose → mechanism → result.

### Step 2, Local AAA (Slide 23)

**Exam Answer:** CONFIGURATION.

**Explanation:**

- CONFIGURATION
- Create a local user, then tell the device to authenticate logins against that local database.
- username admin privilege 15 secret StrongPass123
- aaa authentication login default local

**සිංහලෙන්:** **Step 2, Local AAA** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION
- Create a local user, then tell the device to authenticate logins against that local database.
- username admin privilege 15 secret StrongPass123
- aaa authentication login default local

**🧠 Memory Tip:** Remember **Step 2, Local AAA** by linking its purpose → mechanism → result.

### Step 3, TACACS+ Server-Based AAA (Slide 24)

**Exam Answer:** CONFIGURATION.

**Explanation:**

- CONFIGURATION
- Define the TACACS+ server and its shared key, then build a method list that tries TACACS+ first and falls back to local if the
- server is unreachable.
- tacacs server TACACS-SERVER1
- address ipv4 192.168.1.100
- key MySharedKey
- aaa authentication login default group tacacs+ local
- aaa authorization exec default group tacacs+ local
- aaa accounting exec default start-stop group tacacs+

**සිංහලෙන්:** **Step 3, TACACS+ Server-Based AAA** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION
- Define the TACACS+ server and its shared key, then build a method list that tries TACACS+ first and falls back to local if the
- server is unreachable.
- tacacs server TACACS-SERVER1

**🧠 Memory Tip:** Remember **Step 3, TACACS+ Server-Based AAA** by linking its purpose → mechanism → result.

### Step 4, RADIUS Server-Based AAA (Slide 25)

**Exam Answer:** CONFIGURATION.

**Explanation:**

- CONFIGURATION
- Define the RADIUS server and its shared key, then build a method list the same way, RADIUS first, local as the fallback.
- radius server RADIUS-SERVER1
- address ipv4 192.168.1.200 auth-port 1812 acct-port 1813
- key MySharedKey
- aaa authentication login default group radius local
- Notice the method list itself: group tacacs+ local, or group radius local. The order you write the command in is the fallbackorder, matching exactly
- the ACL-style top-to-bottom logic from the previous section.

**සිංහලෙන්:** **Step 4, RADIUS Server-Based AAA** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONFIGURATION
- Define the RADIUS server and its shared key, then build a method list the same way, RADIUS first, local as the fallback.
- radius server RADIUS-SERVER1
- address ipv4 192.168.1.200 auth-port 1812 acct-port 1813

**🧠 Memory Tip:** Remember **Step 4, RADIUS Server-Based AAA** by linking its purpose → mechanism → result.

### Summary (Slide 26)

**Exam Answer:** Local AAA needs no infrastructure but doesn't scale. Server-based AAA scales and centralises, but adds a dependency on the.

**Explanation:**

- Local AAA needs no infrastructure but doesn't scale. Server-based AAA scales and centralises, but adds a dependency on the
- server being reachable.
- Device administration AAA and network access AAA protect genuinely different things, which is exactly why TACACS+ and
- RADIUS each dominate a different one of them.
- TACACS+ trades a proprietary standard for full-packet encryption and clean AAA separation. RADIUS trades weaker
- encryption for open, multi-vendor, high-volume connection handling.
- A method list is how a device survives its primary AAA source going down, falling back in a defined order rather than simply
- locking everyone out.

**සිංහලෙන්:** **Summary** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Local AAA needs no infrastructure but doesn't scale. Server-based AAA scales and centralises, but adds a dependency on the
- server being reachable.
- Device administration AAA and network access AAA protect genuinely different things, which is exactly why TACACS+ and
- RADIUS each dominate a different one of them.

**🧠 Memory Tip:** Remember **Summary** by linking its purpose → mechanism → result.

### This Week's Lab & Tutorial (Slide 27)

**Exam Answer:** Lab: to be planned in a follow-up discussion, once we've confirmed which of today's configurations are genuinely supported.

**Explanation:**

- Lab: to be planned in a follow-up discussion, once we've confirmed which of today's configurations are genuinely supported
- and testable in Packet Tracer.
- Tutorial worksheet: study-notes-style questions covering local versus centralised AAA, RADIUS versus TACACS+, method lists,
- and Cisco configuration. Use it to prep for the mid-semester test.

**සිංහලෙන්:** **This Week's Lab & Tutorial** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Lab: to be planned in a follow-up discussion, once we've confirmed which of today's configurations are genuinely supported
- and testable in Packet Tracer.
- Tutorial worksheet: study-notes-style questions covering local versus centralised AAA, RADIUS versus TACACS+, method lists,
- and Cisco configuration. Use it to prep for the mid-semester test.

**🧠 Memory Tip:** Remember **This Week's Lab & Tutorial** by linking its purpose → mechanism → result.


## 📊 Important Comparisons

| Comparison/topic | Source | Exam focus |
|---|---:|---|
| Local vs. Server-Based AAA | Slide 4 | Where the decision actually gets made. |
| Local vs. Server-Based: Comparison | Slide 7 | DEPLOYMENT. |
| Device Administration AAA vs. Network | Slide 8 | Access AAA. |
| RADIUS vs. TACACS+ | Slide 12 | Two protocols, two different jobs. |
| RADIUS vs. TACACS+: Full Comparison | Slide 17 | COMPARISON. |
| Summary | Slide 26 | Local AAA needs no infrastructure but doesn't scale. Server-based AAA scales and centralises, but adds a dependency on the. |

## 🛠️ Practical Knowledge

### Deploying and Configuring AAA (Slide 1)

- IE3122: Network Security | Week 10
- Where the decision gets made, who makes it, and how to actually configure it

### Today's Agenda (Slide 2)

- Local versus server-based (centralised) AAA
- Device administration AAA versus network access AAA, and why that distinction matters
- RADIUS versus TACACS+, in full technical detail
- AAA method lists, ordered fallback between AAA sources
- Configuring AAA on Cisco devices: concept alongside the actual command templates

### Local vs. Server-Based: Comparison (Slide 7)

- DEPLOYMENT
- Aspect Local AAA Server-Based AAA
- Consistency Managed per device, inconsistent at scale One central database, consistent everywhere
- Scalability Poor, doesn't scale beyond a few devices Strong, scales to large networks
- Dependency None, entirely self-contained Depends on the AAA server being reachable
- Typical use Small networks, or as a fallback method Enterprise networks

### Device Administration AAA (Slide 9)

- TWO KINDS OF ACCESS
- Controls who can log into the network's own infrastructure devices, a router or switch's CLI, and once in, exactly which
- commands they're allowed to run.
- The stakes here are can this person reconfigure the network, and the natural granularity is per command.
- This is TACACS+'s traditional home ground, covered in detail shortly.

### Network Access AAA (Slide 10)

- TWO KINDS OF ACCESS
- Controls who or what can get onto the network in the first place: WiFi association, a VPN connection (recall Week 9), or
- wired 802.1X port authentication.
- The stakes here are can this device or user reach the network at all. There's no equivalent of per-command granularity, since
- an end user connecting to WiFi isn't issuing router commands.
- This is RADIUS's traditional home ground, built for fast, high-volume, simultaneous connection handling rather than fine-
- grained command control.

### Why This Distinction Actually Matters (Slide 11)

- TWO KINDS OF ACCESS
- TACACS+'s full-packet encryption and its clean separation of all three AAA functions matches device administration's need for
- fine-grained, secure command control.
- RADIUS's lighter design, encrypting only the password, and bundling authentication with authorization matches network
- access's need for fast, high-volume connection handling.
- Neither protocol is simply better overall. Each is well suited to the specific stakes and scale of its own traditional use case,
- which is exactly why both still exist side by side today.

### TACACS+: Mechanism and Use Cases (Slide 15)

- TACACS+
- Terminal Access Controller Access-Control System Plus. Cisco's own protocol for device administration AAA.
- Transport: TCP , on port 49, giving reliable delivery that UDP doesn't guarantee.
- Encrypts the entire packet body, not just the password, and cleanly separates all three AAA functions into genuinely
- independent exchanges rather than bundling them.
- Use cases: administering Cisco routers and switches, controlling exactly which CLI commands a given administrator can run,
- and any enterprise environment needing a detailed, per-command audit trail for its own infrastructure.

### TACACS+: Strengths and Weaknesses (Slide 16)

- TACACS+
- Strengths: full-packet encryption gives meaningfully stronger confidentiality than RADIUS. Genuinely separating
- authentication, authorization, and accounting allows fine-grained control over each independently, including command-level
- authorization. TCP provides reliable delivery.
- Weaknesses: Cisco-proprietary, so it isn't natively supported across other vendors' equipment the way RADIUS is. Carries
- heavier protocol overhead than RADIUS, since it encrypts the full packet and rides on TCP , making it less suited to very high-
- volume simultaneous-connection scenarios such as thousands of WiFi clients.

### AAA Method Lists (Slide 18)

- What happens when the first choice isn't available

### The Same Logic as an ACL, Applied to AAA (Slide 20)

- METHOD LISTS
- Recall Week 7: an ACL is processed top to bottom, and the first matching statement wins, with everything below it never
- even evaluated for that packet.
- A method list works the same way. Each method is tried in the order it's listed, and the first one that actually produces a
- usable result, success or a definitive deny, is what gets applied.
- Fall-through to the next method only happens when a method is unavailable, such as the server not responding at all, not
- simply because it denied the request.

### Configuring AAA on Cisco Devices (Slide 21)

- Concept alongside the actual command templates

### Step 1, Enable AAA (Slide 22)

- CONFIGURATION
- Before any AAA command works at all, AAA itself must be explicitly enabled on the device.
- aaa new-model

### Step 2, Local AAA (Slide 23)

- CONFIGURATION
- Create a local user, then tell the device to authenticate logins against that local database.
- username admin privilege 15 secret StrongPass123
- aaa authentication login default local

### Step 3, TACACS+ Server-Based AAA (Slide 24)

- CONFIGURATION
- Define the TACACS+ server and its shared key, then build a method list that tries TACACS+ first and falls back to local if the
- server is unreachable.
- tacacs server TACACS-SERVER1
- address ipv4 192.168.1.100
- key MySharedKey
- aaa authentication login default group tacacs+ local
- aaa authorization exec default group tacacs+ local
- aaa accounting exec default start-stop group tacacs+

### Step 4, RADIUS Server-Based AAA (Slide 25)

- CONFIGURATION
- Define the RADIUS server and its shared key, then build a method list the same way, RADIUS first, local as the fallback.
- radius server RADIUS-SERVER1
- address ipv4 192.168.1.200 auth-port 1812 acct-port 1813
- key MySharedKey
- aaa authentication login default group radius local
- Notice the method list itself: group tacacs+ local, or group radius local. The order you write the command in is the fallbackorder, matching exactly
- the ACL-style top-to-bottom logic from the previous section.

### This Week's Lab & Tutorial (Slide 27)

- Lab: to be planned in a follow-up discussion, once we've confirmed which of today's configurations are genuinely supported
- and testable in Packet Tracer.
- Tutorial worksheet: study-notes-style questions covering local versus centralised AAA, RADIUS versus TACACS+, method lists,
- and Cisco configuration. Use it to prep for the mid-semester test.

### References (Slide 28)

- Santos & Stuppi, CCNA Security 210-260 Official Cert Guide, 1st Ed., Cisco Press.
- Kaufman, Perlman, Speciner & Perlner, Network Security: Private Communication in a Public World, 3rd Ed., Prentice Hall.
- Cisco Networking Academy, CCNA Security curriculum (AAA configuration chapters).

## ⭐ Important Exam Points

- ⭐ **Local vs. Server-Based AAA (Slide 4):** Where the decision actually gets made.
- ⭐ **Local AAA (Slide 5):** DEPLOYMENT.
- ⭐ **Server-Based (Centralised) AAA (Slide 6):** DEPLOYMENT.
- ⭐ **Local vs. Server-Based: Comparison (Slide 7):** DEPLOYMENT.
- ⭐ **Device Administration AAA vs. Network (Slide 8):** Access AAA.
- ⭐ **Device Administration AAA (Slide 9):** TWO KINDS OF ACCESS.
- ⭐ **Network Access AAA (Slide 10):** TWO KINDS OF ACCESS.
- ⭐ **Why This Distinction Actually Matters (Slide 11):** TWO KINDS OF ACCESS.
- ⭐ **RADIUS vs. TACACS+ (Slide 12):** Two protocols, two different jobs.
- ⭐ **RADIUS: Mechanism and Use Cases (Slide 13):** RADIUS.
- ⭐ **RADIUS: Strengths and Weaknesses (Slide 14):** RADIUS.
- ⭐ **TACACS+: Mechanism and Use Cases (Slide 15):** TACACS+.
- ⭐ **TACACS+: Strengths and Weaknesses (Slide 16):** TACACS+.
- ⭐ **RADIUS vs. TACACS+: Full Comparison (Slide 17):** COMPARISON.
- ⭐ **AAA Method Lists (Slide 18):** What happens when the first choice isn't available.

## ❓ Possible Exam Questions

### MCQs

1. Which statement best matches **Local vs. Server-Based AAA**?
   - A. It is unrelated to network security.
   - B. Where the decision actually gets made.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

2. Which statement best matches **Device Administration AAA vs. Network**?
   - A. It is unrelated to network security.
   - B. Access AAA.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

3. Which statement best matches **RADIUS vs. TACACS+**?
   - A. It is unrelated to network security.
   - B. Two protocols, two different jobs.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

4. Which statement best matches **TACACS+: Strengths and Weaknesses**?
   - A. It is unrelated to network security.
   - B. TACACS+.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

5. Which statement best matches **The Same Logic as an ACL, Applied to AAA**?
   - A. It is unrelated to network security.
   - B. METHOD LISTS.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**


### Short Structured Questions

1. **Explain Local vs. Server-Based AAA.**
   - **Model answer:** Where the decision actually gets made.

2. **Explain Device Administration AAA vs. Network.**
   - **Model answer:** Access AAA.

3. **Explain RADIUS vs. TACACS+.**
   - **Model answer:** Two protocols, two different jobs.

4. **Explain TACACS+: Strengths and Weaknesses.**
   - **Model answer:** TACACS+.

5. **Explain The Same Logic as an ACL, Applied to AAA.**
   - **Model answer:** METHOD LISTS.


### Scenario-Based Question

**Scenario:** An organization must apply the concepts from **AAA Deployment and Configuration** to improve its network security. Identify the relevant mechanism or risk, explain the likely impact, and recommend a layered response.

**Model-answer approach:** Identify the asset and trust boundary; name the relevant protocol/control; explain the mechanism using the lecture terminology; state confidentiality, integrity, or availability impact; then recommend the matching prevention, detection, and verification steps from the slides.

## ⚡ Last-Minute Quick Revision

- **Local vs. Server-Based AAA:** Where the decision actually gets made.
- **Local AAA:** DEPLOYMENT.
- **Server-Based (Centralised) AAA:** DEPLOYMENT.
- **Local vs. Server-Based: Comparison:** DEPLOYMENT.
- **Device Administration AAA vs. Network:** Access AAA.
- **Device Administration AAA:** TWO KINDS OF ACCESS.
- **Network Access AAA:** TWO KINDS OF ACCESS.
- **Why This Distinction Actually Matters:** TWO KINDS OF ACCESS.
- **RADIUS vs. TACACS+:** Two protocols, two different jobs.
- **RADIUS: Mechanism and Use Cases:** RADIUS.
- **RADIUS: Strengths and Weaknesses:** RADIUS.
- **TACACS+: Mechanism and Use Cases:** TACACS+.
- **TACACS+: Strengths and Weaknesses:** TACACS+.
- **RADIUS vs. TACACS+: Full Comparison:** COMPARISON.
- **AAA Method Lists:** What happens when the first choice isn't available.
- **What a Method List Actually Is:** METHOD LISTS.
- **The Same Logic as an ACL, Applied to AAA:** METHOD LISTS.
- **Configuring AAA on Cisco Devices:** Concept alongside the actual command templates.
- **Step 1, Enable AAA:** CONFIGURATION.
- **Step 2, Local AAA:** CONFIGURATION.

## Verification Notes

- Slide coverage: **28 of 28 slides processed**.
- Slide numbers refer to PDF page order.
- Any application example or scenario above extends the slide concept for revision and is not presented as a verbatim lecturer statement.
