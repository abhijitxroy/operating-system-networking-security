

# Container Network Interface (CNI)

## Why CNI Exists

Kubernetes schedules Pods across multiple nodes.

Question:

```text
How Do Pods
Get IP Addresses
And Communicate
Across Nodes?
```

Kubernetes itself does not implement networking.

CNI solves this problem.

---

## What Is CNI?

CNI stands for:

```text
Container Network Interface
```

It is a standard that allows networking plugins to configure container and Pod networking.

Purpose:

```text
Kubernetes
      ↓
CNI Plugin
      ↓
Pod Networking
```

---

## The Engineering Problem

Suppose Kubernetes creates a new Pod.

Question:

```text
How Does The Pod
Receive An IP Address?

How Does It Reach
Other Pods?
```

The CNI plugin performs this work.

---

## High-Level Architecture

```text
Pod
 ↓
CNI Plugin
 ↓
Node Network
 ↓
Other Pods
```

The plugin connects Pods to the cluster network.

---

## Responsibilities Of A CNI Plugin

### IP Address Assignment

Every Pod receives an IP address.

```text
Pod A → 10.x.x.x
Pod B → 10.x.x.x
```

---

### Network Configuration

Creates networking interfaces and routes.

---

### Pod Connectivity

Allows Pods to communicate.

```text
Pod A
  ↔
Pod B
```

---

### Cross-Node Networking

Enables communication between Pods running on different nodes.

---

## Kubernetes Networking Requirement

Kubernetes expects:

```text
Every Pod Can Reach
Every Other Pod
```

without NAT between Pods.

CNI implementations satisfy this requirement.

---

## Popular CNI Plugins

### Calico

Provides:

- Networking
- Network Policies
- Security controls

Widely used in production.

---

### Cilium

Uses:

```text
eBPF
```

Provides advanced networking and observability.

---

### Flannel

Simple networking-focused solution.

Good for learning environments.

---

### Weave Net

Provides overlay networking between nodes.

---

## Overlay vs Underlay Networking

### Overlay

Creates a virtual network above the physical network.

Example:

```text
VXLAN
```

Benefits:

- Easier deployment

Limitations:

- Additional overhead

---

### Underlay

Uses the physical network directly.

Benefits:

- Better performance

Limitations:

- More infrastructure requirements

---

## CNI And Network Policies

Some CNI plugins support:

```text
Network Policies
```

Used to control Pod-to-Pod communication.

Example:

```text
Allow
Deny
```

traffic between workloads.

---

## Production Usage

CNI plugins are fundamental for:

- Kubernetes clusters
- Managed Kubernetes services
- Platform engineering
- Cloud-native applications

Without a CNI plugin, Pods cannot communicate correctly.

---

## Common Production Failures

### IP Exhaustion

Symptoms:

- Pods fail to start

### Routing Problems

Symptoms:

- Cross-node connectivity failure

### Misconfigured Network Policies

Symptoms:

- Traffic unexpectedly blocked

### CNI Plugin Failure

Symptoms:

- Pod networking outage

---

## Common Interview Questions

- What is CNI?
- Why does Kubernetes need CNI?
- What responsibilities does a CNI plugin have?
- Calico vs Cilium?
- What is overlay networking?
- What is underlay networking?
- How do Pods receive IP addresses?
- How are Network Policies enforced?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| CNI | Container Network Interface |
| Purpose | Pod Networking |
| Responsibility | IP Assignment And Connectivity |
| Calico | Networking + Security |
| Cilium | eBPF-Based Networking |
| Flannel | Simple Networking |
| Overlay Network | Virtual Network Layer |
| Underlay Network | Physical Network Based |
| Common Failure | IP Exhaustion |
| Core Goal | Enable Kubernetes Networking |