

# Routing Tables

## Why Routing Tables Exist

Routers must decide where packets should be sent.

Question:

```text
A Packet Arrives.

How Does The Router Know
Where To Forward It?
```

Routing Tables provide the answer.

---

## What Is A Routing Table?

A Routing Table is a collection of routes known to a device.

Purpose:

```text
Destination Network
        ↓
Best Route
        ↓
Next Hop
```

Routers and hosts use routing tables to make forwarding decisions.

---

## The Engineering Problem

Suppose a router receives a packet destined for:

```text
10.10.20.15
```

Question:

```text
Which Interface?

Which Next Hop?
```

The router searches its routing table.

---

## Example Routing Table

```text
Destination        Next Hop
10.0.0.0/8         Router A
172.16.0.0/12      Router B
192.168.1.0/24     Directly Connected
0.0.0.0/0          Default Gateway
```

Each entry represents a possible path.

---

## Common Routing Table Fields

### Destination Network

The target network.

Example:

```text
10.0.0.0/8
```

---

### Next Hop

The next router that should receive the packet.

Example:

```text
192.168.1.1
```

---

### Interface

The outgoing interface.

Example:

```text
eth0
```

---

### Metric

Used to compare routes.

Lower metric generally means a more preferred route.

---

## Longest Prefix Match

Routers select the most specific route.

Example:

```text
10.0.0.0/8
10.10.0.0/16
10.10.20.0/24
```

Destination:

```text
10.10.20.15
```

Selected route:

```text
10.10.20.0/24
```

This is called Longest Prefix Match.

---

## Directly Connected Routes

Routers automatically learn networks connected to their interfaces.

Example:

```text
192.168.1.0/24
```

No next hop is required.

---

## Static Routes

Manually configured routes.

Example:

```text
ip route add 10.0.0.0/8 via 192.168.1.1
```

Useful for small environments.

---

## Dynamic Routes

Learned automatically through routing protocols.

Examples:

- OSPF
- BGP
- EIGRP

Useful for large-scale networks.

---

## Default Route

When no matching route exists:

```text
0.0.0.0/0
```

is used.

Meaning:

```text
Send Traffic
To Default Gateway
```

---

## Viewing Routing Tables In Linux

Show routes:

```bash
ip route
```

Older command:

```bash
route -n
```

Example output:

```text
default via 192.168.1.1 dev eth0
192.168.1.0/24 dev eth0
```

---

## Production Impact

Routing tables are critical for:

- Data centers
- Cloud networking
- Kubernetes nodes
- Enterprise networks
- Internet routing

Incorrect routing entries can break connectivity.

---

## Common Production Failures

### Missing Route

Symptoms:

- Destination unreachable

### Incorrect Route

Symptoms:

- Traffic reaches wrong destination

### Routing Loop

Symptoms:

- High latency
- Packet drops

### Missing Default Route

Symptoms:

- Internet inaccessible

---

## Troubleshooting Commands

```bash
ip route
```

```bash
traceroute
```

```bash
ping
```

```bash
netstat -rn
```

Useful for routing investigations.

---

## Common Interview Questions

- What is a routing table?
- What information does a routing table contain?
- What is a next hop?
- What is a metric?
- What is longest prefix match?
- What is a default route?
- How do you view routes in Linux?
- Static vs dynamic routes?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Routing Table | Route Information Store |
| Destination Network | Target Network |
| Next Hop | Next Router |
| Interface | Outgoing Path |
| Metric | Route Preference |
| Longest Prefix Match | Most Specific Route Wins |
| Direct Route | Locally Connected Network |
| Static Route | Manual Route |
| Dynamic Route | Learned Automatically |
| Default Route | 0.0.0.0/0 |