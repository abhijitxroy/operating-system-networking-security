

# Subnetting

## Why Subnetting Exists

Networks can grow very large.

Example:

```text
10,000 Devices
In One Network
```

Problems:

- Large broadcast domains
- Difficult management
- Reduced performance
- Poor isolation

Question:

```text
How Can Large Networks
Be Divided Into Smaller
Manageable Networks?
```

Subnetting solves this problem.

---

## What Is Subnetting?

Subnetting is the process of dividing a network into smaller logical networks.

Purpose:

```text
One Large Network
        ↓
Multiple Smaller Networks
```

Each subnet becomes an independent network segment.

---

## The Engineering Problem

Suppose an organization owns:

```text
192.168.1.0/24
```

This provides:

```text
256 Addresses
```

Departments:

- Engineering
- HR
- Finance
- Operations

Question:

```text
How Can These Teams
Be Separated?
```

Subnetting provides the solution.

---

## IP Address Structure

IPv4 address:

```text
192.168.1.10
```

Contains:

```text
Network Portion
       +
Host Portion
```

Subnet masks determine the boundary.

---

## What Is A Subnet Mask?

Example:

```text
255.255.255.0
```

Equivalent CIDR:

```text
/24
```

Purpose:

```text
Identify Network
And Host Bits
```

---

## CIDR Notation

Examples:

```text
192.168.1.0/24
10.0.0.0/16
172.16.0.0/12
```

The number after '/' indicates network bits.

---

## Common Subnet Sizes

| CIDR | Total Addresses |
|----------|----------|
| /24 | 256 |
| /25 | 128 |
| /26 | 64 |
| /27 | 32 |
| /28 | 16 |
| /29 | 8 |
| /30 | 4 |

Very common interview topic.

---

## Example Subnetting

Original Network:

```text
192.168.1.0/24
```

Split into two subnets:

```text
192.168.1.0/25
192.168.1.128/25
```

Each subnet contains:

```text
128 Addresses
```

---

## Benefits Of Subnetting

### Smaller Broadcast Domains

Reduces unnecessary traffic.

### Better Security

Departments can be isolated.

### Easier Management

Networks become easier to organize.

### Better Scalability

Supports growth efficiently.

---

## Network Address And Broadcast Address

For:

```text
192.168.1.0/24
```

Network Address:

```text
192.168.1.0
```

Broadcast Address:

```text
192.168.1.255
```

Neither is assigned to hosts.

---

## Usable Host Addresses

For:

```text
192.168.1.0/24
```

Usable range:

```text
192.168.1.1
      ↓
192.168.1.254
```

---

## Production Impact

Subnetting is used everywhere:

- Data centers
- Cloud networks
- Kubernetes clusters
- Corporate networks
- VPC design
- Hybrid cloud environments

Good subnet planning prevents future scaling problems.

---

## Common Production Failures

### Incorrect Subnet Mask

Symptoms:

- Connectivity issues

### Overlapping Subnets

Symptoms:

- Routing confusion
- Traffic loss

### Poor Capacity Planning

Symptoms:

- Address exhaustion

### Incorrect CIDR Design

Symptoms:

- Scaling limitations

---

## Useful Commands

```bash
ip addr
```

```bash
ip route
```

```bash
ifconfig
```

Useful for validating subnet configuration.

---

## Common Interview Questions

- What is subnetting?
- Why is subnetting needed?
- What is a subnet mask?
- What is CIDR notation?
- How many addresses are in a /24 network?
- What is the difference between network and broadcast address?
- Why are overlapping subnets problematic?
- How do you calculate usable hosts?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Subnetting | Divide Networks |
| CIDR | Prefix Length |
| /24 | 256 Addresses |
| Subnet Mask | Network/Host Boundary |
| Network Address | Identifies Network |
| Broadcast Address | Reaches All Hosts |
| Usable Hosts | Between Network And Broadcast |
| Main Benefit | Smaller Network Segments |
| Common Failure | Overlapping Subnets |
| Core Goal | Efficient Address Management |