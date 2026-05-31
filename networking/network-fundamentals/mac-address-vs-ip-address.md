

# MAC Address vs IP Address

## Why Do We Need Both?

A common beginner assumption is:

```text
If IP Address Exists,
Why Do We Need MAC Address?
```

The answer comes from how networks evolved.

Different problems required different identifiers.

```text
MAC Address
      ↓
Identify Device Inside Local Network

IP Address
      ↓
Identify Device Across Networks
```

Both are required for communication.

---

## The Engineering Problem

Imagine sending a package.

You need:

```text
City Address
      ↓
Find Correct Building

Apartment Number
      ↓
Find Correct Person
```

Networks work similarly.

```text
IP Address
      ↓
Find Correct Network

MAC Address
      ↓
Find Correct Device
```

---

## What Is A MAC Address?

MAC stands for:

```text
Media Access Control
```

A MAC address identifies a network interface.

Example:

```text
00:1A:2B:3C:4D:5E
```

Characteristics:

- Layer 2 identifier
- Used inside local networks
- Typically assigned by hardware vendor
- Used by switches

---

## What Is An IP Address?

An IP address identifies a device within an IP network.

Examples:

```text
192.168.1.10
```

```text
10.0.0.15
```

```text
2001:db8::1
```

Characteristics:

- Layer 3 identifier
- Used across networks
- Can change
- Used by routers

---

## OSI Layer Difference

| Identifier | OSI Layer |
|----------|----------|
| MAC Address | Layer 2 (Data Link) |
| IP Address | Layer 3 (Network) |

This is the most important interview distinction.

---

## How Communication Actually Works

Suppose:

```text
Laptop A
IP  : 192.168.1.10
MAC : AA-AA-AA-AA-AA-AA

Laptop B
IP  : 192.168.1.20
MAC : BB-BB-BB-BB-BB-BB
```

Laptop A wants to communicate with Laptop B.

Process:

```text
Destination IP Known
          ↓
ARP Request
          ↓
Find Destination MAC
          ↓
Frame Sent
```

IP determines where traffic should go.

MAC determines which device receives it on the local network.

---

## Why Routers Care About IP Addresses

Routers connect different networks.

Example:

```text
Network A
      ↓
Router
      ↓
Network B
```

Routers make forwarding decisions using:

```text
Destination IP
```

They do not route using MAC addresses.

---

## Why Switches Care About MAC Addresses

Switches operate inside local networks.

They maintain:

```text
MAC Address Table
```

Example:

```text
MAC Address
      ↓
Switch Port
```

Switches forward traffic using MAC addresses.

---

## ARP Connects Both Worlds

ARP exists because applications normally know IP addresses.

Network interfaces require MAC addresses.

ARP performs:

```text
IP Address
      ↓
MAC Address Resolution
```

Without ARP, local Ethernet communication would fail.

---

## Production Impact

Engineers frequently troubleshoot:

- Duplicate IP addresses
- Incorrect subnetting
- ARP failures
- MAC flapping
- Switching issues
- Routing problems

Understanding MAC and IP behavior is foundational for networking debugging.

---

## Common Production Failures

### Duplicate IP Address

Symptoms:

- Intermittent connectivity
- Network instability

### ARP Issues

Symptoms:

- Unable to reach local systems

### Incorrect Routing

Symptoms:

- Traffic reaches wrong network

### MAC Table Problems

Symptoms:

- Unstable switching behavior

### VLAN Misconfiguration

Symptoms:

- Devices cannot communicate

---

## Interview Thinking

- Why do we need both MAC and IP addresses?
- MAC Address vs IP Address?
- Which OSI layer uses MAC addresses?
- Which OSI layer uses IP addresses?
- Why do switches use MAC addresses?
- Why do routers use IP addresses?
- What problem does ARP solve?
- Can communication occur without ARP?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| MAC Address | Device Identifier |
| IP Address | Network Identifier |
| MAC Layer | Layer 2 |
| IP Layer | Layer 3 |
| Switch | Uses MAC Address |
| Router | Uses IP Address |
| ARP | Maps IP To MAC |
| Local Network | MAC Based Delivery |
| Inter-Network Communication | IP Based Routing |
| Most Common Interview Question | Why Both MAC And IP Exist? |