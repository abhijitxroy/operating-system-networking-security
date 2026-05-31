# Linux Process Management

## Why Process Management Matters

Every application running on Linux executes as one or more processes.

Web servers, databases, containers, monitoring agents, CI/CD tools and system services all ultimately depend on processes.

When production systems become slow, unstable or unavailable, process investigation is often one of the first troubleshooting activities.

Understanding process management is therefore a practical engineering skill rather than an operating system theory topic.

---

## The Engineering Problem

A Linux system may run hundreds or thousands of processes simultaneously.

Each process competes for:

- CPU time
- Memory
- Storage
- Network resources
- Operating system services

Linux must continuously decide:

- Which process runs next
- How resources are allocated
- When processes are terminated
- How process isolation is maintained

```text
Applications
      ↓
Processes
      ↓
Linux Scheduler
      ↓
CPU Execution
```

---

## What A Linux Process Actually Contains

A process is more than a running program.

It includes:

- Process ID (PID)
- Virtual memory
- Open files
- Network sockets
- Environment variables
- Security context
- Execution state

The operating system tracks and manages all of this information.

---

## Process Lifecycle

Typical lifecycle:

```text
Created
   ↓
Ready
   ↓
Running
   ↓
Waiting
   ↓
Running
   ↓
Terminated
```

Linux continuously transitions processes through these states.

---

## Why Process Isolation Matters

Without process isolation:

```text
Application Failure
       ↓
Entire System Impact
```

With process isolation:

```text
Application Failure
       ↓
Process Failure
       ↓
System Continues Running
```

Isolation improves:

- Stability
- Reliability
- Security

---

## Parent And Child Processes

Linux creates new processes using fork().

Example:

```text
Parent Process
       ↓
Child Process
```

This relationship is fundamental to Linux process management.

Useful command:

```bash
pstree
```

---

## Signals

Signals allow processes to communicate with each other.

Common examples:

### SIGTERM

Graceful shutdown request.

### SIGKILL

Immediate termination.

### SIGHUP

Configuration reload in many services.

Understanding signals is essential for operating production systems.

---

## Production Impact

Process behavior affects:

- Application availability
- Resource utilization
- Container workloads
- Kubernetes nodes
- Service reliability
- Platform stability

Many incidents ultimately involve runaway, stuck or leaking processes.

---

## Common Production Failures

### High CPU Process

Symptoms:

- System slowness
- High load average

Investigation:

```bash
top
htop
pidstat
```

### Memory Leaking Process

Symptoms:

- Increasing memory usage
- OOM events

Investigation:

```bash
ps aux --sort=-%mem
```

### Zombie Processes

Symptoms:

- Completed processes remain visible

Investigation:

```bash
ps -ef
```

### Runaway Process

Symptoms:

- Unexpected resource consumption
- System instability

Investigation:

```bash
top
ps
pidstat
```

---

## Linux Troubleshooting Commands

### Process List

```bash
ps -ef
```

### Interactive Monitoring

```bash
top
htop
```

### Process Tree

```bash
pstree
```

### Detailed Statistics

```bash
pidstat
```

### Open Files

```bash
lsof
```

### Send Signals

```bash
kill
kill -9
```

---

## Production Debugging Workflow

```text
Identify Impact
       ↓
Locate Process
       ↓
Measure Resource Usage
       ↓
Inspect Logs
       ↓
Find Root Cause
       ↓
Apply Fix
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| More Processes | Higher Resource Usage |
| Strong Isolation | Additional Overhead |
| Aggressive Monitoring | More Operational Cost |
| Graceful Shutdown | Slower Termination |
| High Concurrency | Greater Complexity |

---

## Interview Thinking

- Why were processes introduced?
- Process vs Program?
- Process vs Thread?
- What is a PID?
- What is a zombie process?
- What is an orphan process?
- SIGTERM vs SIGKILL?
- Why is graceful shutdown important?
- How would you investigate high CPU usage?
- How would you identify a memory leak?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Process | Running Execution Unit |
| PID | Process Identifier |
| Parent Process | Creates Child Process |
| Child Process | Forked Execution Unit |
| Signal | Process Communication Mechanism |
| SIGTERM | Graceful Shutdown |
| SIGKILL | Forced Termination |
| Zombie Process | Completed But Not Reaped |
| pstree | Process Relationships |
| pidstat | Process Performance Metrics |