# Lecture 03 – Networking and Security Revision

## 📌 Lecture Overview

This lecture covers **Networking and Security Revision** as presented in the supplied IE3122 slides. The notes follow the source order across 45 slides and retain the lecture's terminology, mechanisms, examples, and configuration details. They are organized for rapid MCQ, structured-answer, and scenario revision.

> **Source boundary:** Content below is derived from `IE3122_Week2_NetworkingAndSecurityRevision_Slides.pdf`. Generic exam prompts/examples are labelled as application material; no unsupported lecturer emphasis is claimed.

## 🎯 Learning Objectives

- LO1
- Describe common network vulnerabilities and attacks.
- LO3
- Analyse a company's network and communication requirements and communicate security requirements.
- By the end of this session you should be able to name the major categories of attackers and attacks, and explain why layered
- defense matters — the foundation for everything from Week 3 onward.

## 📚 Main Topics and Subtopics

### Why Network Security Matters (Slide 4)

**Exam Answer:** Setting the stage.

**Explanation:**

- Setting the stage

**සිංහලෙන්:** **Why Network Security Matters** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Setting the stage

**🧠 Memory Tip:** Remember **Why Network Security Matters** by linking its purpose → mechanism → result.

### What Is Network Security? (Slide 5)

**Exam Answer:** OVERVIEW.

**Explanation:**

- OVERVIEW
- The practice of protecting the confidentiality, integrity, and availability of data as it moves across and is stored on a
- network.
- Covers people, process, and technology — not just firewalls and passwords.
- Applies at every layer we revised in Week 1: physical cabling, switches/routers, protocols, and the applications
- running on top.
- This module builds toward being able to identify weaknesses (LO1) and recommend/configure defenses (LO2, LO4,
- LO5).

**සිංහලෙන්:** **What Is Network Security?** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- OVERVIEW
- The practice of protecting the confidentiality, integrity, and availability of data as it moves across and is stored on a
- network.
- Covers people, process, and technology — not just firewalls and passwords.

**🧠 Memory Tip:** Remember **What Is Network Security?** by linking its purpose → mechanism → result.

### Why It Matters (Slide 6)

**Exam Answer:** OVERVIEW.

**Explanation:**

- OVERVIEW
- Modern organisations run on networks — a compromised network can mean stolen data, halted operations, financial
- loss, and reputational damage.
- Attacks aren't rare or abstract: recall the real 2025–2026 breaches from Week 1's lab (retail ransomware, VPN zero-
- days, exposed devices, vendor breaches).
- Security is not a one-time setup — the threat landscape keeps changing, which is exactly why this lecture exists
- before we get into specific technologies.
- As a future network/security professional, understanding *why* an attack works is what lets you recommend the
- right defense — not just follow a checklist.

**සිංහලෙන්:** **Why It Matters** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- OVERVIEW
- Modern organisations run on networks — a compromised network can mean stolen data, halted operations, financial
- loss, and reputational damage.
- Attacks aren't rare or abstract: recall the real 2025–2026 breaches from Week 1's lab (retail ransomware, VPN zero-

**🧠 Memory Tip:** Remember **Why It Matters** by linking its purpose → mechanism → result.

### The Extended CIA Triad (Slide 7)

**Exam Answer:** Fundamental Information Security Controls.

**Explanation:**

- Fundamental Information Security Controls

**සිංහලෙන්:** **The Extended CIA Triad** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Fundamental Information Security Controls

**🧠 Memory Tip:** Remember **The Extended CIA Triad** by linking its purpose → mechanism → result.

### The CIA Triad (Slide 8)

**Exam Answer:** SECURITY PRINCIPLES.

**Explanation:**

- SECURITY PRINCIPLES
- Confidentiality
- Only authorised people/systems can access the
- data
- Integrity
- Data is accurate and hasn't been altered without
- authorisation
- Availability
- Data and systems are accessible to legitimate
- users when needed
- The CIA Triad is the foundational model for what ‘security’ actually means — almost every control we cover this semester
- protects one or more of these three properties.
- An attack usually targets one corner specifically: theft/eavesdropping breaks confidentiality, tampering breaks integrity, and a
- DoS/DDoS attack breaks availability.
- Trade-offs are common — stronger confidentiality controls (e.g. heavy encryption, strict access checks) can sometimes
- reduce availability if overdone. Good security design balances all three, not maximises one.

**සිංහලෙන්:** **The CIA Triad** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SECURITY PRINCIPLES
- Confidentiality
- Only authorised people/systems can access the
- data

**🧠 Memory Tip:** Remember **The CIA Triad** by linking its purpose → mechanism → result.

### Authentication (Slide 9)

**Exam Answer:** SECURITY PRINCIPLES.

**Explanation:**

- SECURITY PRINCIPLES
- Authentication answers one question: is this person/device really who they claim to be?
- It's distinct from authorisation (what you're allowed to do once verified) — authentication comes first.
- Three general factor categories: something you know (password, PIN), something you have (a token, a phone, a smart
- card), something you are (biometrics — fingerprint, face).
- Multi-Factor Authentication (MFA) combines two or more of these categories — significantly harder to defeat than
- any single factor alone, since compromising a password alone is no longer enough.
- This is a preview: we'll cover authentication systems (RADIUS, TACACS+) in full under AAA in Week 8 — for now, just
- recognise it as one of the core security principles everything else builds on.

**සිංහලෙන්:** **Authentication** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SECURITY PRINCIPLES
- Authentication answers one question: is this person/device really who they claim to be?
- It's distinct from authorisation (what you're allowed to do once verified) — authentication comes first.
- Three general factor categories: something you know (password, PIN), something you have (a token, a phone, a smart

**🧠 Memory Tip:** Remember **Authentication** by linking its purpose → mechanism → result.

### Non-Repudiation (Slide 10)

**Exam Answer:** SECURITY PRINCIPLES.

**Explanation:**

- SECURITY PRINCIPLES
- Non-repudiation means a party can't credibly deny having performed an action — sent a message, approved a
- transaction, accessed a system — once there's verifiable proof they did.
- It's what makes an action accountable after the fact, not just secure in the moment — confidentiality and integrity
- protect the data itself, non-repudiation protects the record of who did what.
- Achieved through mechanisms like digital signatures and audit logging — a digital signature cryptographically ties an
- action to a specific identity in a way that identity can't later disown.
- Real-world relevance: this is why financial transactions, legal documents, and security-critical system changes rely on
- digitally signed records rather than just usernames in a log file.
- Another preview: we'll cover the cryptographic mechanisms behind this — hash functions, digital certificates, PKI —
- in full in Week 12.

**සිංහලෙන්:** **Non-Repudiation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SECURITY PRINCIPLES
- Non-repudiation means a party can't credibly deny having performed an action — sent a message, approved a
- transaction, accessed a system — once there's verifiable proof they did.
- It's what makes an action accountable after the fact, not just secure in the moment — confidentiality and integrity

**🧠 Memory Tip:** Remember **Non-Repudiation** by linking its purpose → mechanism → result.

### Key Terms & Threat Modeling (Slide 11)

**Exam Answer:** The vocabulary we'll use all semester.

**Explanation:**

- The vocabulary we'll use all semester

**සිංහලෙන්:** **Key Terms & Threat Modeling** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- The vocabulary we'll use all semester

**🧠 Memory Tip:** Remember **Key Terms & Threat Modeling** by linking its purpose → mechanism → result.

### Key Terms — Revision (Slide 12)

**Exam Answer:** TERMINOLOGY.

**Explanation:**

- TERMINOLOGY
- Term Meaning
- Asset Anything of value worth protecting — data, a server, a service, even reputation
- Vulnerability A weakness that could be exploited (a bug, misconfiguration, missing patch)
- Threat Anything with the potential to exploit a vulnerability and cause harm
- Exploit The specific method/tool used to take advantage of a vulnerability
- Attack The actual event of a threat using an exploit against a vulnerability
- Impact The real-world consequence of a successful attack — data loss, downtime, cost
- Risk The likelihood and impact of a threat actually exploiting a vulnerability
- Mitigation The control or action taken to reduce a vulnerability, threat, or its impact

**සිංහලෙන්:** **Key Terms — Revision** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TERMINOLOGY
- Term Meaning
- Asset Anything of value worth protecting — data, a server, a service, even reputation
- Vulnerability A weakness that could be exploited (a bug, misconfiguration, missing patch)

**🧠 Memory Tip:** Remember **Key Terms — Revision** by linking its purpose → mechanism → result.

### How These Terms Fit Together (Slide 13)

**Exam Answer:** TERMINOLOGY.

**Explanation:**

- TERMINOLOGY
- 1 · Asset 2 · Vulnerability 3 · Threat 4 · Exploit
- 5 · Attack 6 · Impact 7 · Risk Mitigation
- Read left-to-right, top row then bottom row: a threat uses an exploit against a vulnerability to carry out an attack, which causes an
- impact — together these determine the risk.
- Mitigation is the response: a control that reduces the vulnerability, blocks the exploit, or limits the impact — lowering the overall risk.
- Risk is what security professionals actually manage — you can rarely eliminate every vulnerability, so you prioritise mitigations by
- risk.

**සිංහලෙන්:** **How These Terms Fit Together** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TERMINOLOGY
- 1 · Asset 2 · Vulnerability 3 · Threat 4 · Exploit
- 5 · Attack 6 · Impact 7 · Risk Mitigation
- Read left-to-right, top row then bottom row: a threat uses an exploit against a vulnerability to carry out an attack, which causes an

**🧠 Memory Tip:** Remember **How These Terms Fit Together** by linking its purpose → mechanism → result.

### What Is Threat Modeling? (Slide 14)

**Exam Answer:** TERMINOLOGY.

**Explanation:**

- TERMINOLOGY
- A structured way of asking: what are we protecting, who might attack it, how might they do it, and what should we
- do about it?
- A simple, repeatable process: identify assets → identify likely threats → assess vulnerabilities → prioritise and
- mitigate by risk.
- This is exactly the reasoning LO3 asks of you — analyzing a company's network/communication requirements starts
- with a threat model, not a product list.
- We'll come back to this process every time we look at a new attack category or technology for the rest of the module.

**සිංහලෙන්:** **What Is Threat Modeling?** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TERMINOLOGY
- A structured way of asking: what are we protecting, who might attack it, how might they do it, and what should we
- do about it?
- A simple, repeatable process: identify assets → identify likely threats → assess vulnerabilities → prioritise and

**🧠 Memory Tip:** Remember **What Is Threat Modeling?** by linking its purpose → mechanism → result.

### Worked Example: A Small Online Retailer (Slide 15)

**Exam Answer:** TERMINOLOGY.

**Explanation:**

- TERMINOLOGY
- Step Applied to this company
- Asset Customer payment data, the order-processing database
- Vulnerability Unpatched web server, weak admin password policy
- Threat Financially motivated attackers (black hats, criminal groups)
- Exploit A known, unpatched web-server vulnerability with public exploit code available
- Attack Attackers use the exploit to gain admin access and copy the payment database
- Impact Stolen customer payment data, regulatory fines, loss of customer trust
- Risk High — valuable data + known weaknesses + attackers actively interested
- Mitigation Patch the web server promptly, enforce strong admin passwords + MFA, encrypt stored data
- This is the exact reasoning you'll apply in this week's lab — and in the group assignment later in the semester.

**සිංහලෙන්:** **Worked Example: A Small Online Retailer** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- TERMINOLOGY
- Step Applied to this company
- Asset Customer payment data, the order-processing database
- Vulnerability Unpatched web server, weak admin password policy

**🧠 Memory Tip:** Remember **Worked Example: A Small Online Retailer** by linking its purpose → mechanism → result.

### How Networking — and Its Threats — Have (Slide 16)

**Exam Answer:** Evolved.

**Explanation:**

- Evolved
- Same principles, a much bigger attack surface

**සිංහලෙන්:** **How Networking — and Its Threats — Have** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Evolved
- Same principles, a much bigger attack surface

**🧠 Memory Tip:** Remember **How Networking — and Its Threats — Have** by linking its purpose → mechanism → result.

### From Isolated Systems to Everything Connected (Slide 17)

**Exam Answer:** EVOLUTION.

**Explanation:**

- EVOLUTION
- 1980s–90s
- Isolated LANs
- Physical access was the main risk
- 2000s
- Internet-connected
- Remote attacks become possible
- 2010s
- Cloud & mobile
- Data leaves the building; more entry
- points
- 2020s+
- IoT & remote work
- Billions of devices, no fixed perimeter

**සිංහලෙන්:** **From Isolated Systems to Everything Connected** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- EVOLUTION
- 1980s–90s
- Isolated LANs
- Physical access was the main risk

**🧠 Memory Tip:** Remember **From Isolated Systems to Everything Connected** by linking its purpose → mechanism → result.

### The Threat Landscape Evolved Alongside It (Slide 18)

**Exam Answer:** EVOLUTION.

**Explanation:**

- EVOLUTION
- More connectivity has always meant more attack surface — every new capability (remote access, cloud storage, IoT
- sensors) is also a new way in.
- Attacks have professionalised: from lone hobbyists to organised criminal groups, data brokers, and state-sponsored
- operations (more on this shortly).
- The targets have changed too — attackers now go after cloud misconfigurations, VPN appliances, and supply-
- chain/vendor relationships, not just a single office firewall (recall Week 1's Ivanti VPN and SonicWall vendor-breach
- case studies).
- The core lesson: the fundamentals we revised in Week 1 (layers, protocols) still apply — but the scale and
- sophistication of who's attacking them has grown enormously.

**සිංහලෙන්:** **The Threat Landscape Evolved Alongside It** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- EVOLUTION
- More connectivity has always meant more attack surface — every new capability (remote access, cloud storage, IoT
- sensors) is also a new way in.
- Attacks have professionalised: from lone hobbyists to organised criminal groups, data brokers, and state-sponsored

**🧠 Memory Tip:** Remember **The Threat Landscape Evolved Alongside It** by linking its purpose → mechanism → result.

### Types of Hackers (Slide 19)

**Exam Answer:** Knowing who you're defending against.

**Explanation:**

- Knowing who you're defending against

**සිංහලෙන්:** **Types of Hackers** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Knowing who you're defending against

**🧠 Memory Tip:** Remember **Types of Hackers** by linking its purpose → mechanism → result.

### Hackers Aren't All the Same (Slide 20)

**Exam Answer:** THREAT ACTORS.

**Explanation:**

- THREAT ACTORS
- ‘Hacker’ just means someone with the skill to find and exploit weaknesses in a system — it says nothing about their
- intent.
- Understanding who's likely to target a given organisation is part of LO3's ‘analyse requirements’ — a bank and a small
- blog face very different threat actors.
- Two common ways to categorise attackers: the ‘hat’ spectrum (intent/ethics) and role-based categories (how they
- operate or who they work for).

**සිංහලෙන්:** **Hackers Aren't All the Same** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- THREAT ACTORS
- ‘Hacker’ just means someone with the skill to find and exploit weaknesses in a system — it says nothing about their
- intent.
- Understanding who's likely to target a given organisation is part of LO3's ‘analyse requirements’ — a bank and a small

**🧠 Memory Tip:** Remember **Hackers Aren't All the Same** by linking its purpose → mechanism → result.

### The Hat Spectrum (Slide 21)

**Exam Answer:** THREAT ACTORS.

**Explanation:**

- THREAT ACTORS
- Hat Who they are
- White Hat Ethical hackers authorised to test systems and report weaknesses
- Black Hat Malicious attackers exploiting systems for personal or financial gain
- Grey Hat Find vulnerabilities without permission but without malicious intent — legally ambiguous
- Blue Hat Security professionals (often external/outsourced) who test an organisation's own systems
- Red Hat Aggressively target black hats directly, sometimes using illegal methods themselves
- Green Hat Newcomers still learning — enthusiastic but limited skill, can cause accidental harm

**සිංහලෙන්:** **The Hat Spectrum** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- THREAT ACTORS
- Hat Who they are
- White Hat Ethical hackers authorised to test systems and report weaknesses
- Black Hat Malicious attackers exploiting systems for personal or financial gain

**🧠 Memory Tip:** Remember **The Hat Spectrum** by linking its purpose → mechanism → result.

### Beyond the Hats (Slide 22)

**Exam Answer:** THREAT ACTORS.

**Explanation:**

- THREAT ACTORS
- Category What defines them
- Script Kiddies Little technical skill — run existing tools/scripts written by others
- Access & Data Brokers Sell stolen access or data to other attackers rather than exploiting it themselves
- State-Sponsored Hackers Funded by governments; highly resourced, target high-value/strategic systems
- Hacktivists Motivated by political or social causes, not money — aim to expose or disrupt
- These aren't mutually exclusive with the hat spectrum — a state-sponsored hacker, for instance, is still operating with black-hat intent.

**සිංහලෙන්:** **Beyond the Hats** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- THREAT ACTORS
- Category What defines them
- Script Kiddies Little technical skill — run existing tools/scripts written by others
- Access & Data Brokers Sell stolen access or data to other attackers rather than exploiting it themselves

**🧠 Memory Tip:** Remember **Beyond the Hats** by linking its purpose → mechanism → result.

### Key Motivations (Slide 23)

**Exam Answer:** THREAT ACTORS.

**Explanation:**

- THREAT ACTORS
- Financial gain Ransomware, fraud, selling stolen data
- Ideology / politics Hacktivism — expose or disrupt a cause's opponents
- Espionage State-sponsored theft of intelligence or IP
- Revenge Targeting a specific person or organisation
- Curiosity / challenge Proving a skill, sometimes with no clear malicious goal

**සිංහලෙන්:** **Key Motivations** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- THREAT ACTORS
- Financial gain Ransomware, fraud, selling stolen data
- Ideology / politics Hacktivism — expose or disrupt a cause's opponents
- Espionage State-sponsored theft of intelligence or IP

**🧠 Memory Tip:** Remember **Key Motivations** by linking its purpose → mechanism → result.

### Main Types of Attacks (Slide 24)

**Exam Answer:** Malware, social engineering, DoS/DDoS, and reconnaissance.

**Explanation:**

- Malware, social engineering, DoS/DDoS, and reconnaissance

**සිංහලෙන්:** **Main Types of Attacks** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Malware, social engineering, DoS/DDoS, and reconnaissance

**🧠 Memory Tip:** Remember **Main Types of Attacks** by linking its purpose → mechanism → result.

### Four Broad Attack Categories (Slide 25)

**Exam Answer:** ATTACKS OVERVIEW.

**Explanation:**

- ATTACKS OVERVIEW
- Malware
- Malicious software that runs on a target system
- Social Engineering
- Manipulating people rather than exploiting code
- DoS / DDoS
- Overwhelming a system so legitimate users can't use it
- Access & Reconnaissance
- Gathering information or gaining unauthorised entry

**සිංහලෙන්:** **Four Broad Attack Categories** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ATTACKS OVERVIEW
- Malware
- Malicious software that runs on a target system
- Social Engineering

**🧠 Memory Tip:** Remember **Four Broad Attack Categories** by linking its purpose → mechanism → result.

### Malware: The Basics (Slide 26)

**Exam Answer:** MALWARE.

**Explanation:**

- MALWARE
- Malware = ‘malicious software’ — any program designed to damage, disrupt, or gain unauthorised access to a system.
- Delivered via email attachments, malicious downloads, infected removable media, or exploiting a software
- vulnerability directly.
- Different malware types are defined by *how they spread* and *what they do* once they're running — both matter
- for choosing a defense.

**සිංහලෙන්:** **Malware: The Basics** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- MALWARE
- Malware = ‘malicious software’ — any program designed to damage, disrupt, or gain unauthorised access to a system.
- Delivered via email attachments, malicious downloads, infected removable media, or exploiting a software
- vulnerability directly.

**🧠 Memory Tip:** Remember **Malware: The Basics** by linking its purpose → mechanism → result.

### Malware Types (1/3) (Slide 27)

**Exam Answer:** MALWARE.

**Explanation:**

- MALWARE
- Type How it behaves
- Virus Attaches to a legitimate file/program; spreads when that file is run or shared
- Worm Self-replicating; spreads across a network on its own, no user action needed
- Trojan Disguised as legitimate software; relies on the user installing it themselves

**සිංහලෙන්:** **Malware Types (1/3)** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- MALWARE
- Type How it behaves
- Virus Attaches to a legitimate file/program; spreads when that file is run or shared
- Worm Self-replicating; spreads across a network on its own, no user action needed

**🧠 Memory Tip:** Remember **Malware Types (1/3)** by linking its purpose → mechanism → result.

### Malware Types (2/3) (Slide 28)

**Exam Answer:** MALWARE.

**Explanation:**

- MALWARE
- Type How it behaves
- Ransomware Encrypts the victim's files/systems and demands payment for the decryption key
- Spyware Secretly monitors activity and exfiltrates data (keystrokes, credentials, browsing)
- Rootkit Hides deep in the system to maintain long-term, privileged, hard-to-detect access
- Real-world example: WannaCry (2017) was ransomware that spread using a worm-like mechanism — a reminder that these categories often combine
- in a single real attack.

**සිංහලෙන්:** **Malware Types (2/3)** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- MALWARE
- Type How it behaves
- Ransomware Encrypts the victim's files/systems and demands payment for the decryption key
- Spyware Secretly monitors activity and exfiltrates data (keystrokes, credentials, browsing)

**🧠 Memory Tip:** Remember **Malware Types (2/3)** by linking its purpose → mechanism → result.

### Malware Types (3/3) (Slide 29)

**Exam Answer:** MALWARE.

**Explanation:**

- MALWARE
- Type How it behaves
- Adware Automatically displays or downloads unwanted advertising; often bundled with free software
- Keylogger Records keystrokes to capture passwords, card numbers, and other sensitive input
- Bot / Botnet malware Enrolls an infected device into a remotely controlled network of ‘bots’ (recall Mirai) used for DDoS, spam, or further attack s
- Logic Bomb Malicious code that lies dormant until triggered by a specific condition or date

**සිංහලෙන්:** **Malware Types (3/3)** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- MALWARE
- Type How it behaves
- Adware Automatically displays or downloads unwanted advertising; often bundled with free software
- Keylogger Records keystrokes to capture passwords, card numbers, and other sensitive input

**🧠 Memory Tip:** Remember **Malware Types (3/3)** by linking its purpose → mechanism → result.

### Social Engineering: The Basics (Slide 30)

**Exam Answer:** SOCIAL ENGINEERING.

**Explanation:**

- SOCIAL ENGINEERING
- Attacks that manipulate people rather than exploiting a technical flaw — often the easiest way into an otherwise
- well-defended network.
- Exploits trust, urgency, authority, or fear — recall Week 1's UK retail ransomware case, which began with a help-desk
- social-engineering compromise, not a technical exploit.
- This is exactly why LO1's ‘network vulnerabilities and attacks’ has to include people and process, not just code and
- configuration.

**සිංහලෙන්:** **Social Engineering: The Basics** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SOCIAL ENGINEERING
- Attacks that manipulate people rather than exploiting a technical flaw — often the easiest way into an otherwise
- well-defended network.
- Exploits trust, urgency, authority, or fear — recall Week 1's UK retail ransomware case, which began with a help-desk

**🧠 Memory Tip:** Remember **Social Engineering: The Basics** by linking its purpose → mechanism → result.

### Social Engineering Attack Types (1/2) (Slide 31)

**Exam Answer:** SOCIAL ENGINEERING.

**Explanation:**

- SOCIAL ENGINEERING
- Type How it works
- Phishing Fraudulent email/message impersonating a trusted source to steal credentials or install malware
- Spear Phishing Phishing tailored to a specific individual or organisation using researched personal details
- Whaling Spear phishing targeted specifically at senior executives or other high-value individuals
- Smishing Phishing delivered via SMS/text message rather than email
- Vishing Voice-call version of phishing — often impersonating a bank or help desk

**සිංහලෙන්:** **Social Engineering Attack Types (1/2)** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SOCIAL ENGINEERING
- Type How it works
- Phishing Fraudulent email/message impersonating a trusted source to steal credentials or install malware
- Spear Phishing Phishing tailored to a specific individual or organisation using researched personal details

**🧠 Memory Tip:** Remember **Social Engineering Attack Types (1/2)** by linking its purpose → mechanism → result.

### Social Engineering Attack Types (2/2) (Slide 32)

**Exam Answer:** SOCIAL ENGINEERING.

**Explanation:**

- SOCIAL ENGINEERING
- Type How it works
- Pretexting Inventing a false scenario/identity to obtain information (e.g. posing as IT support)
- Baiting Offering something enticing (free download, USB drive) that delivers malware when used
- Quid Pro Quo Offering a fake service or benefit (e.g. ‘free IT support’) in exchange for information or access
- Tailgating / Piggybacking Physically following an authorised person into a restricted area
- Shoulder Surfing Directly observing someone entering a password or PIN, or viewing sensitive info on their screen

**සිංහලෙන්:** **Social Engineering Attack Types (2/2)** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SOCIAL ENGINEERING
- Type How it works
- Pretexting Inventing a false scenario/identity to obtain information (e.g. posing as IT support)
- Baiting Offering something enticing (free download, USB drive) that delivers malware when used

**🧠 Memory Tip:** Remember **Social Engineering Attack Types (2/2)** by linking its purpose → mechanism → result.

### DoS and DDoS (Slide 33)

**Exam Answer:** DOS/DDOS.

**Explanation:**

- DOS/DDOS
- Single Attacker Target Server DoS — one source overwhelms the target
- Bot
- Bot
- Bot
- Target Server DDoS — many distributed bots (a botnet) flood the target at once
- Goal: exhaust bandwidth, processing power, or connection limits so legitimate users can't get through — an attack on Availability.

**සිංහලෙන්:** **DoS and DDoS** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DOS/DDOS
- Single Attacker Target Server DoS — one source overwhelms the target
- Bot
- Bot

**🧠 Memory Tip:** Remember **DoS and DDoS** by linking its purpose → mechanism → result.

### DoS/DDoS: Real-World Examples (Slide 34)

**Exam Answer:** DOS/DDOS.

**Explanation:**

- DOS/DDOS
- Mirai botnet (2016): malware infected huge numbers of insecure IoT devices (cameras, routers) and used them to
- launch massive DDoS attacks, including one that took down major internet services via a DNS provider.
- GitHub (2018): hit by one of the largest recorded DDoS attacks at the time, peaking at 1.35 Tbps — mitigated through
- a dedicated DDoS-protection service.
- The common thread: DDoS scales with however many devices an attacker can compromise — which is why insecure
- IoT devices are such an attractive target.

**සිංහලෙන්:** **DoS/DDoS: Real-World Examples** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- DOS/DDOS
- Mirai botnet (2016): malware infected huge numbers of insecure IoT devices (cameras, routers) and used them to
- launch massive DDoS attacks, including one that took down major internet services via a DNS provider.
- GitHub (2018): hit by one of the largest recorded DDoS attacks at the time, peaking at 1.35 Tbps — mitigated through

**🧠 Memory Tip:** Remember **DoS/DDoS: Real-World Examples** by linking its purpose → mechanism → result.

### Access & Reconnaissance Attacks (Slide 35)

**Exam Answer:** ACCESS/RECON.

**Explanation:**

- ACCESS/RECON
- Reconnaissance: gathering information about a target before attacking — scanning for open ports, mapping network
- topology, identifying software versions.
- Access attacks: attempts to gain unauthorised entry to a system or account once a weakness is found.
- Often the *first phase* of a larger attack — recon tells an attacker where to focus, access attacks get them in the
- door.

**සිංහලෙන්:** **Access & Reconnaissance Attacks** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACCESS/RECON
- Reconnaissance: gathering information about a target before attacking — scanning for open ports, mapping network
- topology, identifying software versions.
- Access attacks: attempts to gain unauthorised entry to a system or account once a weakness is found.

**🧠 Memory Tip:** Remember **Access & Reconnaissance Attacks** by linking its purpose → mechanism → result.

### Access & Reconnaissance: Examples (Slide 36)

**Exam Answer:** ACCESS/RECON.

**Explanation:**

- ACCESS/RECON
- Technique What it does
- Port scanning Probes a host for open ports/services to identify potential entry points
- Password/credential attacks Brute-force or dictionary attacks, or reusing credentials leaked elsewhere (credential stuffing)
- Footprinting Passively gathering public info about a target (DNS records, employee info, tech stack)
- Man-in-the-Middle Intercepting communication between two parties, often after gaining network access

**සිංහලෙන්:** **Access & Reconnaissance: Examples** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACCESS/RECON
- Technique What it does
- Port scanning Probes a host for open ports/services to identify potential entry points
- Password/credential attacks Brute-force or dictionary attacks, or reusing credentials leaked elsewhere (credential stuffing)

**🧠 Memory Tip:** Remember **Access & Reconnaissance: Examples** by linking its purpose → mechanism → result.

### Security Controls & Layered Defense (Slide 37)

**Exam Answer:** No single control stops everything.

**Explanation:**

- No single control stops everything

**සිංහලෙන්:** **Security Controls & Layered Defense** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- No single control stops everything

**🧠 Memory Tip:** Remember **Security Controls & Layered Defense** by linking its purpose → mechanism → result.

### Types of Security Controls (Slide 38)

**Exam Answer:** CONTROLS.

**Explanation:**

- CONTROLS
- Category Examples
- Administrative Policies, training, background checks, security awareness programs
- Technical Firewalls, encryption, access control lists, IDS/IPS (later weeks)
- Physical Locked server rooms, badge access, security cameras, cable locks

**සිංහලෙන්:** **Types of Security Controls** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONTROLS
- Category Examples
- Administrative Policies, training, background checks, security awareness programs
- Technical Firewalls, encryption, access control lists, IDS/IPS (later weeks)

**🧠 Memory Tip:** Remember **Types of Security Controls** by linking its purpose → mechanism → result.

### Controls by Function (Slide 39)

**Exam Answer:** CONTROLS.

**Explanation:**

- CONTROLS
- Function Purpose
- Preventive Stop an incident before it happens (e.g. firewall rules, training)
- Deterrent Discourage an attack without necessarily stopping it (e.g. warning banners, visible cameras)
- Detective Identify an incident that's happening or already happened (e.g. logging, IDS)
- Corrective Actively fix the immediate problem once detected (e.g. quarantining infected hosts, patching)
- Recovery Restore systems, data, and operations to normal after an incident (e.g. backups, disaster recovery plans)
- Compensating An alternative control used when the ideal control isn't feasible (e.g. extra monitoring where patching isn't yet possible)
- Corrective and Recovery are related but distinct: corrective stops the bleeding, recovery gets you back to normal.

**සිංහලෙන්:** **Controls by Function** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONTROLS
- Function Purpose
- Preventive Stop an incident before it happens (e.g. firewall rules, training)
- Deterrent Discourage an attack without necessarily stopping it (e.g. warning banners, visible cameras)

**🧠 Memory Tip:** Remember **Controls by Function** by linking its purpose → mechanism → result.

### Defense in Depth (Slide 40)

**Exam Answer:** CONTROLS.

**Explanation:**

- CONTROLS
- ApplicationData
- Perimeter → Network → Host → App → Data
- Each ring is a control an attacker must get through — if one layer fails, the next one can still stop or slow them down.

**සිංහලෙන්:** **Defense in Depth** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONTROLS
- ApplicationData
- Perimeter → Network → Host → App → Data
- Each ring is a control an attacker must get through — if one layer fails, the next one can still stop or slow them down.

**🧠 Memory Tip:** Remember **Defense in Depth** by linking its purpose → mechanism → result.

### Why Layered Defense Matters (Slide 41)

**Exam Answer:** CONTROLS.

**Explanation:**

- CONTROLS
- No single control stops every attack category we covered today — a firewall doesn't stop phishing; security training
- doesn't stop a DDoS flood.
- Layering different control types (administrative + technical + physical, preventive + detective + corrective) means one
- failure doesn't mean total compromise.
- This is the mindset the rest of the module builds on: each remaining technology (firewalls, AAA, VPN, IPS/IDS,
- cryptography) is one layer in this bigger picture, not a silver bullet on its own.

**සිංහලෙන්:** **Why Layered Defense Matters** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONTROLS
- No single control stops every attack category we covered today — a firewall doesn't stop phishing; security training
- doesn't stop a DDoS flood.
- Layering different control types (administrative + technical + physical, preventive + detective + corrective) means one

**🧠 Memory Tip:** Remember **Why Layered Defense Matters** by linking its purpose → mechanism → result.

### Matching Controls to Today's Attack Categories (Slide 42)

**Exam Answer:** CONTROLS.

**Explanation:**

- CONTROLS
- Attack category Controls that help (preview)
- Malware Technical: endpoint protection, patching. Administrative: safe-download policy.
- Social engineering Administrative: security-awareness training. Technical: email filtering.
- DoS / DDoS Technical: rate limiting, DDoS-protection services, redundant capacity.
- Access & reconnaissance Technical: firewalls, strong authentication (AAA, Week 8). Detective: logging/IDS (Week 10).
- This mapping is exactly what this week's lab asks you to build for a scenario company — no need to memorise it, just understand the logic.

**සිංහලෙන්:** **Matching Controls to Today's Attack Categories** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CONTROLS
- Attack category Controls that help (preview)
- Malware Technical: endpoint protection, patching. Administrative: safe-download policy.
- Social engineering Administrative: security-awareness training. Technical: email filtering.

**🧠 Memory Tip:** Remember **Matching Controls to Today's Attack Categories** by linking its purpose → mechanism → result.

### Summary (Slide 43)

**Exam Answer:** Network security protects confidentiality, integrity, and availability — and depends on people and process as much as.

**Explanation:**

- Network security protects confidentiality, integrity, and availability — and depends on people and process as much as
- technology.
- Threat modeling (asset → threat → vulnerability → risk) is the reasoning behind every security decision we'll make this
- semester.
- Threat actors range from curious green hats to organised, state-sponsored operations — and their motivations shape what
- they target.
- Attacks fall into four broad categories: malware, social engineering, DoS/DDoS, and access/reconnaissance — often
- combined in a real incident.
- No single control is enough — layered defense across administrative, technical, and physical controls is the foundation for
- everything from Week 3 onward.

**සිංහලෙන්:** **Summary** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Network security protects confidentiality, integrity, and availability — and depends on people and process as much as
- technology.
- Threat modeling (asset → threat → vulnerability → risk) is the reasoning behind every security decision we'll make this
- semester.

**🧠 Memory Tip:** Remember **Summary** by linking its purpose → mechanism → result.

### This Week's Lab & Tutorial (Slide 44)

**Exam Answer:** Lab (runs in the Week 3 session, based on this lecture): a combined exercise — classify real incidents by threat-actor.

**Explanation:**

- Lab (runs in the Week 3 session, based on this lecture): a combined exercise — classify real incidents by threat-actor
- type and attack category, then design a layered-defense control set for a scenario company.
- Tutorial worksheet: 12 study-notes-style questions covering today's terms, threat actors, attack types, and controls —
- use it to prep for the mid-semester test.

**සිංහලෙන්:** **This Week's Lab & Tutorial** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Lab (runs in the Week 3 session, based on this lecture): a combined exercise — classify real incidents by threat-actor
- type and attack category, then design a layered-defense control set for a scenario company.
- Tutorial worksheet: 12 study-notes-style questions covering today's terms, threat actors, attack types, and controls —
- use it to prep for the mid-semester test.

**🧠 Memory Tip:** Remember **This Week's Lab & Tutorial** by linking its purpose → mechanism → result.


## 📊 Important Comparisons

| Comparison/topic | Source | Exam focus |
|---|---:|---|
| Summary | Slide 43 | Network security protects confidentiality, integrity, and availability — and depends on people and process as much as. |

## 🛠️ Practical Knowledge

### What Is Network Security? (Slide 5)

- OVERVIEW
- The practice of protecting the confidentiality, integrity, and availability of data as it moves across and is stored on a
- network.
- Covers people, process, and technology — not just firewalls and passwords.
- Applies at every layer we revised in Week 1: physical cabling, switches/routers, protocols, and the applications
- running on top.
- This module builds toward being able to identify weaknesses (LO1) and recommend/configure defenses (LO2, LO4,
- LO5).

### Why It Matters (Slide 6)

- OVERVIEW
- Modern organisations run on networks — a compromised network can mean stolen data, halted operations, financial
- loss, and reputational damage.
- Attacks aren't rare or abstract: recall the real 2025–2026 breaches from Week 1's lab (retail ransomware, VPN zero-
- days, exposed devices, vendor breaches).
- Security is not a one-time setup — the threat landscape keeps changing, which is exactly why this lecture exists
- before we get into specific technologies.
- As a future network/security professional, understanding *why* an attack works is what lets you recommend the
- right defense — not just follow a checklist.

### The CIA Triad (Slide 8)

- SECURITY PRINCIPLES
- Confidentiality
- Only authorised people/systems can access the
- data
- Integrity
- Data is accurate and hasn't been altered without
- authorisation
- Availability
- Data and systems are accessible to legitimate
- users when needed
- The CIA Triad is the foundational model for what ‘security’ actually means — almost every control we cover this semester
- protects one or more of these three properties.
- An attack usually targets one corner specifically: theft/eavesdropping breaks confidentiality, tampering breaks integrity, and a
- DoS/DDoS attack breaks availability.
- Trade-offs are common — stronger confidentiality controls (e.g. heavy encryption, strict access checks) can sometimes
- reduce availability if overdone. Good security design balances all three, not maximises one.

### Key Terms — Revision (Slide 12)

- TERMINOLOGY
- Term Meaning
- Asset Anything of value worth protecting — data, a server, a service, even reputation
- Vulnerability A weakness that could be exploited (a bug, misconfiguration, missing patch)
- Threat Anything with the potential to exploit a vulnerability and cause harm
- Exploit The specific method/tool used to take advantage of a vulnerability
- Attack The actual event of a threat using an exploit against a vulnerability
- Impact The real-world consequence of a successful attack — data loss, downtime, cost
- Risk The likelihood and impact of a threat actually exploiting a vulnerability
- Mitigation The control or action taken to reduce a vulnerability, threat, or its impact

### Worked Example: A Small Online Retailer (Slide 15)

- TERMINOLOGY
- Step Applied to this company
- Asset Customer payment data, the order-processing database
- Vulnerability Unpatched web server, weak admin password policy
- Threat Financially motivated attackers (black hats, criminal groups)
- Exploit A known, unpatched web-server vulnerability with public exploit code available
- Attack Attackers use the exploit to gain admin access and copy the payment database
- Impact Stolen customer payment data, regulatory fines, loss of customer trust
- Risk High — valuable data + known weaknesses + attackers actively interested
- Mitigation Patch the web server promptly, enforce strong admin passwords + MFA, encrypt stored data
- This is the exact reasoning you'll apply in this week's lab — and in the group assignment later in the semester.

### The Threat Landscape Evolved Alongside It (Slide 18)

- EVOLUTION
- More connectivity has always meant more attack surface — every new capability (remote access, cloud storage, IoT
- sensors) is also a new way in.
- Attacks have professionalised: from lone hobbyists to organised criminal groups, data brokers, and state-sponsored
- operations (more on this shortly).
- The targets have changed too — attackers now go after cloud misconfigurations, VPN appliances, and supply-
- chain/vendor relationships, not just a single office firewall (recall Week 1's Ivanti VPN and SonicWall vendor-breach
- case studies).
- The core lesson: the fundamentals we revised in Week 1 (layers, protocols) still apply — but the scale and
- sophistication of who's attacking them has grown enormously.

### Beyond the Hats (Slide 22)

- THREAT ACTORS
- Category What defines them
- Script Kiddies Little technical skill — run existing tools/scripts written by others
- Access & Data Brokers Sell stolen access or data to other attackers rather than exploiting it themselves
- State-Sponsored Hackers Funded by governments; highly resourced, target high-value/strategic systems
- Hacktivists Motivated by political or social causes, not money — aim to expose or disrupt
- These aren't mutually exclusive with the hat spectrum — a state-sponsored hacker, for instance, is still operating with black-hat intent.

### Social Engineering: The Basics (Slide 30)

- SOCIAL ENGINEERING
- Attacks that manipulate people rather than exploiting a technical flaw — often the easiest way into an otherwise
- well-defended network.
- Exploits trust, urgency, authority, or fear — recall Week 1's UK retail ransomware case, which began with a help-desk
- social-engineering compromise, not a technical exploit.
- This is exactly why LO1's ‘network vulnerabilities and attacks’ has to include people and process, not just code and
- configuration.

### DoS and DDoS (Slide 33)

- DOS/DDOS
- Single Attacker Target Server DoS — one source overwhelms the target
- Bot
- Bot
- Bot
- Target Server DDoS — many distributed bots (a botnet) flood the target at once
- Goal: exhaust bandwidth, processing power, or connection limits so legitimate users can't get through — an attack on Availability.

### Matching Controls to Today's Attack Categories (Slide 42)

- CONTROLS
- Attack category Controls that help (preview)
- Malware Technical: endpoint protection, patching. Administrative: safe-download policy.
- Social engineering Administrative: security-awareness training. Technical: email filtering.
- DoS / DDoS Technical: rate limiting, DDoS-protection services, redundant capacity.
- Access & reconnaissance Technical: firewalls, strong authentication (AAA, Week 8). Detective: logging/IDS (Week 10).
- This mapping is exactly what this week's lab asks you to build for a scenario company — no need to memorise it, just understand the logic.

### Summary (Slide 43)

- Network security protects confidentiality, integrity, and availability — and depends on people and process as much as
- technology.
- Threat modeling (asset → threat → vulnerability → risk) is the reasoning behind every security decision we'll make this
- semester.
- Threat actors range from curious green hats to organised, state-sponsored operations — and their motivations shape what
- they target.
- Attacks fall into four broad categories: malware, social engineering, DoS/DDoS, and access/reconnaissance — often
- combined in a real incident.
- No single control is enough — layered defense across administrative, technical, and physical controls is the foundation for
- everything from Week 3 onward.

### This Week's Lab & Tutorial (Slide 44)

- Lab (runs in the Week 3 session, based on this lecture): a combined exercise — classify real incidents by threat-actor
- type and attack category, then design a layered-defense control set for a scenario company.
- Tutorial worksheet: 12 study-notes-style questions covering today's terms, threat actors, attack types, and controls —
- use it to prep for the mid-semester test.

## ⭐ Important Exam Points

- ⭐ **Why Network Security Matters (Slide 4):** Setting the stage.
- ⭐ **What Is Network Security? (Slide 5):** OVERVIEW.
- ⭐ **Why It Matters (Slide 6):** OVERVIEW.
- ⭐ **The Extended CIA Triad (Slide 7):** Fundamental Information Security Controls.
- ⭐ **The CIA Triad (Slide 8):** SECURITY PRINCIPLES.
- ⭐ **Authentication (Slide 9):** SECURITY PRINCIPLES.
- ⭐ **Non-Repudiation (Slide 10):** SECURITY PRINCIPLES.
- ⭐ **Key Terms & Threat Modeling (Slide 11):** The vocabulary we'll use all semester.
- ⭐ **Key Terms — Revision (Slide 12):** TERMINOLOGY.
- ⭐ **How These Terms Fit Together (Slide 13):** TERMINOLOGY.
- ⭐ **What Is Threat Modeling? (Slide 14):** TERMINOLOGY.
- ⭐ **Worked Example: A Small Online Retailer (Slide 15):** TERMINOLOGY.
- ⭐ **How Networking — and Its Threats — Have (Slide 16):** Evolved.
- ⭐ **From Isolated Systems to Everything Connected (Slide 17):** EVOLUTION.
- ⭐ **The Threat Landscape Evolved Alongside It (Slide 18):** EVOLUTION.

## ❓ Possible Exam Questions

### MCQs

1. Which statement best matches **Why Network Security Matters**?
   - A. It is unrelated to network security.
   - B. Setting the stage.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

2. Which statement best matches **Key Terms — Revision**?
   - A. It is unrelated to network security.
   - B. TERMINOLOGY.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

3. Which statement best matches **Hackers Aren't All the Same**?
   - A. It is unrelated to network security.
   - B. THREAT ACTORS.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

4. Which statement best matches **Malware Types (2/3)**?
   - A. It is unrelated to network security.
   - B. MALWARE.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

5. Which statement best matches **Access & Reconnaissance: Examples**?
   - A. It is unrelated to network security.
   - B. ACCESS/RECON.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**


### Short Structured Questions

1. **Explain Why Network Security Matters.**
   - **Model answer:** Setting the stage.

2. **Explain Key Terms — Revision.**
   - **Model answer:** TERMINOLOGY.

3. **Explain Hackers Aren't All the Same.**
   - **Model answer:** THREAT ACTORS.

4. **Explain Malware Types (2/3).**
   - **Model answer:** MALWARE.

5. **Explain Access & Reconnaissance: Examples.**
   - **Model answer:** ACCESS/RECON.


### Scenario-Based Question

**Scenario:** An organization must apply the concepts from **Networking and Security Revision** to improve its network security. Identify the relevant mechanism or risk, explain the likely impact, and recommend a layered response.

**Model-answer approach:** Identify the asset and trust boundary; name the relevant protocol/control; explain the mechanism using the lecture terminology; state confidentiality, integrity, or availability impact; then recommend the matching prevention, detection, and verification steps from the slides.

## ⚡ Last-Minute Quick Revision

- **Why Network Security Matters:** Setting the stage.
- **What Is Network Security?:** OVERVIEW.
- **Why It Matters:** OVERVIEW.
- **The Extended CIA Triad:** Fundamental Information Security Controls.
- **The CIA Triad:** SECURITY PRINCIPLES.
- **Authentication:** SECURITY PRINCIPLES.
- **Non-Repudiation:** SECURITY PRINCIPLES.
- **Key Terms & Threat Modeling:** The vocabulary we'll use all semester.
- **Key Terms — Revision:** TERMINOLOGY.
- **How These Terms Fit Together:** TERMINOLOGY.
- **What Is Threat Modeling?:** TERMINOLOGY.
- **Worked Example: A Small Online Retailer:** TERMINOLOGY.
- **How Networking — and Its Threats — Have:** Evolved.
- **From Isolated Systems to Everything Connected:** EVOLUTION.
- **The Threat Landscape Evolved Alongside It:** EVOLUTION.
- **Types of Hackers:** Knowing who you're defending against.
- **Hackers Aren't All the Same:** THREAT ACTORS.
- **The Hat Spectrum:** THREAT ACTORS.
- **Beyond the Hats:** THREAT ACTORS.
- **Key Motivations:** THREAT ACTORS.

## Verification Notes

- Slide coverage: **45 of 45 slides processed**.
- Slide numbers refer to PDF page order.
- Any application example or scenario above extends the slide concept for revision and is not presented as a verbatim lecturer statement.
