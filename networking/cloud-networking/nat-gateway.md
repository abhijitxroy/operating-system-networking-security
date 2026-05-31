

# NAT Gateway

## Why NAT Gateway Exists

Many cloud resources should access the Internet but should not be directly accessible from the Internet.

Examples:

- Application servers
- Internal services
- Backend workers
- Database support services

Question:

```text
How Can Private Resources
Access The Internet
Without Becoming Public?
```

A NAT Gateway solves this problem.

---

## What Is A NAT Gateway?

NAT stands for:

```text
Network Address Translation
```

A NAT Gateway allows resources in private subnets to initiate outbound Internet connections.

Purpose:

```text
Private Subnet
      ↓
NAT Gateway
      ↓
Internet
```

Inbound Internet connections are not allowed.

---

## The Engineering Problem

Suppose an application server runs in a private subnet.

Requirements:

```text
Download Updates
Call External APIs
Pull Container Images
```

Question:

```text
How Can It Reach
The Internet
Without A Public IP?
```

The NAT Gateway provides the answer.

---

## High-Level Architecture

```text
Private Instance
       ↓
Private Subnet
       ↓
NAT Gateway
       ↓
Internet Gateway
       ↓
Internet
```

The NAT Gateway is typically deployed in a public subnet.

---

## How NAT Works

Private resources use private IP addresses.

Example:

```text
10.0.1.10
```

The NAT Gateway translates traffic to a public address.

```text
Private IP
     ↓
Public IP
     ↓
Internet
```

Responses are returned to the original private resource.

---

## NAT Gateway Requirements

### Public Subnet

The NAT Gateway must reside in a public subnet.

---

### Internet Gateway

The VPC requires an Internet Gateway.

---

### Route Table

Private subnet route:

```text
0.0.0.0/0
      ↓
NAT Gateway
```

Internet-bound traffic is forwarded to the NAT Gateway.

---

## Private Subnet Relationship

Typical architecture:

```text
Public Subnet
      ↓
Internet Gateway

Private Subnet
      ↓
NAT Gateway
      ↓
Internet
```

Private resources remain hidden from direct Internet access.

---

## NAT Gateway vs Internet Gateway

| Feature | NAT Gateway | Internet Gateway |
|----------|----------|----------|
| Outbound Internet Access | Yes | Yes |
| Inbound Internet Access | No | Yes |
| Public IP Required On Instance | No | Usually Yes |
| Private Subnet Support | Yes | No |
| Primary Use | Private Resources | Public Resources |

---

## Production Usage

Common use cases:

- Private application servers
- Kubernetes worker nodes
- Internal microservices
- Backend processing systems
- Secure cloud architectures

Most production cloud environments use NAT gateways extensively.

---

## Common Production Failures

### Missing Route Table Entry

Symptoms:

- No outbound Internet access

### NAT Gateway Failure

Symptoms:

- Private resources lose connectivity

### Incorrect Subnet Placement

Symptoms:

- NAT does not function correctly

### Missing Internet Gateway

Symptoms:

- External communication fails

---

## Cloud Architecture Relevance

NAT Gateways are commonly used with:

```text
VPC
 ↓
Private Subnets
 ↓
Route Tables
 ↓
Internet Gateway
```

These concepts form the foundation of cloud network design.

---

## Common Interview Questions

- What is a NAT Gateway?
- Why is a NAT Gateway needed?
- NAT Gateway vs Internet Gateway?
- Why place application servers in private subnets?
- Can inbound Internet traffic reach a private instance through NAT?
- Where should a NAT Gateway be deployed?
- What route table entry is required?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| NAT Gateway | Private To Internet Connectivity |
| NAT | Network Address Translation |
| Private Subnet | No Direct Internet Access |
| Outbound Access | Allowed |
| Inbound Access | Blocked |
| Route Table | Direct Traffic To NAT |
| Internet Gateway | Required For External Access |
| Common Use Case | Private Application Servers |
| Common Failure | Missing Route |
| Core Goal | Secure Internet Access For Private Resources |