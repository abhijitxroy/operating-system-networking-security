

# Memory Management

## Why Memory Management Was Invented

Early computers executed one program at a time.

As systems evolved, multiple applications started running simultaneously.

This created a new problem.

Multiple programs needed memory at the same time.

Without proper memory management:

- Applications could overwrite each other's data
- System crashes became common
- Memory utilization remained poor
- Security isolation was impossible

Memory management was created to solve resource sharing, isolation, and efficiency problems.

---

## The Engineering Problem

Memory is a finite resource.

Every running process needs:

- Application code
- Runtime libraries
- Heap memory
- Stack memory
- Cached data

The operating system must continuously answer:

- Who gets memory?
- How much memory?
- When should memory be reclaimed?
- How can processes be isolated?
- How can limited memory support large workloads?

```text
Applications
      ↓
Memory Manager
      ↓
Physical Memory (RAM)
```

---

## What Memory Management Actually Does

Modern operating systems provide:

- Memory allocation
- Memory isolation
- Virtual memory
- Address translation
- Memory protection
- Page management
- Memory reclamation
- Performance optimization

Most applications believe they own memory exclusively.

The operating system creates that illusion.

---

## How Memory Management Evolved

### Direct Memory Access

Applications accessed physical memory directly.

Problems:

- No isolation
- Frequent corruption
- Poor stability

### Fixed Partitioning

Memory divided into predefined regions.

Problems:

- Internal fragmentation
- Wasted memory

### Paging

Introduced virtual memory pages.

Solved:

- Better utilization
- Process isolation

### Modern Virtual Memory

Focuses on:

- Scalability
- Isolation
- Large address spaces
- Performance

---

## Virtual Memory

Virtual memory is one of the most important operating system innovations.

Applications use virtual addresses.

The operating system maps them to physical memory.

Benefits:

- Process isolation
- Large address spaces
- Improved security
- Better memory utilization

Without virtual memory, modern operating systems would not scale effectively.

---

## Paging

Paging divides memory into fixed-size units.

Benefits:

- Simplified allocation
- Improved isolation
- Efficient memory management

Challenges:

- Page faults
- Translation overhead
- Fragmentation concerns

---

## TLB (Translation Lookaside Buffer)

Address translation occurs frequently.

Performing page table lookups for every memory access would be expensive.

TLB acts as a cache for address translations.

Benefits:

- Faster memory access
- Reduced translation overhead

TLB performance directly impacts application performance.

---

## Production Impact

Memory behavior directly affects:

- API latency
- Database performance
- JVM applications
- Containers
- Kubernetes nodes
- Cloud infrastructure

Many production incidents originate from memory pressure rather than CPU limitations.

---

## Common Production Failures

### Memory Leak

Symptoms:

- Memory usage continuously grows
- Application eventually crashes

Investigation:

- Heap analysis
- Memory profiling
- Garbage collection metrics

### Out Of Memory (OOM)

Symptoms:

- Process termination
- OOM Killer events

Investigation:

```bash
dmesg
journalctl -k
```

### Excessive Swapping

Symptoms:

- High latency
- Slow applications
- System appears frozen

Investigation:

```bash
vmstat
free -h
sar
```

### Page Fault Storms

Symptoms:

- High CPU usage
- Performance degradation

Investigation:

```bash
vmstat
sar
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

### Process Memory Usage

```bash
top
htop
ps
```

### Kernel Memory Information

```bash
cat /proc/meminfo
```

### Historical Analysis

```bash
sar
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Isolation | Additional Overhead |
| Virtual Memory | Translation Cost |
| Large Caches | Reduced Free Memory |
| Swapping | Higher Latency |
| Performance | Increased Complexity |
| Protection | Additional Processing |

---

## Interview Thinking

- Why was virtual memory invented?
- Why can't processes directly access physical memory?
- What problem does paging solve?
- Why is the TLB important?
- What causes page faults?
- What is memory fragmentation?
- How would you investigate a memory leak?
- What happens when a Linux system runs out of memory?
- What is the OOM Killer?
- Why can excessive swapping destroy performance?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Memory Management | Controls Memory Usage |
| Virtual Memory | Address Abstraction Layer |
| Physical Memory | Actual RAM |
| Paging | Fixed Size Memory Units |
| Page Fault | Missing Page Access |
| TLB | Address Translation Cache |
| Memory Leak | Unreleased Memory Growth |
| Swapping | Memory Moved To Disk |
| OOM Killer | Terminates Processes During Memory Exhaustion |
| Isolation | Prevents Process Interference |