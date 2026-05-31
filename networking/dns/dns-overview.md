

# DNS Overview

## Why DNS Exists

Humans remember names better than numbers.

Example:

```text
openai.com
```

is easier to remember than:

```text
104.18.x.x
```

Computers communicate using IP addresses.

Humans prefer domain names.

DNS exists to bridge this gap.

---

## The Engineering Problem

Suppose a user opens:

```text
https://example.com
```

The browser cannot communicate using the domain name.

It first needs:

```text
IP Address
```

Question:

```text
How Does The Browser Find The Correct IP?
```

DNS solves this problem.

---

## What Is DNS?

DNS stands for:

```text
Domain Name System
```

Purpose:

```text
Domain Name
      ↓
IP Address
```

DNS is often called:

```text
The Phonebook Of The Internet
```

---

## Simple DNS Example

User enters:

```text
www.google.com
```

DNS returns:

```text
142.250.x.x
```

Browser then communicates using the returned IP address.

---

## Why DNS Is Critical

Without DNS:

```text
Every Website
Every API
Every Service
```

would require users to remember IP addresses.

Modern Internet services depend heavily on DNS.

---

## High-Level DNS Flow

```text
User
 ↓
Browser
 ↓
DNS Resolver
 ↓
DNS Servers
 ↓
IP Address Returned
 ↓
Application Connection
```

This process usually completes in milliseconds.

---

## DNS Is A Distributed System

DNS is not a single server.

It consists of:

- Recursive Resolvers
- Root Servers
- TLD Servers
- Authoritative Servers

This architecture allows DNS to scale globally.

---

## Common DNS Components

### DNS Resolver

Receives queries from clients.

Examples:

- ISP DNS
- Enterprise DNS
- Public DNS

### Root Servers

Top level of the DNS hierarchy.

### TLD Servers

Examples:

```text
.com
.org
.net
.io
```

### Authoritative Servers

Store the actual DNS records and provide final answers.

---

## Common DNS Uses

- Website access
- API communication
- Service discovery
- Cloud platforms
- Kubernetes networking
- Email routing
- Load balancing

---

## Production Impact

DNS failures can cause:

- Website outages
- API failures
- Service discovery failures
- Kubernetes issues
- Cloud connectivity problems

Many major incidents ultimately trace back to DNS.

---

## Useful Commands

```bash
dig google.com
```

```bash
nslookup google.com
```

```bash
host google.com
```

---

## Common Interview Questions

- What is DNS?
- Why does DNS exist?
- How does DNS resolution work?
- What are Root Servers?
- What are Authoritative DNS Servers?
- Why is DNS critical?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| DNS | Domain To IP Mapping |
| Resolver | Performs DNS Lookup |
| Root Server | Top Of DNS Hierarchy |
| TLD Server | Domain Category Lookup |
| Authoritative Server | Final DNS Answer |
| Common Protocol | Usually UDP |
| Core Purpose | Find IP From Domain Name |