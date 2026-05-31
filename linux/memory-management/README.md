

# Linux Memory Management

## Why Memory Management Matters

CPU problems are visible.

Memory problems are often silent until systems become unstable.

Many production incidents originate from:

- Memory leaks
- OOM events
- Excessive swapping
- Cache pressure
- Resource contention

Understanding Linux memory behavior is essential for debugging and operating production systems.

---

## The Engineering Problem

Applications need memory to execute.

Modern servers run:

- Applications
- Databases
- Containers
- Monitoring agents
- Background services

All compete for finite memory resources.

Linux must continuously decide:

- How memory is allocated
- When memory is reclaimed
- What happens when memory runs out
- Which workloads receive priority

```text
Applications
      ↓
Linux Memory Manager
      ↓
Physical Memory
```

---

## How Linux Thinks About Memory

Linux attempts to use available memory efficiently.

A common misunderstanding:

```text
Free Memory = Healthy
```

In reality:

Linux often uses free memory for:

- Page cache
- Buffers
- Filesystem acceleration

Unused memory is often considered wasted memory.

---

## Virtual Memory

Applications do not directly use physical memory.

Linux provides virtual memory.

Benefits:

- Isolation
- Security
- Large address spaces
- Better resource management

Applications believe they own memory independently even when sharing the same machine.

---

## Page Cache

One of the most important Linux performance features.

Linux caches filesystem data in memory.

Benefits:

- Faster reads
- Reduced disk access
- Improved application performance

Many engineers incorrectly assume high cache usage indicates a memory problem.

Often it is a performance optimization.

---

## Swap

### Why Swap Exists

Memory is finite.

Linux may move less frequently used pages to disk.

```text
RAM
 ↓
Swap
```

Benefits:

- Delays OOM situations
- Improves survivability during spikes

Tradeoff:

- Increased latency

Heavy swapping usually indicates memory pressure.

---

## OOM Killer

When Linux cannot satisfy memory requests:

```text
Memory Exhausted
        ↓
OOM Killer Activated
        ↓
Process Terminated
```

The OOM Killer exists to keep the system alive.

Without it, entire systems could become unusable.

---

## Production Impact

Memory behavior affects:

- API latency
- Database performance
- Container stability
- Kubernetes workloads
- Application availability
- Infrastructure efficiency

Many outages are caused by memory exhaustion rather than CPU shortages.

---

## Common Production Failures

### Memory Leak

Symptoms:

- Gradually increasing memory usage
- Eventual crashes

Investigation:

- Heap analysis
- Application profiling
- Runtime metrics

### OOM Events

Symptoms:

- Sudden process termination
- Container restarts

Investigation:

```bash
dmesg
journalctl -k
```

### Excessive Swapping

Symptoms:

- High latency
- Slow applications
- System stalls

Investigation:

```bash
vmstat
free -h
sar
```

### Cache Pressure

Symptoms:

- Reduced performance
- Frequent disk activity

Investigation:

```bash
vmstat
iostat
```

---

## Linux Troubleshooting Commands

### Memory Overview

```bash
free -h
```

### Virtual Memory Statistics

```bash
vmstat
```

### Detailed Memory Information

```bash
cat /proc/meminfo
```

### OOM Investigation

```bash
dmesg
journalctl -k
```

### Historical Analysis

```bash
sar
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Aggressive Caching | Less Free Memory |
| Swap Usage | Higher Latency |
| High Density | Resource Contention |
| Memory Efficiency | Operational Complexity |
| Isolation | Additional Overhead |

---

## Interview Thinking

- Why does Linux use cache aggressively?
- Why is free memory not always a useful metric?
- Why does swap exist?
- What is the OOM Killer?
- How would you investigate memory pressure?
- How would you investigate OOM events?
- Why can swapping destroy performance?
- How would you differentiate a memory leak from cache usage?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Virtual Memory | Memory Abstraction Layer |
| Page Cache | Filesystem Data Cache |
| Swap | Disk-Based Memory Extension |
| OOM Killer | Protects System During Exhaustion |
| Memory Leak | Unreleased Memory Growth |
| free -h | Memory Overview |
| vmstat | Virtual Memory Statistics |
| /proc/meminfo | Detailed Memory Information |
| dmesg | Kernel Events |
| Memory Pressure | Demand Exceeds Available Resources |