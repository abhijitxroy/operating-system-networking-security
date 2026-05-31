

# Routing vs Switching

## Why This Comparison Matters

Modern networks depend on both:

- Switching
- Routing

A very common networking interview question is:

```text
Routing
    vs
Switching
```

Understanding the difference is essential for network design and troubleshooting.

---

## The Engineering Problem

Suppose two devices communicate:

```text
PC A
192.168.1.10

PC B
192.168.1.20
```

Question:

```text
How Is Traffic Delivered?
```

Now suppose:

```text
PC A
192.168.1.10

Server
10.10.10.20
```

Question:

```text
How Is Traffic Delivered Now?
```

The answer involves switching and routing.

---

## What Is Switching?

Switching forwards traffic inside the same network.

Example:

```text
192.168.1.10
      ↓
192.168.1.20
```

A switch uses:

```text
MAC Addresses
```

to forward frames.

Switching primarily operates at:

```text
Layer 2
(Data Link Layer)
```

---

## What Is Routing?

Routing forwards traffic between different networks.

Example:

```text
192.168.1.10
      ↓
10.10.10.20
```

A router uses:

```text
IP Addresses
```

to forward packets.

Routing primarily operates at:

```text
Layer 3
(Network Layer)
```

---

## Switching Example

```text
Laptop
      ↓
Switch
      ↓
Printer
```

Both devices exist in the same network.

No router is required.

---

## Routing Example

```text
Laptop
      ↓
Router
      ↓
Internet
      ↓
Server
```

Traffic must cross network boundaries.

A router is required.

---

## Address Types Used

### Switching

Uses:

```text
MAC Address
```

Example:

```text
AA:BB:CC:DD:EE:FF
```

---

### Routing

Uses:

```text
IP Address
```

Example:

```text
192.168.1.10
```

---

## Tables Used

### Switching

Uses:

```text
MAC Address Table
```

Maps:

```text
MAC Address
      ↓
Switch Port
```

---

### Routing

Uses:

```text
Routing Table
```

Maps:

```text
Destination Network
      ↓
Next Hop
```

---

## High-Level Comparison

| Feature | Switching | Routing |
|----------|----------|----------|
| Layer | Layer 2 | Layer 3 |
| Address Type | MAC | IP |
| Device | Switch | Router |
| Scope | Same Network | Different Networks |
| Table Used | MAC Table | Routing Table |
| Purpose | Local Delivery | Inter-Network Delivery |

---

## Production Impact

Switching is critical for:

- LANs
- Data centers
- Server racks

Routing is critical for:

- Internet connectivity
- Cloud networking
- Enterprise networking
- Multi-region architectures

Modern networks require both.

---

## Common Production Failures

### Switching Problems

Symptoms:

- Devices in same subnet cannot communicate

Possible causes:

- VLAN issues
- MAC learning problems

### Routing Problems

Symptoms:

- Remote networks unreachable

Possible causes:

- Missing routes
- Incorrect gateway
- Routing loops

---

## Troubleshooting Commands

```bash
ip addr
```

```bash
ip route
```

```bash
arp -a
```

```bash
traceroute
```

Useful for distinguishing switching and routing issues.

---

## Common Interview Questions

- Routing vs Switching?
- Which OSI layers are involved?
- MAC address vs IP address?
- Switch vs Router?
- When is a router required?
- When is a switch sufficient?
- What tables do switches and routers use?

---

## Quick Revision

| Concept | Switching | Routing |
|----------|----------|----------|
| Layer | L2 | L3 |
| Address | MAC | IP |
| Device | Switch | Router |
| Scope | Same Network | Different Networks |
| Table | MAC Table | Routing Table |
| Goal | Local Communication | Network-To-Network Communication |
| Common Failure | VLAN Issue | Missing Route |
| Core Purpose | Forward Frames | Forward Packets |