

# HTTPS Overview

## Why HTTPS Exists

HTTP sends data in plain text.

Problem:

```text
Client
   ↓
Network
   ↓
Server
```

Anyone capable of intercepting traffic may be able to read the data.

Examples:

- Passwords
- Credit card information
- Session cookies
- Personal information

HTTPS was created to secure communication.

---

## The Engineering Problem

Suppose a user logs into:

```text
https://bank.com
```

Without encryption:

```text
Username
Password
Session Data
```

could potentially be exposed during transmission.

Question:

```text
How Can Client And Server
Communicate Securely?
```

HTTPS solves this problem.

---

## What Is HTTPS?

HTTPS stands for:

```text
HyperText Transfer Protocol Secure
```

HTTPS is:

```text
HTTP
  +
TLS
```

HTTP provides communication.

TLS provides security.

---

## High-Level HTTPS Flow

```text
Client
   ↓
TLS Handshake
   ↓
Secure Connection
   ↓
HTTP Requests
   ↓
HTTP Responses
```

Communication becomes encrypted.

---

## Core Security Goals

### Confidentiality

Protects data from unauthorized viewing.

### Integrity

Ensures data is not modified during transmission.

### Authentication

Verifies the identity of the server.

These are the primary goals of HTTPS.

---

## TLS Certificates

Servers present a digital certificate.

Example:

```text
example.com
      ↓
Certificate
```

The certificate helps prove:

```text
Server Identity
```

---

## Certificate Authorities (CA)

Certificates are issued by trusted authorities.

Examples:

- Public Certificate Authorities
- Enterprise Certificate Authorities

Browsers trust approved certificate authorities.

---

## HTTPS Ports

Default ports:

```text
HTTP  → Port 80
HTTPS → Port 443
```

Port 443 is the standard HTTPS port.

---

## HTTPS Request Example

```text
Browser
   ↓
TLS Handshake
   ↓
Encrypted HTTP Request
   ↓
Encrypted HTTP Response
```

The underlying HTTP communication remains the same.

Only the transport becomes secure.

---

## Why HTTPS Matters

HTTPS protects:

- Authentication credentials
- User sessions
- API traffic
- Financial transactions
- Personal information

Modern applications should always use HTTPS.

---

## Production Impact

HTTPS is required for:

- Banking systems
- E-commerce platforms
- SaaS applications
- APIs
- Cloud platforms
- Mobile applications

Many browser features require HTTPS.

---

## Common Production Failures

### Expired Certificate

Symptoms:

- Browser warnings
- Connection failures

### Invalid Certificate

Symptoms:

- Certificate trust errors

### TLS Misconfiguration

Symptoms:

- Handshake failures

### Mixed Content

Symptoms:

- Browser security warnings

---

## HTTP vs HTTPS

| Feature | HTTP | HTTPS |
|----------|----------|----------|
| Encryption | No | Yes |
| Integrity Protection | No | Yes |
| Authentication | No | Yes |
| Default Port | 80 | 443 |
| Security | Low | High |
| Production Usage | Rare | Standard |

---

## Common Interview Questions

- What is HTTPS?
- Why was HTTPS created?
- HTTP vs HTTPS?
- What is TLS?
- Why are certificates needed?
- What is a Certificate Authority?
- Why is HTTPS important?
- What happens when a certificate expires?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| HTTPS | HTTP + TLS |
| Confidentiality | Encryption |
| Integrity | Prevent Modification |
| Authentication | Verify Identity |
| Certificate | Server Identity Proof |
| CA | Trusted Certificate Issuer |
| HTTP Port | 80 |
| HTTPS Port | 443 |
| Common Failure | Expired Certificate |
| Core Goal | Secure Communication |