# Networking Troubleshooting

## Why Networking Troubleshooting Exists

Modern systems depend on network communication.

Examples:

- APIs
- Databases
- Kubernetes clusters
- Cloud services
- Load balancers
- DNS infrastructure

When connectivity breaks, applications often fail even though the application itself is healthy.

Networking troubleshooting exists to identify where communication is failing.

---

## The Engineering Problem

Users usually report symptoms.

Examples:

- Application timeout
- Service unavailable
- Slow response times
- Connection refused
- DNS resolution failures

The visible symptom is rarely enough.

```text
Application Error
        ↓
Network Symptom
        ↓
Actual Root Cause
```

Engineers must trace the communication path.

---

## The Biggest Networking Mistake

Many engineers immediately assume:

```text
Network Is Down
```

In reality the issue may be:

- DNS
- Firewall rules
- Routing
- Load balancers
- Security groups
- Application listeners

Always validate assumptions using evidence.

---

## Common Networking Failure Domains

### DNS

Examples:

- Resolution failures
- Incorrect records
- DNS latency

### Connectivity

Examples:

- Packet loss
- Timeouts
- Network interruptions

### Routing

Examples:

- Incorrect routes
- Traffic black holes

### Security Controls

Examples:

- Firewalls
- Security groups
- Network ACLs

### Load Balancing

Examples:

- Unhealthy backends
- Misconfigured listeners

---

## A Practical Troubleshooting Workflow

```text
Identify Impact
      ↓
Validate DNS
      ↓
Validate Connectivity
      ↓
Validate Routing
      ↓
Validate Security Controls
      ↓
Find Root Cause
```

---

## DNS Troubleshooting

Common symptoms:

- Host not found
- Service discovery failures

Useful commands:

```bash
dig
nslookup
host
```

Investigation:

- DNS records
- Resolver configuration
- Response latency

DNS is one of the most common causes of networking incidents.

---

## Connectivity Troubleshooting

Common symptoms:

- Packet loss
- High latency
- Timeouts

Useful commands:

```bash
ping
traceroute
mtr
```

Investigation:

- Reachability
- Latency patterns
- Packet loss patterns

---

## Port Troubleshooting

Services communicate through ports.

Common symptoms:

- Connection refused
- Service unavailable

Useful commands:

```bash
ss -tulpn
netstat -tulpn
nc
```

Investigation:

- Listening services
- Open ports
- Firewall restrictions

---

## Packet Analysis

When symptoms remain unclear, inspect packets.

Useful commands:

```bash
tcpdump
wireshark
```

Questions:

- Is traffic leaving?
- Is traffic arriving?
- Are packets dropped?

Packet captures often reveal hidden problems.

---

## Cloud Networking Troubleshooting

Common areas:

- Security groups
- Network ACLs
- Route tables
- Load balancers
- Private networking

Many cloud incidents are networking incidents disguised as application failures.

---

## Production Impact

Networking failures affect:

- Applications
- Databases
- Kubernetes clusters
- Cloud services
- End users

A single networking issue can create a large blast radius.

---

## Common Production Failures

### DNS Outages

Symptoms:

- Service discovery failures
- Application outages

### Firewall Misconfiguration

Symptoms:

- Connection blocked
- Timeout errors

### Routing Problems

Symptoms:

- Traffic black holes
- Intermittent connectivity

### Load Balancer Issues

Symptoms:

- Failed requests
- Partial outages

### Packet Loss

Symptoms:

- High latency
- Poor application performance

---

## Investigation Mindset

```text
Symptom
   ↓
DNS
   ↓
Connectivity
   ↓
Routing
   ↓
Security Controls
   ↓
Packet Analysis
   ↓
Root Cause
```

Always follow the packet path.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Strong Security | Reduced Connectivity Flexibility |
| Network Segmentation | Increased Complexity |
| High Availability | More Components To Debug |
| Detailed Monitoring | Additional Cost |
| Deep Packet Analysis | Increased Investigation Time |

---

## Interview Thinking

- How would you troubleshoot a timeout?
- DNS issue vs network issue?
- Why does packet loss matter?
- How would you investigate intermittent connectivity?
- What causes connection refused errors?
- How would you debug a routing issue?
- Why is tcpdump valuable?
- How would you perform networking RCA?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Networking Troubleshooting | Communication Path Analysis |
| DNS | Service Discovery |
| ping | Reachability Test |
| traceroute | Route Investigation |
| ss | Socket Inspection |
| tcpdump | Packet Capture |
| Firewall | Traffic Filtering |
| Routing | Path Selection |
| Packet Loss | Communication Degradation |
| RCA | Root Cause Identification |