

# Public vs Private Subnets

## Why Subnets Exist In Cloud Networking

A VPC is usually divided into smaller network segments.

Question:

```text
Should Every Resource
Be Accessible From
The Internet?
```

The answer is usually no.

Cloud environments use public and private subnets to separate resources.

---

## What Is A Public Subnet?

A public subnet is a subnet whose route table contains a route to an Internet Gateway.

Example:

```text
Public Subnet
      ↓
Internet Gateway
      ↓
Internet
```

Resources can potentially communicate directly with the Internet.

---

## Common Public Subnet Resources

Examples:

- Public load balancers
- Bastion hosts
- Reverse proxies
- Public web servers

These resources must be reachable from outside the VPC.

---

## What Is A Private Subnet?

A private subnet does not provide direct inbound Internet access.

Example:

```text
Private Subnet
      ↓
No Direct Internet Access
```

Resources remain hidden from the public Internet.

---

## Common Private Subnet Resources

Examples:

- Application servers
- Databases
- Internal APIs
- Kubernetes worker nodes
- Backend services

These systems typically should not be exposed publicly.

---

## The Engineering Problem

Suppose an application consists of:

```text
Load Balancer
Application Server
Database
```

Question:

```text
Which Components
Should Be Public?

Which Components
Should Be Private?
```

Typical design:

```text
Load Balancer → Public
Application Server → Private
Database → Private
```

---

## High-Level Architecture

```text
Internet
    ↓
Public Subnet
    ↓
Load Balancer
    ↓
Private Subnet
    ↓
Application Servers
    ↓
Database
```

This is one of the most common cloud architectures.

---

## Internet Access For Private Subnets

Private resources sometimes need outbound Internet access.

Examples:

- Software updates
- Package downloads
- External APIs

This is commonly achieved using:

```text
NAT Gateway
```

---

## Public vs Private Comparison

| Feature | Public Subnet | Private Subnet |
|----------|----------|----------|
| Direct Internet Access | Yes | No |
| Internet Gateway Route | Yes | No |
| Public Resources | Yes | Usually No |
| Database Placement | Rare | Common |
| Application Placement | Sometimes | Common |
| Security Risk | Higher | Lower |

---

## Security Benefits

Private subnets provide:

- Reduced attack surface
- Better isolation
- Improved security posture
- Protection for sensitive services

A common cloud best practice is:

```text
Expose Only What Must Be Public
```

---

## Production Usage

Public Subnets:

- Internet-facing services
- Entry points

Private Subnets:

- Internal workloads
- Databases
- Backend systems

Most production workloads run primarily in private subnets.

---

## Common Production Failures

### Application In Wrong Subnet

Symptoms:

- Security exposure

### Missing NAT Gateway

Symptoms:

- No outbound Internet access

### Incorrect Route Tables

Symptoms:

- Connectivity failures

### Overexposed Services

Symptoms:

- Increased attack surface

---

## Common Interview Questions

- What is a public subnet?
- What is a private subnet?
- How does a private subnet access the Internet?
- Why place databases in private subnets?
- Public subnet vs private subnet?
- What role does a NAT Gateway play?
- What route makes a subnet public?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Public Subnet | Direct Internet Connectivity |
| Private Subnet | No Direct Internet Access |
| Internet Gateway | Enables Public Access |
| NAT Gateway | Private Outbound Access |
| Public Resource | Load Balancer |
| Private Resource | Database |
| Main Benefit | Security Isolation |
| Common Failure | Wrong Subnet Placement |
| Best Practice | Minimize Public Exposure |
| Core Goal | Secure Workload Separation |