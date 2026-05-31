

# DNS In Kubernetes

## Why DNS Is Needed In Kubernetes

Pods are temporary.

Example:

```text
Pod A
  ↓
Deleted
  ↓
New Pod Created
```

IP addresses can change.

Question:

```text
How Can Applications
Find Each Other
Without Hardcoding IPs?
```

DNS solves this problem.

---

## What Is DNS In Kubernetes?

Kubernetes provides built-in service discovery using DNS.

Purpose:

```text
Service Name
      ↓
IP Address
```

Applications communicate using names instead of IP addresses.

---

## The Engineering Problem

Suppose:

```text
Frontend Pod
      ↓
Backend Service
```

Question:

```text
How Does Frontend
Find Backend
When Pods Change?
```

DNS provides a stable lookup mechanism.

---

## High-Level Architecture

```text
Application
      ↓
DNS Query
      ↓
CoreDNS
      ↓
Service IP
```

The application receives the destination address automatically.

---

## CoreDNS

CoreDNS is the default DNS server in Kubernetes.

Responsibilities:

- Service discovery
- DNS resolution
- Cluster DNS management

Most Kubernetes clusters use CoreDNS.

---

## Service DNS Names

Example service:

```text
backend
```

DNS name:

```text
backend.default.svc.cluster.local
```

Components:

```text
service.namespace.svc.cluster.local
```

---

## Namespace Awareness

Different namespaces can contain services with the same name.

Example:

```text
backend.dev
backend.prod
```

DNS resolves them correctly.

---

## Service Discovery Flow

```text
Frontend Pod
      ↓
backend.default.svc.cluster.local
      ↓
CoreDNS
      ↓
ClusterIP
      ↓
Backend Pods
```

Applications rarely need Pod IPs directly.

---

## Pod DNS

Pods also receive DNS configuration.

Example:

```text
/etc/resolv.conf
```

contains DNS settings used for lookups.

---

## DNS And Services

Kubernetes automatically creates DNS records for:

- ClusterIP Services
- Headless Services
- Some Pod-based lookups

DNS is tightly integrated with Services.

---

## Headless Services

Normal Service:

```text
DNS → ClusterIP
```

Headless Service:

```text
DNS → Individual Pod IPs
```

Useful for:

- Stateful applications
- Databases
- Distributed systems

---

## Production Usage

DNS is critical for:

- Microservices
- Service discovery
- StatefulSets
- Service Meshes
- Platform engineering

Nearly every Kubernetes workload depends on DNS.

---

## Common Production Failures

### CoreDNS Failure

Symptoms:

- Service discovery stops working

### Incorrect Service Name

Symptoms:

- Application connection failures

### DNS Latency

Symptoms:

- Slow application communication

### Namespace Confusion

Symptoms:

- Wrong service resolution

---

## Useful Commands

Check DNS:

```bash
kubectl get svc -A
```

```bash
kubectl get pods -n kube-system
```

Test DNS:

```bash
nslookup backend
```

```bash
dig backend.default.svc.cluster.local
```

---

## Common Interview Questions

- How does DNS work in Kubernetes?
- What is CoreDNS?
- How are Services discovered?
- What is cluster.local?
- What is a headless Service?
- Why use DNS instead of Pod IPs?
- How would you troubleshoot Kubernetes DNS?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| CoreDNS | Kubernetes DNS Server |
| Purpose | Service Discovery |
| Service Name | Stable Endpoint |
| DNS Record | Name → Address |
| Namespace | DNS Isolation |
| Cluster Domain | cluster.local |
| Headless Service | DNS Returns Pod IPs |
| Main Dependency | Services |
| Common Failure | CoreDNS Issues |
| Core Goal | Find Services Reliably |