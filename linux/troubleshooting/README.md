

# Linux Troubleshooting

## Why Troubleshooting Matters

Production systems rarely fail with clear error messages.

Most incidents begin with symptoms.

Examples:

- Slow applications
- High latency
- Service failures
- Resource exhaustion
- Intermittent outages

The ability to troubleshoot Linux systems systematically is one of the most valuable engineering skills.

---

## The Engineering Problem

Modern Linux systems contain many moving parts.

Examples:

- Applications
- Services
- Processes
- Storage
- Memory
- Networking
- Containers

A failure in any layer can impact the entire platform.

Engineers must determine:

- What failed?
- Where did it fail?
- Why did it fail?
- How can it be prevented?

```text
Symptom
   ↓
Evidence
   ↓
Root Cause
   ↓
Fix
```

---

## The Biggest Troubleshooting Mistake

Many engineers start with assumptions.

Strong engineers start with evidence.

Bad workflow:

```text
Guess
 ↓
Change Something
 ↓
Hope It Works
```

Better workflow:

```text
Observe
 ↓
Measure
 ↓
Collect Evidence
 ↓
Build Hypothesis
 ↓
Validate
```

---

## A Standard Linux Investigation Flow

### Step 1: Verify Service Health

```bash
systemctl status
```

### Step 2: Check Logs

```bash
journalctl
```

### Step 3: Check CPU

```bash
top
htop
pidstat
```

### Step 4: Check Memory

```bash
free -h
vmstat
```

### Step 5: Check Storage

```bash
df -h
du -sh *
```

### Step 6: Check Network

```bash
ss -tulpn
ping
dig
```

---

## Common Production Failures

### High CPU Usage

Symptoms:

- Slow applications
- High load average

Investigation:

```bash
top
pidstat
```

### Memory Exhaustion

Symptoms:

- OOM events
- Container restarts

Investigation:

```bash
free -h
dmesg
journalctl -k
```

### Disk Full

Symptoms:

- Write failures
- Service instability

Investigation:

```bash
df -h
du -sh *
```

### DNS Failure

Symptoms:

- Hostnames fail
- External services unreachable

Investigation:

```bash
dig
nslookup
```

### Service Startup Failure

Symptoms:

- Application unavailable

Investigation:

```bash
systemctl status
journalctl -u <service>
```

---

## Evidence Collection Commands

### Processes

```bash
ps -ef
pstree
```

### Memory

```bash
free -h
cat /proc/meminfo
```

### Storage

```bash
df -h
lsblk
```

### Networking

```bash
ip addr
ip route
ss -tulpn
```

### Logs

```bash
journalctl
```

---

## Root Cause Analysis Mindset

Avoid fixing symptoms only.

Example:

```text
Disk Full
```

Symptom fix:

```text
Delete Files
```

Root cause analysis:

```text
Why Did Files Grow?
Why Was Monitoring Missing?
Why Was Retention Misconfigured?
```

The goal is preventing recurrence.

---

## Production Debugging Workflow

```text
Incident
    ↓
Identify Impact
    ↓
Collect Evidence
    ↓
Find Bottleneck Or Failure
    ↓
Determine Root Cause
    ↓
Apply Fix
    ↓
Validate Recovery
    ↓
Prevent Recurrence
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Faster Recovery | Risk Of Missing Root Cause |
| Deep Investigation | Longer Resolution Time |
| More Monitoring | Additional Cost |
| Extensive Logging | Higher Storage Usage |
| Automation | Increased Complexity |

---

## Interview Thinking

- How would you investigate a slow Linux server?
- How would you investigate high CPU usage?
- How would you investigate memory leaks?
- How would you investigate a disk full incident?
- How would you troubleshoot DNS failures?
- Why is evidence collection important?
- What is root cause analysis?
- Why do recurring incidents happen?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Troubleshooting | Evidence-Based Investigation |
| Symptom | Observable Problem |
| Root Cause | Actual Failure Source |
| systemctl | Service Investigation |
| journalctl | Log Analysis |
| top | CPU Investigation |
| free -h | Memory Investigation |
| df -h | Storage Investigation |
| ss | Network Investigation |
| RCA | Prevent Recurrence |