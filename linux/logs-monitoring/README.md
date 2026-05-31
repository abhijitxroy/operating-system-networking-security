

# Linux Logs And Monitoring

## Why Logs Exist

When systems fail, engineers need evidence.

Without logs, troubleshooting becomes guesswork.

Logs were created to record what happened inside a system so engineers can:

- Understand failures
- Investigate incidents
- Debug applications
- Audit activity
- Monitor system health

Logs are one of the most important sources of truth during production incidents.

---

## The Engineering Problem

Modern systems contain:

- Applications
- Databases
- Containers
- Operating systems
- Network services
- Background jobs

Failures can occur anywhere.

Engineers need visibility into system behavior.

```text
System Event
      ↓
Log Entry
      ↓
Investigation
      ↓
Root Cause
```

Without observability, production systems become difficult to operate.

---

## Why Monitoring Exists

Logs explain what happened.

Monitoring helps detect problems before users report them.

Monitoring answers:

- Is the system healthy?
- Is performance degrading?
- Are resources running out?
- Is availability impacted?

Logs and monitoring complement each other.

---

## Linux Logging Architecture

Modern Linux systems commonly use:

```text
Applications
      ↓
System Logs
      ↓
systemd-journald
      ↓
journalctl
```

Many environments also forward logs to centralized platforms.

Examples:

- ELK Stack
- OpenSearch
- Splunk
- Grafana Loki

---

## journalctl

The most important Linux log investigation tool.

Common usage:

```bash
journalctl
```

View recent logs:

```bash
journalctl -n 100
```

Follow logs:

```bash
journalctl -f
```

Service-specific logs:

```bash
journalctl -u nginx
```

---

## System Metrics Engineers Watch

### CPU

Indicators:

- Utilization
- Load average
- Context switching

### Memory

Indicators:

- Free memory
- Cache usage
- Swap usage
- OOM events

### Storage

Indicators:

- Disk utilization
- IOPS
- Latency
- Inode consumption

### Network

Indicators:

- Throughput
- Errors
- Packet drops
- Latency

---

## Common Production Failures

### High CPU Usage

Investigation:

```bash
top
htop
pidstat
```

### Memory Exhaustion

Investigation:

```bash
free -h
vmstat
journalctl
```

### Service Failures

Investigation:

```bash
systemctl status <service>
journalctl -u <service>
```

### Disk Full

Investigation:

```bash
df -h
du -sh *
```

---

## Monitoring Tools Commonly Used

Linux engineers frequently encounter:

- Prometheus
- Grafana
- Node Exporter
- ELK Stack
- OpenSearch
- Loki
- Datadog
- New Relic

The operating system remains the source of the underlying metrics.

---

## Production Debugging Workflow

```text
Alert Fires
      ↓
Check Metrics
      ↓
Identify Impacted Resource
      ↓
Review Logs
      ↓
Find Root Cause
      ↓
Implement Fix
      ↓
Validate Recovery
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Detailed Logs | Higher Storage Usage |
| Longer Retention | Increased Cost |
| More Metrics | Monitoring Overhead |
| Faster Detection | Additional Complexity |
| Centralized Logging | Infrastructure Cost |

---

## Interview Thinking

- Why do logs exist?
- Why is monitoring important?
- Logs vs Metrics?
- How would you investigate a failed service?
- How would you investigate high CPU usage?
- What information does journalctl provide?
- Why centralize logs?
- What metrics would you monitor first during an outage?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Logs | Historical Evidence |
| Monitoring | System Health Visibility |
| journalctl | Linux Log Investigation Tool |
| Metrics | Quantitative System Data |
| Alerting | Failure Detection |
| CPU Metrics | Utilization And Load |
| Memory Metrics | Usage And Pressure |
| Disk Metrics | Capacity And Performance |
| Centralized Logging | Unified Log Analysis |
| Root Cause Analysis | Identify Why Failure Happened |