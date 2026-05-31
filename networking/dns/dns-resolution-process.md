

# DNS Resolution Process

## Why DNS Resolution Matters

DNS is one of the first operations performed when accessing a website, API, or cloud service.

Before communication begins:

```text
Domain Name
      ↓
IP Address
```

must be resolved.

Understanding DNS resolution is critical for troubleshooting modern systems.

---

## The Engineering Problem

A user enters:

```text
https://www.example.com
```

The browser cannot communicate using:

```text
www.example.com
```

It needs:

```text
IP Address
```

Question:

```text
How Is The IP Address Found?
```

The DNS Resolution Process answers this question.

---

## High-Level Flow

```text
User
 ↓
Browser
 ↓
DNS Resolver
 ↓
Root Server
 ↓
TLD Server
 ↓
Authoritative DNS Server
 ↓
IP Address Returned
 ↓
Application Connection
```

---

## Step 1: Browser Cache Check

The browser first checks:

```text
Local DNS Cache
```

Question:

```text
Do We Already Know The IP?
```

If found:

```text
Use Cached Result
```

No DNS query is needed.

---

## Step 2: Operating System Cache Check

If the browser cache misses:

```text
Operating System DNS Cache
```

is checked.

Examples:

- Linux
- Windows
- macOS

If found:

```text
Use Cached Result
```

---

## Step 3: Query Recursive Resolver

If no cache exists:

```text
DNS Resolver
```

is queried.

Examples:

- ISP DNS
- Enterprise DNS
- Public DNS

Common Public DNS:

```text
8.8.8.8
1.1.1.1
```

---

## Step 4: Root Server Lookup

If the resolver does not know the answer:

It asks a Root DNS Server.

Question:

```text
Who Handles .com?
```

The root server responds with:

```text
TLD Server Information
```

---

## Step 5: TLD Server Lookup

The resolver contacts:

```text
.com TLD Server
```

Question:

```text
Who Handles example.com?
```

Response:

```text
Authoritative DNS Server
```

---

## Step 6: Authoritative DNS Lookup

The resolver contacts:

```text
Authoritative DNS Server
```

Question:

```text
What Is The IP For
www.example.com?
```

Response:

```text
IP Address
```

This is the final answer.

---

## Step 7: Response Returned

The resolver returns:

```text
IP Address
```

to the client.

The result is cached according to:

```text
TTL
```

for future requests.

---

## Complete DNS Resolution Flow

```text
Browser Cache
      ↓
OS Cache
      ↓
Recursive Resolver
      ↓
Root Server
      ↓
TLD Server
      ↓
Authoritative Server
      ↓
IP Address
      ↓
Client
```

---

## Why Caching Is Important

Without caching:

```text
Every Request
      ↓
Full DNS Resolution
```

This would increase:

- Latency
- DNS traffic
- Infrastructure load

Caching dramatically improves performance.

---

## Typical DNS Protocol Usage

Most DNS queries use:

```text
UDP Port 53
```

Sometimes:

```text
TCP Port 53
```

is used for:

- Large responses
- Zone transfers

---

## Production Impact

DNS resolution affects:

- Websites
- APIs
- Cloud services
- Kubernetes service discovery
- Load balancers
- CDNs

A DNS resolution failure can make healthy systems appear unavailable.

---

## Common Production Failures

### Resolver Failure

Symptoms:

- Name resolution errors

### Incorrect DNS Records

Symptoms:

- Traffic reaches wrong destination

### Expired Cache

Symptoms:

- Increased lookup latency

### Authoritative DNS Failure

Symptoms:

- Domain unavailable

---

## Useful Commands

```bash
dig example.com
```

```bash
dig example.com +trace
```

```bash
nslookup example.com
```

```bash
host example.com
```

---

## Common Interview Questions

- How does DNS resolution work?
- What happens when you enter a URL?
- What is a Recursive Resolver?
- What is an Authoritative DNS Server?
- Why are Root Servers needed?
- Why is caching important?
- Why does DNS usually use UDP?
- When does DNS use TCP?

---

## Quick Revision

| Component | Responsibility |
|----------|----------|
| Browser Cache | First Lookup Layer |
| OS Cache | Local Cache |
| Resolver | Performs Lookup |
| Root Server | TLD Discovery |
| TLD Server | Domain Discovery |
| Authoritative Server | Final Answer |
| TTL | Cache Lifetime |
| UDP 53 | Most DNS Queries |
| TCP 53 | Large Responses/Transfers |
| Core Goal | Domain To IP Resolution |