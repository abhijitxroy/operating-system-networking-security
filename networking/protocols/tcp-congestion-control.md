

# TCP Congestion Control

## Why TCP Congestion Control Exists

Early networks experienced a major problem.

```text
More Traffic
      ↓
More Packet Loss
      ↓
More Retransmissions
      ↓
Even More Traffic
      ↓
Network Collapse
```

Without congestion control, TCP connections could overwhelm networks.

TCP Congestion Control was created to prevent congestion collapse and maintain network stability.

---

## The Engineering Problem

Imagine a highway.

```text
10 Cars
      ↓
Smooth Traffic
```

Now imagine:

```text
10,000 Cars
      ↓
Traffic Jam
```

Networks behave similarly.

If senders transmit data faster than the network can handle, congestion occurs.

TCP must automatically detect and react to congestion.

---

## What Is Congestion?

Congestion occurs when:

```text
Incoming Traffic
       >
Network Capacity
```

Results:

- Packet loss
- Increased latency
- Queue buildup
- Reduced throughput

---

## How TCP Detects Congestion

TCP cannot directly see congestion.

Instead it looks for symptoms.

Common signals:

- Packet loss
- Duplicate acknowledgements
- Retransmission timeout
- Increased latency

TCP assumes packet loss often indicates congestion.

---

## Congestion Window (cwnd)

TCP maintains:

```text
Congestion Window
(cwnd)
```

Purpose:

```text
Control
How Much Data
Can Be In Flight
```

The congestion window expands when the network is healthy and shrinks when congestion is detected.

---

## Slow Start

When a connection begins:

TCP does not know network capacity.

Therefore it starts conservatively.

```text
1
↓
2
↓
4
↓
8
↓
16
```

Growth is exponential.

This phase is called:

```text
Slow Start
```

Despite the name, growth is actually very aggressive.

---

## Slow Start Threshold

TCP maintains:

```text
ssthresh
```

When reached:

```text
Slow Start
      ↓
Congestion Avoidance
```

The growth pattern changes.

---

## Congestion Avoidance

After reaching the threshold:

Growth becomes slower.

```text
16
↓
17
↓
18
↓
19
```

Growth is approximately linear.

Goal:

```text
Increase Carefully
Without Causing Congestion
```

---

## Packet Loss Detection

TCP interprets packet loss as a warning sign.

Example:

```text
Packet Sent
      ↓
ACK Missing
      ↓
Potential Congestion
```

TCP responds by reducing transmission rate.

---

## Fast Retransmit

If TCP receives:

```text
3 Duplicate ACKs
```

It assumes a packet was lost.

Instead of waiting for timeout:

```text
Immediate Retransmission
```

This improves recovery speed.

---

## Fast Recovery

After Fast Retransmit:

TCP reduces the congestion window.

However it does not restart completely.

Benefits:

- Faster recovery
- Better throughput
- Reduced performance impact

---

## Congestion Control Algorithms

Over time multiple algorithms evolved.

### Tahoe

Introduced:

- Slow Start
- Congestion Avoidance
- Fast Retransmit

### Reno

Added:

- Fast Recovery

### New Reno

Improved loss recovery.

### CUBIC

Default in many Linux systems.

Designed for:

- High bandwidth networks
- Long-distance links

### BBR

Developed by:

```text
Google
```

Focus:

```text
Bandwidth
+
Round Trip Time
```

Rather than relying mainly on packet loss.

---

## Production Impact

Congestion control directly affects:

- API performance
- File transfers
- Cloud networking
- Kubernetes networking
- Video streaming
- Database replication

Large-scale systems depend heavily on TCP congestion behavior.

---

## Common Production Symptoms

### Packet Loss

Symptoms:

- Reduced throughput
- Retransmissions

### Network Congestion

Symptoms:

- High latency
- Queue buildup

### Long Distance Links

Symptoms:

- Poor TCP utilization

### Misconfigured Networks

Symptoms:

- Unstable performance

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

Useful for investigating retransmissions and congestion behavior.

---

## Common Interview Questions

- Why does TCP need congestion control?
- What is congestion collapse?
- What is the congestion window?
- What is Slow Start?
- What is Congestion Avoidance?
- What are duplicate ACKs?
- What is Fast Retransmit?
- Reno vs CUBIC vs BBR?
- Why does packet loss reduce throughput?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Congestion Control | Prevent Network Overload |
| cwnd | Congestion Window |
| Slow Start | Exponential Growth |
| ssthresh | Slow Start Threshold |
| Congestion Avoidance | Linear Growth |
| Packet Loss | Congestion Signal |
| Fast Retransmit | Recover Without Timeout |
| Reno | Fast Recovery Support |
| CUBIC | Common Linux Default |
| BBR | Bandwidth And RTT Based Approach |