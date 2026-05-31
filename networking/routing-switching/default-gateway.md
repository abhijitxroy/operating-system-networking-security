# Default Gateway

## Why A Default Gateway Exists

Devices can communicate directly only with systems in the same network.

Example:

```text
PC A → 192.168.1.10
PC B → 192.168.1.20
```

Communication works because both devices are in the same subnet.

Question:

```text
How Does A Device Reach
Google.com
Or
Another Network?
```

The Default Gateway solves this problem.

---

## The Engineering Problem

Suppose a machine has:

```text
IP Address:
192.168.1.10
```

It wants to reach:

```text
8.8.8.8
```

The destination is outside the local network.

Question:

```text
Where Should The Packet Go?
```

The answer is:

```text
Default Gateway
```

---

## What Is A Default Gateway?

A Default Gateway is the router used when the destination network is unknown or outside the local subnet.

Example:

```text
Host
  ↓
Default Gateway
  ↓
Other Networks
```

It acts as the exit point from a local network.

---

## Simple Example

Host:

```text
IP Address:
192.168.1.10

Subnet Mask:
255.255.255.0

Default Gateway:
192.168.1.1
```

Destination:

```text
8.8.8.8
```

Decision:

```text
Outside Local Network
        ↓
Send To 192.168.1.1
```

---

## How Gateway Selection Works

Step 1:

```text
Check Destination IP
```

Step 2:

```text
Is Destination In Local Subnet?
```

If yes:

```text
Send Directly
```

If no:

```text
Send To Default Gateway
```

---

## Packet Flow Example

```text
Laptop
   ↓
Default Gateway
   ↓
ISP Router
   ↓
Internet
   ↓
Destination Server
```

Almost every Internet request follows this model.

---

## Default Route

Routers often store:

```text
0.0.0.0/0
```

Meaning:

```text
Unknown Network
      ↓
Use This Route
```

This is called the Default Route.

---

## Viewing Default Gateway

Linux:

```bash
ip route
```

Example:

```text
default via 192.168.1.1
```

Older command:

```bash
route -n
```

---

## Production Impact

Default gateways are critical for:

- Internet access
- Cloud connectivity
- Data center networking
- Kubernetes nodes
- Corporate networks
- Virtual machines

Without a valid gateway, external communication fails.

---

## Common Production Failures

### Incorrect Gateway

Symptoms:

- No Internet access
- External systems unreachable

### Gateway Down

Symptoms:

- Entire subnet loses connectivity

### Routing Misconfiguration

Symptoms:

- Intermittent packet loss
- Incorrect traffic paths

### Firewall Issues

Symptoms:

- Gateway reachable
- Traffic blocked beyond gateway

---

## Troubleshooting Commands

```bash
ip route
```

```bash
ping GATEWAY_IP
```

```bash
traceroute 8.8.8.8
```

```bash
netstat -rn
```

Useful for validating routing behavior.

---

## Common Interview Questions

- What is a Default Gateway?
- Why is a Default Gateway needed?
- How does a host decide whether to use a gateway?
- What is a Default Route?
- What does 0.0.0.0/0 mean?
- What happens if the gateway is unavailable?
- How do you view the configured gateway in Linux?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Default Gateway | Exit Point From Local Network |
| Router | Forwards Traffic To Other Networks |
| Local Traffic | Sent Directly |
| Remote Traffic | Sent To Gateway |
| Default Route | 0.0.0.0/0 |
| Common Command | ip route |
| Gateway Failure | Loss Of External Connectivity |
| Internet Access | Depends On Gateway |
| Most Common Use | Reach Other Networks |
| Core Purpose | Forward Non-Local Traffic |
