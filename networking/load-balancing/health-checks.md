

# Health Checks

## Why Health Checks Exist

A load balancer distributes traffic across multiple servers.

Question:

```text
How Does The Load Balancer Know
Which Servers Are Healthy?
```

Without health checks:

```text
Healthy Server
Unhealthy Server
```

both may continue receiving traffic.

Health checks solve this problem.

---

## What Is A Health Check?

A health check is a mechanism used to verify whether a backend server is available and functioning correctly.

Purpose:

```text
Healthy?
    ↓
Receive Traffic

Unhealthy?
    ↓
Remove From Rotation
```

---

## The Engineering Problem

Suppose a load balancer manages:

```text
Server A
Server B
Server C
```

Server B crashes.

Question:

```text
How Does The Load Balancer
Detect The Failure?
```

Health checks provide the answer.

---

## High-Level Flow

```text
Load Balancer
      ↓
Health Check
      ↓
Backend Server
      ↓
Healthy / Unhealthy
```

Traffic decisions depend on the result.

---

## Active Health Checks

The load balancer periodically sends requests.

Example:

```text
GET /health
```

Expected response:

```text
200 OK
```

If successful:

```text
Server Remains Active
```

---

## Passive Health Checks

The load balancer observes real traffic.

Example indicators:

- Connection failures
- Timeouts
- 5xx errors

No dedicated probe is required.

---

## Common Health Check Types

### TCP Health Check

Verifies:

```text
Can A TCP Connection
Be Established?
```

Fast and simple.

---

### HTTP Health Check

Verifies:

```text
Application Endpoint
Returns Success
```

Common example:

```text
/health
/ready
/status
```

---

### HTTPS Health Check

Same as HTTP but over TLS.

Useful for production web applications.

---

### Custom Health Check

Checks deeper dependencies.

Examples:

- Database connectivity
- Cache availability
- Message queue access

---

## Health Check Parameters

### Interval

How often checks run.

Example:

```text
Every 10 Seconds
```

---

### Timeout

Maximum wait time.

Example:

```text
2 Seconds
```

---

### Healthy Threshold

Number of successful checks required.

---

### Unhealthy Threshold

Number of failures required.

---

## Health Check Endpoint Example

```http
GET /health
```

Response:

```http
200 OK
```

Simple and common production pattern.

---

## Production Impact

Health checks improve:

- Availability
- Reliability
- User experience
- Automatic recovery

Without health checks, failed servers may continue receiving traffic.

---

## Common Production Failures

### Incorrect Health Check URL

Symptoms:

- Healthy servers marked unhealthy

### Aggressive Timeouts

Symptoms:

- False failures

### Shallow Health Checks

Symptoms:

- Broken applications reported healthy

### Dependency Failure

Symptoms:

- Server healthy but service unusable

---

## Kubernetes Example

Kubernetes uses:

```text
Liveness Probe
Readiness Probe
Startup Probe
```

These concepts are built around health checking.

---

## Common Interview Questions

- What is a health check?
- Why are health checks required?
- Active vs passive health checks?
- TCP vs HTTP health checks?
- What should a /health endpoint return?
- What is a readiness check?
- What happens when a server becomes unhealthy?
- How do load balancers avoid failed servers?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Health Check | Verify Backend Health |
| Active Check | Dedicated Probe |
| Passive Check | Observe Traffic |
| TCP Check | Connection Validation |
| HTTP Check | Endpoint Validation |
| Interval | Check Frequency |
| Timeout | Maximum Wait Time |
| Healthy Threshold | Success Requirement |
| Unhealthy Threshold | Failure Requirement |
| Core Goal | Route Traffic Only To Healthy Servers |