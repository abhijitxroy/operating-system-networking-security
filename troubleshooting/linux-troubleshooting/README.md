

# Linux Troubleshooting

## Why Linux Troubleshooting Exists

Most modern infrastructure ultimately runs on Linux.

Examples:

- Cloud servers
- Containers
- Kubernetes nodes
- Databases
- Monitoring systems
- CI/CD platforms

When production incidents occur, engineers often need Linux-level visibility to identify the root cause.

Linux troubleshooting exists to systematically investigate operating system behavior.

---

## The Engineering Problem

Applications frequently report symptoms.

Examples:

- Slow responses
- High latency
- Timeouts
- Service crashes
- Resource exhaustion

The actual cause may exist at the operating system layer.

```text
Application Problem
        ↓
Linux Resource Issue
        ↓
Root Cause
```

Engineers must investigate below the application layer.

---

## Common Linux Failure Domains

### CPU

Examples:

- CPU saturation
- Runaway processes
- Excessive context switching

### Memory

Examples:

- Memory leaks
- OOM events
- Swap pressure

### Storage

Examples:

- Disk full
- High I/O wait
- Inode exhaustion

### Networking

Examples:

- DNS failures
- Connection issues
- Packet loss

### Processes

Examples:

- Hung processes
- Zombie processes
- Service crashes

---

## A Practical Troubleshooting Workflow

```text
Identify Impact
      ↓
Check Resources
      ↓
Review Logs
      ↓
Analyze Processes
      ↓
Analyze Dependencies
      ↓
Find Root Cause
```

Avoid changing system configuration before gathering evidence.

---

## CPU Troubleshooting

Common symptoms:

- High latency
- Slow applications
- System unresponsiveness

Useful commands:

```bash
top
htop
mpstat
pidstat
```

Investigation:

- High CPU processes
- Context switching
- Load averages

---

## Memory Troubleshooting

Common symptoms:

- OOMKilled workloads
- Slow performance
- Process crashes

Useful commands:

```bash
free -h
vmstat
cat /proc/meminfo
```

Investigation:

- Available memory
- Swap usage
- Memory growth trends

---

## Disk Troubleshooting

Common symptoms:

- Write failures
- Application instability
- Slow databases

Useful commands:

```bash
df -h
du -sh
iostat
```

Investigation:

- Disk utilization
- I/O wait
- Inode usage

---

## Process Troubleshooting

Processes often reveal the actual issue.

Useful commands:

```bash
ps -ef
pstree
lsof
```

Investigation:

- Process state
- Open files
- Resource usage

---

## Log Analysis

Logs are often the fastest path to diagnosis.

Useful commands:

```bash
journalctl
tail
less
grep
```

Review:

- Errors
- Warnings
- Service failures
- Kernel messages

---

## Networking Troubleshooting

Useful commands:

```bash
ping
ss
netstat
dig
traceroute
```

Common symptoms:

- Timeouts
- DNS failures
- Connectivity issues

---

## Production Impact

Linux failures can affect:

- Entire servers
- Kubernetes nodes
- Databases
- Applications
- Cloud workloads

A single Linux issue can impact multiple dependent services.

---

## Common Production Failures

### CPU Saturation

Symptoms:

- Slow services
- Increased latency

### Memory Exhaustion

Symptoms:

- OOM events
- Application crashes

### Disk Full

Symptoms:

- Write failures
- Service instability

### DNS Failures

Symptoms:

- Service discovery issues

### File Descriptor Exhaustion

Symptoms:

- Connection failures
- Resource allocation errors

---

## Investigation Mindset

```text
Symptom
   ↓
Metrics
   ↓
Logs
   ↓
System State
   ↓
Dependency Analysis
   ↓
Root Cause
```

Linux troubleshooting should be evidence driven.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Rich Logging | Higher Storage Cost |
| Detailed Monitoring | Additional Overhead |
| Aggressive Resource Limits | Stability Risk |
| Deep Investigation | Longer Resolution Time |
| Fast Recovery | Risk Of Missing Root Cause |

---

## Interview Thinking

- How would you troubleshoot a slow Linux server?
- How would you investigate high CPU usage?
- What causes OOM events?
- How would you investigate disk latency?
- What causes file descriptor exhaustion?
- How would you troubleshoot DNS failures?
- Which logs would you review first?
- How would you perform Linux RCA?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Linux Troubleshooting | Operating System Investigation |
| CPU Saturation | Compute Bottleneck |
| Memory Exhaustion | Resource Shortage |
| Disk Full | Storage Capacity Problem |
| I/O Wait | Storage Performance Issue |
| File Descriptor | Process Resource Limit |
| journalctl | System Log Investigation |
| top | Runtime Visibility |
| vmstat | Resource Analysis |
| RCA | Root Cause Identification |