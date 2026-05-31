

# Kubernetes Network Troubleshooting

## Why Kubernetes Networking Fails

Kubernetes networking involves multiple layers.

Examples:

```text
Pod Networking
Services
DNS
CNI
Ingress
Network Policies
```

Question:

```text
Why Can't Pods Communicate?

Why Is The Service Unreachable?

Why Does DNS Fail?
```

A structured troubleshooting approach is essential.

---

## Troubleshooting Mindset

Always start with:

```text
What Is Failing?
```

Determine whether the issue involves:

```text
Pod
Service
DNS
Ingress
Network Policy
```

Avoid changing configurations before identifying the root cause.

---

## Step 1: Verify Pod Health

Check Pods:

```bash
kubectl get pods -A
```

Get detailed information:

```bash
kubectl describe pod <pod-name>
```

Verify:

- Pod is Running
- Pod has an IP
- No restart loops

---

## Step 2: Verify Pod Connectivity

Check Pod IPs:

```bash
kubectl get pods -o wide
```

Test connectivity:

```bash
kubectl exec -it <pod> -- ping <pod-ip>
```

Symptoms:

```text
Pod Cannot Reach Pod
```

Possible causes:

- CNI failure
- Routing issue
- Network Policy restriction

---

## Step 3: Verify Services

Check Services:

```bash
kubectl get svc
```

Inspect configuration:

```bash
kubectl describe svc <service-name>
```

Verify:

- Correct selector
- Correct ports
- Correct Service type

---

## Step 4: Verify Endpoints

Check endpoints:

```bash
kubectl get endpoints
```

Question:

```text
Does The Service
Actually Have
Backend Pods?
```

Common issue:

```text
Wrong Labels
```

Result:

```text
Service Has No Endpoints
```

---

## Step 5: Verify DNS

Check CoreDNS:

```bash
kubectl get pods -n kube-system
```

Test DNS:

```bash
nslookup service-name
```

or

```bash
dig service-name
```

Common symptoms:

```text
Name Resolution Failure
```

---

## Step 6: Verify CNI

Check CNI Pods:

```bash
kubectl get pods -A
```

Look for:

```text
Calico
Cilium
Flannel
```

Symptoms:

```text
Cross-Node Communication Failure
```

Common causes:

- CNI crash
- Routing issues
- IP exhaustion

---

## Step 7: Verify Network Policies

List policies:

```bash
kubectl get networkpolicy -A
```

Inspect policy:

```bash
kubectl describe networkpolicy <policy>
```

Symptoms:

```text
Traffic Blocked Unexpectedly
```

Common cause:

```text
Default Deny Policy
```

---

## Step 8: Verify Ingress

Check Ingress:

```bash
kubectl get ingress
```

Inspect:

```bash
kubectl describe ingress <name>
```

Verify:

- Host rules
- Path rules
- TLS configuration
- Backend service mapping

---

## Common Production Issues

### Service Has No Endpoints

Cause:

```text
Selector Mismatch
```

---

### DNS Failure

Cause:

```text
CoreDNS Problem
```

---

### Pod Communication Failure

Cause:

```text
CNI Or Network Policy
```

---

### External Access Failure

Cause:

```text
Ingress Misconfiguration
```

---

### Intermittent Connectivity

Cause:

```text
Routing Or CNI Issues
```

---

## Production Debugging Workflow

```text
Application Failure
         ↓
Pod Health
         ↓
Pod Connectivity
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

This workflow resolves a large percentage of Kubernetes networking incidents.

---

## Common Interview Questions

- How do you troubleshoot Kubernetes networking?
- Why would a Service have no endpoints?
- How do you debug DNS failures?
- How do you verify Pod connectivity?
- What role does CNI play?
- How do Network Policies affect communication?
- How would you troubleshoot Ingress issues?

---

## Quick Revision

| Problem | Common Cause |
|----------|----------|
| Pod Cannot Reach Pod | CNI Issue |
| Service Unreachable | Wrong Selector |
| No Endpoints | Label Mismatch |
| DNS Failure | CoreDNS Problem |
| Traffic Blocked | Network Policy |
| External Access Failure | Ingress Issue |
| Cross-Node Failure | Routing Or CNI |
| Pod Restarting | Application Problem |
| First Check | Pod Health |
| Core Goal | Isolate Failure Layer |