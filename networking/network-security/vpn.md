# VPN (Virtual Private Network)

## Why VPNs Exist

Data often travels across untrusted networks.

Example:

```text
Home Network
     ↓
Public Internet
     ↓
Corporate Network
```

Question:

```text
How Can Data Travel
Securely Across
Public Networks?
```

VPNs solve this problem.

---

## What Is A VPN?

VPN stands for:

```text
Virtual Private Network
```

Purpose:

```text
Create Secure
Encrypted Communication
Across Public Networks
```

A VPN creates a protected tunnel between systems.

---

## The Engineering Problem

Suppose an employee works remotely.

Without a VPN:

```text
Laptop
   ↓
Internet
   ↓
Corporate Systems
```

Sensitive traffic may be exposed.

A VPN encrypts the connection.

---

## High-Level VPN Flow

```text
Remote User
      ↓
Encrypted Tunnel
      ↓
VPN Gateway
      ↓
Corporate Network
```

Traffic remains protected while traversing the Internet.

---

## VPN Tunnel

A VPN creates a logical tunnel.

```text
User Traffic
      ↓
Encryption
      ↓
Secure Tunnel
      ↓
Destination
```

Anyone observing the network sees encrypted data.

---

## Core Security Benefits

### Confidentiality

Protects data from being read.

---

### Integrity

Protects data from tampering.

---

### Authentication

Verifies trusted participants.

---

## Common VPN Types

### Remote Access VPN

Connects individual users.

Example:

```text
Employee
    ↓
Corporate Network
```

Very common for remote work.

---

### Site-To-Site VPN

Connects entire networks.

Example:

```text
Office A
    ↓
VPN Tunnel
    ↓
Office B
```

Common for enterprises.

---

### Client-To-Site VPN

A device connects directly to a VPN gateway.

Often used by remote employees.

---

## Common VPN Technologies

Examples:

- IPsec
- OpenVPN
- WireGuard
- SSL VPN

Widely used in production environments.

---

## VPN vs HTTPS

HTTPS:

```text
Protects Application Traffic
```

VPN:

```text
Protects Network Traffic
```

They solve different problems and are often used together.

---

## Production Usage

VPNs are common in:

- Remote work environments
- Enterprise networks
- Cloud connectivity
- Hybrid cloud architectures
- Secure administration
- Partner network integration

---

## Common Production Failures

### Authentication Failure

Symptoms:

- User cannot connect

### Tunnel Failure

Symptoms:

- Connectivity lost

### Routing Issues

Symptoms:

- Resources unreachable

### Performance Problems

Symptoms:

- High latency
- Slow transfers

---

## Cloud Relevance

VPNs are commonly used for:

```text
On-Premises
      ↓
VPN
      ↓
Cloud Network
```

Common in hybrid cloud environments.

---

## Common Interview Questions

- What is a VPN?
- Why are VPNs needed?
- Site-to-site vs remote access VPN?
- VPN vs HTTPS?
- What is a VPN tunnel?
- What security benefits does a VPN provide?
- What is IPsec?
- When would you use a VPN in cloud environments?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| VPN | Secure Network Tunnel |
| Tunnel | Encrypted Communication Path |
| Remote Access VPN | User To Network |
| Site-To-Site VPN | Network To Network |
| IPsec | Common VPN Technology |
| WireGuard | Modern VPN Protocol |
| Confidentiality | Protect Data |
| Authentication | Verify Identity |
| Cloud Usage | Hybrid Connectivity |
| Core Goal | Secure Communication Across Public Networks |
