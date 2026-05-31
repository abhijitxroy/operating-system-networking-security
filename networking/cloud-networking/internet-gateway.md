

# Internet Gateway

## Why Internet Gateway Exists

Cloud resources inside a VPC are isolated by default.

Question:

```text
How Can Resources
Communicate With
The Internet?
```

An Internet Gateway solves this problem.

---

## What Is An Internet Gateway?

An Internet Gateway (IGW) is a cloud networking component that enables communication between a VPC and the Internet.

Purpose:

```text
VPC
 ↓
Internet Gateway
 ↓
Internet
```

It acts as the entry and exit point for Internet traffic.

---

## The Engineering Problem

Suppose a web server runs inside a VPC.

Question:

```text
How Can Users
Access The Website
From The Internet?
```

Without an Internet Gateway:

```text
Internet Access
      ❌
```

The server remains unreachable from outside the VPC.

---

## High-Level Architecture

```text
Internet
    ↓
Internet Gateway
    ↓
Public Subnet
    ↓
Web Server
```

Traffic flows through the Internet Gateway.

---

## How Internet Access Works

Requirements:

### Internet Gateway Attached

```text
VPC
 ↓
Internet Gateway
```

---

### Route Table Entry

Example:

```text
0.0.0.0/0
      ↓
Internet Gateway
```

This route sends Internet-bound traffic to the IGW.

---

### Public IP Address

The resource typically needs:

```text
Public IP
```

or

```text
Elastic/Public Address
```

depending on the cloud provider.

---

## Public Subnet Relationship

A subnet becomes effectively public when:

```text
Route To Internet Gateway
```

exists.

Example:

```text
Public Subnet
      ↓
Internet Gateway
      ↓
Internet
```

---

## Inbound And Outbound Traffic

### Inbound

```text
Internet
    ↓
Application
```

Users access services.

---

### Outbound

```text
Application
     ↓
Internet
```

Resources access updates, APIs, and external services.

---

## Internet Gateway vs NAT Gateway

| Feature | Internet Gateway | NAT Gateway |
|----------|----------|----------|
| Internet Access | Yes | Yes |
| Inbound Internet Traffic | Yes | No |
| Public Resources | Yes | No |
| Private Resources | No | Yes |
| Primary Use | Public Access | Outbound Only |

---

## Production Usage

Internet Gateways are commonly used for:

- Public websites
- APIs
- Load balancers
- Bastion hosts
- Internet-facing applications

They are a foundational cloud networking component.

---

## Common Production Failures

### Missing Route

Symptoms:

- No Internet connectivity

### Missing Public IP

Symptoms:

- Resource unreachable

### Security Group Restrictions

Symptoms:

- Traffic blocked

### Incorrect Subnet Design

Symptoms:

- Public service inaccessible

---

## Cloud Architecture Relevance

Internet Gateways are closely related to:

```text
VPC
 ↓
Subnets
 ↓
Route Tables
 ↓
Security Groups
```

These concepts are frequently used together.

---

## Common Interview Questions

- What is an Internet Gateway?
- Why is an Internet Gateway needed?
- How does a public subnet work?
- Internet Gateway vs NAT Gateway?
- Does an Internet Gateway provide security?
- What route table entry is required?
- Why might an instance still be unreachable after attaching an IGW?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Internet Gateway | VPC To Internet Connectivity |
| Public Subnet | Route To IGW |
| Route Table | Direct Traffic |
| Public IP | Internet Reachability |
| Inbound Traffic | Allowed |
| Outbound Traffic | Allowed |
| IGW | Public Access |
| NAT Gateway | Private Outbound Access |
| Common Failure | Missing Route |
| Core Goal | Enable Internet Connectivity |