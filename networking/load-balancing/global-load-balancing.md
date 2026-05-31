

# Global Load Balancing

## Why Global Load Balancing Exists

Modern applications often run in multiple regions.

Example:

```text
US Region
Europe Region
Asia Region
```

Question:

```text
How Do Users Reach
The Best Region?

How Do We Handle
Regional Failures?
```

Global Load Balancing solves these problems.

---

## What Is Global Load Balancing?

Global Load Balancing distributes traffic across multiple geographic locations.

Purpose:

```text
Users Worldwide
        ↓
Best Region
        ↓
Application
```

Traffic is routed to the most appropriate location.

---

## The Engineering Problem

Suppose an application runs in:

```text
Mumbai
Frankfurt
Virginia
```

Question:

```text
Which Region Should Serve
A User In India?

What If Frankfurt Fails?
```

Global load balancing determines the answer.

---

## High-Level Architecture

```text
User
  ↓
Global Load Balancer
  ↓
Region A
Region B
Region C
```

The global layer chooses the region.

Local load balancers then distribute traffic inside that region.

---

## Common Traffic Routing Strategies

### Geographic Routing

Route users to the nearest region.

Example:

```text
India User
     ↓
Mumbai Region
```

Benefits:

- Lower latency
- Better user experience

---

### Latency-Based Routing

Route traffic to the region with the lowest response time.

Example:

```text
Measure Latency
       ↓
Choose Fastest Region
```

---

### Failover Routing

Primary region serves traffic.

If it becomes unhealthy:

```text
Primary Region
      ↓
Failure
      ↓
Secondary Region
```

---

### Weighted Routing

Traffic distributed using percentages.

Example:

```text
Region A → 80%
Region B → 20%
```

Useful for migrations and canary deployments.

---

## DNS-Based Global Load Balancing

A common implementation.

```text
DNS Query
     ↓
Global Decision
     ↓
Regional Endpoint Returned
```

Often used because it scales well globally.

---

## Anycast Routing

Multiple regions advertise the same IP address.

```text
Same IP
    ↓
Nearest Healthy Region
```

Widely used by CDNs and large cloud providers.

---

## Benefits Of Global Load Balancing

### Lower Latency

Users reach nearby infrastructure.

### Higher Availability

Traffic can move to healthy regions.

### Disaster Recovery

Regional outages have reduced impact.

### Better Scalability

Traffic spread globally.

---

## Production Usage

Used by:

- Cloud providers
- CDNs
- E-commerce platforms
- Streaming services
- SaaS platforms
- Global APIs

Large Internet-scale applications depend heavily on it.

---

## Common Production Failures

### DNS Misconfiguration

Symptoms:

- Users routed incorrectly

### Region Outage

Symptoms:

- Increased latency
- Service disruption

### Health Check Failure

Symptoms:

- Traffic sent to unhealthy regions

### Traffic Imbalance

Symptoms:

- Regional overload

---

## Common Interview Questions

- What is Global Load Balancing?
- Why is it needed?
- DNS-based load balancing vs Anycast?
- What is latency-based routing?
- What is geographic routing?
- What is failover routing?
- How do global systems handle regional failures?
- How do CDNs route users globally?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Global Load Balancing | Multi-Region Traffic Distribution |
| Geographic Routing | Nearest Region |
| Latency-Based Routing | Fastest Region |
| Failover Routing | Backup Region |
| Weighted Routing | Percentage-Based Traffic |
| DNS-Based Routing | Global DNS Decision |
| Anycast | Same IP, Nearest Region |
| Main Benefit | Availability + Low Latency |
| Common Failure | Wrong Regional Routing |
| Core Goal | Route Users To The Best Region |