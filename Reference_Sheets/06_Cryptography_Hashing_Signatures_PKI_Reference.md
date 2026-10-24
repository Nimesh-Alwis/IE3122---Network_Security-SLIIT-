<style>@page{size:A4 landscape;margin:4mm}body{font-size:5pt;line-height:1.04;column-count:2;column-gap:4mm}h1,h2{column-span:all;margin:2px 0}table{width:100%;border-collapse:collapse;break-inside:avoid}th,td{border:0;padding:1px 2px;vertical-align:top}th{background:#ddd}p{margin:2px 0}code{font-size:4.5pt}</style>

# IE3122 Reference 06 — Cryptography, Hashing, Signatures & PKI

## Principles and cipher families

| Concept | Exam-ready fact |
|---|---|
| Kerckhoffs | System remains secure when algorithm/design is public; only key must be secret. Public scrutiny, replaceable keys and no “security by obscurity.” |
| Confusion / diffusion | Hide relationship key↔ciphertext / spread one plaintext bit across many ciphertext bits (avalanche). |
| Caesar | `C=(P+k) mod 26`; only 26 shifts → brute force. NETWORK +5 = `SJYBTW P` without the space: `SJYBTWP`. |
| Vigenère | Repeating-key polyalphabetic substitution masks simple single-letter frequencies, but periodicity/key reuse enables Kasiski/frequency attacks. |
| Symmetric | Same secret encrypts/decrypts; fast for bulk data, but secure key distribution/scale is hard. Pairwise keys for `n` users=`n(n−1)/2`; n=200→19,900. Does not alone give non-repudiation. |
| Asymmetric | Public/private key pair; enables key agreement/encryption/signatures; easier identity-scale but slower/larger. RSA depends on factoring; ECC gives comparable security with smaller keys—good constrained signer. |
| Hybrid | Authenticate/key-agree asymmetrically → encrypt application data with fast symmetric session keys. Do not bulk-encrypt VPN data directly with RSA. |
| Diffie–Hellman | Parties exchange public values and derive same secret without sending it. Unaunthenticated DH is MITM-vulnerable; bind exchange using signatures/certificates/PSK. Ephemeral DH gives forward secrecy. |

## Block/stream and modes

| Choice | Operation / property | Failure / correct use |
|---|---|---|
| Block cipher | Fixed blocks; modes handle long data; often padding | AES is standard primitive; mode/nonce/authentication determine security |
| Stream cipher | Keystream XOR plaintext; no padding; low latency; error often affects corresponding bits | Never reuse key+nonce/keystream; reuse gives `C1 XOR C2 = P1 XOR P2` (WEP lesson) |
| ECB | Each block independently under same key | Equal plaintext blocks→equal ciphertext patterns; unsuitable for structured/long data |
| CBC | Each plaintext block XOR previous ciphertext; random unpredictable IV; padding | Hides repeated patterns; sequential; padding-oracle risk unless authenticated |
| CTR | Encrypt nonce+counter to create keystream; parallel/no padding | Nonce/counter must never repeat with same key; malleable without MAC |
| GCM | CTR-like encryption + authentication tag (AEAD) | Confidentiality+integrity; unique nonce mandatory |
| Disk / voice / low-end TLS | Disk→AES-XTS; real-time voice→authenticated stream/AEAD; low-end without AES acceleration→ChaCha20-Poly1305 | Justify using random access, latency, hardware and integrity need |

## Hash, MAC, signature

| Primitive | Key? | Guarantees / use | Does not guarantee |
|---|---|---|---|
| Cryptographic hash | No | Fixed digest, preimage/second-preimage/collision resistance, avalanche; file comparison | Sender identity/authenticity: attacker can replace message and hash |
| HMAC/MAC | Shared secret | Integrity + origin authentication among key holders; IPsec peer packet protection | Non-repudiation: either key holder could generate it |
| Digital signature | Sign private key; verify public key | Integrity, origin authentication, supports non-repudiation when identity/key governance trusted | Confidentiality; truth of content; safety of endpoint; identity if public key is not validated |

Second preimage: given `m`, find different `m'` with same hash. Collision: find any two distinct messages with same hash; ideal work roughly `2^(n/2)` due birthday effect. MD5/SHA-1 collision-broken; prefer SHA-256/SHA-3 family as required.

**Password storage:** unsalted fast SHA-256 permits identical-hash correlation, dictionary/brute force and precomputed tables. Use unique random salt + deliberately slow memory-hard password KDF (Argon2id; alternatively approved bcrypt/scrypt/PBKDF2 parameters), store parameters/salt/hash; optional server-side pepper. Salt defeats precomputation, not guessing.

**Signing:** hash message → sign digest with sender private key → send message+signature. Verify by hashing received message and verifying signature using validated sender public key. Digest makes signing efficient/fixed-size. Success proves signature matches message/key, not that claims are true or private key was never stolen.

## Certificates and PKI

Certificate binds subject identity/name to public key and includes issuer, serial, validity, extensions/key usage and CA signature. Trust chain: leaf → intermediate(s) → locally trusted root. Root kept highly protected/offline; intermediates issue leaves and limit blast radius. Root compromise undermines all descendant trust; intermediate compromise can be revoked/replaced within its scope.

| Browser/client check | Prevents/detects |
|---|---|
| Chain signatures to trusted root | Forged/untrusted issuer |
| Hostname in SAN matches requested host | Valid cert used for wrong site/MITM |
| Current time within validity | Expired/not-yet-valid credential |
| Key Usage / Extended Key Usage / constraints | Key or CA used outside authorized purpose |
| Revocation via OCSP/CRL where policy enforces | Known compromised/withdrawn cert |
| Algorithm/key strength and certificate transparency/pinning policy | Weak signatures, mis-issuance visibility |

DV proves domain control, not business legitimacy; appropriate public TLS baseline. Self-signed provides encryption but no public third-party identity unless fingerprint/root is securely pre-trusted—reasonable controlled lab/internal environment. Publishing file+hash on same compromised page offers little authenticity; sign release or publish digest through independently authenticated channel.

| CRL | OCSP |
|---|---|
| Download periodic signed revoked-serial list; cache/offline possible, can be large/stale | Query status per certificate; fresher/smaller but privacy, latency and responder availability; stapling helps |

Revocation is a weak point because clients may soft-fail when responder is unavailable and status propagates imperfectly. DigiNotar (2011) issued fraudulent certificates after CA compromise; demonstrated one trusted CA can endanger global names, accelerating removal/auditing and Certificate Transparency-style defenses.

## TLS 1.3 primitive map

| Need | Primitive |
|---|---|
| Agree fresh session secret | (EC)DHE key agreement |
| Bind server identity to public key | CA-signed certificate |
| Prove possession of certificate private key | Digital signature over handshake transcript |
| Confirm handshake integrity/key possession | Finished MAC over transcript |
| Protect application records | Symmetric AEAD (AES-GCM or ChaCha20-Poly1305) |

## Cisco certificate enrollment order

Practical dependency: set identity/domain and generate RSA key pair → create/configure trustpoint (enrollment URL, subject, revocation policy) → authenticate CA (verify/import CA certificate) → enroll/request device certificate. Some IOS workflows define the trustpoint before key generation/association; invariant is that a key pair and authenticated CA trust exist before successful enrollment. `revocation-check none` is acceptable only for an isolated lab because revoked credentials remain trusted.
