

# L4 vs L7 Load Balancing

## Why This Comparison Matters

Not all load balancers make decisions using the same information.

Question:

```text
Should Traffic Be Routed
Using Network Information?

Or

Using Application Information?
```

This leads to:

- Layer 4 Load Balancing
- Layer 7 Load Balancing

A very common system design and networking interview topic.

---

## The OSI Layer Context

```text
Layer 7 → Application
Layer 6 → Presentation
Layer 5 → Session
Layer 4 → Transport
Layer 3 → Network
```

Load balancers commonly operate at:

```text
Layer 4
or
Layer 7
```

---

## What Is Layer 4 Load Balancing?

Layer 4 load balancing operates using transport-layer information.

Uses:

```text
IP Address
Port Number
Protocol
```

Examples:

```text
TCP
UDP
```

The load balancer does not inspect application content.

---

## L4 Traffic Flow

```text
Client
   ↓
L4 Load Balancer
   ↓
Backend Server
```

Decision based on:

```text
Source IP
Destination IP
Port
```

---

## Benefits Of L4 Load Balancing

- Faster processing
- Lower overhead
- High throughput
- Simpler architecture

Common for very high-volume traffic.

---

## Limitations Of L4 Load Balancing

Cannot inspect:

```text
HTTP Headers
Cookies
URLs
Hostnames
```

Routing decisions are limited.

---

## What Is Layer 7 Load Balancing?

Layer 7 load balancing operates using application-layer information.

Examples:

```text
HTTP
HTTPS
gRPC
```

The load balancer can inspect requests before routing them.

---

## L7 Traffic Flow

```text
Client
   ↓
L7 Load Balancer
   ↓
Inspect Request
   ↓
Backend Server
```

Routing decisions can use request content.

---

## L7 Routing Examples

### Path-Based Routing

```text
/api
     ↓
API Servers

/images
       ↓
Image Servers
```

---

### Host-Based Routing

```text
api.company.com
       ↓
API Cluster

admin.company.com
         ↓
Admin Cluster
```

---

### Header-Based Routing

Route using:

```text
HTTP Headers
Cookies
User Attributes
```

---

## Benefits Of L7 Load Balancing

- Intelligent routing
- URL-based routing
- Host-based routing
- Header-based routing
- Better application awareness

Common for modern web platforms.

---

## Limitations Of L7 Load Balancing

- More CPU usage
- Higher complexity
- Additional latency

Application inspection requires more processing.

---

## High-Level Comparison

| Feature | L4 Load Balancing | L7 Load Balancing |
|----------|----------|----------|
| OSI Layer | Layer 4 | Layer 7 |
| Decision Based On | IP And Port | Application Data |
| Protocol Awareness | Low | High |
| Performance | Faster | Slightly Slower |
| Complexity | Lower | Higher |
| URL Routing | No | Yes |
| Header Routing | No | Yes |
| Host Routing | No | Yes |

---

## Production Usage

### L4 Common Usage

- Databases
- TCP services
- High-throughput systems
- Network appliances

### L7 Common Usage

- APIs
- Websites
- Microservices
- Kubernetes Ingress
- API Gateways

---

## Common Production Failures

### Wrong Load Balancer Type

Symptoms:

- Missing routing capabilities

### TLS Termination Issues

Symptoms:

- HTTPS failures

### Incorrect Routing Rules

Symptoms:

- Traffic reaches wrong service

### Performance Bottlenecks

Symptoms:

- Increased latency

---

## Common Interview Questions

- L4 vs L7 load balancing?
- Which OSI layers are involved?
- Why is L4 faster?
- Why is L7 more flexible?
- What is path-based routing?
- What is host-based routing?
- When should L4 be used?
- When should L7 be used?

---

## Quick Revision

| Concept | L4 | L7 |
|----------|----------|----------|
| Layer | Transport Layer | Application Layer |
| Uses | IP And Port | Request Content |
| Speed | Faster | More Processing |
| Routing Flexibility | Limited | Advanced |
| URL Awareness | No | Yes |
| Header Awareness | No | Yes |
| Common Usage | TCP Services | Web Applications |
| Core Benefit | Performance | Intelligent Routing |