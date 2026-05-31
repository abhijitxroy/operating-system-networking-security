

# NAT (Network Address Translation)

## Why NAT Exists

IPv4 addresses are limited.

Organizations may have:

- Thousands of devices
- Hundreds of servers
- Millions of users

But only a small number of public IP addresses.

Question:

```text
How Can Many Devices
Share A Small Number
Of Public IP Addresses?
```

NAT solves this problem.

---

## What Is NAT?

NAT stands for:

```text
Network Address Translation
```

Purpose:

```text
Private IP
      ↓
Public IP
```

NAT modifies IP address information while packets pass through a router or firewall.

---

## The Engineering Problem

Suppose a laptop has:

```text
192.168.1.10
```

This is a private IP address.

Private IPs are not routable on the public Internet.

Question:

```text
How Can This Device
Access Google.com?
```

The NAT device translates the private address into a public address.

---

## High-Level NAT Flow

```text
Laptop
192.168.1.10
      ↓
NAT Router
      ↓
203.x.x.x
      ↓
Internet
```

External systems see the public IP.

---

## Private IP Address Ranges

Common private ranges:

```text
10.0.0.0/8

172.16.0.0/12

192.168.0.0/16
```

These addresses are widely used inside organizations.

---

## Source NAT (SNAT)

Most common NAT type.

Example:

```text
192.168.1.10
      ↓
203.0.113.10
```

The source address is translated before leaving the network.

Used for:

- Internet access
- Corporate networks
- Home networks

---

## Destination NAT (DNAT)

Used to redirect incoming traffic.

Example:

```text
203.0.113.10
      ↓
192.168.1.20
```

Common for:

- Publishing web servers
- Reverse proxies
- Port forwarding

---

## Port Address Translation (PAT)

Also called:

```text
NAT Overload
```

Many devices share one public IP.

Example:

```text
192.168.1.10:5001
192.168.1.11:5002
192.168.1.12:5003
         ↓
203.0.113.10
```

Ports allow traffic to be mapped back correctly.

---

## NAT Translation Table

NAT devices maintain mappings.

Example:

| Private Address | Public Address |
|----------|----------|
| 192.168.1.10:5001 | 203.0.113.10:40001 |
| 192.168.1.11:5002 | 203.0.113.10:40002 |

This table enables return traffic.

---

## Benefits Of NAT

### Conserves IPv4 Addresses

Allows many devices to share few public addresses.

### Simplifies Internal Networks

Private addressing can be reused.

### Adds Basic Isolation

Internal systems are not directly exposed.

---

## Limitations Of NAT

### Breaks End-To-End Connectivity

Direct communication becomes harder.

### Additional Complexity

Troubleshooting becomes more difficult.

### Stateful Device Requirement

Translation tables must be maintained.

---

## Production Impact

NAT is used heavily in:

- Home networks
- Enterprise networks
- Cloud environments
- Kubernetes clusters
- Firewalls
- Internet gateways

Nearly every organization uses NAT somewhere.

---

## Common Production Failures

### NAT Table Exhaustion

Symptoms:

- Connection failures
- Intermittent connectivity

### Incorrect Port Forwarding

Symptoms:

- Service unreachable

### Firewall And NAT Conflicts

Symptoms:

- Unexpected traffic drops

### Asymmetric Routing

Symptoms:

- Broken sessions

---

## Troubleshooting Commands

```bash
ip addr
```

```bash
ip route
```

```bash
traceroute
```

```bash
tcpdump
```

Useful for tracking packet flow across translation boundaries.

---

## Common Interview Questions

- What is NAT?
- Why was NAT created?
- What is SNAT?
- What is DNAT?
- What is PAT?
- Why does NAT help conserve IPv4 addresses?
- What are NAT limitations?
- How does port forwarding work?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| NAT | Address Translation |
| SNAT | Change Source Address |
| DNAT | Change Destination Address |
| PAT | Many Hosts One Public IP |
| Private IP | Internal Address |
| Public IP | Internet-Routable Address |
| NAT Table | Translation Mapping |
| Common Benefit | IPv4 Conservation |
| Common Limitation | Breaks End-To-End Connectivity |
| Core Purpose | Private To Public Communication |