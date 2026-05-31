# Threads And Concurrency

## Why Threads Were Invented

Processes provide isolation.

However, process creation is relatively expensive.

As applications became more complex, engineers needed a lighter execution model.

Common requirements:

- Parallel work
- Better CPU utilization
- Faster response times
- Shared memory access
- Reduced process overhead

Threads were introduced to solve these problems.

---

## The Engineering Problem

Consider a web server.

Without concurrency:

```text
Request 1
   ↓
Request 2
   ↓
Request 3
```

Every request waits.

As traffic increases:

- Latency grows
- Throughput drops
- User experience degrades

Engineers needed a way to perform multiple tasks simultaneously.

---

## Process vs Thread

A process owns resources.

A thread executes work.

```text
Process
 ├── Thread 1
 ├── Thread 2
 └── Thread 3
```

Threads share:

- Memory
- Files
- Network connections
- Process resources

But maintain their own:

- Stack
- Registers
- Execution state

---

## Why Concurrency Matters

Modern systems perform many activities simultaneously.

Examples:

- Handling API requests
- Database operations
- Log processing
- Background jobs
- Container workloads

Concurrency improves:

- Responsiveness
- Throughput
- Resource utilization

---

## Why Concurrency Is Hard

Shared resources create risk.

Example:

```text
Thread A
      ↓
Shared Data
      ↑
Thread B
```

Potential problems:

- Race conditions
- Deadlocks
- Starvation
- Data corruption

Concurrency improves performance but increases complexity.

---

## Race Conditions

Race conditions occur when outcomes depend on execution timing.

Symptoms:

- Inconsistent behavior
- Data corruption
- Intermittent failures

These are among the most difficult production bugs to reproduce.

---

## Synchronization

Synchronization protects shared resources.

Common mechanisms:

- Mutexes
- Semaphores
- Read/Write Locks
- Condition Variables
- Atomic Operations

Purpose:

```text
Correctness
      ↓
Predictable Behavior
```

---

## Deadlocks

Concurrency introduces locking.

Locking introduces deadlock risk.

Example:

```text
Thread A Waiting For B
Thread B Waiting For A
```

Neither can proceed.

Deadlocks remain a common production issue.

---

## Production Impact

Threads and concurrency affect:

- API servers
- Databases
- Kubernetes workloads
- Distributed systems
- Message processing systems
- Cloud platforms

Most high-performance applications depend heavily on concurrency.

---

## Common Production Failures

### Race Conditions

Symptoms:

- Random failures
- Data inconsistency

### Deadlocks

Symptoms:

- Requests hang indefinitely
- Thread pools stall

### Thread Leaks

Symptoms:

- Growing thread count
- Resource exhaustion

### Thread Pool Saturation

Symptoms:

- High latency
- Request backlogs

### Lock Contention

Symptoms:

- Low throughput
- High waiting time

---

## Linux Investigation Examples

### Process And Thread View

```bash
ps -eLf
```

### CPU Analysis

```bash
top -H
```

### Thread Statistics

```bash
pidstat -t
```

### Java Thread Dumps

```bash
jstack
```

### Open Resources

```bash
lsof
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Higher Throughput | More Complexity |
| Shared Memory Efficiency | Synchronization Risk |
| Faster Execution | Debugging Difficulty |
| Concurrency | Race Conditions |
| Parallelism | Lock Contention |

---

## Interview Thinking

- Why were threads invented?
- Process vs Thread?
- Why is concurrency difficult?
- What is a race condition?
- What is synchronization?
- What causes deadlocks?
- Thread vs Process memory model?
- How would you investigate thread contention?
- How would you debug a deadlock?
- Why do modern servers rely heavily on concurrency?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Thread | Lightweight Execution Unit |
| Process | Resource Owner |
| Concurrency | Multiple Tasks Progressing Together |
| Parallelism | Simultaneous Execution |
| Race Condition | Timing Dependent Failure |
| Mutex | Mutual Exclusion Mechanism |
| Semaphore | Resource Coordination Mechanism |
| Deadlock | Circular Waiting Condition |
| Thread Pool | Managed Worker Threads |
| Lock Contention | Competition For Shared Resources |