

# Network Latency, Bandwidth And Throughput

## Why This Topic Exists

Engineers frequently say:

```text
The Network Is Slow
```

However network performance problems usually fall into different categories.

Examples:

- High latency
- Low bandwidth
- Poor throughput
- Packet loss
- Network congestion

Understanding the difference is critical for troubleshooting and system design.

---

## The Engineering Problem

Many production incidents are misdiagnosed because engineers confuse:

```text
Latency
Bandwidth
Throughput
```

These terms describe different aspects of network behavior.

Optimizing the wrong one often fails to solve the problem.

---

## Latency

Latency measures:

```text
How Long Data Takes To Travel
From Source To Destination
```

Typically measured in:

```text
Milliseconds (ms)
```

Example:

```text
Request
    ↓
50 ms
    ↓
Response
```

Lower latency generally improves responsiveness.

---

## Real-World Analogy

Imagine a highway.

```text
Latency
     ↓
Travel Time
```

Example:

```text
City A → City B
30 Minutes
```

Latency is how long the journey takes.

---

## Bandwidth

Bandwidth measures:

```text
Maximum Data Capacity
```

Common units:

```text
Mbps
Gbps
Tbps
```

Example:

```text
1 Gbps Link
```

Bandwidth describes potential capacity.

It does not guarantee actual performance.

---

## Real-World Analogy

Using the highway example:

```text
Bandwidth
      ↓
Number Of Lanes
```

More lanes allow more vehicles to travel simultaneously.

---

## Throughput

Throughput measures:

```text
Actual Data Successfully Delivered
```

Example:

```text
1 Gbps Capacity
500 Mbps Actual Transfer
```

Throughput is what users experience.

---

## Why Throughput Is Lower Than Bandwidth

Common causes:

- Congestion
- Packet loss
- TCP limitations
- Protocol overhead
- Resource bottlenecks

Example:

```text
Bandwidth = 1 Gbps
Throughput = 650 Mbps
```

This is normal in real systems.

---

## Latency vs Bandwidth

A common interview question.

Example:

```text
Satellite Internet
```

Characteristics:

```text
High Bandwidth
High Latency
```

Example:

```text
Local Data Center Network
```

Characteristics:

```text
Lower Bandwidth
Very Low Latency
```

Bandwidth and latency are independent metrics.

---

## Packet Loss

Packet loss occurs when packets fail to reach their destination.

Effects:

- Retransmissions
- Reduced throughput
- Increased latency
- Poor application performance

Even small packet loss can significantly impact TCP performance.

---

## Jitter

Jitter measures variation in latency.

Example:

```text
Packet 1 = 10 ms
Packet 2 = 90 ms
Packet 3 = 15 ms
```

High jitter affects:

- Video calls
- Voice traffic
- Real-time applications

---

## Production Impact

Engineers regularly investigate:

- Slow APIs
- Video conferencing issues
- Database latency
- Cloud networking delays
- Cross-region communication

Understanding these metrics improves troubleshooting speed.

---

## Common Production Failures

### High Latency

Symptoms:

- Slow requests
- Poor responsiveness

### Bandwidth Saturation

Symptoms:

- Congestion
- Queue buildup

### Packet Loss

Symptoms:

- Retransmissions
- Performance degradation

### High Jitter

Symptoms:

- Choppy voice calls
- Streaming issues

### TCP Congestion

Symptoms:

- Reduced throughput
- Slow transfers

---

## Troubleshooting Mindset

```text
Application Slow
       ↓
Measure Latency
       ↓
Measure Throughput
       ↓
Check Packet Loss
       ↓
Check Congestion
       ↓
Identify Root Cause
```

Never assume bandwidth is the problem.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Higher Bandwidth | Increased Cost |
| Lower Latency | Infrastructure Investment |
| Global Reach | Higher Network Delay |
| Redundancy | More Complexity |
| Traffic Optimization | Additional Operational Overhead |

---

## Interview Thinking

- Latency vs bandwidth?
- Bandwidth vs throughput?
- Why is throughput lower than bandwidth?
- What causes packet loss?
- What is jitter?
- Why do video calls suffer from jitter?
- High bandwidth but poor performance possible?
- How would you troubleshoot a slow network?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Latency | Time Required To Deliver Data |
| Bandwidth | Maximum Network Capacity |
| Throughput | Actual Data Delivered |
| Packet Loss | Missing Network Traffic |
| Jitter | Variation In Latency |
| Congestion | Excess Traffic Demand |
| High Bandwidth | Not Equal To High Performance |
| Low Latency | Better Responsiveness |
| TCP Performance | Sensitive To Packet Loss |
| Most Common Mistake | Confusing Bandwidth With Throughput |