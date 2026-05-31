

# Network Policies

## Why Network Policies Exist

By default, many Kubernetes environments allow broad Pod-to-Pod communication.

Question:

```text
Should Every Pod
Be Able To Talk To
Every Other Pod?
```

Usually the answer is no.

Network Policies provide traffic control between workloads.

---

## What Is A Network Policy?

A Network Policy is a Kubernetes resource that controls network traffic between Pods.

Purpose:

```text
Allow
Or
Deny
Traffic
```

It acts like a firewall for Pod communication.

---

## The Engineering Problem

Suppose a cluster contains:

```text
Frontend Pods
Backend Pods
Database Pods
```

Question:

```text
Should Frontend Pods
Access Databases Directly?
```

Typical answer:

```text
Frontend
   ↓
Backend
   ↓
Database
```

Network Policies enforce these rules.

---

## High-Level Architecture

```text
Frontend Pod
      ↓ Allowed
Backend Pod
      ↓ Allowed
Database Pod
```

All other traffic can be blocked.

---

## Types Of Rules

### Ingress Rules

Control incoming traffic.

Example:

```text
Who Can Reach This Pod?
```

---

### Egress Rules

Control outgoing traffic.

Example:

```text
Where Can This Pod Connect?
```

---

## Pod Selectors

Policies target Pods using labels.

Example:

```text
app=backend
```

Only matching Pods are affected.

---

## Namespace Selectors

Policies can allow traffic from specific namespaces.

Example:

```text
production
```

while blocking others.

---

## Default Deny Model

Common security practice:

```text
Deny Everything
      ↓
Explicitly Allow
Required Traffic
```

This follows least-privilege principles.

---

## Example Security Design

```text
Frontend
   ↓
Backend
   ↓
Database
```

Allowed:

```text
Frontend → Backend
Backend → Database
```

Blocked:

```text
Frontend → Database
```

---

## Network Policies And CNI

Network Policies require CNI support.

Examples:

- Calico
- Cilium

Not all CNI implementations enforce Network Policies.

---

## Production Usage

Network Policies are critical for:

- Multi-tenant clusters
- Production environments
- Security-sensitive workloads
- Zero Trust architectures
- Regulatory compliance

---

## Common Production Failures

### Missing Policy

Symptoms:

- Excessive access

### Incorrect Selector

Symptoms:

- Policy not applied

### Overly Restrictive Policy

Symptoms:

- Application communication failure

### Unsupported CNI

Symptoms:

- Policies ignored

---

## Useful Commands

```bash
kubectl get networkpolicy
```

```bash
kubectl describe networkpolicy <name>
```

```bash
kubectl get networkpolicy -A
```

---

## Common Interview Questions

- What is a Network Policy?
- Why are Network Policies needed?
- Ingress vs Egress rules?
- How are Pods selected?
- What is a default deny policy?
- Do Network Policies work without CNI support?
- How do Network Policies support Zero Trust?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Network Policy | Pod Traffic Control |
| Ingress Rule | Incoming Traffic |
| Egress Rule | Outgoing Traffic |
| Pod Selector | Target Pods |
| Namespace Selector | Target Namespaces |
| Default Deny | Block By Default |
| Dependency | CNI Support |
| Main Benefit | Reduced Attack Surface |
| Common Failure | Incorrect Selectors |
| Core Goal | Secure Pod Communication |