

# Linux Performance

## Why Performance Engineering Matters

Most production outages are not caused by complete system failure.

They are caused by performance degradation.

Examples:

- Slow APIs
- High latency databases
- Delayed batch jobs
- Kubernetes node pressure
- Resource contention

Performance engineering helps identify bottlenecks before they become incidents.

---

## The Engineering Problem

Applications compete for finite resources.

Examples:

- CPU
- Memory
- Storage
- Network bandwidth

When demand exceeds capacity:

```text
Resource Bottleneck
        ↓
Latency Increases
        ↓
User Impact
```

The goal of performance analysis is to identify the bottleneck rather than guessing.

---

## The Four Primary Resources

### CPU

Questions:

- Is CPU saturated?
- Is context switching excessive?
- Is load increasing?

### Memory

Questions:

- Is memory exhausted?
- Is swapping occurring?
- Is cache pressure increasing?

### Storage

Questions:

- Is I/O latency high?
- Are disks saturated?
- Is throughput limited?

### Network

Questions:

- Is packet loss occurring?
- Is latency increasing?
- Is bandwidth constrained?

---

## A Performance Investigation Mindset

Many engineers immediately blame the application.

Experienced engineers first collect evidence.

Typical workflow:

```text
Identify Symptoms
        ↓
Measure Resources
        ↓
Find Bottleneck
        ↓
Validate Hypothesis
        ↓
Implement Fix
        ↓
Measure Again
```

---

## Core Linux Performance Tools

### top

Real-time process visibility.

```bash
top
```

Useful for:

- CPU usage
- Memory usage
- Process analysis

---

### htop

Improved interactive monitoring.

```bash
htop
```

---

### vmstat

System-wide resource statistics.

```bash
vmstat
```

Useful for:

- CPU
- Memory
- Swap
- Context switches

---

### iostat

Storage performance analysis.

```bash
iostat
```

Useful for:

- Disk utilization
- I/O latency
- Throughput

---

### pidstat

Per-process performance metrics.

```bash
pidstat
```

---

### sar

Historical performance analysis.

```bash
sar
```

Useful when investigating incidents that already occurred.

---

## Common Production Bottlenecks

### CPU Bottleneck

Symptoms:

- High utilization
- Increased latency
- Slow response times

Investigation:

```bash
top
pidstat
```

### Memory Bottleneck

Symptoms:

- Swapping
- OOM events
- Slow applications

Investigation:

```bash
free -h
vmstat
```

### Storage Bottleneck

Symptoms:

- Slow queries
- Slow startup
- High wait times

Investigation:

```bash
iostat
iotop
```

### Network Bottleneck

Symptoms:

- Timeouts
- Packet loss
- Increased latency

Investigation:

```bash
ss
tcpdump
ping
```

---

## Performance Metrics Engineers Watch

### CPU Metrics

- Utilization
- Load Average
- Context Switches
- Run Queue Length

### Memory Metrics

- Available Memory
- Swap Usage
- Page Faults
- Cache Usage

### Storage Metrics

- IOPS
- Throughput
- Utilization
- Latency

### Network Metrics

- Throughput
- Errors
- Retransmissions
- Packet Loss

---

## Production Debugging Workflow

```text
User Reports Slowness
          ↓
Check CPU
          ↓
Check Memory
          ↓
Check Storage
          ↓
Check Network
          ↓
Identify Bottleneck
          ↓
Validate Fix
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Higher Throughput | More Resource Usage |
| Lower Latency | Increased Cost |
| Aggressive Caching | Higher Memory Consumption |
| Higher Concurrency | Greater Complexity |
| Better Utilization | Contention Risk |

---

## Interview Thinking

- How would you investigate a slow Linux server?
- CPU bound vs I/O bound workloads?
- What is load average?
- Why can low CPU systems still be slow?
- How would you identify a storage bottleneck?
- What metrics would you check first during an outage?
- Why is performance troubleshooting evidence-driven?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Performance Engineering | Bottleneck Identification |
| CPU | Compute Resource |
| Memory | Working Data Resource |
| Storage | Persistence Resource |
| Network | Communication Resource |
| top | Real-Time Monitoring |
| vmstat | System Statistics |
| iostat | Storage Analysis |
| pidstat | Process Metrics |
| sar | Historical Performance Data |