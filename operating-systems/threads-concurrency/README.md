

# Threads And Concurrency

## Why Threads Were Invented

Processes solved one major problem.

They provided isolation.

However, engineers soon discovered another challenge.

Creating processes is relatively expensive.

Every process requires:

- Separate memory space
- Process metadata
- Resource management
- Context switching overhead

Many workloads needed concurrent execution without the cost of creating multiple processes.

Threads were introduced to solve this problem.

A thread became the smallest unit of execution inside a process.

---

## The Engineering Problem

Modern applications often perform multiple activities simultaneously.

Examples:

- Web servers handling requests
- Databases processing queries
- Browsers loading pages
- IDEs compiling code
- Streaming platforms processing data

Running everything sequentially wastes CPU resources and reduces responsiveness.

Concurrency allows multiple tasks to make progress at the same time.

```text
Process
 ├── Thread 1
 ├── Thread 2
 ├── Thread 3
 └── Thread 4
```

---

## Process vs Thread

### Process

Owns:

- Memory space
- Files
- Security context
- Resources

### Thread

Shares:

- Process memory
- Files
- Resources

Has its own:

- Stack
- Registers
- Program counter

This sharing makes threads significantly lighter than processes.

---

## Why Concurrency Exists

Concurrency improves:

- Responsiveness
- Throughput
- Resource utilization
- Scalability

Example:

```text
Single Thread
      ↓
Request Waits For Database
      ↓
CPU Idle
```

With concurrency:

```text
Thread A Waiting
Thread B Working
Thread C Processing
```

The CPU remains productive.

---

## Concurrency Is Not Parallelism

A common interview topic.

### Concurrency

Multiple tasks make progress.

### Parallelism

Multiple tasks execute simultaneously.

```text
Concurrency
Task A ↔ Task B

Parallelism
Task A + Task B At Same Time
```

Modern systems often use both.

---

## Why Concurrency Creates Problems

Threads share memory.

Shared memory creates risks.

Examples:

- Race conditions
- Deadlocks
- Starvation
- Data corruption
- Lock contention

Most production concurrency bugs originate from shared state.

---

## Thread Lifecycle

Typical lifecycle:

```text
New
 ↓
Runnable
 ↓
Running
 ↓
Blocked
 ↓
Runnable
 ↓
Terminated
```

The scheduler continuously manages these transitions.

---

## Context Switching

The operating system switches CPU execution between threads.

Benefits:

- Better utilization
- Fair scheduling

Cost:

- CPU overhead
- Cache invalidation
- Performance impact

Excessive context switching can reduce overall throughput.

---

## Production Impact

Threads directly affect:

- API performance
- Database throughput
- JVM applications
- Containers
- Kubernetes workloads
- Cloud services

Modern backend systems depend heavily on concurrency.

Poor concurrency design often limits scalability before infrastructure limits are reached.

---

## Common Production Failures

### Thread Explosion

Symptoms:

- High CPU usage
- Memory pressure
- Reduced throughput

Investigation:

```bash
ps -eLf
jstack
```

### Thread Starvation

Symptoms:

- Some tasks never execute
- Growing queues

Investigation:

- Thread dump analysis
- Scheduler review

### Lock Contention

Symptoms:

- Slow response times
- Reduced scalability

Investigation:

- Profilers
- Thread dumps
- Lock analysis

### Race Conditions

Symptoms:

- Intermittent failures
- Data corruption
- Difficult reproduction

Investigation:

- Concurrency testing
- Code review
- Load testing

---

## Modern Concurrency Models

Engineers commonly use:

- Thread pools
- Event loops
- Reactive systems
- Actor models
- Async programming
- Coroutines

Most modern frameworks try to reduce the complexity of direct thread management.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| More Threads | More Overhead |
| Higher Concurrency | Greater Complexity |
| Shared Memory | Synchronization Risks |
| Better Throughput | Harder Debugging |
| Low Latency | Increased Resource Usage |

---

## Interview Thinking

- Why were threads invented?
- Process vs Thread?
- Why are threads cheaper than processes?
- Concurrency vs Parallelism?
- Why does shared memory create problems?
- What is thread starvation?
- What causes lock contention?
- Why can more threads reduce performance?
- How would you debug a concurrency issue?
- Why do modern frameworks use thread pools?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Thread | Smallest Unit Of Execution |
| Process | Resource Ownership Boundary |
| Concurrency | Multiple Tasks Make Progress |
| Parallelism | Multiple Tasks Execute Simultaneously |
| Context Switch | CPU Changes Execution Unit |
| Race Condition | Result Depends On Timing |
| Lock Contention | Threads Compete For Resource |
| Thread Pool | Reusable Worker Threads |
| Starvation | Thread Never Gets CPU Or Resource |
| Shared Memory | Enables Fast Communication But Adds Risk |