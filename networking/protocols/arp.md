

# ARP (Address Resolution Protocol)

## Why ARP Exists

A common networking question is:

```text
If A Device Knows The Destination IP Address,
Why Doesn't It Send Traffic Directly?
```

Because Ethernet networks deliver frames using:

```text
MAC Addresses
```

Applications typically know IP addresses.

Network interfaces require MAC addresses.

ARP exists to bridge this gap.

---

## The Engineering Problem

Suppose:

```text
Laptop A
IP: 192.168.1.10

Laptop B
IP: 192.168.1.20
```

Laptop A wants to send traffic.

It knows:

```text
Destination IP
```

It does not know:

```text
Destination MAC Address
```

Without the MAC address, Ethernet delivery cannot occur.

---

## What Is ARP?

ARP stands for:

```text
Address Resolution Protocol
```

Purpose:

```text
IP Address
      ↓
MAC Address
```

ARP maps Layer 3 addresses to Layer 2 addresses.

---

## How ARP Works

Step 1:

```text
Need MAC For 192.168.1.20
```

Step 2:

ARP Request Broadcast:

```text
Who Has 192.168.1.20?
```

Step 3:

Destination Replies:

```text
I Am 192.168.1.20
My MAC Is BB:BB:BB:BB:BB:BB
```

Step 4:

Sender stores the result and sends traffic.

---

## ARP Request

ARP requests use:

```text
Broadcast
```

Meaning:

```text
One Sender
      ↓
Everyone On Local Network
```

All devices receive the request.

---

## ARP Reply

ARP replies use:

```text
Unicast
```

Meaning:

```text
One Device
      ↓
Original Requester
```

Only the requester receives the response.

---

## ARP Cache

Constant ARP lookups would be inefficient.

Systems therefore maintain:

```text
ARP Cache
```

Example:

```text
192.168.1.20
      ↓
BB:BB:BB:BB:BB:BB
```

This reduces network overhead.

---

## Viewing ARP Cache

Linux:

```bash
ip neigh
```

or

```bash
arp -a
```

Useful during troubleshooting.

---

## ARP In Real Communication

Example:

```text
Browser
   ↓
TCP/IP Stack
   ↓
ARP Lookup
   ↓
Ethernet Frame
   ↓
Network
```

Most local network communication depends on ARP.

---

## ARP And Routers

ARP only works within a local network.

When traffic crosses networks:

```text
Host
  ↓
Default Gateway MAC
  ↓
Router
```

The host ARPs for the router's MAC address.

---

## Production Impact

ARP issues can cause:

- Connectivity failures
- Intermittent communication
- Packet loss
- Network instability

Many Layer 2 issues involve ARP behavior.

---

## Common Production Failures

### ARP Cache Stale Entry

Symptoms:

- Intermittent connectivity
- Failed communication

### Duplicate IP Address

Symptoms:

- Unpredictable network behavior

### ARP Flooding

Symptoms:

- Increased network traffic
- Reduced performance

### Incorrect Gateway ARP

Symptoms:

- Unable to leave subnet

---

## Security Risks

### ARP Spoofing

An attacker sends fake ARP responses.

Goal:

```text
Victim
   ↓
Attacker
   ↓
Gateway
```

This enables:

- Traffic interception
- Man-in-the-middle attacks

ARP has no built-in authentication.

---

## Troubleshooting Commands

```bash
arp -a
ip neigh
ping
tcpdump arp
```

Useful for validating address resolution.

---

## Common Interview Questions

- Why does ARP exist?
- What problem does ARP solve?
- ARP request vs ARP reply?
- Why is ARP request broadcast?
- Why is ARP reply unicast?
- Does ARP work across routers?
- What is an ARP cache?
- What is ARP spoofing?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| ARP | Maps IP To MAC |
| ARP Request | Broadcast |
| ARP Reply | Unicast |
| ARP Cache | Stores Mappings |
| Layer Relationship | Layer 3 To Layer 2 |
| Local Network | ARP Scope |
| Default Gateway | Common ARP Target |
| ARP Spoofing | Fake ARP Response Attack |
| Troubleshooting Command | ip neigh |
| Core Purpose | Address Resolution |