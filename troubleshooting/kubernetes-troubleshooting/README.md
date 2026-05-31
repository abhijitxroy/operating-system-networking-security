# Kubernetes Troubleshooting

## Why Kubernetes Troubleshooting Exists

Kubernetes simplifies large-scale workload orchestration.

It also introduces multiple abstraction layers.

Engineers must troubleshoot:

- Pods
- Nodes
- Services
- Ingress
- Networking
- Storage
- Scheduling
- Control Plane Components

Kubernetes troubleshooting exists to systematically identify failures across these layers.

---

## The Engineering Problem

Applications running on Kubernetes depend on many components.

```text
Application
      ↓
Pod
      ↓
Node
      ↓
Cluster
      ↓
Cloud Infrastructure
```

A visible application failure may originate from any layer.

The challenge is identifying the actual failure domain.

---

## The Biggest Kubernetes Mistake

Many engineers immediately investigate application code.

In reality, the issue may be:

- Scheduling failures
- Resource limits
- DNS problems
- Service discovery failures
- Network policies
- Storage issues

Always start with evidence.

---

## Common Kubernetes Failure Domains

### Workloads

Examples:

- Pods
- Deployments
- StatefulSets

### Scheduling

Examples:

- Resource constraints
- Node affinity
- Taints and tolerations

### Networking

Examples:

- Services
- Ingress
- DNS
- CNI

### Storage

Examples:

- Persistent Volumes
- Persistent Volume Claims

### Cluster Infrastructure

Examples:

- Nodes
- Control Plane
- Cloud Resources

---

## A Practical Troubleshooting Workflow

```text
Identify Impact
      ↓
Identify Failure Domain
      ↓
Review Events
      ↓
Review Logs
      ↓
Validate Dependencies
      ↓
Find Root Cause
```

---

## Pod Troubleshooting

Pods are often the first investigation point.

Common symptoms:

- CrashLoopBackOff
- ImagePullBackOff
- Pending State
- OOMKilled

Useful commands:

```bash
kubectl get pods
kubectl describe pod
kubectl logs
```

Always inspect events before making assumptions.

---

## Scheduling Troubleshooting

Pods may fail to schedule.

Common causes:

- Insufficient CPU
- Insufficient Memory
- Taints
- Affinity Rules
- Node Conditions

Useful commands:

```bash
kubectl describe pod
kubectl get nodes
```

---

## Networking Troubleshooting

Networking is a major source of Kubernetes incidents.

Common symptoms:

- Service unreachable
- DNS failures
- Connection timeouts

Investigation:

- Service configuration
- Endpoint availability
- DNS resolution
- Network policies
- Ingress configuration

Useful commands:

```bash
kubectl get svc
kubectl get endpoints
nslookup
```

---

## Resource Troubleshooting

Resource limits frequently cause production issues.

Symptoms:

- OOMKilled
- CPU throttling
- Pod restarts

Investigation:

```bash
kubectl top pod
kubectl top node
```

Review:

- Requests
- Limits
- Utilization

---

## Storage Troubleshooting

Storage failures affect stateful workloads.

Common symptoms:

- Pending PVCs
- Mount failures
- Application startup failures

Investigation:

```bash
kubectl get pvc
kubectl describe pvc
```

---

## Production Impact

Kubernetes failures can affect:

- Multiple applications
- Entire clusters
- Platform availability
- Deployment pipelines
- Customer-facing services

The blast radius often extends beyond a single workload.

---

## Common Production Failures

### CrashLoopBackOff

Symptoms:

- Continuous restarts

Common causes:

- Application failures
- Missing configuration
- Dependency failures

### ImagePullBackOff

Symptoms:

- Pods never start

Common causes:

- Registry issues
- Authentication failures

### OOMKilled

Symptoms:

- Frequent pod restarts

Common causes:

- Insufficient memory limits

### DNS Failures

Symptoms:

- Service discovery issues

Common causes:

- CoreDNS issues
- Network problems

### Node Pressure

Symptoms:

- Evictions
- Scheduling failures

Common causes:

- CPU exhaustion
- Memory exhaustion
- Disk pressure

---

## Investigation Mindset

```text
Symptom
   ↓
Events
   ↓
Logs
   ↓
Dependencies
   ↓
Resource Analysis
   ↓
Root Cause
```

Kubernetes troubleshooting is often dependency troubleshooting.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Higher Abstraction | Reduced Visibility |
| Automated Scheduling | More Complexity |
| Rapid Scaling | More Failure Modes |
| Resource Isolation | Configuration Overhead |
| Platform Flexibility | Harder Debugging |

---

## Interview Thinking

- How would you troubleshoot a failing pod?
- CrashLoopBackOff vs ImagePullBackOff?
- How would you investigate Pending pods?
- Why do Kubernetes networking issues occur frequently?
- How would you troubleshoot service discovery failures?
- What causes OOMKilled events?
- How would you investigate node pressure?
- Kubernetes issue vs application issue?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Kubernetes Troubleshooting | Multi-Layer Investigation |
| Pod | Primary Workload Unit |
| CrashLoopBackOff | Repeated Container Failure |
| ImagePullBackOff | Image Retrieval Failure |
| OOMKilled | Memory Exhaustion |
| Service | Internal Traffic Routing |
| DNS | Service Discovery |
| PVC | Persistent Storage Request |
| Node Pressure | Resource Exhaustion |
| Events | First Source Of Evidence |