# kube-proxy

## Why kube-proxy Exists

Pods are temporary.

Example:

```text
Pod A
Pod B
Pod C
```

Pods can be created, deleted, and replaced.

Question:

```text
How Can Applications
Use A Stable Endpoint
When Pods Continuously Change?
```

kube-proxy helps solve this problem.

---

## What Is kube-proxy?

kube-proxy is a Kubernetes networking component that implements Service networking.

Purpose:

```text
Service
   ↓
kube-proxy
   ↓
Pods
```

It routes traffic from Services to healthy backend Pods.

---

## The Engineering Problem

Suppose:

```text
frontend-service
```

must distribute traffic to:

```text
Pod A
Pod B
Pod C
```

Question:

```text
How Does Traffic Reach
The Correct Pod?
```

kube-proxy manages this routing.

---

## High-Level Architecture

```text
Client
  ↓
Service IP
  ↓
kube-proxy
  ↓
Backend Pods
```

Applications interact with the Service rather than individual Pods.

---

## Service Networking

Every Service receives a virtual IP.

Example:

```text
10.96.0.10
```

Applications send traffic to:

```text
Service IP
```

kube-proxy forwards requests to backend Pods.

---

## Load Balancing

Example:

```text
Request 1 → Pod A
Request 2 → Pod B
Request 3 → Pod C
```

Traffic is distributed across available Pods.

---

## Endpoint Updates

When Pods change:

```text
Old Pod Deleted
      ↓
New Pod Created
```

kube-proxy updates routing rules automatically.

Applications continue using the same Service address.

---

## kube-proxy Modes

### iptables Mode

Most common deployment mode.

Uses:

```text
iptables Rules
```

to route traffic.

---

### IPVS Mode

Uses:

```text
IP Virtual Server
```

Benefits:

- Better scalability
- Faster rule processing

Common in large clusters.

---

### eBPF-Based Replacements

Some modern CNIs reduce or replace kube-proxy functionality.

Example:

```text
Cilium
```

Uses eBPF for service routing.

---

## kube-proxy And Services

kube-proxy works with:

- ClusterIP
- NodePort
- LoadBalancer

It is a core component of Kubernetes Service networking.

---

## Production Usage

kube-proxy is present in most Kubernetes clusters.

Responsibilities:

- Service routing
- Load balancing
- Endpoint management

Without it, Services cannot function correctly.

---

## Common Production Failures

### kube-proxy Crash

Symptoms:

- Service connectivity failures

### Stale Rules

Symptoms:

- Traffic routed incorrectly

### Endpoint Issues

Symptoms:

- Requests fail intermittently

### Large Rule Sets

Symptoms:

- Performance degradation

---

## Useful Commands

```bash
kubectl get pods -n kube-system
```

```bash
kubectl logs <kube-proxy-pod> -n kube-system
```

```bash
kubectl get endpoints
```

---

## Common Interview Questions

- What is kube-proxy?
- Why is kube-proxy needed?
- How does a Service route traffic?
- kube-proxy vs CNI?
- iptables vs IPVS?
- What happens when Pods are replaced?
- Can Kubernetes Services work without kube-proxy?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| kube-proxy | Service Networking Component |
| Purpose | Route Service Traffic |
| Service IP | Stable Endpoint |
| Backend Pods | Actual Workloads |
| iptables | Common Routing Mode |
| IPVS | Scalable Routing Mode |
| Endpoint Updates | Automatic |
| Main Dependency | Kubernetes Services |
| Common Failure | Service Connectivity Issues |
| Core Goal | Connect Services To Pods |