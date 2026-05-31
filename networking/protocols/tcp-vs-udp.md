

# TCP vs UDP

## Why Do We Need Both TCP And UDP?

Network applications have different requirements.

Some applications require:

- Reliability
- Ordered delivery
- Error recovery

Others require:

- Speed
- Low latency
- Minimal overhead

A single protocol cannot optimize for both goals.

TCP and UDP were created to solve different communication problems.

---

## The Engineering Problem

Imagine two scenarios.

Scenario 1:

```text
Online Banking
```

Every byte matters.

Data loss is unacceptable.

Scenario 2:

```text
Live Video Call
```

A delayed packet is often worse than a lost packet.

Different applications require different transport protocols.

---

## What Is TCP?

TCP stands for:

```text
Transmission Control Protocol
```

TCP is:

- Connection oriented
- Reliable
- Ordered
- Error checked

TCP prioritizes correctness over speed.

---

## TCP Characteristics

TCP provides:

### Three-Way Handshake

```text
SYN
 ↓
SYN-ACK
 ↓
ACK
```

### Reliable Delivery

Lost packets are retransmitted.

### Ordered Delivery

Data arrives in the correct sequence.

### Flow Control

Protects receivers.

### Congestion Control

Protects networks.

---

## What Is UDP?

UDP stands for:

```text
User Datagram Protocol
```

UDP is:

- Connectionless
- Lightweight
- Fast
- Minimal overhead

UDP prioritizes speed over reliability.

---

## UDP Characteristics

UDP provides:

- No handshake
- No retransmission
- No ordering guarantee
- No flow control
- No congestion control

The application is responsible for handling failures if needed.

---

## TCP vs UDP Comparison

| Feature | TCP | UDP |
|----------|----------|----------|
| Connection | Yes | No |
| Reliability | Yes | No |
| Ordering | Yes | No |
| Handshake | Yes | No |
| Retransmission | Yes | No |
| Flow Control | Yes | No |
| Congestion Control | Yes | No |
| Speed | Slower | Faster |
| Overhead | Higher | Lower |

---

## TCP Communication Flow

```text
Connection Setup
       ↓
Data Transfer
       ↓
Acknowledgements
       ↓
Reliable Delivery
```

TCP continuously tracks communication state.

---

## UDP Communication Flow

```text
Send Packet
      ↓
Best Effort Delivery
```

No connection state is maintained.

---

## Common TCP Use Cases

Applications requiring reliability:

- HTTP
- HTTPS
- SSH
- SMTP
- Databases
- APIs
- File Transfers

Missing data cannot be tolerated.

---

## Common UDP Use Cases

Applications prioritizing speed:

- DNS
- VoIP
- Video Conferencing
- Online Gaming
- Live Streaming
- DHCP

Low latency is more important than perfect reliability.

---

## Why DNS Uses UDP

A common interview question.

Most DNS queries are:

```text
Small
Fast
Request/Response
```

UDP avoids TCP handshake overhead.

This improves performance.

---

## Why HTTP Uses TCP

Another common interview question.

Web pages require:

```text
Reliable Delivery
Ordered Data
```

Missing packets could corrupt content.

TCP guarantees correctness.

---

## Production Impact

Protocol selection affects:

- Latency
- Throughput
- Reliability
- Scalability
- User experience

Choosing the wrong protocol can create performance or reliability issues.

---

## Common Production Problems

### TCP Retransmissions

Symptoms:

- Increased latency
- Reduced throughput

### TCP Connection Exhaustion

Symptoms:

- Connection failures
- Resource pressure

### UDP Packet Loss

Symptoms:

- Audio drops
- Video glitches

### Network Congestion

Symptoms:

- Poor application performance

---

## Common Interview Questions

- TCP vs UDP?
- Why is TCP reliable?
- Why is UDP faster?
- Why does DNS use UDP?
- Why does HTTP use TCP?
- Can UDP be reliable?
- When should TCP be used?
- When should UDP be used?
- Which protocol is connectionless?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| TCP | Reliable Communication |
| UDP | Fast Communication |
| TCP Handshake | Required |
| UDP Handshake | Not Required |
| TCP Ordering | Guaranteed |
| UDP Ordering | Not Guaranteed |
| HTTP/HTTPS | TCP |
| DNS | Usually UDP |
| Gaming | Often UDP |
| Most Common Interview Question | TCP vs UDP Tradeoffs |