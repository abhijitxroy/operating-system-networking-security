

# Virtual Private Cloud (VPC)

## Why VPC Exists

Organizations need isolated networking environments in the cloud.

Question:

```text
How Can Multiple Customers
Use The Same Cloud Provider
Without Sharing Networks?
```

A Virtual Private Cloud (VPC) solves this problem.

---

## What Is A VPC?

VPC stands for:

```text
Virtual Private Cloud
```

A VPC is a logically isolated network inside a cloud provider.

Purpose:

```text
Cloud Provider
      ↓
Virtual Private Cloud
      ↓
Your Resources
```

It provides control over networking, routing, and security.

---

## The Engineering Problem

Suppose an organization deploys:

```text
Applications
Databases
Load Balancers
```

Question:

```text
Where Should These
Resources Live?
```

The VPC becomes the network boundary for these resources.

---

## High-Level Architecture

```text
VPC
 ├── Public Subnet
 ├── Private Subnet
 ├── Route Tables
 ├── Security Controls
 └── Cloud Resources
```

Most cloud networking components exist inside a VPC.

---

## CIDR Block

A VPC is assigned an IP address range.

Example:

```text
10.0.0.0/16
```

This CIDR block defines available addresses.

Example capacity:

```text
10.0.0.0 - 10.0.255.255
```

---

## Subnets

VPCs are divided into subnets.

Example:

```text
10.0.1.0/24
Public Subnet

10.0.2.0/24
Private Subnet
```

Subnets help organize workloads.

---

## Route Tables

Route tables determine where traffic should go.

Example:

```text
Destination
      ↓
Target
```

Used for:

- Internet access
- Private routing
- VPN connectivity
- VPC peering

---

## Internet Gateway

Provides Internet connectivity.

```text
VPC
 ↓
Internet Gateway
 ↓
Internet
```

Typically used by public subnets.

---

## NAT Gateway

Provides outbound Internet access for private resources.

```text
Private Subnet
      ↓
NAT Gateway
      ↓
Internet
```

Inbound Internet access remains blocked.

---

## Security Groups

Virtual firewalls attached to resources.

Examples:

- Virtual machines
- Databases
- Load balancers

Security Groups control resource-level traffic.

---

## Network ACLs (NACLs)

Subnet-level security controls.

Purpose:

```text
Subnet Boundary Protection
```

Provide additional filtering.

---

## Public And Private Design

Common architecture:

```text
Internet
    ↓
Load Balancer
(Public Subnet)
    ↓
Application Servers
(Private Subnet)
    ↓
Database
(Private Subnet)
```

This is a widely used production pattern.

---

## Production Benefits

### Isolation

Networks remain logically separated.

### Security

Fine-grained traffic control.

### Scalability

Supports large environments.

### Flexibility

Custom network architecture.

---

## Common Production Failures

### Overlapping CIDR Ranges

Symptoms:

- Connectivity problems

### Incorrect Route Tables

Symptoms:

- Traffic failures

### Wrong Subnet Placement

Symptoms:

- Security exposure

### Misconfigured Security Groups

Symptoms:

- Services unreachable

---

## Cloud Architecture Relevance

Every major cloud provider offers a VPC-like concept.

Examples:

- AWS VPC
- Azure Virtual Network (VNet)
- Google Cloud VPC

The concept is fundamental to cloud networking.

---

## Common Interview Questions

- What is a VPC?
- Why is a VPC needed?
- What is a CIDR block?
- What is the difference between a VPC and a subnet?
- How does Internet access work?
- What is a NAT Gateway?
- Security Groups vs NACL?
- How would you design a secure VPC?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| VPC | Isolated Cloud Network |
| CIDR | IP Address Range |
| Subnet | Smaller Network Segment |
| Route Table | Traffic Routing |
| Internet Gateway | Public Connectivity |
| NAT Gateway | Private Outbound Access |
| Security Group | Resource Firewall |
| NACL | Subnet Firewall |
| Common Pattern | Public + Private Subnets |
| Core Goal | Secure Cloud Networking Foundation |