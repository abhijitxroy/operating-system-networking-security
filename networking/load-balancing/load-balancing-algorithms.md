

# Load Balancing Algorithms

## Why Load Balancing Algorithms Exist

A load balancer must decide:

```text
Which Backend Server
Should Receive The Next Request?
```

When multiple healthy servers exist:

```text
Server A
Server B
Server C
```

an algorithm determines traffic distribution.

---

## What Is A Load Balancing Algorithm?

A load balancing algorithm is the strategy used to select a backend server.

Purpose:

```text
Incoming Traffic
       ↓
Selection Logic
       ↓
Backend Server
```

Different algorithms optimize for different goals.

---

## The Engineering Problem

Suppose:

```text
Server A
Server B
Server C
```

All are healthy.

Question:

```text
How Should Traffic
Be Distributed?
```

Possible goals:

- Equal distribution
- Capacity awareness
- Session affinity
- Lowest latency

---

## Round Robin

Most common algorithm.

Traffic distribution:

```text
Request 1 → Server A
Request 2 → Server B
Request 3 → Server C
Request 4 → Server A
```

Benefits:

- Simple
- Predictable
- Easy to implement

---

## Weighted Round Robin

Servers receive traffic according to assigned weights.

Example:

```text
Server A → Weight 3
Server B → Weight 2
Server C → Weight 1
```

Traffic distribution favors larger servers.

Useful when backend capacity differs.

---

## Least Connections

Traffic goes to the server with the fewest active connections.

Example:

```text
Server A → 100 Connections
Server B → 20 Connections
```

New requests:

```text
Send To Server B
```

Useful for long-lived connections.

---

## Weighted Least Connections

Combines:

- Capacity weighting
- Active connection counts

Provides more intelligent distribution.

---

## Least Response Time

Routes traffic to the fastest responding server.

Example:

```text
Server A → 10ms
Server B → 50ms
```

Traffic favors:

```text
Server A
```

Useful for latency-sensitive systems.

---

## IP Hash

Uses client IP address.

Example:

```text
Client IP
      ↓
Hash Function
      ↓
Server Selection
```

Often used for session affinity.

---

## Consistent Hashing

Maps requests to servers using hashing.

Benefits:

- Stable distribution
- Minimal reshuffling when servers change

Common in:

- Distributed systems
- Caching platforms
- CDNs

---

## Random Selection

Randomly selects a backend.

Simple but less predictable.

Generally less common in production.

---

## Algorithm Comparison

| Algorithm | Best For |
|----------|----------|
| Round Robin | Equal Servers |
| Weighted Round Robin | Different Capacities |
| Least Connections | Long-Lived Sessions |
| Weighted Least Connections | Mixed Workloads |
| Least Response Time | Low Latency |
| IP Hash | Sticky Sessions |
| Consistent Hashing | Distributed Systems |

---

## Production Impact

Algorithm choice affects:

- Performance
- Scalability
- Resource utilization
- User experience

Selecting the wrong algorithm can overload servers.

---

## Common Production Failures

### Uneven Traffic Distribution

Symptoms:

- Some servers overloaded

### Incorrect Weights

Symptoms:

- Capacity imbalance

### Sticky Session Issues

Symptoms:

- Session failures

### Poor Algorithm Selection

Symptoms:

- High latency
- Reduced throughput

---

## Common Interview Questions

- What is Round Robin?
- What is Weighted Round Robin?
- Least Connections vs Round Robin?
- What is Consistent Hashing?
- What algorithm supports sticky sessions?
- Which algorithm works best for unequal servers?
- How do large-scale systems distribute traffic?

---

## Quick Revision

| Algorithm | Key Idea |
|----------|----------|
| Round Robin | Sequential Distribution |
| Weighted Round Robin | Capacity-Based Distribution |
| Least Connections | Fewest Active Connections |
| Weighted Least Connections | Capacity + Connections |
| Least Response Time | Fastest Server |
| IP Hash | Client-Based Routing |
| Consistent Hashing | Stable Mapping |
| Random | Random Distribution |
| Common Choice | Round Robin |
| Core Goal | Efficient Traffic Distribution |