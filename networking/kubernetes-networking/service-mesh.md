

# Service Mesh

## Why Service Mesh Exists

Modern applications often consist of many microservices.

Example:

```text
Frontend
    ↓
API
    ↓
Auth Service
    ↓
Payment Service
```

Question:

```text
How Do We Manage
Service-To-Service
Communication At Scale?
```

A Service Mesh helps solve this problem.

---

## What Is A Service Mesh?

A Service Mesh is a dedicated infrastructure layer for managing service-to-service communication.

Purpose:

```text
Traffic Management
Security
Observability
Reliability
```

Applications focus on business logic while the mesh handles networking concerns.

---

## The Engineering Problem

Suppose services need:

```text
Encryption
Retries
Load Balancing
Traffic Routing
Monitoring
```

Implementing these features in every application creates complexity.

A Service Mesh centralizes these capabilities.

---

## High-Level Architecture

```text
Service A
    ↓
Sidecar Proxy
    ↓
Network
    ↓
Sidecar Proxy
    ↓
Service B
```

Traffic flows through proxies instead of directly between services.

---

## Core Components

### Data Plane

Handles actual traffic.

Typically consists of:

```text
Sidecar Proxies
```

Examples:

```text
Envoy
```

---

### Control Plane

Manages mesh configuration.

Responsibilities:

- Traffic policies
- Security policies
- Service discovery
- Observability configuration

---

## Traffic Management

A Service Mesh supports:

### Load Balancing

```text
Request
   ↓
Healthy Service Instance
```

---

### Traffic Splitting

Example:

```text
90% → Version 1
10% → Version 2
```

Useful for canary deployments.

---

### Retries

Automatically retry failed requests.

---

### Circuit Breaking

Prevent cascading failures.

---

## Security Features

### Mutual TLS (mTLS)

Services authenticate each other.

```text
Service A
    ↔
Service B
```

Encrypted communication is enforced.

---

### Identity-Based Security

Access decisions can be based on workload identity.

---

## Observability

Provides visibility into:

- Latency
- Errors
- Traffic volume
- Service dependencies

Example:

```text
Who Called Which Service?
```

can be answered easily.

---

## Popular Service Meshes

### Istio

Most widely known Kubernetes service mesh.

---

### Linkerd

Lightweight and simple.

---

### Consul Connect

Service networking and service mesh platform.

---

## Service Mesh vs Kubernetes Service

| Feature | Kubernetes Service | Service Mesh |
|----------|----------|----------|
| Service Discovery | Yes | Yes |
| Load Balancing | Basic | Advanced |
| Traffic Splitting | No | Yes |
| mTLS | No | Yes |
| Observability | Limited | Extensive |
| Retries | No | Yes |

---

## Production Usage

Service Mesh is common in:

- Large microservice platforms
- Financial systems
- Enterprise Kubernetes platforms
- Multi-team environments

It becomes more valuable as service count grows.

---

## Common Production Failures

### Misconfigured Policies

Symptoms:

- Traffic failures

### Certificate Issues

Symptoms:

- mTLS communication problems

### Proxy Resource Consumption

Symptoms:

- Increased CPU and memory usage

### Complex Debugging

Symptoms:

- Additional troubleshooting layers

---

## Common Interview Questions

- What is a Service Mesh?
- Why is a Service Mesh needed?
- What is mTLS?
- What is the difference between a Service and a Service Mesh?
- What is a sidecar proxy?
- What is Istio?
- How does traffic splitting work?
- When should a Service Mesh be used?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Service Mesh | Service Communication Layer |
| Data Plane | Handles Traffic |
| Control Plane | Manages Policies |
| Sidecar Proxy | Traffic Interception |
| mTLS | Secure Service Communication |
| Traffic Splitting | Canary Deployments |
| Observability | Traffic Visibility |
| Popular Mesh | Istio |
| Common Drawback | Operational Complexity |
| Core Goal | Secure And Manage Service Communication |