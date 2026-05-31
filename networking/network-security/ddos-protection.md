

# DDoS Protection

## Why DDoS Protection Exists

Internet-facing systems are exposed to malicious traffic.

Question:

```text
What Happens If Millions
Of Requests Hit A Service
At The Same Time?
```

Possible results:

- Service outage
- High latency
- Resource exhaustion
- Revenue loss

DDoS protection helps keep services available.

---

## What Is A DDoS Attack?

DDoS stands for:

```text
Distributed Denial Of Service
```

Purpose:

```text
Overwhelm A Target
With Massive Traffic
```

Attack traffic originates from many systems simultaneously.

---

## The Engineering Problem

Suppose a website normally receives:

```text
10,000 Requests Per Minute
```

An attacker generates:

```text
10,000,000 Requests Per Minute
```

Question:

```text
How Can Legitimate Users
Still Access The Service?
```

DDoS mitigation provides the answer.

---

## High-Level Attack Flow

```text
Bot 1
Bot 2
Bot 3
Bot 4
   ↓
Target Service
```

Large numbers of compromised devices generate traffic.

---

## Common DDoS Attack Types

### Volumetric Attacks

Goal:

```text
Consume Bandwidth
```

Examples:

- UDP Flood
- ICMP Flood

---

### Protocol Attacks

Goal:

```text
Exhaust Network Resources
```

Examples:

- SYN Flood
- Fragmentation Attacks

---

### Application Layer Attacks

Goal:

```text
Overload Application Logic
```

Examples:

- HTTP Flood
- API Abuse

Often harder to detect because traffic may look legitimate.

---

## What Is A Botnet?

A botnet is a collection of compromised systems.

Example:

```text
Device A
Device B
Device C
      ↓
Attack Target
```

Botnets commonly generate DDoS traffic.

---

## DDoS Protection Techniques

### Rate Limiting

Restrict request volume.

Example:

```text
100 Requests Per Minute
Per Client
```

---

### Traffic Filtering

Block suspicious traffic.

Examples:

- IP filtering
- Geographic filtering
- Reputation filtering

---

### Web Application Firewall (WAF)

Protects applications from malicious requests.

Useful for:

- HTTP attacks
- API attacks

---

### CDN Protection

Content Delivery Networks absorb large traffic volumes.

Benefits:

- Distributed infrastructure
- Traffic scrubbing
- Global scale

---

### Load Balancing

Distributes traffic across multiple systems.

Helps improve resilience during attacks.

---

## Traffic Scrubbing

Suspicious traffic is filtered before reaching the application.

```text
Attack Traffic
      ↓
Scrubbing Center
      ↓
Clean Traffic
      ↓
Application
```

---

## Production Impact

DDoS protection is critical for:

- E-commerce platforms
- SaaS products
- APIs
- Cloud services
- Financial systems
- Public websites

Downtime directly impacts business operations.

---

## Common Production Failures

### Missing Rate Limits

Symptoms:

- Resource exhaustion

### Weak Filtering Rules

Symptoms:

- Attack traffic reaches application

### Single Region Deployment

Symptoms:

- Regional saturation

### Insufficient Capacity

Symptoms:

- Service outage during traffic spikes

---

## Common Interview Questions

- What is a DDoS attack?
- Difference between DoS and DDoS?
- What is a botnet?
- What is a SYN flood?
- How does rate limiting help?
- How do CDNs help mitigate DDoS attacks?
- What is traffic scrubbing?
- How would you protect a public API from DDoS attacks?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| DDoS | Distributed Denial Of Service |
| Goal | Exhaust Resources |
| Botnet | Multiple Compromised Devices |
| Volumetric Attack | Consume Bandwidth |
| Protocol Attack | Exhaust Network Resources |
| Application Attack | Overload Application Logic |
| Rate Limiting | Restrict Request Volume |
| WAF | Application Protection |
| CDN | Distributed DDoS Defense |
| Core Goal | Maintain Service Availability |