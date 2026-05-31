

# VPC Peering

## Why VPC Peering Exists

Organizations often deploy workloads across multiple VPCs.

Examples:

- Production VPC
- Development VPC
- Shared Services VPC
- Security VPC

Question:

```text
How Can Two VPCs
Communicate Privately
Without Using The Internet?
```

VPC Peering solves this problem.

---

## What Is VPC Peering?

VPC Peering is a networking connection between two VPCs.

Purpose:

```text
VPC A
  ↕
VPC B
```

Resources in both VPCs can communicate using private IP addresses.

---

## The Engineering Problem

Suppose:

```text
Application
      ↓
VPC A

Database
     ↓
VPC B
```

Question:

```text
How Can They Communicate
Without Exposing Traffic
To The Internet?
```

A VPC peering connection provides direct private connectivity.

---

## High-Level Architecture

```text
VPC A
   ↔
VPC Peering
   ↔
VPC B
```

Traffic remains on the cloud provider's private network.

---

## How VPC Peering Works

Steps:

```text
Create Peering Connection
         ↓
Accept Connection
         ↓
Update Route Tables
         ↓
Allow Traffic
```

After configuration, resources can communicate privately.

---

## Route Table Requirements

Example:

```text
VPC A CIDR
10.0.0.0/16

VPC B CIDR
10.1.0.0/16
```

Route in VPC A:

```text
10.1.0.0/16
      ↓
Peering Connection
```

Route in VPC B:

```text
10.0.0.0/16
      ↓
Peering Connection
```

---

## Security Requirements

Connectivity alone is not enough.

Security controls must also allow traffic.

Examples:

- Security Groups
- NACLs
- Firewall Rules

---

## Benefits

### Private Communication

Traffic does not traverse the public Internet.

### Low Latency

Uses provider internal networking.

### Simpler Architecture

Direct connectivity between VPCs.

### No VPN Required

For many cloud-only scenarios.

---

## VPC Peering Limitations

### No Transitive Routing

Example:

```text
VPC A ↔ VPC B
VPC B ↔ VPC C
```

Does NOT mean:

```text
VPC A ↔ VPC C
```

Traffic is not automatically forwarded.

---

### Scaling Challenges

As VPC count increases:

```text
More Peering Connections
```

Operational complexity grows rapidly.

---

### Overlapping CIDR Blocks

Peering generally requires:

```text
Non-Overlapping Networks
```

---

## VPC Peering vs Transit Gateway

| Feature | VPC Peering | Transit Gateway |
|----------|----------|----------|
| Architecture | Point-To-Point | Hub And Spoke |
| Scaling | Limited | High |
| Route Management | Distributed | Centralized |
| Best For | Few VPCs | Many VPCs |
| Operational Complexity | Higher At Scale | Lower |

---

## Production Usage

Common scenarios:

- Shared services access
- Cross-team communication
- Multi-VPC architectures
- Development and production separation
- Cloud-native platforms

---

## Common Production Failures

### Missing Route

Symptoms:

- Connectivity failure

### Security Group Restrictions

Symptoms:

- Traffic blocked

### Overlapping CIDR Ranges

Symptoms:

- Peering creation failure

### Incorrect Peering Configuration

Symptoms:

- Resources unreachable

---

## Common Interview Questions

- What is VPC Peering?
- Why is VPC Peering needed?
- How does VPC Peering work?
- What routes are required?
- What are the limitations of VPC Peering?
- What is transitive routing?
- VPC Peering vs Transit Gateway?
- Why are overlapping CIDRs a problem?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| VPC Peering | Private VPC Connectivity |
| Communication | Private IP Based |
| Internet Usage | Not Required |
| Route Tables | Must Be Updated |
| Security Controls | Still Required |
| Transitive Routing | Not Supported |
| CIDR Requirement | Non-Overlapping |
| Alternative | Transit Gateway |
| Common Failure | Missing Route |
| Core Goal | Private VPC Communication |