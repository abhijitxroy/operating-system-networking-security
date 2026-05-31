

# Static vs Dynamic Routing

## Why This Comparison Matters

Routers need routes to reach destination networks.

Question:

```text
How Should Routes Be Added?

Manually?
Or
Automatically?
```

This leads to two routing approaches:

- Static Routing
- Dynamic Routing

A very common networking interview topic.

---

## What Is Static Routing?

Static Routing means routes are manually configured by administrators.

Example:

```text
Network
10.0.0.0/8
      ↓
Next Hop
192.168.1.1
```

The router does not learn routes automatically.

---

## Static Route Example

Linux:

```bash
ip route add 10.0.0.0/8 via 192.168.1.1
```

Router:

```text
Destination Network
        ↓
Manual Next Hop
```

---

## Advantages Of Static Routing

- Simple
- Predictable
- Low overhead
- Easy for small environments
- No routing protocol required

---

## Limitations Of Static Routing

- Manual maintenance
- Poor scalability
- Slow adaptation to failures
- Operational overhead

Large networks become difficult to manage.

---

## What Is Dynamic Routing?

Dynamic Routing allows routers to learn routes automatically.

Routers exchange routing information.

Example:

```text
Router A
    ↔
Router B
    ↔
Router C
```

Routes are learned and updated automatically.

---

## Common Dynamic Routing Protocols

### OSPF

Common inside enterprises and data centers.

### BGP

Used across the Internet.

### EIGRP

Cisco-focused dynamic routing protocol.

---

## Advantages Of Dynamic Routing

- Scalable
- Automatic route learning
- Faster recovery from failures
- Better for large environments

---

## Limitations Of Dynamic Routing

- More complex
- Protocol overhead
- Additional CPU and memory usage
- Requires protocol configuration

---

## Failure Recovery Comparison

### Static Routing

```text
Link Failure
      ↓
Manual Intervention Required
```

### Dynamic Routing

```text
Link Failure
      ↓
Route Recalculation
      ↓
Automatic Recovery
```

Dynamic routing is far more resilient.

---

## High-Level Comparison

| Feature | Static Routing | Dynamic Routing |
|----------|----------|----------|
| Route Learning | Manual | Automatic |
| Scalability | Low | High |
| Complexity | Low | Higher |
| Failure Recovery | Manual | Automatic |
| Administrative Effort | High | Lower |
| Best For | Small Networks | Large Networks |

---

## Production Usage

Static routing is common for:

- Small networks
- Default routes
- Lab environments

Dynamic routing is common for:

- Enterprises
- Data centers
- Cloud networks
- ISPs
- Internet routing

---

## Common Production Failures

### Static Route Misconfiguration

Symptoms:

- Network unreachable

### Missing Static Route

Symptoms:

- Partial connectivity

### Dynamic Route Instability

Symptoms:

- Route flapping
- Intermittent traffic loss

### Protocol Misconfiguration

Symptoms:

- Routes not learned

---

## Troubleshooting Commands

```bash
ip route
```

```bash
traceroute
```

```bash
ping
```

```bash
netstat -rn
```

Useful for route validation.

---

## Common Interview Questions

- Static vs Dynamic Routing?
- When should static routing be used?
- When should dynamic routing be used?
- What are OSPF and BGP?
- Which approach scales better?
- How does dynamic routing recover from failures?
- Why is static routing still used?

---

## Quick Revision

| Concept | Static Routing | Dynamic Routing |
|----------|----------|----------|
| Learning | Manual | Automatic |
| Scalability | Low | High |
| Maintenance | Manual | Automated |
| Recovery | Manual | Automatic |
| Complexity | Simple | More Complex |
| Protocols | None Required | OSPF, BGP, EIGRP |
| Best Use Case | Small Networks | Large Networks |
| Core Advantage | Predictability | Adaptability |