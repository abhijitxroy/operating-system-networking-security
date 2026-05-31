

# Load Balancing Overview

## Why Load Balancing Exists

Applications often start with a single server.

Example:

```text
Users
  ↓
Server
```

As traffic grows:

- Increased latency
- Resource exhaustion
- Downtime risk
- Single point of failure

Question:

```text
How Can Traffic Be Distributed
Across Multiple Servers?
```

Load balancing solves this problem.

---

## What Is Load Balancing?

Load balancing is the process of distributing traffic across multiple backend systems.

Purpose:

```text
Users
  ↓
Load Balancer
  ↓
Server A
Server B
Server C
```

The load balancer decides where requests should go.

---

## The Engineering Problem

Suppose an application receives:

```text
100,000 Requests Per Minute
```

A single server may not handle the load.

Question:

```text
How Can Capacity Increase
Without Changing The Application?
```

Add more servers and place a load balancer in front.

---

## High-Level Architecture

```text
Clients
   ↓
Load Balancer
   ↓
Backend Servers
```

Clients communicate with the load balancer.

Backend servers process requests.

---

## Core Goals

### Scalability

Support growing traffic.

```text
1 Server
   ↓
10 Servers
```

---

### High Availability

If one server fails:

```text
Server A ❌
Server B ✅
Server C ✅
```

Traffic continues flowing.

---

### Reliability

Prevent individual server failures from causing outages.

---

### Better Resource Utilization

Distribute work evenly.

---

## Traffic Distribution Example

```text
Request 1 → Server A
Request 2 → Server B
Request 3 → Server C
Request 4 → Server A
```

This prevents overloading a single backend.

---

## Load Balancer Responsibilities

Common responsibilities:

- Traffic distribution
- Health checks
- Failover
- SSL/TLS termination
- Session persistence
- Routing decisions

Modern load balancers often perform multiple functions.

---

## Horizontal Scaling

Load balancing enables:

```text
Scale Out
```

Instead of:

```text
Bigger Server
```

we can add:

```text
More Servers
```

This is a foundational cloud architecture concept.

---

## Production Usage

Load balancing is used by:

- Websites
- APIs
- Microservices
- Cloud platforms
- Kubernetes clusters
- SaaS applications

Almost every large-scale system depends on load balancing.

---

## Common Production Failures

### Single Load Balancer Failure

Symptoms:

- Complete outage

### Misconfigured Routing

Symptoms:

- Requests reach wrong backend

### Unhealthy Backends

Symptoms:

- Increased errors

### Capacity Limits

Symptoms:

- High latency
- Dropped requests

---

## Common Interview Questions

- What is load balancing?
- Why is load balancing needed?
- How does load balancing improve availability?
- How does load balancing improve scalability?
- What is horizontal scaling?
- What is a single point of failure?
- What responsibilities does a load balancer have?
- Where is load balancing used?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Load Balancing | Traffic Distribution |
| Load Balancer | Traffic Controller |
| Scalability | Support More Traffic |
| Availability | Survive Failures |
| Reliability | Reduce Outages |
| Health Checks | Detect Failures |
| Horizontal Scaling | Add More Servers |
| Backend Server | Processes Requests |
| SPOF | Single Point Of Failure |
| Core Goal | Efficient Traffic Distribution |