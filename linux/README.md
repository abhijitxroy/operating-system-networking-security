# Network Fundamentals

## Why Networking Exists

Computers become significantly more valuable when they can communicate.

Modern systems depend on communication between:

- Applications
- Databases
- APIs
- Containers
- Kubernetes clusters
- Cloud services
- Users

Networking exists to move data reliably between systems.

Without networking:

```text
Isolated Systems
       ↓
Limited Capability
```

With networking:

```text
Connected Systems
       ↓
Distributed Computing
```

---

## The Engineering Problem

Applications need to exchange information.

Questions must be answered:

- Where should data go?
- How is the destination identified?
- How is reliability maintained?
- How are failures handled?
- How is communication secured?

Networking provides the mechanisms that solve these problems.

---

## How Data Moves Across Networks

A simplified view:

```text
Application
      ↓
Transport Layer
      ↓
IP Layer
      ↓
Network Infrastructure
      ↓
Destination System
```

Every network technology builds upon this fundamental idea.

---

## Why The TCP/IP Model Matters

The TCP/IP model separates responsibilities.

| Layer | Responsibility |
|----------|----------|
| Application | User-Facing Communication |
| Transport | Reliability And Delivery |
| Internet | Addressing And Routing |
| Network Access | Physical Transmission |

This separation allows networking technologies to evolve independently.

---

## IP Addresses

Computers need identities.

IP addresses provide that identity.

Examples:

```text
10.0.0.10
192.168.1.20
172.16.5.15
```

Without IP addressing:

```text
No Destination
      ↓
No Communication
```

---

## Ports

An IP address identifies a machine.

A port identifies a service.

Example:

```text
Server
  ↓
10.0.0.10
  ↓
Port 443
```

This allows multiple applications to run on the same host.

---

## TCP vs UDP

### TCP

Designed for reliability.

Characteristics:

- Connection oriented
- Ordered delivery
- Error recovery
- Higher overhead

Common examples:

- HTTP
- HTTPS
- SSH
- Databases

### UDP

Designed for speed.

Characteristics:

- Connectionless
- Lower overhead
- No delivery guarantees

Common examples:

- DNS
- Streaming
- Real-time communication

---

## DNS

Humans prefer names.

Networks use IP addresses.

DNS bridges the gap.

```text
openai.com
      ↓
IP Address
```

Without DNS, modern systems would be difficult to operate.

---

## Routing

Networks need path selection.

Routing determines:

```text
Destination
      ↓
Best Path
```

Large-scale networking depends heavily on routing decisions.

---

## Production Impact

Networking directly affects:

- Application availability
- API communication
- Database connectivity
- Cloud infrastructure
- Kubernetes clusters
- Load balancing
- Service discovery

Many application incidents are actually networking incidents.

---

## Common Production Failures

### DNS Failures

Symptoms:

- Services unreachable
- Resolution failures

### Routing Problems

Symptoms:

- Traffic blackholes
- Intermittent connectivity

### Port Connectivity Issues

Symptoms:

- Connection refused
- Timeout errors

### Packet Loss

Symptoms:

- High latency
- Unstable communication

### MTU Problems

Symptoms:

- Intermittent failures
- Large request failures

---

## Fundamental Troubleshooting Commands

### Connectivity

```bash
ping
```

### Path Analysis

```bash
traceroute
```

### DNS Investigation

```bash
dig
```

### Socket Analysis

```bash
ss -tulpn
```

### Packet Capture

```bash
tcpdump
```

---

## Production Debugging Workflow

```text
Identify Impact
      ↓
Verify DNS
      ↓
Verify Connectivity
      ↓
Verify Route
      ↓
Verify Port
      ↓
Capture Packets
      ↓
Find Root Cause
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Reliability | Additional Overhead |
| Performance | Reduced Guarantees |
| Security | Increased Complexity |
| Global Reach | More Failure Points |
| Scalability | Additional Architecture |

---

## Interview Thinking

- Why was networking invented?
- Why do IP addresses exist?
- Why do ports exist?
- TCP vs UDP?
- Why does DNS exist?
- How does routing work?
- How would you investigate a connectivity issue?
- Why can networking failures appear as application failures?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Networking | System Communication |
| IP Address | Machine Identity |
| Port | Service Identity |
| TCP | Reliable Delivery |
| UDP | Fast Delivery |
| DNS | Name Resolution |
| Routing | Path Selection |
| ping | Connectivity Test |
| traceroute | Route Analysis |
| tcpdump | Packet Investigation |