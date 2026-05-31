

# VLAN (Virtual Local Area Network)

## Why VLANs Exist

Large networks often contain many devices.

Example:

```text
Engineering
HR
Finance
Operations
```

If all devices share one network:

- Large broadcast domains
- Poor isolation
- Security concerns
- Difficult management

Question:

```text
How Can One Physical Network
Be Split Into Multiple
Logical Networks?
```

VLANs solve this problem.

---

## What Is A VLAN?

VLAN stands for:

```text
Virtual Local Area Network
```

Purpose:

```text
One Physical Switch
         ↓
Multiple Logical Networks
```

Devices in different VLANs behave as if they are on separate networks.

---

## The Engineering Problem

Suppose a company has:

```text
100 Devices
One Switch Infrastructure
```

Requirements:

```text
Engineering Separate From HR
Finance Separate From Operations
```

Without buying separate switches.

VLANs provide logical segmentation.

---

## VLAN Example

```text
VLAN 10 → Engineering
VLAN 20 → HR
VLAN 30 → Finance
```

Even when connected to the same switch.

Devices communicate freely within the same VLAN.

---

## Broadcast Domains

Each VLAN creates a separate broadcast domain.

Example:

```text
VLAN 10
      ↓
Broadcast Stays Inside VLAN 10
```

Benefits:

- Reduced broadcast traffic
- Better performance
- Better isolation

---

## VLAN IDs

Each VLAN has an identifier.

Example:

```text
VLAN 10
VLAN 20
VLAN 30
```

Typical VLAN range:

```text
1 - 4094
```

---

## Access Ports

An access port belongs to a single VLAN.

Example:

```text
PC
 ↓
Switch Port
 ↓
VLAN 10
```

Common for:

- User devices
- Printers
- Servers

---

## Trunk Ports

A trunk carries multiple VLANs.

Example:

```text
Switch A
    ↕
Trunk Link
    ↕
Switch B
```

Used between:

- Switches
- Switch and Router
- Switch and Firewall

---

## Inter-VLAN Communication

Different VLANs cannot communicate directly.

Example:

```text
VLAN 10
      X
VLAN 20
```

A Layer 3 device is required.

Example:

```text
Router
or
Layer 3 Switch
```

---

## VLAN Benefits

### Better Security

Departments can be isolated.

### Better Performance

Smaller broadcast domains.

### Easier Management

Logical segmentation.

### Scalability

Supports organizational growth.

---

## Production Usage

VLANs are common in:

- Enterprises
- Data centers
- Campus networks
- Corporate offices
- Server environments

Nearly every medium or large network uses VLANs.

---

## Common Production Failures

### Incorrect VLAN Assignment

Symptoms:

- Device unreachable

### Trunk Misconfiguration

Symptoms:

- VLAN traffic missing

### Native VLAN Mismatch

Symptoms:

- Intermittent connectivity

### Missing Inter-VLAN Routing

Symptoms:

- VLANs cannot communicate

---

## Troubleshooting Concepts

Verify:

- VLAN membership
- Trunk configuration
- Inter-VLAN routing
- Switch port configuration

These are common production checks.

---

## Common Interview Questions

- What is a VLAN?
- Why are VLANs needed?
- What is a broadcast domain?
- Access port vs trunk port?
- Can VLANs communicate directly?
- What is Inter-VLAN Routing?
- What are VLAN benefits?
- Why are VLANs important for security?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| VLAN | Logical Network Segmentation |
| VLAN ID | VLAN Identifier |
| Broadcast Domain | Separate Per VLAN |
| Access Port | Single VLAN |
| Trunk Port | Multiple VLANs |
| Inter-VLAN Routing | VLAN Communication Via L3 Device |
| Main Benefit | Isolation |
| Security Benefit | Department Separation |
| Common Failure | Wrong VLAN Assignment |
| Core Purpose | Multiple Networks On One Infrastructure |