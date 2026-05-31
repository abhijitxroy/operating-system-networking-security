

# Load Balancer Types

## Why Multiple Load Balancer Types Exist

Different applications have different requirements.

Examples:

- Websites
- APIs
- Databases
- Streaming services
- Kubernetes clusters

Question:

```text
Should Traffic Be Balanced
At The Network Layer?

Or

At The Application Layer?
```

Different load balancer types solve different problems.

---

## What Is A Load Balancer?

A load balancer distributes traffic across multiple backend systems.

Purpose:

```text
Users
  ↓
Load Balancer
  ↓
Backend Servers
```

Goals:

- Scalability
- Availability
- Reliability

---

## Major Load Balancer Categories

Common types:

```text
Hardware Load Balancers
Software Load Balancers
Layer 4 Load Balancers
Layer 7 Load Balancers
Global Load Balancers
```

---

## Hardware Load Balancers

Dedicated physical appliances.

Examples:

- F5 BIG-IP
- Citrix ADC

Benefits:

- High performance
- Specialized hardware

Limitations:

- Expensive
- Less flexible

Common in traditional enterprise environments.

---

## Software Load Balancers

Run as software on servers or cloud platforms.

Examples:

- NGINX
- HAProxy
- Envoy

Benefits:

- Flexible
- Cloud friendly
- Cost effective

Widely used in modern infrastructure.

---

## Layer 4 Load Balancers

Operate at:

```text
Transport Layer
```

Routing decisions use:

- IP address
- Port number
- Protocol

Examples:

```text
TCP
UDP
```

Benefits:

- High throughput
- Lower latency

---

## Layer 7 Load Balancers

Operate at:

```text
Application Layer
```

Can inspect:

- URLs
- Headers
- Cookies
- Hostnames

Benefits:

- Intelligent routing
- Application awareness

Common for web applications and APIs.

---

## Internal Load Balancers

Used inside private networks.

Example:

```text
Microservice
     ↓
Internal Load Balancer
     ↓
Microservice
```

Not directly exposed to the Internet.

---

## External Load Balancers

Public-facing load balancers.

Example:

```text
Internet Users
      ↓
External Load Balancer
      ↓
Application Servers
```

Common for websites and APIs.

---

## Global Load Balancers

Distribute traffic across regions.

Example:

```text
India User
      ↓
Mumbai Region

Europe User
       ↓
Frankfurt Region
```

Used for low latency and disaster recovery.

---

## Cloud Load Balancers

Managed by cloud providers.

Examples:

- AWS Elastic Load Balancer
- Azure Load Balancer
- Google Cloud Load Balancing

Benefits:

- Managed service
- Automatic scaling
- Integrated monitoring

---

## High-Level Comparison

| Type | Primary Purpose |
|----------|----------|
| Hardware LB | Dedicated Performance |
| Software LB | Flexible Traffic Distribution |
| L4 LB | Fast Network-Level Routing |
| L7 LB | Intelligent Application Routing |
| Internal LB | Private Traffic |
| External LB | Public Traffic |
| Global LB | Multi-Region Routing |
| Cloud LB | Managed Load Balancing |

---

## Production Impact

Organizations often use multiple load balancer types together.

Example:

```text
Global Load Balancer
         ↓
Regional L7 Load Balancer
         ↓
Application Cluster
```

Modern cloud architectures commonly combine several layers.

---

## Common Production Failures

### Wrong Load Balancer Selection

Symptoms:

- Missing required features

### Misconfigured Routing Rules

Symptoms:

- Traffic reaches wrong backend

### Capacity Limits

Symptoms:

- Increased latency
- Request drops

### Regional Failure

Symptoms:

- Traffic unavailable globally

---

## Common Interview Questions

- What are different load balancer types?
- Hardware vs software load balancer?
- Internal vs external load balancer?
- L4 vs L7 load balancer?
- Why use a global load balancer?
- What are cloud load balancers?
- Which load balancer would you choose for APIs?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Hardware LB | Physical Appliance |
| Software LB | Software-Based Routing |
| L4 LB | IP And Port Based |
| L7 LB | Application Aware |
| Internal LB | Private Network Traffic |
| External LB | Internet Traffic |
| Global LB | Multi-Region Routing |
| Cloud LB | Managed Service |
| Main Goal | Traffic Distribution |
| Core Benefit | Scalability And Availability |