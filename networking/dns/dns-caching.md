

# DNS Caching

## Why DNS Caching Exists

DNS resolution requires multiple network requests.

Without caching:

```text
User Request
      ↓
DNS Lookup
      ↓
Root Server
      ↓
TLD Server
      ↓
Authoritative Server
```

This process would occur for every request.

Result:

- Higher latency
- Increased DNS traffic
- Poor scalability

DNS caching exists to improve performance and reduce unnecessary lookups.

---

## The Engineering Problem

Imagine millions of users accessing:

```text
google.com
```

If every request triggered a full DNS resolution:

```text
Millions Of Queries
        ↓
DNS Infrastructure Overload
```

Caching reduces repeated work.

---

## What Is DNS Caching?

DNS caching stores DNS query results temporarily.

Example:

```text
google.com
      ↓
142.250.x.x
```

Instead of performing another lookup:

```text
Use Cached Result
```

This makes future requests faster.

---

## How DNS Caching Works

First request:

```text
Client
   ↓
DNS Resolver
   ↓
DNS Lookup
   ↓
IP Address Returned
```

Result stored in cache.

Second request:

```text
Client
   ↓
DNS Resolver Cache
   ↓
Immediate Response
```

No external lookup required.

---

## Where DNS Caching Occurs

DNS caching exists at multiple layers.

### Browser Cache

Browsers cache DNS results.

Examples:

- Chrome
- Firefox
- Edge
- Safari

---

### Operating System Cache

Operating systems maintain local DNS caches.

Examples:

- Linux
- Windows
- macOS

---

### Recursive Resolver Cache

Resolvers store query results.

Examples:

- ISP DNS
- Enterprise DNS
- Public DNS Services

This is where most DNS caching benefits occur.

---

### Application Cache

Some applications implement their own DNS caching.

Examples:

- Java applications
- Databases
- Service meshes

---

## What Is TTL?

TTL stands for:

```text
Time To Live
```

TTL determines:

```text
How Long A DNS Record
Can Remain Cached
```

Example:

```text
TTL = 300 Seconds
```

Meaning:

```text
Cache Valid For 5 Minutes
```

---

## TTL Example

DNS Record:

```text
api.company.com
      ↓
10.0.0.10
      ↓
TTL 300
```

For the next 300 seconds:

```text
Cached Answer Used
```

After expiration:

```text
New DNS Lookup Required
```

---

## Benefits Of DNS Caching

### Faster Responses

Cached lookups avoid network round trips.

### Reduced DNS Traffic

Fewer queries reach authoritative servers.

### Better Scalability

DNS infrastructure handles larger workloads.

### Improved User Experience

Applications load faster.

---

## Challenges Of DNS Caching

Caching introduces tradeoffs.

### Stale Records

Old data may remain in cache.

### Slow Change Propagation

DNS updates may not be visible immediately.

### Troubleshooting Complexity

Different systems may use different cached answers.

---

## DNS Cache Propagation

A common misconception:

```text
DNS Updated
      ↓
Everyone Sees Change Immediately
```

Reality:

```text
DNS Updated
      ↓
Caches Expire Gradually
      ↓
Changes Become Visible
```

This process is called DNS propagation.

---

## Production Impact

DNS caching directly affects:

- Website performance
- API latency
- Cloud infrastructure
- Kubernetes service discovery
- Global application delivery

Caching is essential for Internet-scale systems.

---

## Common Production Issues

### Stale DNS Cache

Symptoms:

- Old IP addresses used
- Unexpected routing behavior

### Long TTL

Symptoms:

- Slow migration rollouts
- Delayed DNS updates

### Short TTL

Symptoms:

- Increased DNS traffic
- Higher resolver load

### Cache Inconsistency

Symptoms:

- Different clients see different results

---

## Useful Commands

Linux:

```bash
dig google.com
```

```bash
dig google.com +trace
```

```bash
systemd-resolve --statistics
```

Useful for DNS investigation.

---

## Common Interview Questions

- Why does DNS caching exist?
- What is TTL?
- Where does DNS caching occur?
- What is DNS propagation?
- Why can DNS changes take time?
- Long TTL vs Short TTL?
- What problems can stale caches cause?
- Why is DNS caching important for scalability?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| DNS Cache | Stores Query Results |
| TTL | Cache Lifetime |
| Browser Cache | Local DNS Cache |
| OS Cache | System DNS Cache |
| Resolver Cache | Recursive DNS Cache |
| DNS Propagation | Cache Expiration Process |
| Long TTL | Better Performance, Slower Updates |
| Short TTL | Faster Updates, More Queries |
| Common Failure | Stale Records |
| Core Purpose | Faster DNS Resolution |