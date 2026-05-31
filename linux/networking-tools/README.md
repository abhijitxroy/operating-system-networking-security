

# Linux Networking Tools

## Why Networking Tools Matter

Most production systems fail over the network before they fail over hardware.

Applications, databases, containers, Kubernetes clusters, cloud services, and APIs all depend on reliable network communication.

When systems become unreachable, slow, or unstable, Linux networking tools become the primary source of evidence.

This section focuses on host-level network investigation rather than networking theory.

---

## The Engineering Problem

When an application cannot communicate successfully, engineers must determine:

- Is the host reachable?
- Is DNS working?
- Is routing correct?
- Is the port open?
- Is TLS working?
- Is packet loss occurring?
- Is latency increasing?

Linux networking tools help answer these questions.

```text
Application Problem
        ↓
Network Investigation
        ↓
Evidence Collection
        ↓
Root Cause
```

---

## Core Linux Networking Tools

### ip

Modern Linux networking administration tool.

Common usage:

```bash
ip addr
ip route
ip link
```

Used for:

- IP addresses
- Interfaces
- Routing tables

---

### ss

Modern socket inspection tool.

```bash
ss -tulpn
```

Used for:

- Listening ports
- Active connections
- Process ownership

---

### ping

Basic connectivity testing.

```bash
ping google.com
```

Useful for:

- Reachability
- Latency checks
- Packet loss detection

---

### traceroute

Shows packet path through the network.

```bash
traceroute google.com
```

Useful for:

- Routing issues
- Network path analysis

---

### dig

DNS investigation tool.

```bash
dig openai.com
```

Useful for:

- DNS records
- Resolution problems
- DNS troubleshooting

---

### tcpdump

One of the most powerful troubleshooting tools.

```bash
tcpdump -i any
```

Useful for:

- Packet capture
- Connection analysis
- DNS debugging
- TLS troubleshooting

---

## Production Impact

These tools are frequently used during:

- API outages
- DNS failures
- Kubernetes issues
- Load balancer incidents
- TLS problems
- Service communication failures
- Cloud networking incidents

---

## Common Production Failures

### DNS Failure

Symptoms:

- Hostnames fail
- Applications unreachable

Investigation:

```bash
dig
nslookup
```

### Port Not Listening

Symptoms:

- Connection refused

Investigation:

```bash
ss -tulpn
```

### Routing Problems

Symptoms:

- Host unreachable

Investigation:

```bash
ip route
traceroute
```

### Packet Loss

Symptoms:

- Slow applications
- Intermittent failures

Investigation:

```bash
ping
tcpdump
```

---

## Production Debugging Workflow

```text
Verify DNS
      ↓
Verify Connectivity
      ↓
Verify Route
      ↓
Verify Port
      ↓
Capture Traffic
      ↓
Identify Root Cause
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Deep Visibility | Higher Investigation Time |
| Packet Capture | More Data To Analyze |
| Detailed Monitoring | Additional Overhead |
| Security Controls | Potential Connectivity Complexity |

---

## Interview Thinking

- How would you investigate a service that is unreachable?
- ping vs traceroute?
- netstat vs ss?
- How would you investigate DNS failures?
- When would you use tcpdump?
- How would you identify a routing problem?
- How would you investigate a port connectivity issue?

---

## Quick Revision

| Tool | Primary Usage |
|----------|----------|
| ip | Network Configuration |
| ss | Socket Inspection |
| ping | Connectivity Testing |
| traceroute | Path Analysis |
| dig | DNS Investigation |
| tcpdump | Packet Capture |
| ip route | Routing Table |
| ip addr | IP Addresses |
| ss -tulpn | Listening Ports |
| tcpdump -i any | Traffic Analysis |