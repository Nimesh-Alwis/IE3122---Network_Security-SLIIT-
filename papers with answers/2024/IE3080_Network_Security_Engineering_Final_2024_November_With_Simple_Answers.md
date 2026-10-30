# Sri Lanka Institute of Information Technology

B.Sc. Honours Degree in Information Technology

Specialized in Computer Systems & Networking

Final Examination  
Year 3, Semester 1 (2024)

IE3080 – Network Security Engineering

Duration: 2 Hours

November 2024

## Instructions to Candidates:

- This paper has 04 questions.
- Answer all questions in the booklet given.
- The total marks for the paper is 100.
- This paper contains 04 pages, including the cover page.
- This paper proceeds with 10 minutes of reading time.
- Calculators are allowed but electronic devices capable of storing and retrieving text are not allowed.

## Question 01 — 25 Marks

a. A hybrid cloud is a cloud computing environment that combines on-premises data centers (private clouds) with public clouds, allowing organizations to run applications and manage data seamlessly across these environments. It provides a flexible, cost-effective IT infrastructure by unifying different computing resources. Your organization is planning to transition to a cloud-based infrastructure while managing network security for a hybrid cloud environment. You are tasked with ensuring the security of this infrastructure, mitigating both internal and external threats. Design a comprehensive security plan to secure the organization's hybrid cloud infrastructure. Your plan should address the following.

i. Identify and explain the potential network security threats (both internal and external) that are relevant to this transition. (10 Marks)

ii. Propose security strategies to mitigate these threats, including technologies, processes, and policies that need to be implemented. (10 Marks)

iii. Evaluate the effectiveness of your proposed strategies by discussing possible challenges or limitations and how they could be addressed. (5 Marks)

## Question 02 — 25 Marks

a. Your organization is planning to implement a Public Key Infrastructure (PKI) to ensure secure communication between internal systems, external partners, and customers. As the network security engineer, you are responsible for designing and deploying the PKI system.

i. Analyze the components of a PKI system and explain how they ensure secure communication. Discuss the roles of Certificate Authorities (CAs), digital certificates, and certificate revocation in maintaining security. (10 Marks)

ii. Design a PKI deployment strategy for a large-scale organization, illustrating how internal and external parties would securely exchange data using public key cryptography. Provide a detailed process flow that includes key generation, certificate issuance, and certificate management. (10 Marks)

iii. Evaluate the limitations of PKI in the context of scalability, certificate management, and interoperability with third-party systems. Propose solutions to mitigate these challenges. (5 Marks)

## Question 03 — 25 Marks

a. A small-to-medium-sized enterprise (SME) with multiple branch offices across Sri Lanka needs to establish a secure and reliable network connection between its headquarters and branches. The company is considering using a VPN (Virtual Private Network) solution to achieve this. (8 marks)

i. Above specific requirements of the SME, which VPN algorithm(s) and connection technology would be most suitable for their network?

ii. State your analysis and recommendations for the above customer's current need relating to VPN Technologies.

b. Considering the above SME’s increasing complexity and scale of their networks, what are the key advantages and disadvantages of using point-to-point VPNs for their network infrastructures? (8 marks)

c. In industry, the complexity of network environments, and the growing importance of user authentication, what are the key advantages and disadvantages of using AAA (Authentication, Authorization, and Accounting) solutions, and how can they be effectively implemented to enhance network security and user experience? (9 marks)

## Question 04 — 25 Marks

a. Given the increasing sophistication of cyber threats, how can a Cisco ASA be effectively configured to provide robust perimeter security for a large enterprise network?

i. Please ensure to evaluate your answer using, Firewall Rules, Intrusion Prevention Systems (IPS), VPN Tunnels, Content Filtering, Advance Threat Protection (ATP), High Availability, Monitoring, and Logging. (12 marks)

b. In a large University network, how can a DMZ (Demilitarized Zone) be effectively implemented to provide robust security and protect sensitive data while ensuring seamless connectivity for students, faculty, and staff? Discuss and evaluate the DMZ functions and their benefits. (8 marks)

c. Considering the evolving threat landscape and the intricate nature of contemporary networks, what are the key strategies and best practices for leveraging Cisco ASDM (Adaptive Security Device Manager) to enhance network security, streamline management, and optimize performance in large-scale enterprise environments? (5 marks)

~ End of question paper ~

---

# Simple English Answer Guide

## Question 01 Answer — Hybrid-Cloud Security (25 marks)

### i. Internal and external threats (10 marks)

**Internal threats**

- Privileged staff may misuse access or steal cloud data.
- Users may accidentally expose storage, keys or security groups.
- Weak passwords and excessive permissions can allow account misuse.
- Unpatched on-premise systems can become an entry point to the cloud.
- Shadow IT may place data in unapproved services.

**External threats**

- Phishing and credential theft can compromise cloud accounts.
- Internet-facing APIs/apps may suffer injection, authentication or software attacks.
- DDoS can make public/cloud services unavailable.
- Malware/ransomware can spread across connected environments.
- Data can be intercepted over insecure links; supply-chain/cloud-provider compromise is also possible.

### ii. Security strategies (10 marks)

- Use centralized identity, MFA, role-based least privilege and regular access reviews.
- Apply Zero Trust: authenticate every request and verify device condition.
- Encrypt data at rest and in transit; protect keys in KMS/HSM and rotate them.
- Connect environments with authenticated IPsec/private links and segment workloads using VPC/VNet, VLAN and firewall rules.
- Deploy NGFW/WAF, API protection, IDS/IPS and DDoS protection.
- Patch systems, scan vulnerabilities and harden cloud configurations using approved templates.
- Centralize cloud/on-premise logs in a SIEM; alert on unusual access.
- Maintain immutable backups and tested incident-response/DR plans.
- Use data classification, DLP, secure development and vendor-risk policies.

### iii. Effectiveness, limitations and solutions (5 marks)

- Many tools increase complexity; solve with centralized policy, automation and trained staff.
- Encryption/key management can fail through poor handling; use managed KMS/HSM, rotation and separation of duties.
- Security controls add cost/latency; prioritize by risk, test performance and scale controls.
- Multi-cloud tools differ; use common standards, infrastructure-as-code and continuous configuration checks.
- False alerts cause fatigue; tune rules and maintain incident playbooks.

The plan is effective because it provides preventive, detective and recovery controls across both environments.

## Question 02 Answer — Public Key Infrastructure (25 marks)

### i. PKI components and secure communication (10 marks)

- **Root CA:** Highest trust anchor; signs subordinate CA certificates and is normally kept offline.
- **Subordinate/issuing CA:** Issues certificates to users, servers and devices.
- **Registration Authority (RA):** Verifies the identity of certificate applicants.
- **Digital certificate:** Binds an identity/domain to a public key and is signed by a CA.
- **Public/private keys:** Public key can be shared; private key must remain secret.
- **Repository:** Publishes certificates and trust chains.
- **CRL/OCSP:** Shows whether a certificate has been revoked before expiry.
- **Policies/CPS:** Define identity checks, certificate use, lifetime and responsibilities.

Certificates support authentication. Public-key cryptography securely agrees/protects keys, digital signatures provide integrity and authenticity, and symmetric session encryption protects data efficiently.

### ii. Large-scale deployment and flow (10 marks)

```text
Offline Root CA
      |
      +---- Issuing CA for internal users/devices
      |
      +---- Issuing CA for external services/partners
```

1. Define certificate policy, algorithms, lifetimes and trust boundaries.
2. Protect the offline root and CA keys in HSMs; use redundant issuing CAs.
3. User/server creates a key pair locally and protects its private key.
4. It creates a Certificate Signing Request containing identity and public key.
5. RA verifies identity/authorization.
6. Issuing CA signs and returns the certificate and chain.
7. Automatically deploy certificates/trust anchors using MDM, directory or certificate-management tools.
8. During TLS, parties validate signature, hostname, dates, chain and revocation status.
9. They establish encrypted session keys and exchange protected data.
10. Inventory, monitor, renew and revoke certificates; publish CRL/OCSP updates and audit all CA activity.

### iii. Limitations and mitigations (5 marks)

- **Scalability:** Thousands of certificates are hard to track. Use automated enrollment, discovery, renewal and inventory.
- **Expiry/outage:** Expired certificates stop services. Alert early and auto-renew.
- **CA/private-key compromise:** It breaks trust. Use offline root, HSM, MFA, dual control and a tested compromise plan.
- **Revocation delay:** CRL/OCSP may be unavailable or stale. Use resilient responders, short-lived certificates and monitoring.
- **Third-party interoperability:** Different policies/formats/trust anchors. Use X.509 standards, cross-certification or controlled trust gateways and test integrations.

## Question 03 Answers — VPN and AAA (25 marks)

### a(i–ii) Suitable branch VPN (8 marks)

Use an **IPsec site-to-site VPN** between HQ and branch security gateways.

- IKEv2 for negotiation and authentication.
- AES-256-GCM for encryption plus integrity, or AES-256 with SHA-256.
- Diffie-Hellman group 14 or stronger/ECDH for key exchange.
- Certificates are more scalable than shared passwords; use strong PSKs only for very small deployments.
- Use broadband/fibre Internet with dual links where availability is important.
- A hub-and-spoke design is simple; DMVPN/SD-WAN can scale dynamic branches better.
- Apply routing, monitoring, QoS and failover; use Perfect Forward Secrecy and regular rekeying.

This provides confidentiality, integrity and peer authentication at a lower cost than private leased lines.

### b. Point-to-point VPN advantages/disadvantages (8 marks)

**Advantages**

- Strong encrypted link between two known sites.
- Simple policy and troubleshooting for a small number of branches.
- Lower cost than leased lines.
- Each tunnel can use specific routes and controls.

**Disadvantages**

- Full mesh requires `n(n−1)/2` tunnels and becomes difficult to manage.
- Adding/changing branches needs repeated configuration.
- Key/certificate rotation and monitoring grow with tunnel count.
- Hub-and-spoke may create bottlenecks and a hub failure affects all branches.
- Internet quality affects latency and availability.

For growth, use DMVPN/SD-WAN or centrally managed route-based IPsec with redundant hubs.

### c. AAA evaluation and implementation (9 marks)

**Authentication** verifies identity, **authorization** decides permitted actions, and **accounting** records activity.

**Advantages**

- Central accounts and consistent policy.
- Least-privilege roles and TACACS+ command authorization.
- Central logs support audits and incident investigation.
- Faster account revocation and MFA integration.

**Disadvantages**

- Server/network failure may block logins.
- Deployment and integration add cost and complexity.
- A compromised central server has large impact.
- Poor policy may frustrate users.

**Effective implementation**

- Use redundant TACACS+ for device administration and RADIUS for Wi-Fi/VPN access.
- Protect servers, use encrypted management paths and MFA.
- Define RBAC roles and least privilege; send accounting logs to SIEM.
- Keep tested local emergency access and monitor server health.
- Use SSO where suitable to improve user experience without removing MFA.

## Question 04 Answers — Cisco ASA, DMZ and ASDM (25 marks)

### a. Cisco ASA perimeter configuration (12 marks)

- Create security zones/interfaces: OUTSIDE, DMZ, INSIDE and management.
- Use default-deny ACLs; allow only required source, destination, protocol and port combinations.
- Configure NAT carefully and publish public services only through the DMZ.
- Enable IPS/signature inspection to block known exploits and anomalies.
- Configure site-to-site IPsec and remote-access VPNs with strong algorithms, certificates and MFA.
- Use URL/content filtering and malware controls through supported security services.
- Integrate Advanced Threat Protection/sandboxing to analyse suspicious files.
- Deploy two ASAs in failover/high-availability mode with synchronized configuration/state.
- Restrict management to a dedicated network using SSH/HTTPS, MFA/AAA and trusted hosts.
- Send logs to syslog/SIEM, enable NTP, monitor sessions/interface health and alert on threats.
- Patch ASA/ASDM, back up configurations and review rules regularly.
- Test failover, VPN, IPS and recovery without disrupting production.

### b. University DMZ (8 marks)

```text
Internet → Perimeter firewall → DMZ (web, DNS, mail, VPN)
                              → Internal firewall/core
                                 ├─ Student network
                                 ├─ Staff/faculty network
                                 └─ Sensitive admin/research systems
```

- Place Internet-facing services in the DMZ, not the internal network.
- Allow Internet-to-DMZ only on required ports.
- Deny direct Internet-to-internal access.
- Permit tightly controlled DMZ-to-internal flows only when necessary.
- Separate student, staff and sensitive systems using VLANs/zones and least privilege.
- Add WAF/IPS, hardened servers, patching, EDR and centralized logs.
- Use redundant firewalls/links and backups for availability.

The DMZ contains a public-server compromise, reduces attack surface and still lets students/staff reach approved services.

### c. ASDM strategies and best practices (5 marks)

- Use ASDM dashboards and real-time monitoring to view connections, VPNs, threats and performance.
- Use object groups and clearly named rules to reduce duplication and mistakes.
- Apply least-privilege ACL/NAT changes through change control; review packet-tracer results before deployment.
- Restrict ASDM to trusted management hosts, HTTPS, AAA/MFA and supported software versions.
- Back up/export configurations before changes and keep audit logs.
- Remove shadowed/unused rules, tune inspection/logging and monitor CPU, memory and interface use.
- For many devices, use centralized management/orchestration rather than separate manual ASDM changes.

~ End of answer guide ~
