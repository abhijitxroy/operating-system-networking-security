# Processes

## Why Processes Were Invented

Early computing systems ran programs directly on hardware, but this approach lacked flexibility and safety.

Programs needed a way to run independently, manage resources, and coexist without interfering.

Processes were invented to provide isolated, manageable units of execution.

---

## The Engineering Problem

Multiple applications want to run simultaneously on a single machine.

Without process abstraction:

- Programs interfere with each other's memory and resources.
- Bugs in one program can crash the entire system.
- Coordinating CPU time and resource access is chaotic.
- Debugging and monitoring become difficult.

Processes solve these problems by encapsulating execution contexts and providing isolation.

---

## Program vs Process

A **program** is a passive set of instructions stored on disk.

A **process** is a running instance of a program with its own state and resources.

Multiple processes can run the same program simultaneously, each with independent execution.

---

## What A Process Actually Contains

- **PID (Process ID):** Unique identifier for the process.
- **Memory:** Code, data, stack, and heap segments.
- **Open Files:** Handles to files, sockets, pipes the process uses.
- **Network Connections:** Active communication endpoints.
- **Execution State:** CPU registers, program counter, stack pointer, and scheduling info.

These components allow the OS to manage and isolate processes effectively.

---

## Process Lifecycle

Processes move through stages:

- **New:** Created but not yet running.
- **Running:** Actively executing instructions.
- **Waiting:** Paused, waiting for I/O or events.
- **Ready:** Waiting to be scheduled.
- **Terminated:** Finished execution or killed.

The OS manages transitions to maximize utilization and responsiveness.

---

## Process Creation And Termination

Processes are typically created by:

- **Forking:** Creating a child process duplicating the parent.
- **Exec:** Replacing a process’s memory with a new program.

Termination happens when:

- Process completes work.
- Killed by another process or the OS.
- Crashes due to errors.

Proper creation and cleanup are essential to prevent resource leaks.

---

## Parent And Child Processes

Processes form hierarchies.

- Parent processes spawn children.
- Children inherit some resources but run independently.
- The OS tracks relationships for signaling and cleanup.

In containerized and cloud environments, process trees reflect workload structures and dependencies.

---

## Context Switching: Why It Exists

The CPU can only execute one process at a time.

Context switching saves the current process state and loads another’s state to share CPU time.

This enables multitasking and responsiveness but adds overhead.

Excessive switching can degrade performance, especially in high-demand systems.

---

## Why Process Isolation Matters

Isolation prevents processes from:

- Accessing or corrupting each other's memory.
- Interfering with resources or data.
- Compromising system stability and security.

Containers and Kubernetes rely heavily on process isolation to enforce workload boundaries.

---

## Production Impact

Process behavior directly affects:

- Application responsiveness and throughput.
- Container resource limits and scheduling.
- Database connection handling.
- Cloud platform scaling and reliability.

Process failures or inefficiencies propagate to user experience and infrastructure costs.

---

## Common Production Failures

### Runaway Processes

Consume excessive CPU or memory, starving other workloads.

### Zombie Processes

Terminated but not cleaned up, consuming process table entries.

### Orphan Processes

Lost parent processes, adopted by init, can cause resource leaks.

### Memory Leaking Processes

Gradually consume more memory, leading to exhaustion.

### Excessive Context Switching

High CPU overhead reducing effective throughput.

---

## Linux Investigation Examples

```bash
ps          # View process list and states
top         # Real-time CPU and memory usage
htop        # Interactive process viewer with tree view
pstree      # Visualize process hierarchies
pidstat     # Detailed per-process statistics
lsof        # List open files and network connections per process
```

These tools help diagnose process-related issues in production environments.

---

## Engineering Tradeoffs

| Goal               | Tradeoff                 |
|--------------------|--------------------------|
| Performance        | Context Switching Overhead |
| Isolation          | Resource Duplication      |
| Responsiveness     | Increased Scheduling Complexity |
| Resource Sharing   | Potential Interference    |
| Scalability       | Management Overhead       |

---

## Interview Thinking

- Why do processes provide better resource management than running programs directly?
- How does process isolation improve security in multi-tenant environments?
- What problems arise from runaway or zombie processes?
- How does context switching enable multitasking but affect performance?
- How do parent-child relationships affect process lifecycle and cleanup?
- How would you investigate high CPU usage caused by a runaway process?
- How do containers leverage process concepts to enforce boundaries?

---

## Quick Revision

| Concept             | Key Idea                        |
|---------------------|--------------------------------|
| Process             | Running instance of a program  |
| PID                 | Unique process identifier      |
| Context Switching   | CPU sharing mechanism           |
| Process Isolation   | Prevents interference and corruption |
| Parent Process      | Spawns and manages children    |
| Zombie Process      | Terminated but uncleared       |
| Orphan Process      | Lost parent, adopted by init   |
| Runaway Process     | Excessive resource consumption |
| lsof                | Lists process open files       |
| pstree              | Shows process hierarchies      |