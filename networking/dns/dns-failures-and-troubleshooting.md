

# DNS Failures And Troubleshooting

## Why DNS Troubleshooting Matters

DNS is one of the most common causes of production incidents.

Applications may appear unavailable even when:

- Servers are healthy
- Networks are healthy
- Databases are healthy

The real issue may simply be DNS.

---

## The Engineering Problem

A user reports:

```text
Application Is Down
```

Possible reality:

```text
Application Healthy
       ↓
DNS Failure
       ↓
Application Appears Down
```

Understanding DNS troubleshooting helps engineers identify the real root cause.

---

## Common DNS Failure Types

### DNS Resolution Failure

Symptoms:

```text
Unknown Host
Name Resolution Failed
Temporary Failure In Name Resolution
```

Common causes:

- DNS server unavailable
- Resolver misconfiguration
- Network issue

---

### Incorrect DNS Record

Symptoms:

```text
Traffic Reaches Wrong System
```

Common causes:

- Incorrect A record
- Incorrect CNAME
- Configuration mistakes

---

### DNS Server Outage

Symptoms:

- Widespread failures
- Multiple applications affected

Common causes:

- Infrastructure outage
- Resource exhaustion
- Misconfiguration

---

### DNS Cache Issues

Symptoms:

- Different users see different behavior
- Old IP addresses returned

Common causes:

- Stale cache
- Long TTL values

---

### Slow DNS Responses

Symptoms:

- Slow website loading
- Increased API latency

Common causes:

- Resolver overload
- Network latency
- Inefficient DNS design

---

## DNS Troubleshooting Workflow

A practical workflow:

```text
Identify Symptom
       ↓
Verify DNS Resolution
       ↓
Verify DNS Server
       ↓
Verify Returned Records
       ↓
Verify Cache Behavior
       ↓
Verify Network Connectivity
       ↓
Find Root Cause
```

---

## Step 1: Verify Resolution

Use:

```bash
dig example.com
```

or

```bash
nslookup example.com
```

Questions:

```text
Does DNS Resolve?
Is An IP Returned?
```

---

## Step 2: Verify Authoritative Answer

Use:

```bash
dig example.com +trace
```

Purpose:

```text
Follow Entire DNS Resolution Path
```

Useful for identifying delegation problems.

---

## Step 3: Verify DNS Records

Check:

- A records
- AAAA records
- CNAME records
- MX records
- TXT records

Example:

```bash
dig example.com A
```

---

## Step 4: Check TTL Values

Example:

```bash
dig example.com
```

Review:

```text
TTL
```

Unexpected TTL values often explain propagation issues.

---

## Step 5: Verify Resolver Configuration

Linux:

```bash
cat /etc/resolv.conf
```

Questions:

```text
Which DNS Server Is Being Used?
```

Misconfigured resolvers are common production issues.

---

## Step 6: Verify Network Connectivity

DNS may fail because DNS servers cannot be reached.

Check:

```bash
ping DNS_SERVER
```

```bash
traceroute DNS_SERVER
```

---

## Production Failure Examples

### Kubernetes DNS Failure

Symptoms:

- Service discovery failure
- Pod communication issues

Typical causes:

- CoreDNS problems
- Network policy issues

---

### Cloud DNS Failure

Symptoms:

- Regional outages
- API failures

Typical causes:

- Misconfigured DNS records
- Resolver issues

---

### DNS Migration Problems

Symptoms:

- Partial traffic failures

Typical causes:

- Cached records
- Long TTL values

---

## Useful DNS Commands

```bash
dig
```

```bash
nslookup
```

```bash
host
```

```bash
dig +trace
```

```bash
cat /etc/resolv.conf
```

These commands solve most DNS investigations.

---

## Production Troubleshooting Mindset

Never assume:

```text
Application Down
      =
Application Problem
```

Always verify:

```text
DNS
 ↓
Network
 ↓
Application
```

DNS issues often masquerade as application failures.

---

## Common Interview Questions

- How would you troubleshoot DNS failures?
- What does dig do?
- What does dig +trace do?
- Why might different users get different DNS results?
- What causes DNS propagation delays?
- How do you verify DNS records?
- How do you verify the resolver being used?
- Why are DNS issues difficult to diagnose?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Resolution Failure | Name Cannot Resolve |
| Incorrect Record | Wrong Destination |
| DNS Outage | Resolver Unavailable |
| Cache Issue | Stale Data |
| Slow DNS | Increased Lookup Latency |
| dig | Primary DNS Tool |
| dig +trace | Full Resolution Path |
| TTL | Cache Lifetime |
| resolv.conf | Resolver Configuration |
| Core Goal | Verify Resolution Path |