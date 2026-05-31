

# Network Troubleshooting Basics

## Why Network Troubleshooting Matters

One of the most common statements during production incidents is:

```text
The Network Is Down
```

In reality, networking problems can originate from many different layers.

Examples:

- DNS failures
- Routing issues
- Firewall rules
- Load balancers
- Application listeners
- Packet loss
- Network congestion

Effective troubleshooting requires a structured approach.

---

## The Engineering Problem

Applications communicate through networks.

When communication fails:

```text
Application Error
       ↓
Network Investigation
       ↓
Root Cause
```

The visible symptom is rarely enough to identify the actual failure.

---

## The Golden Rule

Never start with assumptions.

Start with evidence.

Bad approach:

```text
Problem
   ↓
Guess
   ↓
Random Fix
```

Better approach:

```text
Problem
   ↓
Evidence
   ↓
Investigation
   ↓
Root Cause
```

---

## A Practical Troubleshooting Flow

```text
Identify Symptom
       ↓
Check DNS
       ↓
Check Connectivity
       ↓
Check Routing
       ↓
Check Security Controls
       ↓
Check Application
       ↓
Find Root Cause
```

This workflow solves a large percentage of networking incidents.

---

## Step 1: Verify DNS

Many outages are DNS related.

Questions:

```text
Can The Hostname Resolve?
```

Useful commands:

```bash
dig google.com
nslookup google.com
host google.com
```

Common symptoms:

- Unknown host
- Service discovery failures
- Intermittent connectivity

---

## Step 2: Verify Connectivity

Questions:

```text
Can The Destination Be Reached?
```

Useful commands:

```bash
ping
traceroute
mtr
```

Check:

- Reachability
- Latency
- Packet loss

---

## Step 3: Verify Ports

A host may be reachable while the service is unavailable.

Useful commands:

```bash
nc
ss
netstat
```

Questions:

```text
Is The Service Listening?
```

```text
Is The Port Reachable?
```

---

## Step 4: Verify Routing

Routing determines how packets move between networks.

Common issues:

- Missing routes
- Incorrect routes
- Traffic black holes

Useful commands:

```bash
ip route
route -n
traceroute
```

---

## Step 5: Verify Security Controls

Many networking incidents are actually security policy issues.

Examples:

- Firewalls
- Security groups
- Network ACLs
- Network policies

Symptoms:

- Timeouts
- Blocked connections

---

## Step 6: Capture Packets

If the issue remains unclear:

```text
Look At The Packets
```

Useful tools:

```bash
tcpdump
wireshark
```

Questions:

- Is traffic leaving?
- Is traffic arriving?
- Is traffic being dropped?

Packet captures often reveal the truth.

---

## Common Production Failures

### DNS Failure

Symptoms:

- Host not found
- Service discovery issues

### Firewall Block

Symptoms:

- Timeouts
- Connection failures

### Routing Problem

Symptoms:

- Reachability issues

### Packet Loss

Symptoms:

- Slow applications
- Retransmissions

### Load Balancer Misconfiguration

Symptoms:

- Partial outages
- Unhealthy backend traffic

---

## Useful Troubleshooting Commands

| Command | Purpose |
|----------|----------|
| ping | Connectivity Test |
| traceroute | Path Investigation |
| mtr | Path And Loss Analysis |
| dig | DNS Troubleshooting |
| nslookup | DNS Validation |
| ss | Socket Inspection |
| netstat | Connection Inspection |
| tcpdump | Packet Capture |
| ip route | Route Analysis |
| curl | Application Connectivity |

---

## Production Mindset

A network problem may actually be:

- DNS issue
- Routing issue
- Firewall issue
- Load balancer issue
- Application issue

Always isolate the failing layer before taking action.

---

## Interview Thinking

- How would you troubleshoot a timeout?
- What would you check first?
- DNS issue vs connectivity issue?
- Why use traceroute?
- Why use tcpdump?
- What causes packet loss?
- How would you debug intermittent failures?
- How would you isolate the failing layer?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| DNS Check | First Investigation Step |
| Connectivity Check | Verify Reachability |
| Port Check | Verify Service Availability |
| Routing Check | Verify Traffic Path |
| Firewall Check | Verify Traffic Permissions |
| Packet Capture | Ground Truth |
| traceroute | Path Visibility |
| tcpdump | Packet Visibility |
| Evidence First | Avoid Assumptions |
| Root Cause | Goal Of Troubleshooting |