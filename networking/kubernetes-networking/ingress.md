

# Ingress

## Why Ingress Exists

A Kubernetes cluster may contain many services.

Example:

```text
Frontend Service
API Service
Auth Service
```

Question:

```text
How Can External Users
Access Multiple Services
Using A Single Entry Point?
```

Ingress solves this problem.

---

## What Is Ingress?

Ingress is a Kubernetes resource that manages external HTTP and HTTPS access to services.

Purpose:

```text
Internet
    ↓
Ingress
    ↓
Services
```

It provides routing and traffic management.

---

## The Engineering Problem

Suppose a cluster contains:

```text
frontend-service
api-service
admin-service
```

Question:

```text
How Do We Route
Different Requests
To Different Services?
```

Ingress provides centralized routing.

---

## High-Level Architecture

```text
Internet
    ↓
Ingress Controller
    ↓
Ingress Rules
    ↓
Services
    ↓
Pods
```

Ingress itself defines rules.

The Ingress Controller implements them.

---

## Ingress Controller

Ingress resources require an Ingress Controller.

Examples:

- NGINX Ingress Controller
- Traefik
- HAProxy Ingress
- Cloud Provider Ingress Controllers

Without a controller, Ingress rules do nothing.

---

## Host-Based Routing

Example:

```text
api.example.com
      ↓
api-service

admin.example.com
      ↓
admin-service
```

Different hostnames route to different services.

---

## Path-Based Routing

Example:

```text
example.com/api
        ↓
api-service

example.com/admin
        ↓
admin-service
```

Useful for multiple applications behind one domain.

---

## TLS Termination

Ingress commonly handles:

```text
HTTPS
TLS Certificates
```

Example:

```text
Client
   ↓ HTTPS
Ingress
   ↓ HTTP/HTTPS
Service
```

Centralizes certificate management.

---

## Ingress vs Service

| Feature | Service | Ingress |
|----------|----------|----------|
| Purpose | Internal Access | External Access |
| Routing | Basic | Advanced |
| Host Rules | No | Yes |
| Path Rules | No | Yes |
| TLS Handling | Limited | Common |
| Entry Point | Service IP | Single Gateway |

---

## Production Usage

Ingress is commonly used for:

- Web applications
- APIs
- Microservices
- Multi-tenant platforms
- Kubernetes platforms

It is the standard HTTP/HTTPS entry point for many clusters.

---

## Common Production Failures

### Missing Ingress Controller

Symptoms:

- Routes do not work

### DNS Misconfiguration

Symptoms:

- Domain unreachable

### TLS Certificate Issues

Symptoms:

- HTTPS failures

### Incorrect Routing Rules

Symptoms:

- Traffic reaches wrong service

---

## Useful Commands

```bash
kubectl get ingress
```

```bash
kubectl describe ingress <name>
```

```bash
kubectl get ingress -A
```

---

## Common Interview Questions

- What is Ingress?
- Why is Ingress needed?
- What is an Ingress Controller?
- Host-based vs path-based routing?
- How is TLS handled in Kubernetes?
- Ingress vs Service?
- How would you expose multiple services externally?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Ingress | External HTTP/HTTPS Routing |
| Ingress Controller | Implements Ingress Rules |
| Host Routing | Domain Based Routing |
| Path Routing | URL Path Routing |
| TLS Termination | HTTPS Management |
| Entry Point | Single Gateway |
| Dependency | Ingress Controller |
| Common Failure | DNS/TLS Issues |
| Main Benefit | Centralized Access |
| Core Goal | Route External Traffic To Services |