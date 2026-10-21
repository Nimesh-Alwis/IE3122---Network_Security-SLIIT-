# Lecture 11 – AAA Foundations

## 📌 Lecture Overview

This lecture covers **AAA Foundations** as presented in the supplied IE3122 slides. The notes follow the source order across 31 slides and retain the lecture's terminology, mechanisms, examples, and configuration details. They are organized for rapid MCQ, structured-answer, and scenario revision.

> **Source boundary:** Content below is derived from `IE3122_Week10_AAAFoundations_Slides.pdf`. Generic exam prompts/examples are labelled as application material; no unsupported lecturer emphasis is claimed.

## 🎯 Learning Objectives

- LO3
- Analyse security requirements and recommend appropriate technologies.
- LO4
- Evaluate different security technologies, compare them, and identify appropriate use cases.
- By the end of this session you should be able to explain what each of the three A's actually controls, and recommend the right access control
- model for a given scenario.

## 📚 Main Topics and Subtopics

### Foundations (Slide 4)

**Exam Answer:** Three genuinely separate questions.

**Explanation:**

- Three genuinely separate questions

**සිංහලෙන්:** **Foundations** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Three genuinely separate questions

**🧠 Memory Tip:** Remember **Foundations** by linking its purpose → mechanism → result.

### What Is AAA? (Slide 5)

**Exam Answer:** FOUNDATIONS.

**Explanation:**

- FOUNDATIONS
- Authentication answers who are you, verifying that an entity genuinely is who it claims to be.
- Authorization answers what are you allowed to do, determining which resources and actions an authenticated entity can
- actually access.
- Accounting answers what did you actually do, recording activity for auditing, billing, or investigation after the fact.
- These are three distinct security functions working together, not three names for the same check.

**සිංහලෙන්:** **What Is AAA?** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FOUNDATIONS
- Authentication answers who are you, verifying that an entity genuinely is who it claims to be.
- Authorization answers what are you allowed to do, determining which resources and actions an authenticated entity can
- actually access.

**🧠 Memory Tip:** Remember **What Is AAA?** by linking its purpose → mechanism → result.

### Why Three Separate Functions, Not One (Slide 6)

**Exam Answer:** FOUNDATIONS.

**Explanation:**

- FOUNDATIONS
- You can be authenticated without being authorized for everything. A verified employee has proven who they are, but that
- alone doesn't mean they can reach every system in the building.
- Authorization is meaningless without authentication first. You cannot decide what someone is allowed to do until you know
- who they actually are.
- Accounting happens regardless of the authorization outcome. Both successful actions and denied attempts get recorded,
- since a pattern of failed access attempts is itself valuable security information.
- Merging these into one blunt pass/fail check loses exactly this granularity, and is why real systems keep them as three
- deliberately separate stages.

**සිංහලෙන්:** **Why Three Separate Functions, Not One** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FOUNDATIONS
- You can be authenticated without being authorized for everything. A verified employee has proven who they are, but that
- alone doesn't mean they can reach every system in the building.
- Authorization is meaningless without authentication first. You cannot decide what someone is allowed to do until you know

**🧠 Memory Tip:** Remember **Why Three Separate Functions, Not One** by linking its purpose → mechanism → result.

### AAA as a Modular Framework (Slide 7)

**Exam Answer:** FOUNDATIONS.

**Explanation:**

- FOUNDATIONS
- Recall Week 9: IPsec was built as a modular framework, a menu of interchangeable choices for each of several functions, not
- one fixed protocol.
- AAA is built the same way. The authentication method (password, certificate, biometric, multi-factor), the authorization
- model (covered in detail shortly), and the accounting mechanism (local logging or centralised) are all independently
- selectable.
- A real AAA deployment is assembled by picking one option from each of these three rows, exactly like building an IPsec
- configuration from its own framework table.

**සිංහලෙන්:** **AAA as a Modular Framework** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FOUNDATIONS
- Recall Week 9: IPsec was built as a modular framework, a menu of interchangeable choices for each of several functions, not
- one fixed protocol.
- AAA is built the same way. The authentication method (password, certificate, biometric, multi-factor), the authorization

**🧠 Memory Tip:** Remember **AAA as a Modular Framework** by linking its purpose → mechanism → result.

### Authentication (Slide 8)

**Exam Answer:** Proving who you actually are.

**Explanation:**

- Proving who you actually are

**සිංහලෙන්:** **Authentication** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Proving who you actually are

**🧠 Memory Tip:** Remember **Authentication** by linking its purpose → mechanism → result.

### Something You Know (Slide 9)

**Exam Answer:** AUTHENTICATION METHOD 1.

**Explanation:**

- AUTHENTICATION METHOD 1
- Mechanism: the user provides a secret only they should know, a password, PIN, or answer to a security question, which the system checks
- against a stored reference value.
- Examples: passwords, PINs, passphrases, and security questions such as a first pet's name.
- Use cases: the default, baseline method for almost every system, website logins, device unlock codes, and initial account setup.
- Strengths: cheap and simple to implement, needs no special hardware, universally understood, and can be changed instantly if compromised.
- Weaknesses: vulnerable to phishing, guessing, shoulder-surfing, and keylogging. Users routinely choose weak or reused passwords across
- many sites, undermining the whole model even when the mechanism itself is sound.

**සිංහලෙන්:** **Something You Know** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHENTICATION METHOD 1
- Mechanism: the user provides a secret only they should know, a password, PIN, or answer to a security question, which the system checks
- against a stored reference value.
- Examples: passwords, PINs, passphrases, and security questions such as a first pet's name.

**🧠 Memory Tip:** Remember **Something You Know** by linking its purpose → mechanism → result.

### Something You Have (Slide 10)

**Exam Answer:** AUTHENTICATION METHOD 2.

**Explanation:**

- AUTHENTICATION METHOD 2
- Mechanism: the user proves possession of a physical or digital item, and the system verifies a code that item generates or receives.
- Examples: hardware security keys, smart cards, RSA-style tokens, SMS one-time codes, and authenticator apps generating time-based codes.
- Use cases: banking cards paired with a PIN, corporate VPN access via a token, two-factor authentication on sensitive accounts, and badge-
- based building access.
- Strengths: cannot be guessed or phished the way a password can, since an attacker needs to physically obtain or clone the item itself.
- Weaknesses: the item can be lost or stolen, and SMS-based codes specifically can be intercepted through SIM-swapping attacks. Replacing a
- lost token has real cost and logistics.

**සිංහලෙන්:** **Something You Have** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHENTICATION METHOD 2
- Mechanism: the user proves possession of a physical or digital item, and the system verifies a code that item generates or receives.
- Examples: hardware security keys, smart cards, RSA-style tokens, SMS one-time codes, and authenticator apps generating time-based codes.
- Use cases: banking cards paired with a PIN, corporate VPN access via a token, two-factor authentication on sensitive accounts, and badge-

**🧠 Memory Tip:** Remember **Something You Have** by linking its purpose → mechanism → result.

### Something You Are: Physical Biometrics (Slide 11)

**Exam Answer:** AUTHENTICATION METHOD 3A.

**Explanation:**

- AUTHENTICATION METHOD 3A
- Mechanism: measures a fixed, largely unchanging anatomical characteristic of the body, captured by a scanner or sensor and compared against a
- stored enrolment template.
- Examples: fingerprint ridge patterns, facial geometry, iris and retina patterns, hand geometry, and DNA matching.
- Use cases: smartphone unlock, border control and passport e-gates, high-security facility access, and forensic identification.
- Strengths: extremely high uniqueness between individuals, and stable over long periods of time, a person's fingerprint or iris pattern doesn't
- meaningfully change year to year.
- Weaknesses: needs specialised hardware, can be disrupted by physical conditions such as a cut affecting a fingerprint or cataracts affecting an iris
- scan, and if the trait itself is ever compromised, it can never be reissued, unlike a password or even a physical token.

**සිංහලෙන්:** **Something You Are: Physical Biometrics** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHENTICATION METHOD 3A
- Mechanism: measures a fixed, largely unchanging anatomical characteristic of the body, captured by a scanner or sensor and compared against a
- stored enrolment template.
- Examples: fingerprint ridge patterns, facial geometry, iris and retina patterns, hand geometry, and DNA matching.

**🧠 Memory Tip:** Remember **Something You Are: Physical Biometrics** by linking its purpose → mechanism → result.

### Something You Are: Behavioural Biometrics (Slide 12)

**Exam Answer:** AUTHENTICATION METHOD 3B.

**Explanation:**

- AUTHENTICATION METHOD 3B
- Mechanism: measures patterns in how a person performs an action over time, rather than a fixed physical trait, compared against a behavioural
- baseline built through observation.
- Examples: keystroke dynamics (typing rhythm and pressure), gait analysis, signature dynamics (the speed and rhythm of signing, not just the
- resulting image), and speech cadence.
- Use cases: continuous authentication running in the background during a session, fraud detection during a banking transaction, and ongoing
- workplace session verification.
- Strengths: can authenticate continuously throughout a session rather than only once at login, making it far harder for an attacker who got past the
- initial login to stay undetected, and it's genuinely difficult to consciously imitate someone else's natural patterns.
- Weaknesses: less mature and standardised than physical biometrics, with higher false-positive and false-negative rates, since normal behaviour
- naturally varies day to day. Behavioural traits are also less stable over time than physical ones, changing with stress, fatigue, injury, or a different
- device.

**සිංහලෙන්:** **Something You Are: Behavioural Biometrics** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHENTICATION METHOD 3B
- Mechanism: measures patterns in how a person performs an action over time, rather than a fixed physical trait, compared against a behavioural
- baseline built through observation.
- Examples: keystroke dynamics (typing rhythm and pressure), gait analysis, signature dynamics (the speed and rhythm of signing, not just the

**🧠 Memory Tip:** Remember **Something You Are: Behavioural Biometrics** by linking its purpose → mechanism → result.

### Multi-Factor Authentication (Slide 13)

**Exam Answer:** AUTHENTICATION METHOD 4.

**Explanation:**

- AUTHENTICATION METHOD 4
- Mechanism: combines two or more factors from genuinely different categories above, not two instances of the same category. Two different
- passwords is still only one factor type, repeated.
- Examples: a password combined with an authenticator app code; a fingerprint combined with a PIN; a smart card combined with biometric
- verification for high-security facilities.
- Use cases: online banking, corporate remote access and VPN (recall Week 9), cloud service logins, and any system protecting genuinely
- sensitive data or high-value transactions.
- Strengths: dramatically reduces the risk that one compromised factor leads to full account takeover, and is increasingly treated as a baseline
- expectation rather than an optional extra.
- Weaknesses: adds friction to login that can hurt adoption if handled poorly, and isn't perfectly immune either. SIM-swapping can still defeat
- SMS-based MFA specifically, and prompt bombing can trick a user into approving a push notification they never initiated.

**සිංහලෙන්:** **Multi-Factor Authentication** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHENTICATION METHOD 4
- Mechanism: combines two or more factors from genuinely different categories above, not two instances of the same category. Two different
- passwords is still only one factor type, repeated.
- Examples: a password combined with an authenticator app code; a fingerprint combined with a PIN; a smart card combined with biometric

**🧠 Memory Tip:** Remember **Multi-Factor Authentication** by linking its purpose → mechanism → result.

### Authentication Methods, Compared (Slide 14)

**Exam Answer:** AUTHENTICATION SUMMARY.

**Explanation:**

- AUTHENTICATION SUMMARY
- Method Example Key Strength Key Weakness
- Something You Know Password, PIN Cheap, simple, no hardware needed Phishable, guessable, often reused
- Something You Have Hardware token, authenticator app Cannot be guessed or phished remotely Can be lost, stolen, or SIM-swapped
- Are, Physical Fingerprint, facial recognition High uniqueness, stable over time Permanent if compromised; needs hardware
- Are, Behavioural Keystroke dynamics, gait Enables continuous authentication Less stable; higher false-positive rate
- Multi-Factor Password plus authenticator app Defeats a single compromised factor Adds friction; vulnerable to prompt bombing or SIM-swapping

**සිංහලෙන්:** **Authentication Methods, Compared** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHENTICATION SUMMARY
- Method Example Key Strength Key Weakness
- Something You Know Password, PIN Cheap, simple, no hardware needed Phishable, guessable, often reused
- Something You Have Hardware token, authenticator app Cannot be guessed or phished remotely Can be lost, stolen, or SIM-swapped

**🧠 Memory Tip:** Remember **Authentication Methods, Compared** by linking its purpose → mechanism → result.

### Authorization (Slide 15)

**Exam Answer:** Deciding what an authenticated identity can actually do.

**Explanation:**

- Deciding what an authenticated identity can actually do

**සිංහලෙන්:** **Authorization** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Deciding what an authenticated identity can actually do

**🧠 Memory Tip:** Remember **Authorization** by linking its purpose → mechanism → result.

### Privilege Levels and Command Authorization (Slide 16)

**Exam Answer:** AUTHORIZATION.

**Explanation:**

- AUTHORIZATION
- Cisco IOS uses a numeric privilege scale from 0 to 15. Level 0 has almost no access, level 1 is basic user EXEC mode, and level
- 15 is full privileged, administrative access.
- Command authorization goes further than simply logged in or not. It controls exactly which specific commands an
- authenticated user can run once they're in, for example allowing a junior technician to run show commands while denying
- configure terminal entirely.
- This is the practical, device-level version of authorization's core question: once someone's identity is confirmed, exactly how
- much power do they actually have?

**සිංහලෙන්:** **Privilege Levels and Command Authorization** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHORIZATION
- Cisco IOS uses a numeric privilege scale from 0 to 15. Level 0 has almost no access, level 1 is basic user EXEC mode, and level
- 15 is full privileged, administrative access.
- Command authorization goes further than simply logged in or not. It controls exactly which specific commands an

**🧠 Memory Tip:** Remember **Privilege Levels and Command Authorization** by linking its purpose → mechanism → result.

### Access Control Models: Overview (Slide 17)

**Exam Answer:** AUTHORIZATION.

**Explanation:**

- AUTHORIZATION
- Beyond privilege levels on one device, four general models exist for deciding who actually controls access decisions across a
- system, and how.
- DAC: the resource's own owner decides. MAC: a central authority decides, using fixed classification labels. RBAC: access is
- tied to a job role. RuBAC: access is decided by conditional rules evaluated at the moment of the request.
- These models are genuinely independent of which protocol carries the decision. RADIUS and TACACS+, covered in Deck B, are
- how a decision gets communicated. These four models are what actually gets decided in the first place.

**සිංහලෙන්:** **Access Control Models: Overview** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHORIZATION
- Beyond privilege levels on one device, four general models exist for deciding who actually controls access decisions across a
- system, and how.
- DAC: the resource's own owner decides. MAC: a central authority decides, using fixed classification labels. RBAC: access is

**🧠 Memory Tip:** Remember **Access Control Models: Overview** by linking its purpose → mechanism → result.

### DAC, Discretionary Access Control (Slide 18)

**Exam Answer:** AUTHORIZATION.

**Explanation:**

- AUTHORIZATION
- The owner of a resource decides who else can access it, and can grant or revoke that access at their own discretion, at any
- time.
- Example: standard Windows and Linux file permissions. If you create a file, you personally decide who else can read or write
- it.
- Advantage: highly flexible, since decisions are made by whoever actually knows the resource best.
- Disadvantage: control is scattered across every individual owner, making a single, consistent, organisation-wide policy
- difficult to enforce or audit.

**සිංහලෙන්:** **DAC, Discretionary Access Control** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHORIZATION
- The owner of a resource decides who else can access it, and can grant or revoke that access at their own discretion, at any
- time.
- Example: standard Windows and Linux file permissions. If you create a file, you personally decide who else can read or write

**🧠 Memory Tip:** Remember **DAC, Discretionary Access Control** by linking its purpose → mechanism → result.

### MAC, Mandatory Access Control (Slide 19)

**Exam Answer:** AUTHORIZATION.

**Explanation:**

- AUTHORIZATION
- A central authority sets fixed classification labels, such as Top Secret, Secret, Confidential, and Unclassified, and access is
- strictly determined by comparing a user's clearance to a resource's label.
- Individual users, even a file's own creator, cannot override or change these labels themselves.
- Example: military and government classified systems, and SELinux's enforcement model.
- Advantage: highly consistent, since no individual can accidentally or deliberately weaken the policy. Disadvantage: inflexible,
- with real administrative overhead to manage classifications correctly.

**සිංහලෙන්:** **MAC, Mandatory Access Control** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHORIZATION
- A central authority sets fixed classification labels, such as Top Secret, Secret, Confidential, and Unclassified, and access is
- strictly determined by comparing a user's clearance to a resource's label.
- Individual users, even a file's own creator, cannot override or change these labels themselves.

**🧠 Memory Tip:** Remember **MAC, Mandatory Access Control** by linking its purpose → mechanism → result.

### RBAC, Role-Based Access Control (Slide 20)

**Exam Answer:** AUTHORIZATION.

**Explanation:**

- AUTHORIZATION
- Access is tied to a user's job role within the organisation, not to them individually and not to any resource owner's personal
- discretion.
- Example: an HR Manager role automatically gets access to personnel files; a Sales Representative role gets access to the CRM
- but not to HR systems at all.
- Advantage: manages well at scale. When someone changes jobs, you change their role assignment once, rather than
- touching every individual permission they hold.
- This is the dominant model in most enterprise networks, and the one that most directly maps onto AAA's authorization
- function in a typical business deployment.

**සිංහලෙන්:** **RBAC, Role-Based Access Control** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHORIZATION
- Access is tied to a user's job role within the organisation, not to them individually and not to any resource owner's personal
- discretion.
- Example: an HR Manager role automatically gets access to personnel files; a Sales Representative role gets access to the CRM

**🧠 Memory Tip:** Remember **RBAC, Role-Based Access Control** by linking its purpose → mechanism → result.

### RuBAC, Rule-Based Access Control (Slide 21)

**Exam Answer:** AUTHORIZATION.

**Explanation:**

- AUTHORIZATION
- Access is decided by evaluating if-then conditional rules at the moment of the request, rather than a fixed, pre-assigned label
- or role.
- Example conditions: time of day, only allowing access during business hours; source location or IP address; device type; or
- combinations of these evaluated together.
- Advantage: genuinely context-aware, able to adapt access dynamically as circumstances change.
- Recall Week 7: an ACL is itself a rule-based access control mechanism, evaluated top to bottom, condition by condition.
- RuBAC is that same logic applied to authorization generally, not just packet filtering.

**සිංහලෙන්:** **RuBAC, Rule-Based Access Control** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHORIZATION
- Access is decided by evaluating if-then conditional rules at the moment of the request, rather than a fixed, pre-assigned label
- or role.
- Example conditions: time of day, only allowing access during business hours; source location or IP address; device type; or

**🧠 Memory Tip:** Remember **RuBAC, Rule-Based Access Control** by linking its purpose → mechanism → result.

### The Four Access Control Models, Compared (Slide 22)

**Exam Answer:** AUTHORIZATION.

**Explanation:**

- AUTHORIZATION
- Model Who Decides Flexibility Typical Use Case
- DAC The resource's own owner High, but inconsistent across owners General-purpose file systems (Windows, Linux)
- MAC A central authority, via fixed labels Low, but highly consistent Military and government classified systems
- RBAC The user's organisational role Moderate, scales well Enterprise networks, most business systems
- RuBAC Conditional rules evaluated at request time High, genuinely context-aware ACLs, firewalls, time or location-restricted access

**සිංහලෙන්:** **The Four Access Control Models, Compared** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- AUTHORIZATION
- Model Who Decides Flexibility Typical Use Case
- DAC The resource's own owner High, but inconsistent across owners General-purpose file systems (Windows, Linux)
- MAC A central authority, via fixed labels Low, but highly consistent Military and government classified systems

**🧠 Memory Tip:** Remember **The Four Access Control Models, Compared** by linking its purpose → mechanism → result.

### Accounting (Slide 23)

**Exam Answer:** What actually happened, and proving it afterward.

**Explanation:**

- What actually happened, and proving it afterward

**සිංහලෙන්:** **Accounting** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- What actually happened, and proving it afterward

**🧠 Memory Tip:** Remember **Accounting** by linking its purpose → mechanism → result.

### Session Accounting (Slide 24)

**Exam Answer:** ACCOUNTING TYPE 1.

**Explanation:**

- ACCOUNTING TYPE 1
- Mechanism: records the start and stop time of an authenticated session, when a user logged in, when they logged out or timed out, and by calculation,
- the total duration.
- Examples: a log entry showing a specific user logged into a router at a given time and the session ended some minutes later, exactly what Cisco's aaa
- accounting exec records.
- Use cases: a basic audit trail of who accessed a system and for how long, capacity planning around concurrent sessions at pea k times, and spotting
- unusual login timing, such as an admin account logging in at 3am when it normally only appears during business hours.
- Strengths: simple and low overhead to record, just two timestamps per session, giving a genuinely useful audit trail with min imal system impact.
- Weaknesses: tells you who was logged in and for how long, but nothing about what they actually did during that session. A cle an login and logout record
- says nothing about whether the session was used for legitimate work or something malicious.

**සිංහලෙන්:** **Session Accounting** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACCOUNTING TYPE 1
- Mechanism: records the start and stop time of an authenticated session, when a user logged in, when they logged out or timed out, and by calculation,
- the total duration.
- Examples: a log entry showing a specific user logged into a router at a given time and the session ended some minutes later, exactly what Cisco's aaa

**🧠 Memory Tip:** Remember **Session Accounting** by linking its purpose → mechanism → result.

### Command Accounting (Slide 25)

**Exam Answer:** ACCOUNTING TYPE 2.

**Explanation:**

- ACCOUNTING TYPE 2
- Mechanism: records every individual command an authenticated user actually executes during their session, building a detailed , command-by-command
- audit trail.
- Examples: TACACS+'s aaa accounting commands logging each CLI command a network administrator runs, for instance entering configuration mode,
- selecting an interface, then shutting it down, each as its own timestamped entry.
- Use cases: detailed forensic investigation after an incident, reconstructing exactly what an administrator did; compliance requirements demanding proof
- of precisely what changed and by whom; and simply deterring insider misuse, since users know every command is logged.
- Strengths: this is the real audit trail. It directly enables non -repudiation, since you can prove exactly which action a specific identity performed, not just
- that they were logged in at some point.
- Weaknesses: meaningfully higher overhead than session accounting, since every command must be captured and stored, not just t wo timestamps. This
- granularity is one of TACACS+'s defining advantages over RADIUS, recall Deck B, and it generates real volumes of log data that need proper storage and
- review to actually be useful.

**සිංහලෙන්:** **Command Accounting** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACCOUNTING TYPE 2
- Mechanism: records every individual command an authenticated user actually executes during their session, building a detailed , command-by-command
- audit trail.
- Examples: TACACS+'s aaa accounting commands logging each CLI command a network administrator runs, for instance entering configuration mode,

**🧠 Memory Tip:** Remember **Command Accounting** by linking its purpose → mechanism → result.

### Resource Accounting (Slide 26)

**Exam Answer:** ACCOUNTING TYPE 3.

**Explanation:**

- ACCOUNTING TYPE 3
- Mechanism: records the actual resources consumed during a session, data volume transferred, bandwidth used, or connection tim e.
- Examples: an ISP's accounting records historically tracking how many megabytes a customer used in a billing period; a corpora te VPN gateway logging
- how much bandwidth each remote user consumed.
- Use cases: historically the basis for usage-based ISP billing; today used more for capacity planning and usage monitoring, and f or spotting anomalies,
- since a sudden, unusually large data transfer from one account can be a genuine signal of data exfiltration.
- Strengths: gives visibility into the scale of activity, not just its existence, useful for both billing and security monitori ng.
- Weaknesses: doesn't say what was actually done, only how much. A large transfer could be a legitimate backup job or genuine d ata theft, and resource
- accounting alone can't tell the two apart without session or command context alongside it.

**සිංහලෙන්:** **Resource Accounting** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACCOUNTING TYPE 3
- Mechanism: records the actual resources consumed during a session, data volume transferred, bandwidth used, or connection tim e.
- Examples: an ISP's accounting records historically tracking how many megabytes a customer used in a billing period; a corpora te VPN gateway logging
- how much bandwidth each remote user consumed.

**🧠 Memory Tip:** Remember **Resource Accounting** by linking its purpose → mechanism → result.

### Accounting Types, Compared (Slide 27)

**Exam Answer:** ACCOUNTING SUMMARY.

**Explanation:**

- ACCOUNTING SUMMARY
- Type What It Records Example Best For
- Session Login and logout time, duration User logged in 09:14, out 09:47 Basic audit trail, capacity planning
- Command Every command executed User ran configure terminal at 09:15 Forensic investigation, non-repudiation
- Resource Data volume, bandwidth, connection time ISP billing records, VPN bandwidth logs Billing, usage monitoring, anomaly detection

**සිංහලෙන්:** **Accounting Types, Compared** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACCOUNTING SUMMARY
- Type What It Records Example Best For
- Session Login and logout time, duration User logged in 09:14, out 09:47 Basic audit trail, capacity planning
- Command Every command executed User ran configure terminal at 09:15 Forensic investigation, non-repudiation

**🧠 Memory Tip:** Remember **Accounting Types, Compared** by linking its purpose → mechanism → result.

### Accounting and Non-Repudiation (Slide 28)

**Exam Answer:** ACCOUNTING.

**Explanation:**

- ACCOUNTING
- Recall Week 2: non-repudiation means a party cannot later deny having performed an action.
- Accounting is what actually makes non-repudiation possible in practice. Without a recorded log tying a specific action to a
- specific authenticated identity, there is no way to prove afterward who did what.
- This is why accounting matters even for successful, fully authorized actions, not just failed or denied ones. A properly
- authorized action can still need to be proven later, in an audit or an investigation.

**සිංහලෙන්:** **Accounting and Non-Repudiation** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ACCOUNTING
- Recall Week 2: non-repudiation means a party cannot later deny having performed an action.
- Accounting is what actually makes non-repudiation possible in practice. Without a recorded log tying a specific action to a
- specific authenticated identity, there is no way to prove afterward who did what.

**🧠 Memory Tip:** Remember **Accounting and Non-Repudiation** by linking its purpose → mechanism → result.

### Summary (Slide 29)

**Exam Answer:** Authentication, Authorization, and Accounting are three separate, sequential functions. You cannot authorize before authenticating,.

**Explanation:**

- Authentication, Authorization, and Accounting are three separate, sequential functions. You cannot authorize before authenticating,
- and accounting happens regardless of the outcome.
- AAA is a modular framework, echoing IPsec's design from Week 9: an authentication method, an authorization model, and an
- accounting mechanism, each independently chosen.
- DAC, MAC, RBAC, and RuBAC all answer the same question, who actually controls an access decision, in four genuinely differentways,
- with different trade-offs between flexibility and consistency.
- Accounting isn't just a record of failures. It's what turns an authorized action into something that can still be proven after the fact.

**සිංහලෙන්:** **Summary** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Authentication, Authorization, and Accounting are three separate, sequential functions. You cannot authorize before authenticating,
- and accounting happens regardless of the outcome.
- AAA is a modular framework, echoing IPsec's design from Week 9: an authentication method, an authorization model, and an
- accounting mechanism, each independently chosen.

**🧠 Memory Tip:** Remember **Summary** by linking its purpose → mechanism → result.


## 📊 Important Comparisons

| Comparison/topic | Source | Exam focus |
|---|---:|---|
| Authentication Methods, Compared | Slide 14 | AUTHENTICATION SUMMARY. |
| Access Control Models: Overview | Slide 17 | AUTHORIZATION. |
| The Four Access Control Models, Compared | Slide 22 | AUTHORIZATION. |
| Accounting Types, Compared | Slide 27 | ACCOUNTING SUMMARY. |
| Summary | Slide 29 | Authentication, Authorization, and Accounting are three separate, sequential functions. You cannot authorize before authenticating,. |

## 🛠️ Practical Knowledge

### Today's Agenda (Slide 2)

- What AAA actually is, and why it's three separate functions, not one
- Authentication: the factors that prove who you are
- Authorization: privilege levels, command authorization, and the four access control models, DAC, MAC, RBAC, and RuBAC
- Accounting: what gets tracked, and why it matters even when access was properly granted

### AAA as a Modular Framework (Slide 7)

- FOUNDATIONS
- Recall Week 9: IPsec was built as a modular framework, a menu of interchangeable choices for each of several functions, not
- one fixed protocol.
- AAA is built the same way. The authentication method (password, certificate, biometric, multi-factor), the authorization
- model (covered in detail shortly), and the accounting mechanism (local logging or centralised) are all independently
- selectable.
- A real AAA deployment is assembled by picking one option from each of these three rows, exactly like building an IPsec
- configuration from its own framework table.

### Privilege Levels and Command Authorization (Slide 16)

- AUTHORIZATION
- Cisco IOS uses a numeric privilege scale from 0 to 15. Level 0 has almost no access, level 1 is basic user EXEC mode, and level
- 15 is full privileged, administrative access.
- Command authorization goes further than simply logged in or not. It controls exactly which specific commands an
- authenticated user can run once they're in, for example allowing a junior technician to run show commands while denying
- configure terminal entirely.
- This is the practical, device-level version of authorization's core question: once someone's identity is confirmed, exactly how
- much power do they actually have?

### Access Control Models: Overview (Slide 17)

- AUTHORIZATION
- Beyond privilege levels on one device, four general models exist for deciding who actually controls access decisions across a
- system, and how.
- DAC: the resource's own owner decides. MAC: a central authority decides, using fixed classification labels. RBAC: access is
- tied to a job role. RuBAC: access is decided by conditional rules evaluated at the moment of the request.
- These models are genuinely independent of which protocol carries the decision. RADIUS and TACACS+, covered in Deck B, are
- how a decision gets communicated. These four models are what actually gets decided in the first place.

### MAC, Mandatory Access Control (Slide 19)

- AUTHORIZATION
- A central authority sets fixed classification labels, such as Top Secret, Secret, Confidential, and Unclassified, and access is
- strictly determined by comparing a user's clearance to a resource's label.
- Individual users, even a file's own creator, cannot override or change these labels themselves.
- Example: military and government classified systems, and SELinux's enforcement model.
- Advantage: highly consistent, since no individual can accidentally or deliberately weaken the policy. Disadvantage: inflexible,
- with real administrative overhead to manage classifications correctly.

### RuBAC, Rule-Based Access Control (Slide 21)

- AUTHORIZATION
- Access is decided by evaluating if-then conditional rules at the moment of the request, rather than a fixed, pre-assigned label
- or role.
- Example conditions: time of day, only allowing access during business hours; source location or IP address; device type; or
- combinations of these evaluated together.
- Advantage: genuinely context-aware, able to adapt access dynamically as circumstances change.
- Recall Week 7: an ACL is itself a rule-based access control mechanism, evaluated top to bottom, condition by condition.
- RuBAC is that same logic applied to authorization generally, not just packet filtering.

### The Four Access Control Models, Compared (Slide 22)

- AUTHORIZATION
- Model Who Decides Flexibility Typical Use Case
- DAC The resource's own owner High, but inconsistent across owners General-purpose file systems (Windows, Linux)
- MAC A central authority, via fixed labels Low, but highly consistent Military and government classified systems
- RBAC The user's organisational role Moderate, scales well Enterprise networks, most business systems
- RuBAC Conditional rules evaluated at request time High, genuinely context-aware ACLs, firewalls, time or location-restricted access

### Command Accounting (Slide 25)

- ACCOUNTING TYPE 2
- Mechanism: records every individual command an authenticated user actually executes during their session, building a detailed , command-by-command
- audit trail.
- Examples: TACACS+'s aaa accounting commands logging each CLI command a network administrator runs, for instance entering configuration mode,
- selecting an interface, then shutting it down, each as its own timestamped entry.
- Use cases: detailed forensic investigation after an incident, reconstructing exactly what an administrator did; compliance requirements demanding proof
- of precisely what changed and by whom; and simply deterring insider misuse, since users know every command is logged.
- Strengths: this is the real audit trail. It directly enables non -repudiation, since you can prove exactly which action a specific identity performed, not just
- that they were logged in at some point.
- Weaknesses: meaningfully higher overhead than session accounting, since every command must be captured and stored, not just t wo timestamps. This
- granularity is one of TACACS+'s defining advantages over RADIUS, recall Deck B, and it generates real volumes of log data that need proper storage and
- review to actually be useful.

### Resource Accounting (Slide 26)

- ACCOUNTING TYPE 3
- Mechanism: records the actual resources consumed during a session, data volume transferred, bandwidth used, or connection tim e.
- Examples: an ISP's accounting records historically tracking how many megabytes a customer used in a billing period; a corpora te VPN gateway logging
- how much bandwidth each remote user consumed.
- Use cases: historically the basis for usage-based ISP billing; today used more for capacity planning and usage monitoring, and f or spotting anomalies,
- since a sudden, unusually large data transfer from one account can be a genuine signal of data exfiltration.
- Strengths: gives visibility into the scale of activity, not just its existence, useful for both billing and security monitori ng.
- Weaknesses: doesn't say what was actually done, only how much. A large transfer could be a legitimate backup job or genuine d ata theft, and resource
- accounting alone can't tell the two apart without session or command context alongside it.

### Accounting Types, Compared (Slide 27)

- ACCOUNTING SUMMARY
- Type What It Records Example Best For
- Session Login and logout time, duration User logged in 09:14, out 09:47 Basic audit trail, capacity planning
- Command Every command executed User ran configure terminal at 09:15 Forensic investigation, non-repudiation
- Resource Data volume, bandwidth, connection time ISP billing records, VPN bandwidth logs Billing, usage monitoring, anomaly detection

### Coming Up (Slide 30)

- Deck B, next: how AAA is actually deployed, local versus centralised, device administration versus network access, RADIUS
- versus TACACS+ in full detail, and Cisco configuration.
- Tutorial worksheet: study-notes-style questions covering today's three functions and the four access control models. Use it to
- prep for the mid-semester test.

## ⭐ Important Exam Points

- ⭐ **Foundations (Slide 4):** Three genuinely separate questions.
- ⭐ **What Is AAA? (Slide 5):** FOUNDATIONS.
- ⭐ **Why Three Separate Functions, Not One (Slide 6):** FOUNDATIONS.
- ⭐ **AAA as a Modular Framework (Slide 7):** FOUNDATIONS.
- ⭐ **Authentication (Slide 8):** Proving who you actually are.
- ⭐ **Something You Know (Slide 9):** AUTHENTICATION METHOD 1.
- ⭐ **Something You Have (Slide 10):** AUTHENTICATION METHOD 2.
- ⭐ **Something You Are: Physical Biometrics (Slide 11):** AUTHENTICATION METHOD 3A.
- ⭐ **Something You Are: Behavioural Biometrics (Slide 12):** AUTHENTICATION METHOD 3B.
- ⭐ **Multi-Factor Authentication (Slide 13):** AUTHENTICATION METHOD 4.
- ⭐ **Authentication Methods, Compared (Slide 14):** AUTHENTICATION SUMMARY.
- ⭐ **Authorization (Slide 15):** Deciding what an authenticated identity can actually do.
- ⭐ **Privilege Levels and Command Authorization (Slide 16):** AUTHORIZATION.
- ⭐ **Access Control Models: Overview (Slide 17):** AUTHORIZATION.
- ⭐ **DAC, Discretionary Access Control (Slide 18):** AUTHORIZATION.

## ❓ Possible Exam Questions

### MCQs

1. Which statement best matches **Foundations**?
   - A. It is unrelated to network security.
   - B. Three genuinely separate questions.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

2. Which statement best matches **Something You Know**?
   - A. It is unrelated to network security.
   - B. AUTHENTICATION METHOD 1.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

3. Which statement best matches **Authentication Methods, Compared**?
   - A. It is unrelated to network security.
   - B. AUTHENTICATION SUMMARY.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

4. Which statement best matches **MAC, Mandatory Access Control**?
   - A. It is unrelated to network security.
   - B. AUTHORIZATION.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

5. Which statement best matches **Session Accounting**?
   - A. It is unrelated to network security.
   - B. ACCOUNTING TYPE 1.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**


### Short Structured Questions

1. **Explain Foundations.**
   - **Model answer:** Three genuinely separate questions.

2. **Explain Something You Know.**
   - **Model answer:** AUTHENTICATION METHOD 1.

3. **Explain Authentication Methods, Compared.**
   - **Model answer:** AUTHENTICATION SUMMARY.

4. **Explain MAC, Mandatory Access Control.**
   - **Model answer:** AUTHORIZATION.

5. **Explain Session Accounting.**
   - **Model answer:** ACCOUNTING TYPE 1.


### Scenario-Based Question

**Scenario:** An organization must apply the concepts from **AAA Foundations** to improve its network security. Identify the relevant mechanism or risk, explain the likely impact, and recommend a layered response.

**Model-answer approach:** Identify the asset and trust boundary; name the relevant protocol/control; explain the mechanism using the lecture terminology; state confidentiality, integrity, or availability impact; then recommend the matching prevention, detection, and verification steps from the slides.

## ⚡ Last-Minute Quick Revision

- **Foundations:** Three genuinely separate questions.
- **What Is AAA?:** FOUNDATIONS.
- **Why Three Separate Functions, Not One:** FOUNDATIONS.
- **AAA as a Modular Framework:** FOUNDATIONS.
- **Authentication:** Proving who you actually are.
- **Something You Know:** AUTHENTICATION METHOD 1.
- **Something You Have:** AUTHENTICATION METHOD 2.
- **Something You Are: Physical Biometrics:** AUTHENTICATION METHOD 3A.
- **Something You Are: Behavioural Biometrics:** AUTHENTICATION METHOD 3B.
- **Multi-Factor Authentication:** AUTHENTICATION METHOD 4.
- **Authentication Methods, Compared:** AUTHENTICATION SUMMARY.
- **Authorization:** Deciding what an authenticated identity can actually do.
- **Privilege Levels and Command Authorization:** AUTHORIZATION.
- **Access Control Models: Overview:** AUTHORIZATION.
- **DAC, Discretionary Access Control:** AUTHORIZATION.
- **MAC, Mandatory Access Control:** AUTHORIZATION.
- **RBAC, Role-Based Access Control:** AUTHORIZATION.
- **RuBAC, Rule-Based Access Control:** AUTHORIZATION.
- **The Four Access Control Models, Compared:** AUTHORIZATION.
- **Accounting:** What actually happened, and proving it afterward.

## Verification Notes

- Slide coverage: **31 of 31 slides processed**.
- Slide numbers refer to PDF page order.
- Any application example or scenario above extends the slide concept for revision and is not presented as a verbatim lecturer statement.
