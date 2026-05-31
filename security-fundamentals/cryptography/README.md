

# Cryptography

## Why Cryptography Exists

Humans have needed secure communication for centuries.

The fundamental problem has always been the same:

```text
How Can Information Travel Through Untrusted Environments?
```

As systems became connected through networks and the internet, protecting data became a critical engineering requirement.

Cryptography was developed to provide confidentiality, integrity, authentication and trust.

---

## The Engineering Problem

Modern systems constantly exchange sensitive information.

Examples:

- Passwords
- Financial transactions
- Personal information
- API communications
- Cloud credentials
- Database connections

Without cryptography:

```text
Data Sent
     ↓
Network
     ↓
Anyone Can Read Or Modify It
```

Cryptography protects information even when the communication channel cannot be trusted.

---

## Security Goals Of Cryptography

Cryptography exists to provide several guarantees.

### Confidentiality

Only authorized parties can read data.

### Integrity

Data cannot be modified without detection.

### Authentication

Verify identity.

### Non-Repudiation

Prevent denial of performed actions.

These goals form the foundation of modern security systems.

---

## Symmetric Encryption

Uses the same key for:

- Encryption
- Decryption

```text
Shared Secret Key
      ↓
Encrypt
      ↓
Decrypt
```

Benefits:

- Fast
- Efficient
- Suitable for large data volumes

Challenge:

- Secure key distribution

Examples:

- AES
- ChaCha20

---

## Asymmetric Encryption

Uses two keys.

```text
Public Key
Private Key
```

Benefits:

- Solves key exchange challenges
- Enables digital signatures

Tradeoff:

- Slower than symmetric encryption

Examples:

- RSA
- ECC

---

## Hashing

Hashing is different from encryption.

Purpose:

```text
Input
   ↓
Hash Function
   ↓
Fixed-Length Output
```

Characteristics:

- One-way operation
- Integrity verification
- Password storage support

Examples:

- SHA-256
- SHA-512

Passwords should be hashed, not encrypted.

---

## Digital Signatures

Digital signatures provide:

- Authenticity
- Integrity
- Non-repudiation

Common usage:

- Software signing
- Certificates
- Secure communication

Modern software supply chains depend heavily on digital signatures.

---

## TLS And Modern Communication

Most internet communication depends on cryptography.

Examples:

- HTTPS
- APIs
- Cloud services
- Kubernetes communication
- Banking systems

TLS combines:

- Encryption
- Authentication
- Integrity protection

Without TLS, modern internet security would be impossible.

---

## Production Impact

Cryptography directly affects:

- Customer trust
- Regulatory compliance
- Cloud security
- Identity systems
- Financial systems
- Software supply chains

Many security incidents originate from poor cryptographic implementation rather than algorithm weaknesses.

---

## Common Production Failures

### Hardcoded Secrets

Symptoms:

- Credential exposure
- Unauthorized access

### Weak Algorithms

Symptoms:

- Compliance failures
- Security findings

### Expired Certificates

Symptoms:

- Service outages
- TLS failures

### Improper Key Management

Symptoms:

- Data exposure
- Compromised systems

### Weak Password Storage

Symptoms:

- Credential compromise

---

## Security Investigation Mindset

```text
Identify Asset
      ↓
Identify Data Flow
      ↓
Identify Trust Boundary
      ↓
Review Encryption
      ↓
Review Key Management
      ↓
Determine Risk
```

Cryptography should be evaluated as part of the overall system design.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Strong Encryption | Increased Computational Cost |
| Long Key Lengths | Performance Impact |
| Better Security | Operational Complexity |
| Frequent Key Rotation | Administrative Overhead |
| Strong Authentication | User Experience Friction |

---

## Interview Thinking

- Why was cryptography invented?
- Encryption vs Hashing?
- Symmetric vs Asymmetric Encryption?
- Why are passwords hashed instead of encrypted?
- What problem does TLS solve?
- Why is key management difficult?
- What causes certificate-related outages?
- How would you secure sensitive data in transit?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Cryptography | Protect Information |
| Confidentiality | Prevent Unauthorized Reading |
| Integrity | Detect Modification |
| Authentication | Verify Identity |
| AES | Symmetric Encryption |
| RSA | Asymmetric Encryption |
| Hashing | One-Way Transformation |
| Digital Signature | Authenticity Verification |
| TLS | Secure Communication |
| Key Management | Foundation Of Cryptographic Security |