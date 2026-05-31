

# Pod Networking

## Why Pod Networking Exists

Pods are the fundamental execution units in Kubernetes.

Question:

```text
How Do Pods
Communicate With Each Other
Across A Cluster?
```

Pod networking provides the answer.

---

## What Is Pod Networking?

Pod networking is the networking model that allows Pods to communicate.

Kubernetes requires:

```text
Every Pod
Can Reach
Every Other Pod
```

without manual network configuration.

---

## The Engineering Problem

Suppose:

```text
Frontend Pod
      ↓
Backend Pod
      ↓
Database Pod
```

These Pods may run on different nodes.

Question:

```text
How Can They
Communicate Directly?
```

Kubernetes networking makes this possible.

---

## Core Kubernetes Networking Rule

Every Pod receives:

```text
Unique IP Address
```

Example:

```text
Pod A → 10.244.1.10
Pod B → 10.244.2.15
```

Pods communicate using IP networking.

---

## High-Level Architecture

```text
Pod A
   ↓
Cluster Network
   ↓
Pod B
```

The communication works regardless of node placement.

---

## Pod-To-Pod Communication

### Same Node

```text
Pod A
  ↔
Pod B
```

Traffic remains within the node.

---

### Different Nodes

```text
Pod A
   ↓
Node A
   ↓
Cluster Network
   ↓
Node B
   ↓
Pod B
```

Networking components handle routing automatically.

---

## Pod IP Addresses

Each Pod gets:

```text
One IP Address
```

Applications use these addresses for communication.

However, Pod IPs are temporary.

If a Pod is recreated:

```text
New Pod
   ↓
New IP Address
```

---

## Why Services Are Needed

Because Pod IPs change.

Example:

```text
Pod Deleted
      ↓
Pod Recreated
      ↓
New IP
```

Services provide stable endpoints.

---

## Role Of CNI

Container Network Interface (CNI) plugins implement Pod networking.

Examples:

- Calico
- Cilium
- Flannel

Responsibilities:

- Assign IP addresses
- Configure routes
- Enable Pod connectivity

---

## Kubernetes Networking Model

Key principle:

```text
Pods Are First-Class
Network Citizens
```

Meaning:

```text
Pod A
Can Reach
Pod B Directly
```

without special NAT rules.

---

## Production Usage

Pod networking is fundamental for:

- Microservices
- Service meshes
- Platform engineering
- Cloud-native applications
- Kubernetes platforms

Every workload depends on it.

---

## Common Production Failures

### CNI Failure

Symptoms:

- Pods cannot communicate

### IP Exhaustion

Symptoms:

- New Pods fail to start

### Routing Problems

Symptoms:

- Cross-node communication failure

### Network Policy Restrictions

Symptoms:

- Traffic unexpectedly blocked

---

## Useful Commands

```bash
kubectl get pods -o wide
```

```bash
kubectl describe pod <pod-name>
```

```bash
kubectl exec -it <pod-name> -- ping <ip>
```

---

## Common Interview Questions

- How does Pod networking work?
- Why does every Pod have an IP address?
- How do Pods communicate across nodes?
- Why are Services needed?
- What role does CNI play?
- What is meant by first-class network citizen?
- How would you troubleshoot Pod connectivity issues?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Pod Networking | Pod Communication Model |
| Pod IP | Unique Address |
| Same Node Traffic | Local Communication |
| Cross-Node Traffic | Cluster Networking |
| CNI | Networking Implementation |
| Service | Stable Endpoint |
| Pod IP Lifetime | Temporary |
| Main Dependency | CNI Plugin |
| Common Failure | Routing/CNI Issues |
| Core Goal | Enable Pod Connectivity |