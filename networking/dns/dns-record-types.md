

# DNS Record Types

## Why DNS Records Exist

DNS does more than map domain names to IP addresses.

DNS also stores information about:

- Websites
- Email systems
- Service discovery
- Verification records
- Load balancing

DNS records provide this information.

---

## The Engineering Problem

Suppose:

```text
company.com
```

Questions:

```text
What Is The Website IP?

Which Server Receives Email?

Which Service Should Clients Use?
```

Different types of DNS records answer different questions.

---

## What Is A DNS Record?

A DNS record is an entry stored on an authoritative DNS server.

Example:

```text
Domain
   ↓
Associated Information
```

Different record types serve different purposes.

---

## A Record

A stands for:

```text
Address Record
```

Maps:

```text
Domain
   ↓
IPv4 Address
```

Example:

```text
api.company.com
      ↓
10.0.0.10
```

Most website lookups use A records.

---

## AAAA Record

Maps:

```text
Domain
   ↓
IPv6 Address
```

Example:

```text
api.company.com
      ↓
2001:db8::1
```

IPv6 equivalent of an A record.

---

## CNAME Record

CNAME stands for:

```text
Canonical Name
```

Maps:

```text
Alias
   ↓
Real Domain
```

Example:

```text
www.company.com
      ↓
company.com
```

Useful for simplifying DNS management.

---

## MX Record

MX stands for:

```text
Mail Exchange
```

Defines:

```text
Mail Server
For Domain
```

Example:

```text
company.com
      ↓
mail.company.com
```

Required for email delivery.

---

## TXT Record

Stores arbitrary text information.

Common uses:

- Domain verification
- SPF
- DKIM
- DMARC
- Cloud integrations

Example:

```text
Domain Ownership Verification
```

---

## NS Record

NS stands for:

```text
Name Server
```

Defines:

```text
Which DNS Server
Is Authoritative
```

Example:

```text
company.com
      ↓
ns1.provider.com
```

Critical for DNS delegation.

---

## PTR Record

Used for:

```text
Reverse DNS Lookup
```

Maps:

```text
IP Address
      ↓
Domain Name
```

Example:

```text
10.0.0.10
      ↓
api.company.com
```

Common in email systems.

---

## SRV Record

SRV stands for:

```text
Service Record
```

Defines:

- Service location
- Port number
- Priority

Common in:

- Active Directory
- Kubernetes
- Service discovery systems

---

## Common DNS Records Summary

| Record | Purpose |
|----------|----------|
| A | Domain → IPv4 |
| AAAA | Domain → IPv6 |
| CNAME | Alias → Domain |
| MX | Mail Routing |
| TXT | Metadata And Verification |
| NS | Authoritative DNS Servers |
| PTR | Reverse DNS |
| SRV | Service Discovery |

---

## Production Impact

DNS records affect:

- Website availability
- Email delivery
- Cloud integrations
- Kubernetes service discovery
- Authentication systems

Incorrect records frequently cause production outages.

---

## Common Production Failures

### Incorrect A Record

Symptoms:

- Traffic reaches wrong server

### Incorrect MX Record

Symptoms:

- Email delivery failure

### Missing TXT Record

Symptoms:

- Verification failure

### Incorrect NS Record

Symptoms:

- DNS delegation problems

### Broken CNAME

Symptoms:

- Name resolution failure

---

## Useful Commands

```bash
dig company.com A
```

```bash
dig company.com MX
```

```bash
dig company.com TXT
```

```bash
dig company.com NS
```

Useful for record validation.

---

## Common Interview Questions

- What is an A record?
- A vs AAAA?
- What is a CNAME?
- What is an MX record?
- Why are TXT records used?
- What is an NS record?
- What is reverse DNS?
- What is a PTR record?
- What is an SRV record?

---

## Quick Revision

| Record Type | Key Purpose |
|----------|----------|
| A | IPv4 Mapping |
| AAAA | IPv6 Mapping |
| CNAME | Alias Mapping |
| MX | Email Routing |
| TXT | Verification And Metadata |
| NS | DNS Delegation |
| PTR | Reverse Lookup |
| SRV | Service Discovery |
| Most Common | A Record |
| Most Common Interview Topic | A vs CNAME |