

# Cloud Networking

## Why Cloud Networking Exists

Traditional networking was designed around physical infrastructure.

Engineers managed:

- Physical switches
- Physical routers
- Dedicated firewalls
- Fixed network boundaries

Cloud computing introduced a different challenge.

Infrastructure became:

- Dynamic
- Distributed
- API-driven
- Multi-tenant

Cloud networking was created to provide network isolation, connectivity and security without requiring engineers to manage physical networking devices directly.

---

## The Engineering Problem

Organizations wanted:

- Faster provisioning
- Global connectivity
- Secure isolation
- Elastic scaling
- Multi-region architectures

Without cloud networking:

```text
Application
      ↓
Physical Network Changes
      ↓
Slow Delivery
```

Cloud providers introduced software-defined networking.

```text
Application
      ↓
Virtual Network
      ↓
Cloud Infrastructure
```

This dramatically increased operational speed.

---

## What Cloud Networking Actually Does

Cloud networking provides:

- Virtual networks
- Network isolation
- Routing
- Load balancing
- Security controls
- Hybrid connectivity
- Multi-region communication

Engineers consume networking as a platform capability rather than building physical networks.

---

## Virtual Private Cloud (VPC)

The VPC is the foundation of most cloud networking architectures.

A VPC provides:

- Logical isolation
- Private address space
- Route management
- Security boundaries

Think of a VPC as a virtual data center network.

---

## Subnets

Subnets divide networks into smaller segments.

Common patterns:

```text
Public Subnet
    ↓
Internet Facing Services

Private Subnet
    ↓
Internal Services
```

Benefits:

- Better isolation
- Security segmentation
- Controlled access

---

## Route Tables

Route tables determine packet paths.

Questions they answer:

```text
Destination?
      ↓
Which Path?
```

Incorrect routes are one of the most common cloud networking issues.

---

## Security Groups And Network Controls

Cloud platforms commonly provide:

- Security Groups
- Network ACLs
- Firewall Rules

Purpose:

```text
Control Traffic
      ↓
Reduce Exposure
```

Misconfigured security rules are a frequent cause of outages.

---

## Hybrid Networking

Many organizations operate:

```text
On-Premises
      ↔
Cloud
```

Common solutions:

- VPN
- Direct Connect
- ExpressRoute
- Dedicated Interconnects

Hybrid networking enables gradual cloud adoption.

---

## Production Impact

Cloud networking directly affects:

- Application availability
- Service connectivity
- Security posture
- Multi-region deployments
- Kubernetes clusters
- Disaster recovery

Networking problems often appear as application failures.

---

## Common Production Failures

### Security Group Misconfiguration

Symptoms:

- Connection timeouts
- Services unreachable

Investigation:

- Security rules review
- Port verification

### Route Table Errors

Symptoms:

- Traffic blackholes
- Connectivity failures

Investigation:

- Route validation
- Network path analysis

### DNS Problems

Symptoms:

- Service discovery failures
- Resolution errors

Investigation:

- DNS records
- Resolver configuration

### Hybrid Connectivity Issues

Symptoms:

- Intermittent communication
- Cross-network failures

Investigation:

- VPN status
- Route propagation
- Gateway health

---

## Production Debugging Workflow

```text
Identify Impact
       ↓
Validate DNS
       ↓
Validate Routing
       ↓
Validate Security Rules
       ↓
Validate Network Path
       ↓
Find Root Cause
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Strong Isolation | Increased Complexity |
| Multi-Region Design | Higher Cost |
| Security Controls | Operational Overhead |
| Hybrid Connectivity | Additional Failure Points |
| Flexibility | More Networking Abstractions |

---

## Interview Thinking

- Why was cloud networking invented?
- What problem does a VPC solve?
- Why do subnets exist?
- Security Group vs Network ACL?
- Why do route tables matter?
- How would you investigate a cloud connectivity issue?
- Why is hybrid networking difficult?
- How does cloud networking differ from traditional networking?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Cloud Networking | Software Defined Networking |
| VPC | Virtual Network Boundary |
| Subnet | Network Segmentation |
| Route Table | Traffic Path Decision |
| Security Group | Instance-Level Firewall |
| Network ACL | Subnet-Level Filtering |
| VPN | Secure Network Connectivity |
| Hybrid Network | Cloud + On-Prem Connectivity |
| DNS | Service Discovery |
| Multi-Region | Geographic Resilience |