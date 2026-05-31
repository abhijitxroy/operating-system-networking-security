

# Kubernetes Services

## Why Services Exist

Pods are temporary.

Example:

```text
Pod A
   ↓
Deleted
   ↓
Pod B
```

Pod IP addresses can change.

Question:

```text
How Can Applications
Use A Stable Endpoint
When Pods Continuously Change?
```

Kubernetes Services solve this problem.

---

## What Is A Service?

A Service is a stable network endpoint that provides access to a group of Pods.

Purpose:

```text
Service
   ↓
Backend Pods
```

Applications connect to the Service instead of individual Pods.

---

## The Engineering Problem

Suppose:

```text
Frontend Pod
      ↓
Backend Pods
```

Backend Pods may be:

```text
Created
Deleted
Scaled
Replaced
```

A Service provides a stable access layer.

---

## High-Level Architecture

```text
Client
  ↓
Service
  ↓
Pod A
Pod B
Pod C
```

The Service distributes traffic across available Pods.

---

## Service Selector

Services find Pods using labels.

Example:

```text
app=backend
```

Matching Pods automatically become service endpoints.

---

## ClusterIP Service

Default Service type.

```text
Cluster Internal Access
```

Example:

```text
Frontend
   ↓
Backend Service
```

Accessible only within the cluster.

---

## NodePort Service

Exposes a Service through a node port.

```text
Client
   ↓
NodeIP:Port
   ↓
Service
```

Useful for simple external access.

---

## LoadBalancer Service

Integrates with cloud load balancers.

```text
Internet
   ↓
Cloud Load Balancer
   ↓
Service
```

Common in production cloud environments.

---

## ExternalName Service

Maps a Service to an external DNS name.

Example:

```text
database-service
        ↓
external-db.company.com
```

Useful for integrating external systems.

---

## Endpoints

A Service maintains a list of backend Pods.

Example:

```text
Service
   ↓
Pod A
Pod B
Pod C
```

Traffic is routed only to healthy endpoints.

---

## Services And kube-proxy

kube-proxy implements Service networking.

```text
Service IP
      ↓
kube-proxy
      ↓
Pods
```

It handles routing and load balancing.

---

## Services And DNS

CoreDNS automatically creates DNS records.

Example:

```text
backend.default.svc.cluster.local
```

Applications use names instead of IP addresses.

---

## Typical Request Flow

```text
Application
      ↓
DNS Lookup
      ↓
Service IP
      ↓
kube-proxy
      ↓
Backend Pod
```

This is one of the most common traffic flows in Kubernetes.

---

## Production Usage

Services are used by:

- Microservices
- APIs
- Stateful applications
- Platform services
- Service meshes

Nearly every Kubernetes application depends on Services.

---

## Common Production Failures

### Wrong Selector

Symptoms:

- No backend endpoints

### Missing Pods

Symptoms:

- Service unavailable

### DNS Issues

Symptoms:

- Service discovery failures

### Port Misconfiguration

Symptoms:

- Connection failures

---

## Useful Commands

```bash
kubectl get svc
```

```bash
kubectl describe svc <service-name>
```

```bash
kubectl get endpoints
```

---

## Common Interview Questions

- What is a Kubernetes Service?
- Why are Services needed?
- ClusterIP vs NodePort vs LoadBalancer?
- What is an ExternalName Service?
- How does a Service find Pods?
- What are Endpoints?
- How do Services work with DNS?
- What role does kube-proxy play?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Service | Stable Endpoint |
| ClusterIP | Internal Access |
| NodePort | Node-Based Access |
| LoadBalancer | External Cloud Access |
| ExternalName | External DNS Mapping |
| Selector | Finds Pods |
| Endpoints | Backend Pods |
| DNS | Service Discovery |
| kube-proxy | Traffic Routing |
| Core Goal | Stable Access To Pods |