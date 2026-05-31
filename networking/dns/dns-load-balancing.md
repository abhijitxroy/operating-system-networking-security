

# DNS Load Balancing

## Why DNS Load Balancing Exists

Modern applications rarely run on a single server.

Reasons:

- High availability
- Scalability
- Fault tolerance
- Geographic distribution

A mechanism is needed to distribute traffic across multiple systems.

DNS Load Balancing is one of the simplest ways to achieve this.

---

## The Engineering Problem

Suppose an application runs on:

```text
Server A
Server B
Server C
```

Question:

```text
How Do Users Reach
The Appropriate Server?
```

Sending all traffic to a single server creates:

- Bottlenecks
- Outages
- Poor scalability

DNS can help distribute traffic.

---

## What Is DNS Load Balancing?

DNS Load Balancing distributes requests by returning different IP addresses for the same domain.

Example:

```text
api.company.com
```

May return:

```text
10.0.0.10
```

or

```text
10.0.0.11
```

or

```text
10.0.0.12
```

Different clients may receive different answers.

---

## Basic DNS Load Balancing

DNS Record:

```text
api.company.com
```

Associated with:

```text
10.0.0.10
10.0.0.11
10.0.0.12
```

DNS returns one or more addresses.

Traffic becomes distributed across servers.

---

## Round Robin DNS

The simplest DNS load balancing method.

Example:

```text
Request 1 → 10.0.0.10
Request 2 → 10.0.0.11
Request 3 → 10.0.0.12
```

Benefits:

- Easy setup
- No additional infrastructure

Limitations:

- No health awareness
- Uneven traffic distribution

---

## Weighted DNS Load Balancing

Some servers may receive more traffic.

Example:

```text
Server A = 70%
Server B = 20%
Server C = 10%
```

Useful during:

- Migrations
- Canary deployments
- Capacity differences

---

## Geographic DNS Routing

Users are routed based on location.

Example:

```text
India Users
      ↓
India Region

Europe Users
      ↓
Europe Region
```

Benefits:

- Lower latency
- Better user experience

---

## Health Check Based Routing

Modern DNS providers can perform health checks.

Example:

```text
Server Healthy
      ↓
Return IP

Server Unhealthy
      ↓
Remove From Responses
```

Improves availability.

---

## DNS Load Balancing vs Traditional Load Balancers

| Feature | DNS Load Balancing | Load Balancer |
|----------|----------|----------|
| Layer | DNS | Network/Application |
| Traffic Visibility | Limited | Full |
| Health Awareness | Provider Dependent | Strong |
| Session Awareness | No | Yes |
| Simplicity | High | Medium |

DNS is often used together with load balancers.

---

## Production Use Cases

### Multi-Region Applications

Route users to nearest region.

### Disaster Recovery

Redirect traffic during outages.

### Blue-Green Deployments

Shift traffic between environments.

### Global Services

Distribute users worldwide.

---

## Limitations Of DNS Load Balancing

### DNS Caching

Clients may continue using old records.

### Delayed Failover

TTL values slow traffic movement.

### No Connection Awareness

DNS cannot see active sessions.

### Uneven Distribution

Actual traffic may differ from expectations.

---

## Production Impact

DNS Load Balancing is commonly used in:

- CDNs
- Cloud platforms
- SaaS applications
- Global APIs
- Multi-region architectures

It often forms the first layer of traffic distribution.

---

## Common Interview Questions

- What is DNS Load Balancing?
- How does Round Robin DNS work?
- What is Weighted DNS Routing?
- Why is DNS caching a challenge?
- DNS Load Balancing vs Load Balancer?
- How does Geo DNS work?
- What is DNS failover?
- Why is DNS not sufficient by itself for advanced load balancing?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| DNS Load Balancing | Traffic Distribution Using DNS |
| Round Robin | Rotate Responses |
| Weighted Routing | Uneven Traffic Distribution |
| Geo Routing | Location-Based Routing |
| Health Checks | Remove Failed Targets |
| DNS Failover | Redirect During Outage |
| Major Limitation | DNS Caching |
| Common Use Case | Multi-Region Applications |
| Often Combined With | Load Balancers |
| Core Goal | Improve Availability And Scalability |