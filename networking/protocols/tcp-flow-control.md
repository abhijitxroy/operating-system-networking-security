

# TCP Flow Control

## Why TCP Flow Control Exists

Reliable communication requires more than successful delivery.

A sender may be able to transmit data faster than the receiver can process it.

Without protection:

```text
Fast Sender
      ↓
Slow Receiver
      ↓
Buffer Overflow
      ↓
Data Loss
```

TCP Flow Control exists to prevent receivers from being overwhelmed.

---

## The Engineering Problem

Imagine:

```text
Application A
      ↓
10 Gbps
      ↓
Application B
      ↓
1 Gbps Processing Capacity
```

The receiver cannot consume data fast enough.

The sender must slow down.

TCP Flow Control solves this problem.

---

## What Is Flow Control?

Flow Control is a mechanism that controls:

```text
How Much Data
A Sender Can Transmit
Before Receiving Acknowledgement
```

Goal:

```text
Protect Receiver
From Overload
```

---

## Flow Control vs Congestion Control

A very common interview question.

| Mechanism | Protects |
|----------|----------|
| Flow Control | Receiver |
| Congestion Control | Network |

Flow Control focuses on receiver capacity.

Congestion Control focuses on network capacity.

---

## TCP Receive Buffer

TCP maintains a receive buffer.

Example:

```text
Incoming Data
      ↓
Receive Buffer
      ↓
Application
```

The buffer temporarily stores incoming data.

---

## Receive Window (rwnd)

TCP advertises:

```text
Receive Window
(rwnd)
```

Purpose:

```text
Tell Sender
How Much Space Is Available
```

Example:

```text
Receive Buffer
Available = 64 KB
```

Receiver advertises:

```text
rwnd = 64 KB
```

---

## How Flow Control Works

Step 1:

```text
Receiver Advertises Window
```

Step 2:

```text
Sender Transmits Data
```

Step 3:

```text
Receiver Consumes Data
```

Step 4:

```text
Window Updated
```

The cycle repeats continuously.

---

## Sliding Window Mechanism

TCP uses a sliding window.

Concept:

```text
Data Sent
     ↓
ACK Received
     ↓
Window Moves Forward
```

This allows efficient transmission without waiting after every packet.

---

## Zero Window Condition

If the receive buffer becomes full:

```text
rwnd = 0
```

Meaning:

```text
Stop Sending Data
```

The sender temporarily pauses transmission.

---

## Zero Window Probe

When the receiver becomes available again:

TCP uses:

```text
Zero Window Probe
```

Purpose:

```text
Check Whether Receiver
Can Accept Data Again
```

---

## Flow Control Example

Receiver:

```text
Buffer Size = 64 KB
```

Advertises:

```text
rwnd = 64 KB
```

Sender:

```text
Can Send Up To 64 KB
```

As acknowledgements arrive:

```text
Window Slides Forward
```

Communication continues efficiently.

---

## Production Impact

Flow Control affects:

- API communication
- Database replication
- File transfers
- Streaming systems
- Distributed systems

Receiver bottlenecks often appear as throughput issues.

---

## Common Production Symptoms

### Slow Receiver

Symptoms:

- Reduced throughput
- Backpressure

### Full Receive Buffer

Symptoms:

- Zero window events

### Application Bottleneck

Symptoms:

- High latency
- Buffer growth

### Resource Constraints

Symptoms:

- Network underutilization

---

## Troubleshooting Commands

Linux:

```bash
ss -i
```

```bash
netstat -s
```

```bash
tcpdump
```

Useful for observing window size and TCP behavior.

---

## Common Interview Questions

- Why does TCP need Flow Control?
- Flow Control vs Congestion Control?
- What is rwnd?
- What is a receive buffer?
- What is a sliding window?
- What happens when rwnd becomes zero?
- What is a Zero Window Probe?
- How does TCP prevent receiver overload?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Flow Control | Protect Receiver |
| Congestion Control | Protect Network |
| Receive Buffer | Stores Incoming Data |
| rwnd | Receive Window |
| Sliding Window | Efficient Data Transfer |
| Zero Window | Receiver Full |
| Zero Window Probe | Resume Communication |
| Backpressure | Receiver Limitation |
| Throughput Impact | Receiver Dependent |
| Core Goal | Prevent Receiver Overload |