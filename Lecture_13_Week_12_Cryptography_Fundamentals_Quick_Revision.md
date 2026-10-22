# Lecture 13 – Cryptography Fundamentals

## 📌 Lecture Overview

This lecture covers **Cryptography Fundamentals** as presented in the supplied IE3122 slides. The notes follow the source order across 47 slides and retain the lecture's terminology, mechanisms, examples, and configuration details. They are organized for rapid MCQ, structured-answer, and scenario revision.

> **Source boundary:** Content below is derived from `IE3122_Week12_CryptographyFundamentals_Slides.pdf`. Generic exam prompts/examples are labelled as application material; no unsupported lecturer emphasis is claimed.

## 🎯 Learning Objectives

- LO3
- Analyse security requirements and recommend appropriate technologies.
- LO4
- Evaluate different security technologies, compare them, and identify appropriate use cases.
- By the end of this session you should be able to explain how each cipher family works, and recommend the right one for a given scenario.

## 📚 Main Topics and Subtopics

### Foundations (Slide 4)

**Exam Answer:** What cryptography is for, and the vocabulary we need.

**Explanation:**

- What cryptography is for, and the vocabulary we need

**සිංහලෙන්:** **Foundations** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- What cryptography is for, and the vocabulary we need

**🧠 Memory Tip:** Remember **Foundations** by linking its purpose → mechanism → result.

### Why Cryptography Exists (Slide 5)

**Exam Answer:** FOUNDATIONS.

**Explanation:**

- FOUNDATIONS
- Recall Week 9: the internet is an untrusted network. Any device along the path can read, copy, or modify the traffic passing through
- it.
- We usually cannot control the path, so we protect the data itself. Cryptography is the mathematics of making data unreadable,
- tamper-evident, and attributable, even when an attacker can see every packet.
- Almost every defence in this module depends on it: VPN tunnels (Week 9), AAA credential protection (Week 10), and secure routing
- authentication (Week 5) are all cryptography applied to a networking problem.
- Today and next we build the toolbox. This session covers encryption, which provides confidentiality. The next deck covers hashing,
- signatures, and certificates.

**සිංහලෙන්:** **Why Cryptography Exists** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FOUNDATIONS
- Recall Week 9: the internet is an untrusted network. Any device along the path can read, copy, or modify the traffic passing through
- it.
- We usually cannot control the path, so we protect the data itself. Cryptography is the mathematics of making data unreadable,

**🧠 Memory Tip:** Remember **Why Cryptography Exists** by linking its purpose → mechanism → result.

### The Four Security Services (Slide 6)

**Exam Answer:** FOUNDATIONS.

**Explanation:**

- FOUNDATIONS
- Security Service The Question It Answers Cryptographic Tool Covered In
- Confidentiality Can anyone else read this? Symmetric and asymmetric encryption This deck
- Integrity Was this changed in transit? Hash functions, MACs Next deck
- Authentication Who really sent this? MACs, digital signatures, certificates Next deck
- Non-repudiation Can the sender deny it later? Digital signatures Next deck
- Non-repudiation is the same concept met in Week 2, and the goal that command accounting supported in Week 10.

**සිංහලෙන්:** **The Four Security Services** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FOUNDATIONS
- Security Service The Question It Answers Cryptographic Tool Covered In
- Confidentiality Can anyone else read this? Symmetric and asymmetric encryption This deck
- Integrity Was this changed in transit? Hash functions, MACs Next deck

**🧠 Memory Tip:** Remember **The Four Security Services** by linking its purpose → mechanism → result.

### Terminology (Slide 7)

**Exam Answer:** FOUNDATIONS.

**Explanation:**

- FOUNDATIONS
- Plaintext Encrypt(algorithm) Ciphertext Decrypt(algorithm) Plaintext
- Key Key
- Plaintext is the readable original; ciphertext is the scrambled result. The algorithm (cipher) is the method; the key is the secret value that
- controls it.
- Encryption turns plaintext into ciphertext. Decryption reverses it. Cryptanalysis is the study of breaking this without the key.

**සිංහලෙන්:** **Terminology** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FOUNDATIONS
- Plaintext Encrypt(algorithm) Ciphertext Decrypt(algorithm) Plaintext
- Key Key
- Plaintext is the readable original; ciphertext is the scrambled result. The algorithm (cipher) is the method; the key is the secret value that

**🧠 Memory Tip:** Remember **Terminology** by linking its purpose → mechanism → result.

### Kerckhoffs's Principle (Slide 8)

**Exam Answer:** FOUNDATIONS.

**Explanation:**

- FOUNDATIONS
- A cryptosystem should remain secure even if everything about it, except the key, is public knowledge.
- Why this matters: secret algorithms get leaked, reverse engineered, or simply turn out to be weak. Public algorithms get attacked by
- thousands of researchers, and the survivors earn trust. AES was selected through an open public competition for exactly this reason.
- The practical consequence: never design your own cipher and never rely on obscurity. Use standard, well-reviewed algorithms, and
- put all of your effort into protecting the key.
- The warning examples are the proprietary ciphers such as GSM's A5/1 and WEP's RC4 usage, which were weakened or broken once
- they were examined openly. We meet both later today.

**සිංහලෙන්:** **Kerckhoffs's Principle** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FOUNDATIONS
- A cryptosystem should remain secure even if everything about it, except the key, is public knowledge.
- Why this matters: secret algorithms get leaked, reverse engineered, or simply turn out to be weak. Public algorithms get attacked by
- thousands of researchers, and the survivors earn trust. AES was selected through an open public competition for exactly this reason.

**🧠 Memory Tip:** Remember **Kerckhoffs's Principle** by linking its purpose → mechanism → result.

### Callback: Week 9 Was Built From These Primitives (Slide 9)

**Exam Answer:** FOUNDATIONS.

**Explanation:**

- FOUNDATIONS
- Recall the IPsec framework table: confidentiality (DES, 3DES, AES), integrity (MD5, SHA), authentication (pre-shared key or RSA
- signatures), and a Diffie-Hellman group. Every row is a cryptographic primitive.
- Recall the SSL VPN building blocks: key exchange, authentication, and bulk encryption. The bulk encryption row listed RC4 and
- ChaCha20 alongside DES, 3DES, and AES.
- Those two groups are exactly the two families we examine today: stream ciphers (RC4, ChaCha20) and block ciphers (DES, 3DES, AES).
- By the end of the next deck you will be able to explain every cell of both tables, not just recognise the names.

**සිංහලෙන්:** **Callback: Week 9 Was Built From These Primitives** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- FOUNDATIONS
- Recall the IPsec framework table: confidentiality (DES, 3DES, AES), integrity (MD5, SHA), authentication (pre-shared key or RSA
- signatures), and a Diffie-Hellman group. Every row is a cryptographic primitive.
- Recall the SSL VPN building blocks: key exchange, authentication, and bulk encryption. The bulk encryption row listed RC4 and

**🧠 Memory Tip:** Remember **Callback: Week 9 Was Built From These Primitives** by linking its purpose → mechanism → result.

### Classical Ciphers (Slide 10)

**Exam Answer:** Simple ideas, and why they fail.

**Explanation:**

- Simple ideas, and why they fail

**සිංහලෙන්:** **Classical Ciphers** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Simple ideas, and why they fail

**🧠 Memory Tip:** Remember **Classical Ciphers** by linking its purpose → mechanism → result.

### Substitution and Transposition (Slide 11)

**Exam Answer:** CLASSICAL CIPHERS.

**Explanation:**

- CLASSICAL CIPHERS
- Substitution: replace each symbol with a different symbol. The letters keep their positions but change their identity. Caesarand
- Vigenere are both substitution ciphers.
- Transposition: rearrange the positions of the symbols without changing them. For example, write a message in rows of five andread
- it out column by column.
- Every modern cipher combines both ideas many times over, which is why we study the simple versions first. Substitution hides which
- symbol is which; transposition spreads the message out.
- Classical ciphers are not used for real security today. Their value is that their failure is easy to see, and the failures teach the design
- goals of modern ciphers.

**සිංහලෙන්:** **Substitution and Transposition** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CLASSICAL CIPHERS
- Substitution: replace each symbol with a different symbol. The letters keep their positions but change their identity. Caesarand
- Vigenere are both substitution ciphers.
- Transposition: rearrange the positions of the symbols without changing them. For example, write a message in rows of five andread

**🧠 Memory Tip:** Remember **Substitution and Transposition** by linking its purpose → mechanism → result.

### Caesar Cipher (Slide 12)

**Exam Answer:** CLASSICAL CIPHERS.

**Explanation:**

- CLASSICAL CIPHERS
- Mechanism: shift every letter forward by a fixed number of places in the alphabet. The shift amount is the key. Julius Caesar
- reportedly used a shift of 3.
- Worked example with a key of 3: A becomes D, B becomes E, and so on, wrapping from Z back to A.
- HELLO
- shift each letter by 3
- KHOOR
- Decryption shifts backwards by the same amount. Sender and receiver must share the key (the shift), which makes this a symmetric
- cipher.
- Strength: trivial to use by hand. Weakness: there are only 25 possible keys, so an attacker simply tries all of them.

**සිංහලෙන්:** **Caesar Cipher** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CLASSICAL CIPHERS
- Mechanism: shift every letter forward by a fixed number of places in the alphabet. The shift amount is the key. Julius Caesar
- reportedly used a shift of 3.
- Worked example with a key of 3: A becomes D, B becomes E, and so on, wrapping from Z back to A.

**🧠 Memory Tip:** Remember **Caesar Cipher** by linking its purpose → mechanism → result.

### Vigenere Cipher (Slide 13)

**Exam Answer:** CLASSICAL CIPHERS.

**Explanation:**

- CLASSICAL CIPHERS
- Mechanism: use a keyword instead of a single shift. Repeat the keyword along the message, and shift each letter by the value of the
- keyword letter above it (A is 0, B is 1, and so on).
- Worked example with the keyword LEMON and the message ATTACKATDAWN:
- Message A T T A C K A T D A W N
- Key (repeated) L E M O N L E M O N L E
- Ciphertext L X F O P V E F R N H R
- Notice that the letter A becomes L, then O, then E, depending on the key letter. The same plaintext letter no longer always produces the same
- ciphertext letter, which defeats simple frequency counting.
- Seen as a keystream: the repeated keyword acts as a short repeating keystream added to the message. This is a useful bridge to stream ciphers
- later today, though it is a conceptual framing rather than the formal definition.

**සිංහලෙන්:** **Vigenere Cipher** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CLASSICAL CIPHERS
- Mechanism: use a keyword instead of a single shift. Repeat the keyword along the message, and shift each letter by the value of the
- keyword letter above it (A is 0, B is 1, and so on).
- Worked example with the keyword LEMON and the message ATTACKATDAWN:

**🧠 Memory Tip:** Remember **Vigenere Cipher** by linking its purpose → mechanism → result.

### Why Classical Ciphers Fail (Slide 14)

**Exam Answer:** CLASSICAL CIPHERS.

**Explanation:**

- CLASSICAL CIPHERS
- Tiny key space: Caesar has only 25 usable keys. A computer, or a patient human, tries every one instantly. This is a brute force attack.
- Frequency analysis: in English the letter E is the most common, followed by T and A. In a Caesar ciphertext the most frequentletter is
- almost certainly the encrypted E, which reveals the shift immediately.
- Vigenere flattens the frequencies, but it still leaks structure. If the keyword length is found (the Kasiski examination looks for
- repeated ciphertext fragments), the message splits into several ordinary Caesar ciphers, each broken by frequency analysis.
- The lesson: the ciphertext must not reveal any statistical pattern of the plaintext, and the key space must be far too large to search.
- Both ideas shape every modern cipher.

**සිංහලෙන්:** **Why Classical Ciphers Fail** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CLASSICAL CIPHERS
- Tiny key space: Caesar has only 25 usable keys. A computer, or a patient human, tries every one instantly. This is a brute force attack.
- Frequency analysis: in English the letter E is the most common, followed by T and A. In a Caesar ciphertext the most frequentletter is
- almost certainly the encrypted E, which reveals the shift immediately.

**🧠 Memory Tip:** Remember **Why Classical Ciphers Fail** by linking its purpose → mechanism → result.

### What Carried Forward: Confusion and Diffusion (Slide 15)

**Exam Answer:** CLASSICAL CIPHERS.

**Explanation:**

- CLASSICAL CIPHERS
- In 1949 Claude Shannon named the two properties a strong cipher needs.
- Confusion: make the relationship between the key and the ciphertext as complicated as possible, so that knowing the ciphertext tells
- you nothing about the key. Substitution provides confusion.
- Diffusion: spread the influence of each plaintext symbol across many ciphertext symbols, so statistical patterns disappear.
- Transposition and mixing provide diffusion.
- Classical ciphers use one of these once. Modern block ciphers such as AES apply substitution and mixing in repeated rounds, so a
- single changed input bit changes about half of the output bits. That is the avalanche effect, which returns when we study hash
- functions.

**සිංහලෙන්:** **What Carried Forward: Confusion and Diffusion** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- CLASSICAL CIPHERS
- In 1949 Claude Shannon named the two properties a strong cipher needs.
- Confusion: make the relationship between the key and the ciphertext as complicated as possible, so that knowing the ciphertext tells
- you nothing about the key. Substitution provides confusion.

**🧠 Memory Tip:** Remember **What Carried Forward: Confusion and Diffusion** by linking its purpose → mechanism → result.

### Symmetric Encryption (Slide 16)

**Exam Answer:** One shared key at both ends.

**Explanation:**

- One shared key at both ends

**සිංහලෙන්:** **Symmetric Encryption** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- One shared key at both ends

**🧠 Memory Tip:** Remember **Symmetric Encryption** by linking its purpose → mechanism → result.

### The Symmetric Model (Slide 17)

**Exam Answer:** SYMMETRIC ENCRYPTION.

**Explanation:**

- SYMMETRIC ENCRYPTION
- Sender ReceiverThe same shared secret key
- Encrypt with key Decrypt with keyCiphertext crosses the untrusted network
- Both ends use one secret key. Anyone holding the key can encrypt and decrypt, so the key must be shared in advance and kept secret from
- everyone else.
- Examples: DES, 3DES, AES, RC4, ChaCha20. All are very fast, which is why symmetric encryption carries almost all real data.

**සිංහලෙන්:** **The Symmetric Model** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SYMMETRIC ENCRYPTION
- Sender ReceiverThe same shared secret key
- Encrypt with key Decrypt with keyCiphertext crosses the untrusted network
- Both ends use one secret key. Anyone holding the key can encrypt and decrypt, so the key must be shared in advance and kept secret from

**🧠 Memory Tip:** Remember **The Symmetric Model** by linking its purpose → mechanism → result.

### The Key Distribution Problem (Slide 18)

**Exam Answer:** SYMMETRIC ENCRYPTION.

**Explanation:**

- SYMMETRIC ENCRYPTION
- Problem 1, delivery: how do two parties who have never met agree on a secret key over a network that an attacker can read? Sending
- the key in the clear defeats the purpose.
- Problem 2, scale: if every pair of users needs its own secret key, the number of keys for n users is n(n-1)/2.
- Number of Users Keys Needed (n(n-1)/2)
- 10 45
- 100 4,950
- 1,000 499,500
- Asymmetric cryptography, later today, exists largely to solve these two problems.

**සිංහලෙන්:** **The Key Distribution Problem** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SYMMETRIC ENCRYPTION
- Problem 1, delivery: how do two parties who have never met agree on a secret key over a network that an attacker can read? Sending
- the key in the clear defeats the purpose.
- Problem 2, scale: if every pair of users needs its own secret key, the number of keys for n users is n(n-1)/2.

**🧠 Memory Tip:** Remember **The Key Distribution Problem** by linking its purpose → mechanism → result.

### Symmetric Encryption: Strengths, Weaknesses, Use Cases (Slide 19)

**Exam Answer:** SYMMETRIC ENCRYPTION.

**Explanation:**

- SYMMETRIC ENCRYPTION
- Strengths Weaknesses
- Very fast, so it suits large volumes of data and high-speed links.
- Efficient in hardware: modern CPUs include AES instructions (AES-NI).
- Short keys give strong security: 128 bits is considered secure for the
- foreseeable future.
- Simple conceptual model: one key, one operation in each direction.
- The key distribution problem: both ends need the secret before
- communication starts.
- Key count grows as n(n-1)/2, which does not scale.
- Gives no non-repudiation: either holder could have created any message.
- A leaked key exposes everything ever protected with it.
- Use cases: bulk data encryption in VPN tunnels, TLS sessions, Wi -Fi (WPA2 and WPA3 use AES), disk and file encryption, and database encryption.

**සිංහලෙන්:** **Symmetric Encryption: Strengths, Weaknesses, Use Cases** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- SYMMETRIC ENCRYPTION
- Strengths Weaknesses
- Very fast, so it suits large volumes of data and high-speed links.
- Efficient in hardware: modern CPUs include AES instructions (AES-NI).

**🧠 Memory Tip:** Remember **Symmetric Encryption: Strengths, Weaknesses, Use Cases** by linking its purpose → mechanism → result.

### Block vs Stream Ciphers (Slide 20)

**Exam Answer:** Two ways to process data with a shared key.

**Explanation:**

- Two ways to process data with a shared key

**සිංහලෙන්:** **Block vs Stream Ciphers** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Two ways to process data with a shared key

**🧠 Memory Tip:** Remember **Block vs Stream Ciphers** by linking its purpose → mechanism → result.

### Where Block and Stream Ciphers Fit (Slide 21)

**Exam Answer:** BLOCK VS STREAM.

**Explanation:**

- BLOCK VS STREAM
- Encryption Algorithms
- Symmetric (shared key) Asymmetric (key pair)
- Block ciphers Stream ciphers
- DES, 3DES, AES RC4, ChaCha20, A5/1
- Hard math problems
- RSA, Diffie-Hellman, ECC
- Two questions classify a cipher: how many keys does it use, and how does it process data. Block versus stream is conventionally a split within symmetric ciphers.

**සිංහලෙන්:** **Where Block and Stream Ciphers Fit** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- BLOCK VS STREAM
- Encryption Algorithms
- Symmetric (shared key) Asymmetric (key pair)
- Block ciphers Stream ciphers

**🧠 Memory Tip:** Remember **Where Block and Stream Ciphers Fit** by linking its purpose → mechanism → result.

### Block Ciphers: Mechanism (Slide 22)

**Exam Answer:** BLOCK CIPHERS.

**Explanation:**

- BLOCK CIPHERS
- A block cipher encrypts data in fixed-size chunks called blocks, all using the same key. DES and 3DES use 64-bit blocks; AES uses 128-
- bit blocks.
- Real messages are rarely an exact multiple of the block size, so the final block is padded to full length. The receiver removes the
- padding after decryption.
- A block cipher on its own only encrypts one block. To encrypt a long message, a mode of operation defines how successive blocks are
- chained together. The choice of mode matters as much as the choice of cipher.
- Inside the cipher, each block passes through many rounds of substitution and mixing, providing Shannon's confusion and diffusion.

**සිංහලෙන්:** **Block Ciphers: Mechanism** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- BLOCK CIPHERS
- A block cipher encrypts data in fixed-size chunks called blocks, all using the same key. DES and 3DES use 64-bit blocks; AES uses 128-
- bit blocks.
- Real messages are rarely an exact multiple of the block size, so the final block is padded to full length. The receiver removes the

**🧠 Memory Tip:** Remember **Block Ciphers: Mechanism** by linking its purpose → mechanism → result.

### Modes of Operation I: ECB and CBC (Slide 23)

**Exam Answer:** BLOCK CIPHERS.

**Explanation:**

- BLOCK CIPHERS
- ECB: Electronic Codebook CBC: Cipher Block Chaining
- Every block is encrypted independently with the same key.
- Identical plaintext blocks always give identical ciphertext blocks.
- Patterns in the data show through.
- The classic demonstration encrypts a bitmap image in ECB mode: the
- picture is still clearly recognisable in the ciphertext.
- Verdict: do not use ECB for anything longer than one block.
- Each plaintext block is XORed with the previous ciphertext block
- before it is encrypted. The first block uses a random initialisation
- vector (IV).
- Identical plaintext blocks now produce different ciphertext, so
- patterns disappear.
- Costs: encryption is sequential, padding is required, and a bit error
- spreads into the following block. Careless padding checks have also
- enabled padding oracle attacks.
- Verdict: sound if used correctly, but largely superseded.

**සිංහලෙන්:** **Modes of Operation I: ECB and CBC** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- BLOCK CIPHERS
- ECB: Electronic Codebook CBC: Cipher Block Chaining
- Every block is encrypted independently with the same key.
- Identical plaintext blocks always give identical ciphertext blocks.

**🧠 Memory Tip:** Remember **Modes of Operation I: ECB and CBC** by linking its purpose → mechanism → result.

### Modes of Operation II: CTR and GCM (Slide 24)

**Exam Answer:** BLOCK CIPHERS.

**Explanation:**

- BLOCK CIPHERS
- CTR: Counter Mode GCM: Galois/Counter Mode
- The block cipher encrypts a running counter, not the message. The
- output is a keystream, which is XORed with the plaintext.
- This turns a block cipher into a stream cipher. No padding is needed,
- and blocks can be processed in parallel.
- Critical rule: never reuse a counter or nonce value with the same
- key.
- GCM is CTR mode plus an authentication tag. It provides
- confidentiality and integrity together, called authenticated
- encryption.
- Fast, parallelisable, and the default choice in TLS 1.2 and 1.3 and in
- IPsec ESP .
- The same nonce rule applies: a repeated nonce breaks it badly.
- The line between the two families is blurred: CTR and GCM use a block cipher but behave like stream ciphers. This is why the choice of mode is part of the
- design, not an afterthought.

**සිංහලෙන්:** **Modes of Operation II: CTR and GCM** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- BLOCK CIPHERS
- CTR: Counter Mode GCM: Galois/Counter Mode
- The block cipher encrypts a running counter, not the message. The
- output is a keystream, which is XORed with the plaintext.

**🧠 Memory Tip:** Remember **Modes of Operation II: CTR and GCM** by linking its purpose → mechanism → result.

### Block Cipher Algorithms: DES, 3DES, AES (Slide 25)

**Exam Answer:** BLOCK CIPHERS.

**Explanation:**

- BLOCK CIPHERS
- Algorithm Block Size Key Size Status Notes
- DES 64 bits 56 bits Broken, retired Key space is small enough to brute force; a purpose-built machine did so in 1998.
- 3DES 64 bits Up to 168 bits (about 112 bits of real security) Deprecated Applies DES three times. Slow, and the 64-bit block allows birthday attacks on large volumes of data (Sweet32).
- AES 128 bits 128, 192, or 256 bits Current standard Selected by open NIST competition (Rijndael, standardised 2001, FIPS 197). Fast in hardware and software.
- Recall the IPsec framework table in Week 9: this is the confidentiality row, and AES is the choice you would make today.

**සිංහලෙන්:** **Block Cipher Algorithms: DES, 3DES, AES** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- BLOCK CIPHERS
- Algorithm Block Size Key Size Status Notes
- DES 64 bits 56 bits Broken, retired Key space is small enough to brute force; a purpose-built machine did so in 1998.
- 3DES 64 bits Up to 168 bits (about 112 bits of real security) Deprecated Applies DES three times. Slow, and the 64-bit block allows birthday attacks on large volumes of data (Sweet32).

**🧠 Memory Tip:** Remember **Block Cipher Algorithms: DES, 3DES, AES** by linking its purpose → mechanism → result.

### Block Ciphers: Strengths, Weaknesses, Use Cases (Slide 26)

**Exam Answer:** BLOCK CIPHERS.

**Explanation:**

- BLOCK CIPHERS
- Strengths Weaknesses
- Very well studied: AES has withstood over two decades of public
- cryptanalysis.
- Hardware acceleration (AES-NI) makes it extremely fast on most servers
- and laptops.
- Flexible: different modes suit different needs, from random-access disk
- encryption to authenticated network traffic.
- GCM gives encryption and integrity in a single operation.
- Mode choice is easy to get wrong: ECB leaks patterns, and CBC needs
- careful padding handling.
- Padding adds overhead, and short messages still consume a whole block.
- Nonce or IV mistakes can be catastrophic in CTR and GCM.
- Without hardware support, some block ciphers are slower than modern
- stream ciphers.
- Use cases: full-disk encryption (AES-XTS), file and database encryption, TLS and IPsec bulk data (AES -GCM), Wi-Fi WPA2 and WPA3, and VPN tunnels.

**සිංහලෙන්:** **Block Ciphers: Strengths, Weaknesses, Use Cases** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- BLOCK CIPHERS
- Strengths Weaknesses
- Very well studied: AES has withstood over two decades of public
- cryptanalysis.

**🧠 Memory Tip:** Remember **Block Ciphers: Strengths, Weaknesses, Use Cases** by linking its purpose → mechanism → result.

### Stream Ciphers: Mechanism (Slide 27)

**Exam Answer:** STREAM CIPHERS.

**Explanation:**

- STREAM CIPHERS
- Key + nonce Keystream generator
- Plaintext stream
- XOR Ciphertext stream
- A stream cipher generates a pseudo-random keystream from the key (and a nonce), then XORs it with the plaintext one bit or byte at a time.
- Decryption is the same XOR with the same keystream.
- The theoretical ideal is the one-time pad: a truly random key as long as the message, used once. Shannon proved it gives perfectsecrecy, but it
- is impractical because the key must be shared securely and never reused. Stream ciphers approximate it with a short key.

**සිංහලෙන්:** **Stream Ciphers: Mechanism** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- STREAM CIPHERS
- Key + nonce Keystream generator
- Plaintext stream
- XOR Ciphertext stream

**🧠 Memory Tip:** Remember **Stream Ciphers: Mechanism** by linking its purpose → mechanism → result.

### Stream Cipher Algorithms: RC4, ChaCha20, A5/1 (Slide 28)

**Exam Answer:** STREAM CIPHERS.

**Explanation:**

- STREAM CIPHERS
- Algorithm Key Size Status Where It Appeared Notes
- RC4 40 to 2048 bits Broken, prohibited in TLS (RFC 7465) WEP , early WPA (TKIP), SSL and TLS Statistical biases in the keystream allow plaintext recovery. Simple and fast, which made it popular.
- ChaCha20 256 bits Current, recommended TLS 1.3 (with Poly1305), WireGuard, SSH Fast in software without special hardware, which suits mobile devices. Designed by Bernstein.
- A5/1 64 bits Broken in practice GSM (2G) mobile networks Short key and published attacks. Newer mobile generations use stronger ciphers.

**සිංහලෙන්:** **Stream Cipher Algorithms: RC4, ChaCha20, A5/1** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- STREAM CIPHERS
- Algorithm Key Size Status Where It Appeared Notes
- RC4 40 to 2048 bits Broken, prohibited in TLS (RFC 7465) WEP , early WPA (TKIP), SSL and TLS Statistical biases in the keystream allow plaintext recovery. Simple and fast, which made it popular.
- ChaCha20 256 bits Current, recommended TLS 1.3 (with Poly1305), WireGuard, SSH Fast in software without special hardware, which suits mobile devices. Designed by Bernstein.

**🧠 Memory Tip:** Remember **Stream Cipher Algorithms: RC4, ChaCha20, A5/1** by linking its purpose → mechanism → result.

### The Keystream Reuse Weakness: WEP Case Study (Slide 29)

**Exam Answer:** STREAM CIPHERS.

**Explanation:**

- STREAM CIPHERS
- The fatal rule: never use the same keystream twice. If two messages are encrypted with the same keystream, XORing the two ciphertexts
- cancels the keystream and leaves the XOR of the two plaintexts. An attacker can then recover both using known or guessable content.
- WEP (the original Wi-Fi security) used RC4 with a 24-bit initialisation vector (IV) sent in the clear. A 24-bit IV has only about 16.7 million values,
- so on a busy network the same IV, and therefore the same keystream, repeats within a few thousand packets.
- WEP also mixed the IV directly into the RC4 key in a way that leaked key material, so attackers could recover the key itself after capturing
- enough traffic. The attack tools became widely available in the early 2000s.
- Lessons: nonces must never repeat, ciphers must be used in a sound construction, and a secure algorithm inside an insecure protocol is still
- insecure.

**සිංහලෙන්:** **The Keystream Reuse Weakness: WEP Case Study** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- STREAM CIPHERS
- The fatal rule: never use the same keystream twice. If two messages are encrypted with the same keystream, XORing the two ciphertexts
- cancels the keystream and leaves the XOR of the two plaintexts. An attacker can then recover both using known or guessable content.
- WEP (the original Wi-Fi security) used RC4 with a 24-bit initialisation vector (IV) sent in the clear. A 24-bit IV has only about 16.7 million values,

**🧠 Memory Tip:** Remember **The Keystream Reuse Weakness: WEP Case Study** by linking its purpose → mechanism → result.

### Stream Ciphers: Strengths, Weaknesses, Use Cases (Slide 30)

**Exam Answer:** STREAM CIPHERS.

**Explanation:**

- STREAM CIPHERS
- Strengths Weaknesses
- Fast and low latency: each bit or byte can be encrypted as it arrives.
- No padding, and well suited to data of unknown length such as live
- streams.
- A transmission error damages only the corrupted bit, not the following
- data.
- Small and simple to implement, including on constrained devices.
- Keystream reuse is catastrophic and easy to cause by accident.
- On its own offers no integrity: flipping a ciphertext bit flips the same
- plaintext bit, so a MAC or authenticated mode is required.
- A weak design is hard to spot: RC4 and A5/1 both looked reasonable
- before they were broken.
- Needs a unique nonce per message, which the protocol must manage.
- Use cases: TLS 1.3 on mobile devices (ChaCha20 -Poly1305), WireGuard VPN, SSH, live voice and video where low latency matters, and mobile network
- encryption.

**සිංහලෙන්:** **Stream Ciphers: Strengths, Weaknesses, Use Cases** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- STREAM CIPHERS
- Strengths Weaknesses
- Fast and low latency: each bit or byte can be encrypted as it arrives.
- No padding, and well suited to data of unknown length such as live

**🧠 Memory Tip:** Remember **Stream Ciphers: Strengths, Weaknesses, Use Cases** by linking its purpose → mechanism → result.

### Block vs Stream: Full Comparison (Slide 31)

**Exam Answer:** BLOCK VS STREAM.

**Explanation:**

- BLOCK VS STREAM
- Aspect Block Cipher Stream Cipher
- Processing unit Fixed-size blocks (64 or 128 bits) One bit or byte at a time
- Padding Required for the final block in most modes Not needed
- Speed and latency Very fast with hardware support; must wait for a full block Fast in software; low latency
- Error propagation Depends on the mode (CBC spreads an error into the next block) A single bit error stays a single bit error
- Example algorithms DES, 3DES, AES RC4, ChaCha20, A5/1
- Characteristic weakness Wrong mode or padding handling Keystream reuse
- Typical use Disk, file, and bulk network encryption Streaming, mobile, low-latency links

**සිංහලෙන්:** **Block vs Stream: Full Comparison** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- BLOCK VS STREAM
- Aspect Block Cipher Stream Cipher
- Processing unit Fixed-size blocks (64 or 128 bits) One bit or byte at a time
- Padding Required for the final block in most modes Not needed

**🧠 Memory Tip:** Remember **Block vs Stream: Full Comparison** by linking its purpose → mechanism → result.

### Scenario: Which Would You Choose? (Slide 32)

**Exam Answer:** BLOCK VS STREAM.

**Explanation:**

- BLOCK VS STREAM
- Scenario Reasonable Choice Why
- Encrypting a laptop's whole disk Block cipher: AES in XTS mode Data is stored in fixed-size sectors and needs random access. Hardware AES makes it nearly free.
- A live voice call Stream-style: AES in counter mode, or ChaCha20 Packets are small and arrive continuously, so low latency and no padding matter. Real voice systems (SRTP) use AES in counter mode.
- A TLS web session Either, with authentication: AES-GCM or ChaCha20-Poly1305 AES-GCM where hardware AES exists; ChaCha20-Poly1305 on phones without it. Both give encryption and integrity.
- Notice that the best answer is often a block cipher running in a stream-like mode. The real decision is the construction, not the label.

**සිංහලෙන්:** **Scenario: Which Would You Choose?** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- BLOCK VS STREAM
- Scenario Reasonable Choice Why
- Encrypting a laptop's whole disk Block cipher: AES in XTS mode Data is stored in fixed-size sectors and needs random access. Hardware AES makes it nearly free.
- A live voice call Stream-style: AES in counter mode, or ChaCha20 Packets are small and arrive continuously, so low latency and no padding matter. Real voice systems (SRTP) use AES in counter mode.

**🧠 Memory Tip:** Remember **Scenario: Which Would You Choose?** by linking its purpose → mechanism → result.

### Asymmetric Encryption (Slide 33)

**Exam Answer:** A pair of keys instead of one shared secret.

**Explanation:**

- A pair of keys instead of one shared secret

**සිංහලෙන්:** **Asymmetric Encryption** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- A pair of keys instead of one shared secret

**🧠 Memory Tip:** Remember **Asymmetric Encryption** by linking its purpose → mechanism → result.

### The Key Pair (Slide 34)

**Exam Answer:** ASYMMETRIC ENCRYPTION.

**Explanation:**

- ASYMMETRIC ENCRYPTION
- Public key: shared openly with anyone Private key: never leaves its owner
- Anyone may have it, so distribution is easy.
- Used to encrypt data for the owner, or to verify the
- owner's signature.
- Known only to the owner, so it must be protected.
- Used to decrypt data sent to the owner, or to create
- the owner's signature.
- The two keys are mathematically linked: what one key does, only the other can undo. Working out the private key from the public key is
- computationally infeasible.
- For confidentiality: encrypt with the receiver's public key, and only the receiver's private key can decrypt. Signatures reverse the roles (private
- key signs, public key verifies) and are the subject of the next deck.

**සිංහලෙන්:** **The Key Pair** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ASYMMETRIC ENCRYPTION
- Public key: shared openly with anyone Private key: never leaves its owner
- Anyone may have it, so distribution is easy.
- Used to encrypt data for the owner, or to verify the

**🧠 Memory Tip:** Remember **The Key Pair** by linking its purpose → mechanism → result.

### RSA (Slide 35)

**Exam Answer:** ASYMMETRIC ENCRYPTION.

**Explanation:**

- ASYMMETRIC ENCRYPTION
- Mechanism: security rests on the difficulty of factoring the product of two very large prime numbers. Multiplying two primes is easy;
- recovering them from the product is not.
- Key sizes: 2048 bits is the accepted minimum today, and 3072 bits is recommended for longer-term protection. Keys under 2048 bits
- should not be used.
- Uses: key transport (encrypting a small symmetric key for the receiver) and digital signatures. RSA encrypts only small values, with a
- padding scheme such as Optimal Asymmetric Encryption Padding (OAEP), so it is never used to encrypt bulk data directly.
- Status: still widely deployed, but being replaced by elliptic curve methods in new designs, and vulnerable to a large quantum
- computer.

**සිංහලෙන්:** **RSA** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ASYMMETRIC ENCRYPTION
- Mechanism: security rests on the difficulty of factoring the product of two very large prime numbers. Multiplying two primes is easy;
- recovering them from the product is not.
- Key sizes: 2048 bits is the accepted minimum today, and 3072 bits is recommended for longer-term protection. Keys under 2048 bits

**🧠 Memory Tip:** Remember **RSA** by linking its purpose → mechanism → result.

### Diffie-Hellman Key Agreement (Slide 36)

**Exam Answer:** ASYMMETRIC ENCRYPTION.

**Explanation:**

- ASYMMETRIC ENCRYPTION
- Purpose: two parties who have never met agree on a shared secret over a public channel. Diffie-Hellman does not encrypt anything itself; it
- produces the shared key that symmetric encryption then uses.
- How it works, in outline: each side keeps a private value and sends a public value computed from it. Each side combines its own private value
- with the other's public value and arrives at the same shared secret. An eavesdropper sees both public values but cannot compute the secret,
- because that requires solving the discrete logarithm problem.
- Ephemeral Diffie-Hellman uses fresh values for every session, giving forward secrecy: stealing a long-term key later does not expose past
- sessions.
- Weakness: plain Diffie-Hellman does not authenticate the other party, so a man in the middle can agree separate secrets with each side. It
- must be combined with signatures or certificates, which is the topic of the next deck.
- Callback: the Diffie-Hellman group in the IPsec framework table (Week 9) selects the size of the numbers used.

**සිංහලෙන්:** **Diffie-Hellman Key Agreement** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ASYMMETRIC ENCRYPTION
- Purpose: two parties who have never met agree on a shared secret over a public channel. Diffie-Hellman does not encrypt anything itself; it
- produces the shared key that symmetric encryption then uses.
- How it works, in outline: each side keeps a private value and sends a public value computed from it. Each side combines its own private value

**🧠 Memory Tip:** Remember **Diffie-Hellman Key Agreement** by linking its purpose → mechanism → result.

### Diffie-Hellman Key Agreement (Slide 37)

**Exam Answer:** ASYMMETRIC ENCRYPTION.

**Explanation:**

- ASYMMETRIC ENCRYPTION

**සිංහලෙන්:** **Diffie-Hellman Key Agreement** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ASYMMETRIC ENCRYPTION

**🧠 Memory Tip:** Remember **Diffie-Hellman Key Agreement** by linking its purpose → mechanism → result.

### Elliptic Curve Cryptography (ECC) (Slide 38)

**Exam Answer:** ASYMMETRIC ENCRYPTION.

**Explanation:**

- ASYMMETRIC ENCRYPTION
- Mechanism: the same style of key pair, but based on the difficulty of the discrete logarithm problem on an elliptic curve instead of on factoring
- or ordinary modular arithmetic.
- The main advantage is size. A 256-bit elliptic curve key gives roughly the security of a 3072-bit RSA key, so keys, signatures, and computation
- are all smaller and faster.
- Common forms: ECDH (key agreement) and ECDSA (signatures), using curves such as P-256 and Curve25519.
- This makes ECC especially attractive for mobile devices, smart cards, and IoT, and it is now the default in TLS 1.3 and many VPNs.
- Like RSA and Diffie-Hellman, it would be broken by a large quantum computer. NIST has standardised post-quantum replacements, which are
- now beginning to be deployed.

**සිංහලෙන්:** **Elliptic Curve Cryptography (ECC)** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ASYMMETRIC ENCRYPTION
- Mechanism: the same style of key pair, but based on the difficulty of the discrete logarithm problem on an elliptic curve instead of on factoring
- or ordinary modular arithmetic.
- The main advantage is size. A 256-bit elliptic curve key gives roughly the security of a 3072-bit RSA key, so keys, signatures, and computation

**🧠 Memory Tip:** Remember **Elliptic Curve Cryptography (ECC)** by linking its purpose → mechanism → result.

### RSA vs Diffie-Hellman vs ECC (Slide 39)

**Exam Answer:** ASYMMETRIC ENCRYPTION.

**Explanation:**

- ASYMMETRIC ENCRYPTION
- Aspect RSA Diffie-Hellman ECC
- Main purpose Key transport and signatures Key agreement Key agreement (ECDH) and signatures (ECDSA)
- Hard problem Integer factoring Discrete logarithm Elliptic curve discrete logarithm
- Key size for about 128-bit security 3072 bits 3072 bits 256 bits
- Provides forward secrecy? Not by itself Yes, when ephemeral Yes, when ephemeral (ECDHE)
- Typical weakness Large keys, slow No authentication on its own Implementation and curve choice
- All three share the same long-term threat: a sufficiently large quantum computer.

**සිංහලෙන්:** **RSA vs Diffie-Hellman vs ECC** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ASYMMETRIC ENCRYPTION
- Aspect RSA Diffie-Hellman ECC
- Main purpose Key transport and signatures Key agreement Key agreement (ECDH) and signatures (ECDSA)
- Hard problem Integer factoring Discrete logarithm Elliptic curve discrete logarithm

**🧠 Memory Tip:** Remember **RSA vs Diffie-Hellman vs ECC** by linking its purpose → mechanism → result.

### Asymmetric Encryption: Strengths, Weaknesses, Use Cases (Slide 40)

**Exam Answer:** ASYMMETRIC ENCRYPTION.

**Explanation:**

- ASYMMETRIC ENCRYPTION
- Strengths Weaknesses
- Solves key distribution: the public key can be published openly.
- Scales well: n users need only n key pairs, not n(n-1)/2 shared secrets.
- Enables digital signatures, and therefore authentication and non-
- repudiation.
- Allows two strangers to establish a secret over an open network.
- Orders of magnitude slower than symmetric encryption, so unsuitable for
- bulk data.
- Larger keys and larger outputs.
- You must be sure a public key really belongs to its claimed owner. This is
- the problem certificates solve.
- RSA, Diffie-Hellman, and ECC are all vulnerable to a future quantum
- computer.
- Use cases: key exchange in TLS and IKE, digital signatures and certificates, SSH authentication, and secure email (S/MIME and PGP).

**සිංහලෙන්:** **Asymmetric Encryption: Strengths, Weaknesses, Use Cases** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- ASYMMETRIC ENCRYPTION
- Strengths Weaknesses
- Solves key distribution: the public key can be published openly.
- Scales well: n users need only n key pairs, not n(n-1)/2 shared secrets.

**🧠 Memory Tip:** Remember **Asymmetric Encryption: Strengths, Weaknesses, Use Cases** by linking its purpose → mechanism → result.

### Symmetric vs Asymmetric, and Hybrid (Slide 41)

**Exam Answer:** Encryption.

**Explanation:**

- Encryption
- Using each where it is strongest

**සිංහලෙන්:** **Symmetric vs Asymmetric, and Hybrid** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Encryption
- Using each where it is strongest

**🧠 Memory Tip:** Remember **Symmetric vs Asymmetric, and Hybrid** by linking its purpose → mechanism → result.

### Symmetric vs Asymmetric: Full Comparison (Slide 42)

**Exam Answer:** COMPARISON.

**Explanation:**

- COMPARISON
- Aspect Symmetric Asymmetric
- Keys One shared secret key A public and private key pair
- Speed Very fast Much slower
- Key distribution Difficult: the secret must be shared first Easy: the public key can be published
- Keys needed for n users n(n-1)/2 n key pairs
- Security services Confidentiality (with a MAC, integrity) Confidentiality, authentication, non-repudiation (signatures)
- Typical key size 128 to 256 bits 256 bits (ECC) to 3072 bits (RSA)
- Examples AES, ChaCha20 RSA, Diffie-Hellman, ECC
- Best used for Encrypting bulk data Key exchange and signatures

**සිංහලෙන්:** **Symmetric vs Asymmetric: Full Comparison** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- COMPARISON
- Aspect Symmetric Asymmetric
- Keys One shared secret key A public and private key pair
- Speed Very fast Much slower

**🧠 Memory Tip:** Remember **Symmetric vs Asymmetric: Full Comparison** by linking its purpose → mechanism → result.

### Hybrid Encryption: The Synthesis (Slide 43)

**Exam Answer:** COMPARISON.

**Explanation:**

- COMPARISON
- Alice Bob
- Phase 1, handshake: asymmetric cryptography (RSA, DH, ECDH) agrees a
- session key. Slow, but used once.
- Phase 2, bulk data: symmetric cryptography (AES, ChaCha20) uses the
- session key. Fast, used for everything.
- Asymmetric cryptography solves distribution but is slow. Symmetric cryptography is fast but cannot distribute its own keys. Hybrid encryption
- uses each for the job it does well.
- The session key is temporary, so each connection gets a fresh key, limiting the damage if one is ever exposed.

**සිංහලෙන්:** **Hybrid Encryption: The Synthesis** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- COMPARISON
- Alice Bob
- Phase 1, handshake: asymmetric cryptography (RSA, DH, ECDH) agrees a
- session key. Slow, but used once.

**🧠 Memory Tip:** Remember **Hybrid Encryption: The Synthesis** by linking its purpose → mechanism → result.

### Worked Example: TLS and IPsec Are Hybrid Systems (Slide 44)

**Exam Answer:** COMPARISON.

**Explanation:**

- COMPARISON
- Protocol Asymmetric Part (setup) Symmetric Part (data)
- TLS 1.3 (web, SSL VPN) ECDHE key agreement, authenticated with a certificate and signature AES-GCM or ChaCha20-Poly1305 for all application data
- IPsec (IKE, then ESP) IKE uses a Diffie-Hellman exchange and authentication (pre-shared key or certificates) to build the keys ESP encrypts traffic with AES, often in GCM mode
- SSH Key exchange (such as Curve25519) and host and user authentication AES or ChaCha20 for the session
- In every case the expensive asymmetric step happens once at the start, then fast symmetric encryption carries the data.

**සිංහලෙන්:** **Worked Example: TLS and IPsec Are Hybrid Systems** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- COMPARISON
- Protocol Asymmetric Part (setup) Symmetric Part (data)
- TLS 1.3 (web, SSL VPN) ECDHE key agreement, authenticated with a certificate and signature AES-GCM or ChaCha20-Poly1305 for all application data
- IPsec (IKE, then ESP) IKE uses a Diffie-Hellman exchange and authentication (pre-shared key or certificates) to build the keys ESP encrypts traffic with AES, often in GCM mode

**🧠 Memory Tip:** Remember **Worked Example: TLS and IPsec Are Hybrid Systems** by linking its purpose → mechanism → result.

### Summary (Slide 45)

**Exam Answer:** Cryptography provides confidentiality, integrity, authentication, and non-repudiation. Encryption provides the first of these; the next.

**Explanation:**

- Cryptography provides confidentiality, integrity, authentication, and non-repudiation. Encryption provides the first of these; the next
- deck covers the rest.
- Kerckhoffs's principle: the algorithm is public and the key is the secret. Classical ciphers failed on key space and frequency patterns,
- which taught the principles of confusion and diffusion.
- Block ciphers (AES) encrypt fixed blocks and depend on the mode of operation. Stream ciphers (ChaCha20) encrypt a keystream and
- depend on never reusing a nonce. CTR and GCM blur the line between them.
- Asymmetric cryptography (RSA, Diffie-Hellman, ECC) solves key distribution but is slow. Hybrid encryption combines both, and that is
- how TLS, IKE, and SSH work.

**සිංහලෙන්:** **Summary** කියන්නේ මේ slide එකේ දක්වන mechanism/idea එකයි. Exam answer එකේදී එය **කෙසේ ක්‍රියා කරයිද**, security impact එක, සහ අදාළ defense/usage එක technical terms සමඟ සම්බන්ධ කරන්න.

**Example:** Apply the slide's mechanism to a small enterprise network and state the expected result.

**Key Points:**

- Cryptography provides confidentiality, integrity, authentication, and non-repudiation. Encryption provides the first of these; the next
- deck covers the rest.
- Kerckhoffs's principle: the algorithm is public and the key is the secret. Classical ciphers failed on key space and frequency patterns,
- which taught the principles of confusion and diffusion.

**🧠 Memory Tip:** Remember **Summary** by linking its purpose → mechanism → result.


## 📊 Important Comparisons

| Comparison/topic | Source | Exam focus |
|---|---:|---|
| Block vs Stream Ciphers | Slide 20 | Two ways to process data with a shared key. |
| Block vs Stream: Full Comparison | Slide 31 | BLOCK VS STREAM. |
| RSA vs Diffie-Hellman vs ECC | Slide 39 | ASYMMETRIC ENCRYPTION. |
| Symmetric vs Asymmetric, and Hybrid | Slide 41 | Encryption. |
| Symmetric vs Asymmetric: Full Comparison | Slide 42 | COMPARISON. |
| Summary | Slide 45 | Cryptography provides confidentiality, integrity, authentication, and non-repudiation. Encryption provides the first of these; the next. |

## 🛠️ Practical Knowledge

### Why Cryptography Exists (Slide 5)

- FOUNDATIONS
- Recall Week 9: the internet is an untrusted network. Any device along the path can read, copy, or modify the traffic passing through
- it.
- We usually cannot control the path, so we protect the data itself. Cryptography is the mathematics of making data unreadable,
- tamper-evident, and attributable, even when an attacker can see every packet.
- Almost every defence in this module depends on it: VPN tunnels (Week 9), AAA credential protection (Week 10), and secure routing
- authentication (Week 5) are all cryptography applied to a networking problem.
- Today and next we build the toolbox. This session covers encryption, which provides confidentiality. The next deck covers hashing,
- signatures, and certificates.

### The Four Security Services (Slide 6)

- FOUNDATIONS
- Security Service The Question It Answers Cryptographic Tool Covered In
- Confidentiality Can anyone else read this? Symmetric and asymmetric encryption This deck
- Integrity Was this changed in transit? Hash functions, MACs Next deck
- Authentication Who really sent this? MACs, digital signatures, certificates Next deck
- Non-repudiation Can the sender deny it later? Digital signatures Next deck
- Non-repudiation is the same concept met in Week 2, and the goal that command accounting supported in Week 10.

### The Keystream Reuse Weakness: WEP Case Study (Slide 29)

- STREAM CIPHERS
- The fatal rule: never use the same keystream twice. If two messages are encrypted with the same keystream, XORing the two ciphertexts
- cancels the keystream and leaves the XOR of the two plaintexts. An attacker can then recover both using known or guessable content.
- WEP (the original Wi-Fi security) used RC4 with a 24-bit initialisation vector (IV) sent in the clear. A 24-bit IV has only about 16.7 million values,
- so on a busy network the same IV, and therefore the same keystream, repeats within a few thousand packets.
- WEP also mixed the IV directly into the RC4 key in a way that leaked key material, so attackers could recover the key itself after capturing
- enough traffic. The attack tools became widely available in the early 2000s.
- Lessons: nonces must never repeat, ciphers must be used in a sound construction, and a secure algorithm inside an insecure protocol is still
- insecure.

### Scenario: Which Would You Choose? (Slide 32)

- BLOCK VS STREAM
- Scenario Reasonable Choice Why
- Encrypting a laptop's whole disk Block cipher: AES in XTS mode Data is stored in fixed-size sectors and needs random access. Hardware AES makes it nearly free.
- A live voice call Stream-style: AES in counter mode, or ChaCha20 Packets are small and arrive continuously, so low latency and no padding matter. Real voice systems (SRTP) use AES in counter mode.
- A TLS web session Either, with authentication: AES-GCM or ChaCha20-Poly1305 AES-GCM where hardware AES exists; ChaCha20-Poly1305 on phones without it. Both give encryption and integrity.
- Notice that the best answer is often a block cipher running in a stream-like mode. The real decision is the construction, not the label.

## ⭐ Important Exam Points

- ⭐ **Foundations (Slide 4):** What cryptography is for, and the vocabulary we need.
- ⭐ **Why Cryptography Exists (Slide 5):** FOUNDATIONS.
- ⭐ **The Four Security Services (Slide 6):** FOUNDATIONS.
- ⭐ **Terminology (Slide 7):** FOUNDATIONS.
- ⭐ **Kerckhoffs's Principle (Slide 8):** FOUNDATIONS.
- ⭐ **Callback: Week 9 Was Built From These Primitives (Slide 9):** FOUNDATIONS.
- ⭐ **Classical Ciphers (Slide 10):** Simple ideas, and why they fail.
- ⭐ **Substitution and Transposition (Slide 11):** CLASSICAL CIPHERS.
- ⭐ **Caesar Cipher (Slide 12):** CLASSICAL CIPHERS.
- ⭐ **Vigenere Cipher (Slide 13):** CLASSICAL CIPHERS.
- ⭐ **Why Classical Ciphers Fail (Slide 14):** CLASSICAL CIPHERS.
- ⭐ **What Carried Forward: Confusion and Diffusion (Slide 15):** CLASSICAL CIPHERS.
- ⭐ **Symmetric Encryption (Slide 16):** One shared key at both ends.
- ⭐ **The Symmetric Model (Slide 17):** SYMMETRIC ENCRYPTION.
- ⭐ **The Key Distribution Problem (Slide 18):** SYMMETRIC ENCRYPTION.

## ❓ Possible Exam Questions

### MCQs

1. Which statement best matches **Foundations**?
   - A. It is unrelated to network security.
   - B. What cryptography is for, and the vocabulary we need.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

2. Which statement best matches **Caesar Cipher**?
   - A. It is unrelated to network security.
   - B. CLASSICAL CIPHERS.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

3. Which statement best matches **Block vs Stream Ciphers**?
   - A. It is unrelated to network security.
   - B. Two ways to process data with a shared key.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

4. Which statement best matches **Stream Cipher Algorithms: RC4, ChaCha20, A5/1**?
   - A. It is unrelated to network security.
   - B. STREAM CIPHERS.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**

5. Which statement best matches **Diffie-Hellman Key Agreement**?
   - A. It is unrelated to network security.
   - B. ASYMMETRIC ENCRYPTION.
   - C. It always provides confidentiality, integrity, and availability by itself.
   - D. It removes the need for layered security.

   **Answer: B**


### Short Structured Questions

1. **Explain Foundations.**
   - **Model answer:** What cryptography is for, and the vocabulary we need.

2. **Explain Caesar Cipher.**
   - **Model answer:** CLASSICAL CIPHERS.

3. **Explain Block vs Stream Ciphers.**
   - **Model answer:** Two ways to process data with a shared key.

4. **Explain Stream Cipher Algorithms: RC4, ChaCha20, A5/1.**
   - **Model answer:** STREAM CIPHERS.

5. **Explain Diffie-Hellman Key Agreement.**
   - **Model answer:** ASYMMETRIC ENCRYPTION.


### Scenario-Based Question

**Scenario:** An organization must apply the concepts from **Cryptography Fundamentals** to improve its network security. Identify the relevant mechanism or risk, explain the likely impact, and recommend a layered response.

**Model-answer approach:** Identify the asset and trust boundary; name the relevant protocol/control; explain the mechanism using the lecture terminology; state confidentiality, integrity, or availability impact; then recommend the matching prevention, detection, and verification steps from the slides.

## ⚡ Last-Minute Quick Revision

- **Foundations:** What cryptography is for, and the vocabulary we need.
- **Why Cryptography Exists:** FOUNDATIONS.
- **The Four Security Services:** FOUNDATIONS.
- **Terminology:** FOUNDATIONS.
- **Kerckhoffs's Principle:** FOUNDATIONS.
- **Callback: Week 9 Was Built From These Primitives:** FOUNDATIONS.
- **Classical Ciphers:** Simple ideas, and why they fail.
- **Substitution and Transposition:** CLASSICAL CIPHERS.
- **Caesar Cipher:** CLASSICAL CIPHERS.
- **Vigenere Cipher:** CLASSICAL CIPHERS.
- **Why Classical Ciphers Fail:** CLASSICAL CIPHERS.
- **What Carried Forward: Confusion and Diffusion:** CLASSICAL CIPHERS.
- **Symmetric Encryption:** One shared key at both ends.
- **The Symmetric Model:** SYMMETRIC ENCRYPTION.
- **The Key Distribution Problem:** SYMMETRIC ENCRYPTION.
- **Symmetric Encryption: Strengths, Weaknesses, Use Cases:** SYMMETRIC ENCRYPTION.
- **Block vs Stream Ciphers:** Two ways to process data with a shared key.
- **Where Block and Stream Ciphers Fit:** BLOCK VS STREAM.
- **Block Ciphers: Mechanism:** BLOCK CIPHERS.
- **Modes of Operation I: ECB and CBC:** BLOCK CIPHERS.

## Verification Notes

- Slide coverage: **47 of 47 slides processed**.
- Slide numbers refer to PDF page order.
- Any application example or scenario above extends the slide concept for revision and is not presented as a verbatim lecturer statement.
