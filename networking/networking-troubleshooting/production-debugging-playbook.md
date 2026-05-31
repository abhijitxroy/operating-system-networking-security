

# Production Debugging Playbook

## Why A Debugging Playbook Matters

Production incidents are often stressful.

Symptoms:

```text
Application Down
High Latency
Connection Failures
Customer Impact
```

Question:

```text
Where Should We Start?
```

A structured debugging workflow prevents random troubleshooting.

---

## The First Rule

Always begin with:

```text
What Changed?
```

Examples:

- Deployment
- Configuration update
- DNS change
- Firewall change
- Infrastructure modification

Many incidents are caused by recent changes.

---

## Incident Triage

Determine:

```text
Who Is Impacted?
What Is Impacted?
When Did It Start?
```

Classify severity before deep investigation.

---

## Step 1: Verify The Symptom

Do not rely solely on reports.

Validate:

```text
Application Error
Timeout
Connection Failure
Slow Response
```

Reproduce the issue if possible.

---

## Step 2: Check Application Health

Verify:

```text
Application Running
Process Running
Container Running
Pod Running
```

Useful commands:

```bash
ps -ef
```

```bash
kubectl get pods
```

---

## Step 3: Verify DNS

Question:

```text
Can The Name Be Resolved?
```

Commands:

```bash
nslookup <hostname>
```

```bash
dig <hostname>
```

DNS failures often appear as application failures.

---

## Step 4: Verify Connectivity

Commands:

```bash
ping <host>
```

```bash
curl <endpoint>
```

Determine whether the target is reachable.

---

## Step 5: Verify Routing

Commands:

```bash
traceroute <host>
```

```bash
ip route
```

Check whether traffic is reaching the destination.

---

## Step 6: Verify Ports

Question:

```text
Is The Service Listening?
```

Commands:

```bash
ss -tulpn
```

```bash
netstat -tulpn
```

Verify expected ports are open.

---

## Step 7: Verify Firewalls

Check:

```text
Source
Destination
Port
Protocol
```

Examples:

- Security Groups
- NACLs
- Linux Firewalls
- Network Firewalls

---

## Step 8: Capture Traffic

If the issue remains unclear:

```bash
tcpdump
```

Question:

```text
Are Packets Being Sent?

Are Responses Returning?
```

Packet captures often reveal hidden issues.

---

## Step 9: Analyze Packets

Use:

```text
Wireshark
```

to inspect:

- TCP handshakes
- DNS queries
- TLS negotiations
- Retransmissions
- Packet loss

---

## Kubernetes Debugging Flow

```text
Pod Health
     ↓
Service
     ↓
Endpoints
     ↓
DNS
     ↓
CNI
     ↓
Network Policies
     ↓
Ingress
```

Follow the stack from workload to network edge.

---

## Cloud Debugging Flow

```text
Application
     ↓
Security Groups
     ↓
Route Tables
     ↓
NAT Gateway
     ↓
Internet Gateway
     ↓
Load Balancer
```

Validate each layer systematically.

---

## Common Failure Patterns

### DNS Failure

Symptoms:

```text
Host Not Found
```

---

### Connection Refused

Symptoms:

```text
Port Closed
```

---

### Timeout

Symptoms:

```text
No Response
```

---

### Packet Loss

Symptoms:

```text
Slow Or Intermittent Traffic
```

---

### TLS Failure

Symptoms:

```text
Certificate Errors
```

---

## Production Debugging Principles

### Change One Thing At A Time

Avoid introducing additional variables.

### Gather Evidence

Use logs, metrics, traces, and packet captures.

### Verify Assumptions

Never assume a component is healthy.

### Work Layer By Layer

Move systematically through the stack.

---

## Common Interview Questions

- How do you troubleshoot a production outage?
- What is your debugging workflow?
- How do you investigate network timeouts?
- How do you troubleshoot DNS issues?
- When would you use tcpdump?
- When would you use Wireshark?
- How do you debug Kubernetes networking?
- How do you debug cloud networking issues?

---

## Quick Revision

| Step | Goal |
|----------|----------|
| Verify Symptom | Confirm Problem |
| Check Health | Verify Workload |
| Check DNS | Verify Resolution |
| Check Connectivity | Verify Reachability |
| Check Routing | Verify Path |
| Check Ports | Verify Listener |
| Check Firewall | Verify Access |
| Capture Packets | Verify Traffic |
| Analyze Packets | Find Root Cause |
| Core Principle | Debug Systematically |