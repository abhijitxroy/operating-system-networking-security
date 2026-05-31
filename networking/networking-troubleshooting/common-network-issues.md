

# Common Network Issues

## Why Network Troubleshooting Matters

Modern systems depend heavily on networking.

Question:

```text
Why Is The Application Slow?

Why Can't The Service Be Reached?

Why Are Requests Timing Out?
```

Many production incidents are caused by networking problems.

---

## The Troubleshooting Mindset

Always start with:

```text
What Changed?
```

Then verify:

```text
Connectivity
DNS
Routing
Firewall Rules
Application Health
```

Avoid guessing.

---

## DNS Resolution Failure

Symptoms:

```text
Unknown Host
DNS Lookup Failure
Service Not Found
```

Common Causes:

- Wrong DNS server
- Missing DNS record
- DNS outage
- Typographical error

Useful Commands:

```bash
nslookup example.com
```

```bash
dig example.com
```

---

## Network Timeout

Symptoms:

```text
Connection Timed Out
Request Timeout
```

Common Causes:

- Firewall blocking traffic
- Routing issue
- Service unavailable
- Network congestion

Useful Commands:

```bash
ping <host>
```

```bash
traceroute <host>
```

---

## Connection Refused

Symptoms:

```text
Connection Refused
```

Meaning:

```text
Host Reachable
Port Closed
```

Common Causes:

- Service not running
- Wrong port
- Application startup failure

Useful Commands:

```bash
ss -tulpn
```

```bash
netstat -tulpn
```

---

## Packet Loss

Symptoms:

- Slow applications
- Unstable connections
- Intermittent failures

Common Causes:

- Network congestion
- Faulty hardware
- Wireless interference
- ISP issues

Useful Commands:

```bash
ping
```

```bash
mtr
```

---

## Routing Problems

Symptoms:

```text
Host Unreachable
```

Common Causes:

- Missing routes
- Wrong gateway
- VPN issues
- Route conflicts

Useful Commands:

```bash
ip route
```

```bash
traceroute
```

---

## Firewall Blocking Traffic

Symptoms:

```text
Ping Works
Application Fails
```

Common Causes:

- Missing allow rule
- Security group restrictions
- NACL restrictions

Verify:

```text
Source
Destination
Port
Protocol
```

---

## TLS Or Certificate Issues

Symptoms:

```text
Certificate Error
TLS Handshake Failure
```

Common Causes:

- Expired certificate
- Wrong hostname
- Unsupported TLS version

Useful Commands:

```bash
openssl s_client
```

---

## Load Balancer Problems

Symptoms:

- Intermittent failures
- Health check failures
- Uneven traffic distribution

Common Causes:

- Unhealthy backend
- Wrong health check path
- Security restrictions

---

## Kubernetes Networking Issues

Symptoms:

- Service unreachable
- DNS failures
- Pod communication issues

Common Causes:

- CNI failure
- Network Policy blocking traffic
- Service selector mismatch
- CoreDNS failure

Useful Commands:

```bash
kubectl get svc
```

```bash
kubectl get endpoints
```

```bash
kubectl get pods -A
```

---

## Cloud Networking Issues

Symptoms:

- Cannot reach resources
- Internet connectivity failure

Common Causes:

- Route table issues
- Security group issues
- NAT Gateway problems
- Internet Gateway misconfiguration

---

## Production Debugging Workflow

```text
1. Identify Symptom
          ↓
2. Verify DNS
          ↓
3. Verify Connectivity
          ↓
4. Verify Routing
          ↓
5. Verify Firewall Rules
          ↓
6. Verify Application Health
          ↓
7. Capture Packets If Needed
```

This workflow solves many production incidents.

---

## Common Interview Questions

- How do you troubleshoot network issues?
- What causes connection timeouts?
- Connection refused vs timeout?
- How do you troubleshoot DNS failures?
- What causes packet loss?
- How do you troubleshoot Kubernetes networking?
- How do you debug cloud networking problems?

---

## Quick Revision

| Issue | Typical Cause |
|----------|----------|
| DNS Failure | Missing DNS Record |
| Timeout | Firewall Or Routing |
| Connection Refused | Service Not Running |
| Packet Loss | Congestion Or Hardware |
| Routing Failure | Missing Route |
| TLS Error | Certificate Problem |
| Load Balancer Failure | Backend Health Issue |
| Kubernetes Failure | CNI/DNS/Service Issue |
| Cloud Failure | Route/Security Misconfiguration |
| First Troubleshooting Step | Verify Connectivity |