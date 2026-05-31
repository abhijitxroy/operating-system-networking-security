

# Reverse Proxy vs Load Balancer

## Why This Comparison Matters

Reverse proxies and load balancers often appear together in production architectures.

Question:

```text
Are They The Same Thing?

Or

Do They Solve Different Problems?
```

Understanding the distinction is important for system design, cloud platforms, and production troubleshooting.

---

## The Engineering Problem

Suppose users access:

```text
app.company.com
```

Behind the scenes there may be:

```text
Web Servers
API Servers
Microservices
```

Question:

```text
How Do We Hide Backend Systems?

How Do We Distribute Traffic?
```

Reverse proxies and load balancers help solve these problems.

---

## What Is A Reverse Proxy?

A reverse proxy sits in front of backend servers.

```text
Client
   ↓
Reverse Proxy
   ↓
Backend Servers
```

Clients communicate only with the reverse proxy.

Backend servers remain hidden.

---

## Reverse Proxy Responsibilities

Common functions:

- Request forwarding
- SSL/TLS termination
- Caching
- Compression
- Security filtering
- URL routing

It acts as an intermediary between users and applications.

---

## What Is A Load Balancer?

A load balancer distributes traffic across multiple backend systems.

```text
Client
   ↓
Load Balancer
   ↓
Server A
Server B
Server C
```

Goal:

```text
Traffic Distribution
```

---

## Load Balancer Responsibilities

Common functions:

- Traffic distribution
- Health checks
- Failover
- High availability
- Session persistence

Primary focus:

```text
Scalability
And
Availability
```

---

## Where Confusion Happens

Modern products often perform both roles.

Examples:

- NGINX
- HAProxy
- Envoy

They can:

```text
Act As Reverse Proxy
And
Act As Load Balancer
```

depending on configuration.

---

## Reverse Proxy Example

```text
Client
   ↓
Reverse Proxy
   ↓
Application Server
```

Purpose:

```text
Hide Backend Infrastructure
```

Traffic may still go to only one server.

---

## Load Balancer Example

```text
Client
   ↓
Load Balancer
   ↓
Server A
Server B
Server C
```

Purpose:

```text
Distribute Traffic
```

---

## High-Level Comparison

| Feature | Reverse Proxy | Load Balancer |
|----------|----------|----------|
| Primary Goal | Frontend Gateway | Traffic Distribution |
| Backend Hiding | Yes | Often |
| Traffic Distribution | Optional | Core Function |
| Health Checks | Sometimes | Common |
| Failover | Sometimes | Common |
| SSL Termination | Common | Common |
| Caching | Common | Less Common |
| Scalability Focus | Moderate | High |

---

## Production Architecture Example

```text
Users
   ↓
Global Load Balancer
   ↓
Regional Load Balancer
   ↓
Reverse Proxy
   ↓
Application Services
```

Large systems frequently use both.

---

## Production Impact

Reverse proxies help with:

- Security
- Caching
- Traffic control
- Backend abstraction

Load balancers help with:

- Scalability
- Availability
- Fault tolerance

Together they improve reliability and performance.

---

## Common Production Failures

### Reverse Proxy Misconfiguration

Symptoms:

- Wrong routing
- HTTP errors

### SSL Termination Issues

Symptoms:

- HTTPS failures

### Load Balancer Health Check Issues

Symptoms:

- Traffic sent to failed servers

### Incorrect Traffic Rules

Symptoms:

- Requests reach wrong backend

---

## Common Interview Questions

- Reverse proxy vs load balancer?
- Can a reverse proxy perform load balancing?
- Can a load balancer act as a reverse proxy?
- Why use NGINX as a reverse proxy?
- What problems do reverse proxies solve?
- What problems do load balancers solve?
- Why do large systems use both?

---

## Quick Revision

| Concept | Reverse Proxy | Load Balancer |
|----------|----------|----------|
| Main Goal | Frontend Gateway | Traffic Distribution |
| Backend Hiding | Yes | Often |
| Caching | Common |
| Health Checks | Optional | Common |
| Failover | Optional | Core Feature |
| Scalability | Moderate | High |
| Availability | Moderate | High |
| Core Benefit | Control And Security | Scale And Reliability |