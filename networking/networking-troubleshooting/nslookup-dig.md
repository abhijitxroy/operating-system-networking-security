

# nslookup vs dig

## Why DNS Troubleshooting Matters

Many application failures are actually DNS problems.

Question:

```text
Can The Hostname
Be Resolved?

Is DNS Returning
The Correct Address?
```

`nslookup` and `dig` are the most common DNS troubleshooting tools.

---

## What Is DNS?

DNS stands for:

```text
Domain Name System
```

Purpose:

```text
Hostname
    ↓
IP Address
```

Example:

```text
example.com
     ↓
93.x.x.x
```

---

## What Is nslookup?

`nslookup` is a DNS query tool.

Used to:

- Resolve hostnames
- Verify DNS records
- Test DNS servers

Example:

```bash
nslookup google.com
```

---

## What Is dig?

`dig` stands for:

```text
Domain Information Groper
```

It is a more advanced DNS troubleshooting tool.

Benefits:

- Detailed output
- Better diagnostics
- Preferred by many engineers

Example:

```bash
dig google.com
```

---

## The Engineering Problem

Suppose an application reports:

```text
Host Not Found
```

Question:

```text
Is DNS Broken?

Or Is The Application Wrong?
```

Use DNS tools to verify.

---

## Basic Hostname Lookup

Using nslookup:

```bash
nslookup example.com
```

Using dig:

```bash
dig example.com
```

Expected result:

```text
Hostname
    ↓
IP Address
```

---

## Query Specific DNS Server

Using nslookup:

```bash
nslookup example.com 8.8.8.8
```

Using dig:

```bash
dig @8.8.8.8 example.com
```

Useful for comparing DNS servers.

---

## Check A Records

```bash
dig example.com A
```

Returns:

```text
IPv4 Address Records
```

---

## Check AAAA Records

```bash
dig example.com AAAA
```

Returns:

```text
IPv6 Address Records
```

---

## Check MX Records

```bash
dig example.com MX
```

Returns:

```text
Mail Servers
```

---

## Check NS Records

```bash
dig example.com NS
```

Returns:

```text
Authoritative Name Servers
```

---

## Reverse DNS Lookup

Example:

```bash
dig -x 8.8.8.8
```

Purpose:

```text
IP Address
     ↓
Hostname
```

---

## Common DNS Problems

### NXDOMAIN

Meaning:

```text
Domain Does Not Exist
```

---

### Wrong IP Returned

Possible causes:

- DNS propagation delay
- Incorrect record
- Cache issues

---

### DNS Timeout

Possible causes:

- DNS server unreachable
- Firewall restrictions
- Network problems

---

## Production Troubleshooting Workflow

```text
Application Failure
         ↓
DNS Lookup
         ↓
Correct IP?
         ↓
Correct DNS Server?
         ↓
Check Routing
         ↓
Check Application
```

DNS should always be verified early in an investigation.

---

## nslookup vs dig

| Feature | nslookup | dig |
|----------|----------|----------|
| Simplicity | Easy | Moderate |
| Detail Level | Basic | Advanced |
| Troubleshooting | Good | Excellent |
| DNS Record Analysis | Limited | Extensive |
| Recommended For Deep Debugging | No | Yes |

---

## Production Usage

Common uses:

- DNS verification
- Service discovery debugging
- Kubernetes DNS troubleshooting
- Cloud networking investigations
- Email configuration validation

These tools are used regularly by DevOps, SRE, Platform, and Infrastructure engineers.

---

## Common Interview Questions

- What is DNS?
- What is nslookup?
- What is dig?
- Why is dig preferred for troubleshooting?
- How do you check MX records?
- How do you perform reverse DNS lookups?
- What does NXDOMAIN mean?
- How do you troubleshoot DNS failures?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| DNS | Name Resolution System |
| nslookup | Basic DNS Queries |
| dig | Advanced DNS Queries |
| A Record | IPv4 Address |
| AAAA Record | IPv6 Address |
| MX Record | Mail Server |
| NS Record | Name Server |
| Reverse Lookup | IP → Hostname |
| Common Failure | NXDOMAIN |
| Core Goal | Verify DNS Resolution |