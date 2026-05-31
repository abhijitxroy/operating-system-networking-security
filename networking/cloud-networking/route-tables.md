

# Route Tables

## Why Route Tables Exist

Networks need rules that determine where traffic should go.

Question:

```text
When A Packet Leaves
A Resource,
How Does The Network Know
Where To Send It?
```

Route tables solve this problem.

---

## What Is A Route Table?

A route table is a collection of routing rules.

Purpose:

```text
Destination
      ↓
Next Hop
```

It tells the network how traffic should be forwarded.

---

## The Engineering Problem

Suppose a server needs to reach:

```text
Internet
Another Subnet
VPN Connection
```

Question:

```text
Which Path Should
The Traffic Follow?
```

The route table provides the answer.

---

## High-Level Architecture

```text
Instance
    ↓
Route Table
    ↓
Destination
```

Every packet is evaluated against routing rules.

---

## Route Structure

A route typically contains:

```text
Destination CIDR
        ↓
Target
```

Example:

```text
10.0.0.0/16
        ↓
Local
```

---

## Local Route

Every VPC includes a local route.

Example:

```text
10.0.0.0/16
      ↓
Local
```

This allows communication between subnets inside the VPC.

---

## Internet Route

Example:

```text
0.0.0.0/0
      ↓
Internet Gateway
```

Meaning:

```text
All Unknown Destinations
Go To Internet Gateway
```

This is commonly used in public subnets.

---

## NAT Gateway Route

Private subnets commonly use:

```text
0.0.0.0/0
      ↓
NAT Gateway
```

This enables outbound Internet access while keeping resources private.

---

## VPN Route

Example:

```text
192.168.0.0/16
         ↓
VPN Gateway
```

Traffic is sent to an on-premises network.

---

## Route Evaluation

Networks use:

```text
Longest Prefix Match
```

Most specific route wins.

Example:

```text
10.0.0.0/16
10.0.1.0/24
```

Traffic matching:

```text
10.0.1.10
```

uses:

```text
10.0.1.0/24
```

because it is more specific.

---

## Public Subnet Example

```text
Destination     Target
10.0.0.0/16     Local
0.0.0.0/0       Internet Gateway
```

Provides Internet connectivity.

---

## Private Subnet Example

```text
Destination     Target
10.0.0.0/16     Local
0.0.0.0/0       NAT Gateway
```

Provides outbound-only Internet access.

---

## Production Usage

Route tables are used for:

- VPC networking
- Internet access
- Hybrid cloud connectivity
- VPC peering
- Transit gateways
- Multi-region networking

They are fundamental to cloud network design.

---

## Common Production Failures

### Missing Route

Symptoms:

- Resource unreachable

### Wrong Target

Symptoms:

- Traffic blackholed

### Incorrect CIDR Range

Symptoms:

- Partial connectivity

### Route Conflicts

Symptoms:

- Unexpected routing behavior

---

## Common Interview Questions

- What is a route table?
- Why are route tables needed?
- What is a default route?
- What does 0.0.0.0/0 mean?
- What is longest prefix match?
- How does a private subnet reach the Internet?
- What routes are required for a public subnet?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Route Table | Traffic Routing Rules |
| Route | Destination → Target |
| Local Route | Internal VPC Communication |
| Default Route | 0.0.0.0/0 |
| Internet Route | Internet Gateway |
| Private Internet Access | NAT Gateway |
| VPN Route | On-Prem Connectivity |
| Longest Prefix Match | Most Specific Route Wins |
| Common Failure | Missing Route |
| Core Goal | Direct Traffic Correctly |