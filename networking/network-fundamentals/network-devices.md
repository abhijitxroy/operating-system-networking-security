

# Network Devices

## Why Network Devices Exist

A single computer can communicate directly with another.

However modern systems require:

- Thousands of devices
- Multiple networks
- Internet connectivity
- Traffic isolation
- Security controls
- High availability

Network devices exist to make large-scale communication possible.

---

## The Engineering Problem

Imagine connecting every device directly.

```text
Server A
Server B
Server C
Server D
```

This does not scale.

Networks require devices that can:

```text
Connect
Forward
Filter
Route
Protect
```

Different devices solve different networking problems.

---

## Network Device Evolution

Historically:

```text
Hub
  ↓
Switch
  ↓
Router
  ↓
Load Balancer
  ↓
Modern Cloud Networking
```

Each generation solved limitations of the previous one.

---

## Hub

A hub is a Layer 1 device.

Behavior:

```text
Receive Frame
      ↓
Send To Everyone
```

Problems:

- Inefficient
- High collisions
- No intelligence

Hubs are largely obsolete.

---

## Switch

A switch is primarily a Layer 2 device.

Behavior:

```text
MAC Address
      ↓
Switch Port
```

Benefits:

- Reduced collisions
- Better performance
- Efficient forwarding

Switches are the foundation of modern local networks.

---

## Router

Routers connect different networks.

Behavior:

```text
Destination IP
       ↓
Routing Decision
       ↓
Forward Packet
```

Benefits:

- Inter-network communication
- Internet access
- Traffic control

Routers operate primarily at Layer 3.

---

## Firewall

Firewalls enforce security policies.

Behavior:

```text
Traffic
   ↓
Policy Evaluation
   ↓
Allow Or Deny
```

Common uses:

- Access control
- Traffic filtering
- Security enforcement

---

## Load Balancer

Load balancers distribute traffic.

Problem solved:

```text
One Server
      ↓
Overloaded
```

Solution:

```text
Client Requests
       ↓
Load Balancer
       ↓
Multiple Servers
```

Benefits:

- Scalability
- High availability
- Fault tolerance

---

## Gateway

A gateway connects different systems or protocols.

Examples:

- Internet gateways
- API gateways
- Cloud gateways

Purpose:

```text
Different Systems
       ↓
Communication Bridge
```

---

## Proxy Server

A proxy sits between clients and servers.

Benefits:

- Security
- Caching
- Traffic inspection
- Access control

Examples:

```text
Client
   ↓
Proxy
   ↓
Server
```

---

## Wireless Access Point (AP)

Provides wireless network connectivity.

Behavior:

```text
Wi-Fi Devices
       ↓
Access Point
       ↓
Network
```

Common in:

- Offices
- Homes
- Enterprises
- Public networks

---

## Modern Cloud Networking Devices

Cloud providers abstract many traditional devices.

Examples:

- Virtual routers
- Virtual firewalls
- Cloud load balancers
- NAT gateways
- Transit gateways

The networking concepts remain the same even when hardware disappears.

---

## Production Impact

Engineers frequently troubleshoot:

- Switch failures
- Routing issues
- Firewall blocks
- Load balancer health problems
- DNS gateways
- Cloud networking issues

Understanding device responsibilities speeds up troubleshooting.

---

## Common Production Failures

### Switch Failure

Symptoms:

- Local connectivity loss

### Routing Issue

Symptoms:

- Cross-network communication failure

### Firewall Misconfiguration

Symptoms:

- Blocked traffic
- Timeouts

### Load Balancer Failure

Symptoms:

- Service outage
- Uneven traffic distribution

### Access Point Problems

Symptoms:

- Wireless instability

---

## Interview Thinking

- Hub vs Switch?
- Switch vs Router?
- Why do routers use IP addresses?
- Why do switches use MAC addresses?
- What problem does a firewall solve?
- What problem does a load balancer solve?
- What is a gateway?
- How are cloud networking devices different from physical devices?

---

## Quick Revision

| Device | Primary Purpose |
|----------|----------|
| Hub | Broadcast Traffic |
| Switch | Local Network Forwarding |
| Router | Connect Networks |
| Firewall | Security Filtering |
| Load Balancer | Traffic Distribution |
| Gateway | Communication Bridge |
| Proxy | Intermediate Traffic Control |
| Access Point | Wireless Connectivity |
| Cloud Load Balancer | Managed Traffic Distribution |
| NAT Gateway | Internet Access For Private Networks |