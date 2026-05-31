

# High Availability

## Why High Availability Exists

Production systems cannot depend on a single server.

Example:

```text
One Server
    ↓
Failure
    ↓
Application Down
```

Question:

```text
How Can Systems Continue
Operating During Failures?
```

High Availability solves this problem.

---

## What Is High Availability?

High Availability (HA) is the ability of a system to remain operational despite failures.

Goal:

```text
Minimize Downtime
```

Users should continue accessing services even when components fail.

---

## The Engineering Problem

Suppose an application runs on:

```text
Server A
```

If Server A crashes:

```text
Application Unavailable
```

A single point of failure exists.

High Availability removes such dependencies.

---

## High-Level HA Architecture

```text
Users
   ↓
Load Balancer
   ↓
Server A
Server B
Server C
```

If one server fails:

```text
Traffic Redirected
To Healthy Servers
```

---

## Single Point Of Failure (SPOF)

A SPOF is any component whose failure causes service outage.

Examples:

- Single server
- Single database
- Single load balancer
- Single network device

A primary goal of HA design is eliminating SPOFs.

---

## Redundancy

HA depends on redundancy.

Example:

```text
Primary Server
Backup Server
```

If one fails:

```text
Backup Takes Over
```

---

## Failover

Failover is the process of moving traffic or workloads to a healthy component.

Example:

```text
Primary
   ↓
Failure
   ↓
Secondary
```

Automatic failover is preferred in production systems.

---

## Active-Active Architecture

Multiple servers actively handle traffic.

```text
Users
  ↓
Server A
Server B
Server C
```

Benefits:

- Better utilization
- Higher scalability
- Improved resilience

---

## Active-Passive Architecture

One server handles traffic.

Another remains on standby.

```text
Active Server
      ↓
Failure
      ↓
Passive Server
```

Simpler but less resource efficient.

---

## High Availability And Load Balancers

Load balancers are a key HA component.

Responsibilities:

- Traffic distribution
- Failure detection
- Automatic failover
- Health monitoring

---

## Availability Metrics

Often measured using uptime percentages.

Examples:

```text
99.9%
99.99%
99.999%
```

Higher availability generally requires greater complexity and cost.

---

## Production Impact

High Availability is critical for:

- Banking systems
- E-commerce platforms
- Cloud services
- SaaS products
- APIs
- Kubernetes platforms

Downtime directly impacts revenue and user trust.

---

## Common Production Failures

### Single Point Of Failure

Symptoms:

- Complete outage

### Failed Failover

Symptoms:

- Backup system never activated

### Health Check Issues

Symptoms:

- Traffic sent to failed servers

### Capacity Problems

Symptoms:

- Remaining servers overloaded after failure

---

## Common Interview Questions

- What is High Availability?
- What is a Single Point Of Failure?
- What is failover?
- Active-active vs active-passive?
- How do load balancers improve availability?
- What is redundancy?
- What does 99.99% availability mean?
- How would you design a highly available system?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| High Availability | Minimize Downtime |
| SPOF | Single Point Of Failure |
| Redundancy | Duplicate Components |
| Failover | Switch To Healthy Component |
| Active-Active | Multiple Active Nodes |
| Active-Passive | Standby Node Available |
| Load Balancer | Traffic Distribution |
| Health Check | Failure Detection |
| Main Goal | Continuous Service |
| Core Benefit | Resilience During Failures |