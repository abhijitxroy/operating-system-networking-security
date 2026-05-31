

# TLS SSL Handshake

## Why TLS Exists

HTTP sends data in plain text.

Without encryption:

```text
Client
   ↓
Internet
   ↓
Server
```

Sensitive information may be exposed.

Examples:

- Passwords
- Session cookies
- Banking information
- API tokens

TLS was created to secure communication.

---

## What Is TLS?

TLS stands for:

```text
Transport Layer Security
```

Purpose:

- Encryption
- Authentication
- Integrity Protection

TLS is the security layer behind HTTPS.

---

## What Is The TLS Handshake?

Before encrypted communication begins:

```text
Client
   ↔
Server
```

must agree on:

- Encryption algorithms
- Session keys
- Server identity

This negotiation process is called the TLS Handshake.

---

## High-Level TLS Flow

```text
Client Hello
      ↓
Server Hello
      ↓
Certificate Exchange
      ↓
Key Exchange
      ↓
Session Key Creation
      ↓
Secure Communication
```

---

## Step 1: Client Hello

The client starts communication.

Provides:

- Supported TLS versions
- Supported cipher suites
- Random value

Example:

```text
I Support TLS 1.3
```

---

## Step 2: Server Hello

The server responds.

Provides:

- Selected TLS version
- Selected cipher suite
- Server random value

Example:

```text
Let's Use TLS 1.3
```

---

## Step 3: Certificate Exchange

The server sends:

```text
Digital Certificate
```

The certificate contains:

- Server identity
- Public key
- Certificate authority information

---

## Step 4: Certificate Validation

The client validates:

- Certificate chain
- Expiration date
- Domain name
- Trusted CA

If validation fails:

```text
TLS Handshake Failure
```

---

## Step 5: Key Exchange

Client and server establish shared cryptographic secrets.

Goal:

```text
Create Shared Session Key
```

without exposing it over the network.

---

## Step 6: Session Key Creation

Both sides independently derive:

```text
Same Session Key
```

This key is used for encryption.

---

## Step 7: Secure Communication

Once the handshake completes:

```text
HTTPS Traffic
      ↓
Encrypted
```

Application data can now be exchanged securely.

---

## SSL vs TLS

| Feature | SSL | TLS |
|----------|----------|----------|
| Status | Deprecated | Current Standard |
| Security | Weak | Strong |
| Modern Usage | No | Yes |

Although people often say:

```text
SSL Certificate
```

modern systems actually use TLS.

---

## TLS Security Goals

### Confidentiality

Protect data from eavesdropping.

### Integrity

Prevent tampering.

### Authentication

Verify server identity.

---

## Production Impact

TLS protects:

- Banking systems
- E-commerce platforms
- APIs
- SaaS applications
- Cloud services

Nearly every modern Internet service depends on TLS.

---

## Common Production Failures

### Expired Certificate

Symptoms:

- Browser warnings
- Connection failures

### Invalid Certificate

Symptoms:

- Certificate trust errors

### TLS Version Mismatch

Symptoms:

- Handshake failure

### Incorrect Certificate Configuration

Symptoms:

- HTTPS unavailable

---

## Useful Commands

```bash
openssl s_client -connect example.com:443
```

```bash
curl -v https://example.com
```

Useful for TLS troubleshooting.

---

## Common Interview Questions

- What is TLS?
- What is the TLS handshake?
- Why are certificates needed?
- SSL vs TLS?
- What is a Certificate Authority?
- How is a session key created?
- Why is HTTPS secure?
- What happens if certificate validation fails?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| TLS | Secure Transport Layer |
| Handshake | Security Negotiation |
| Client Hello | Supported Capabilities |
| Server Hello | Selected Configuration |
| Certificate | Identity Verification |
| Key Exchange | Shared Secret Creation |
| Session Key | Encrypt Traffic |
| Confidentiality | Prevent Reading |
| Integrity | Prevent Modification |
| Authentication | Verify Identity |