

# Unicast, Multicast And Broadcast

## Why This Topic Exists

Networks do not always send traffic the same way.

Sometimes communication is intended for:

- One device
- A group of devices
- Every device on the network

Different delivery models exist because different communication problems require different solutions.

---

## The Engineering Problem

Imagine a company announcement.

Possible approaches:

```text
One Person
       ↓
Private Message

Specific Team
       ↓
Group Message

Entire Company
       ↓
Broadcast Message
```

Networking uses the same idea.

---

## Unicast

Unicast means:

```text
One Sender
      ↓
One Receiver
```

Example:

```text
Laptop A
      ↓
Laptop B
```

Most Internet traffic is unicast.

Examples:

- Web browsing
- API requests
- Database connections
- SSH sessions

---

## How Unicast Works

A packet contains a single destination address.

```text
Source IP
      ↓
Destination IP
```

Routers forward traffic toward one specific destination.

---

## Production Examples Of Unicast

```text
Browser → Website

Application → Database

Client → API Server

SSH Client → Linux Server
```

Most production systems depend heavily on unicast communication.

---

## Multicast

Multicast means:

```text
One Sender
      ↓
Multiple Interested Receivers
```

The sender transmits traffic once.

The network distributes it to subscribed receivers.

---

## Why Multicast Exists

Without multicast:

```text
Sender
  ↓
Client 1

Sender
  ↓
Client 2

Sender
  ↓
Client 3
```

The same data is sent repeatedly.

Multicast reduces network usage.

```text
Sender
   ↓
Multicast Group
   ↓
Many Receivers
```

---

## Production Examples Of Multicast

Examples:

- IPTV
- Live video distribution
- Financial market feeds
- Routing protocols
- Service discovery systems

Multicast is common in specialized enterprise networks.

---

## Broadcast

Broadcast means:

```text
One Sender
      ↓
Everyone On The Local Network
```

Every device receives the traffic.

---

## Why Broadcast Exists

Sometimes a sender does not know the destination.

Example:

```text
Who Has IP 192.168.1.10?
```

This is how ARP operates.

The request is broadcast to all devices.

---

## Production Examples Of Broadcast

Examples:

- ARP requests
- DHCP discovery
- Legacy network protocols

Broadcast is generally limited to local networks.

Routers do not normally forward broadcast traffic.

---

## Broadcast Storm Problem

Excessive broadcast traffic can create problems.

Symptoms:

- High network utilization
- Packet loss
- Slow communication
- Network instability

Large networks typically minimize broadcasts.

---

## Unicast vs Multicast vs Broadcast

| Type | Communication Model |
|----------|----------|
| Unicast | One To One |
| Multicast | One To Many (Interested Receivers) |
| Broadcast | One To Everyone |

---

## Network Efficiency Comparison

### Unicast

Pros:

- Simple
- Reliable
- Widely supported

Cons:

- Inefficient for large audiences

### Multicast

Pros:

- Efficient distribution
- Lower bandwidth usage

Cons:

- More complex infrastructure

### Broadcast

Pros:

- Easy discovery mechanism

Cons:

- High network overhead

---

## Production Impact

Engineers encounter these concepts during:

- DNS troubleshooting
- ARP troubleshooting
- DHCP troubleshooting
- Routing investigations
- Network performance analysis
- Enterprise networking design

Understanding delivery models helps identify traffic patterns quickly.

---

## Common Interview Questions

- Unicast vs Multicast vs Broadcast?
- Why is broadcast limited to local networks?
- Why does ARP use broadcast?
- Why is multicast more efficient than unicast for streaming?
- What is a broadcast storm?
- Why don't routers forward broadcasts?
- Which communication model does HTTP use?
- Which communication model does DHCP use?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Unicast | One Sender To One Receiver |
| Multicast | One Sender To Interested Group |
| Broadcast | One Sender To Everyone |
| ARP | Uses Broadcast |
| DHCP Discovery | Uses Broadcast |
| HTTP | Uses Unicast |
| IPTV | Often Uses Multicast |
| Broadcast Storm | Excessive Broadcast Traffic |
| Router | Normally Blocks Broadcast Forwarding |
| Most Common Traffic Type | Unicast |