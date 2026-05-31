

# Recursive vs Authoritative DNS

## Why This Topic Matters

A DNS lookup involves multiple DNS servers.

A common interview question is:

```text
Recursive DNS
        vs
Authoritative DNS
```

Understanding the difference is essential for troubleshooting DNS issues and designing Internet-scale systems.

---

## The Engineering Problem

Suppose a user requests:

```text
www.example.com
```

Questions:

```text
Who Searches For The Answer?

Who Owns The Answer?
```

These responsibilities belong to different DNS components.

---

## What Is Recursive DNS?

A Recursive DNS Server performs lookups on behalf of clients.

Role:

```text
Find The Answer
```

The client asks:

```text
What Is The IP Address
For www.example.com?
```

The recursive resolver performs all required DNS queries.

---

## Recursive DNS Responsibilities

- Receive client requests
- Query DNS hierarchy
- Cache results
- Return final answers
- Reduce DNS lookup latency

Examples:

- ISP DNS
- Enterprise DNS
- Public DNS

---

## Common Recursive DNS Providers

```text
Google DNS
8.8.8.8

Cloudflare DNS
1.1.1.1
```

These services act as recursive resolvers.

---

## What Is Authoritative DNS?

An Authoritative DNS Server owns DNS records.

Role:

```text
Provide The Final Answer
```

Example:

```text
example.com
      ↓
Authoritative Server
```

Stores:

- A Records
- AAAA Records
- MX Records
- TXT Records
- CNAME Records

---

## Authoritative DNS Responsibilities

- Store DNS records
- Answer DNS queries
- Manage domain data
- Provide official DNS responses

Authoritative servers do not normally perform recursive lookups.

---

## High-Level Resolution Flow

```text
Client
  ↓
Recursive Resolver
  ↓
Root Server
  ↓
TLD Server
  ↓
Authoritative Server
  ↓
Answer Returned
```

---

## Example Resolution

User requests:

```text
api.company.com
```

Recursive Resolver:

```text
Find The Answer
```

Authoritative Server:

```text
Return The Official Record
```

Response:

```text
10.0.0.10
```

---

## Recursive vs Authoritative DNS

| Feature | Recursive DNS | Authoritative DNS |
|----------|----------|----------|
| Purpose | Find Answer | Own Answer |
| Stores Domain Records | No | Yes |
| Performs Lookups | Yes | No |
| Caching | Yes | Usually Limited |
| Client Facing | Yes | Indirectly |
| Example | 8.8.8.8 | Domain DNS Provider |

---

## Why Caching Exists In Recursive DNS

Without caching:

```text
Every Query
      ↓
Full DNS Resolution
```

Caching reduces:

- Latency
- DNS traffic
- Infrastructure load

This is one of the primary jobs of recursive resolvers.

---

## Production Impact

Engineers frequently troubleshoot:

- Resolver failures
- Incorrect authoritative records
- Cache inconsistencies
- DNS propagation delays
- Delegation issues

Understanding the distinction accelerates root cause analysis.

---

## Common Production Failures

### Recursive Resolver Failure

Symptoms:

- Name resolution failures
- Widespread application issues

### Incorrect Authoritative Record

Symptoms:

- Traffic routed incorrectly

### Stale Recursive Cache

Symptoms:

- Old IP addresses returned

### Delegation Failure

Symptoms:

- Domain unreachable

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

Useful for identifying where DNS resolution is failing.

---

## Common Interview Questions

- Recursive DNS vs Authoritative DNS?
- Which server owns DNS records?
- Which server performs lookups?
- Why do recursive resolvers cache results?
- What happens when authoritative DNS is unavailable?
- What causes DNS propagation delays?
- How does dig +trace help troubleshooting?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Recursive DNS | Finds Answers |
| Authoritative DNS | Owns Answers |
| Recursive Resolver | Queries DNS Hierarchy |
| Authoritative Server | Stores Records |
| Caching | Recursive Resolver Feature |
| DNS Propagation | Cache Expiration Effect |
| Common Public Resolver | 8.8.8.8 |
| Root Cause Analysis | Identify Which Layer Failed |
| Most Common Interview Question | Recursive vs Authoritative |
| Core Difference | Find vs Own |