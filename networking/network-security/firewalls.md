

# Firewalls

## Why Firewalls Exist

Not all network traffic should be allowed.

Example:

```text
Internet
    ↓
Application Server
```

Question:

```text
How Do We Control
Which Traffic Is Allowed
And Which Traffic Is Blocked?
```

Firewalls solve this problem.

---

## What Is A Firewall?

A firewall is a security device or software that monitors and controls network traffic.

Purpose:

```text
Incoming Traffic
       ↓
Allow Or Deny
       ↓
Protected Network
```

Firewalls enforce security policies.

---

## The Engineering Problem

Suppose a web server should accept:

```text
HTTPS (443)
```

but should block:

```text
SSH (22)
From The Internet
```

Question:

```text
How Is This Enforced?
```

Firewall rules provide the answer.

---

## High-Level Architecture

```text
Internet
    ↓
Firewall
    ↓
Application Servers
```

All traffic passes through the firewall.

---

## Firewall Rules

Rules determine whether traffic is:

```text
Allow
or
Deny
```

Example:

```text
Allow TCP 443
Deny TCP 22
```

Rules are evaluated in order.

---

## Packet Filtering Firewall

Uses:

- Source IP
- Destination IP
- Port
- Protocol

Example:

```text
Allow HTTPS
Block Telnet
```

Simple and efficient.

---

## Stateful Firewall

Tracks connection state.

Example:

```text
Request Sent
      ↓
Response Allowed
```

More intelligent than basic packet filtering.

Common in modern networks.

---

## Application Firewall

Inspects application-layer traffic.

Examples:

- HTTP
- HTTPS
- APIs

Can detect application attacks.

---

## Network Firewall vs Host Firewall

### Network Firewall

Protects multiple systems.

```text
Internet
   ↓
Firewall
   ↓
Servers
```

### Host Firewall

Runs on an individual machine.

Examples:

- iptables
- nftables
- Windows Firewall

---

## Default Policies

Common approaches:

### Default Deny

```text
Block Everything
Unless Explicitly Allowed
```

Preferred for security.

### Default Allow

```text
Allow Everything
Unless Explicitly Blocked
```

Generally less secure.

---

## Production Usage

Firewalls are critical for:

- Data centers
- Cloud environments
- Kubernetes clusters
- Corporate networks
- Public APIs
- Internet-facing services

Nearly every production environment uses firewalls.

---

## Common Production Failures

### Missing Rule

Symptoms:

- Service unreachable

### Incorrect Rule Order

Symptoms:

- Unexpected traffic blocks

### Overly Permissive Rules

Symptoms:

- Security exposure

### Firewall Drift

Symptoms:

- Inconsistent environments

---

## Common Commands

Linux:

```bash
iptables -L
```

```bash
nft list ruleset
```

```bash
ufw status
```

Useful for firewall troubleshooting.

---

## Common Interview Questions

- What is a firewall?
- Why are firewalls needed?
- Packet filtering vs stateful firewall?
- Network firewall vs host firewall?
- What is default deny?
- Why is rule order important?
- How do firewalls improve security?
- What ports should be exposed publicly?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Firewall | Traffic Control |
| Rule | Allow Or Deny Traffic |
| Packet Filtering | IP/Port Based Filtering |
| Stateful Firewall | Tracks Connections |
| Application Firewall | Application-Aware Inspection |
| Network Firewall | Protects Multiple Systems |
| Host Firewall | Protects Single Host |
| Default Deny | Most Secure Approach |
| Common Failure | Incorrect Rule Configuration |
| Core Goal | Reduce Attack Surface |