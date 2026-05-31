

# netstat vs ss

## Why These Commands Matter

When troubleshooting networking issues, engineers often need answers to questions like:

```text
Which Ports Are Open?

Which Process Is Listening?

Who Is Connected To This Server?
```

`netstat` and `ss` help answer these questions.

---

## What Is netstat?

`netstat` stands for:

```text
Network Statistics
```

It is a traditional Linux networking utility used to inspect:

- Open ports
- Active connections
- Routing tables
- Network statistics

---

## What Is ss?

`ss` stands for:

```text
Socket Statistics
```

It is the modern replacement for `netstat`.

Benefits:

- Faster
- More scalable
- Better for large systems

Most modern Linux distributions prefer `ss`.

---

## The Engineering Problem

Suppose an application cannot be reached.

Question:

```text
Is The Application
Actually Listening
On The Expected Port?
```

These tools help verify that.

---

## Show Listening Ports

Using netstat:

```bash
netstat -tulpn
```

Using ss:

```bash
ss -tulpn
```

Example Output:

```text
TCP 0.0.0.0:443 LISTEN
```

Meaning:

```text
Application Listening On Port 443
```

---

## Show Established Connections

Using netstat:

```bash
netstat -ant
```

Using ss:

```bash
ss -ant
```

Useful for identifying active client connections.

---

## Find Which Process Owns A Port

Example:

```bash
ss -tulpn
```

Output may show:

```text
PID
Process Name
Port
```

Useful when troubleshooting port conflicts.

---

## Verify Application Startup

Suppose:

```text
Application Started
```

Question:

```text
Is It Actually Listening?
```

Verify:

```bash
ss -tulpn | grep 8080
```

---

## Verify Remote Connections

Check active sessions:

```bash
ss -ant
```

Example:

```text
ESTABLISHED
```

Indicates active communication.

---

## Common Connection States

### LISTEN

```text
Waiting For Connections
```

---

### ESTABLISHED

```text
Active Connection
```

---

### TIME_WAIT

```text
Recently Closed Connection
```

---

### CLOSE_WAIT

```text
Connection Not Fully Closed
```

Can indicate application issues.

---

## Troubleshooting Examples

### Port Already In Use

Symptoms:

```text
Application Startup Failure
```

Check:

```bash
ss -tulpn
```

---

### Application Unreachable

Symptoms:

```text
Connection Refused
```

Verify:

```bash
ss -tulpn
```

Check whether the service is listening.

---

### Excessive Connections

Symptoms:

```text
Server Under Load
```

Check:

```bash
ss -ant
```

---

## netstat vs ss

| Feature | netstat | ss |
|----------|----------|----------|
| Age | Older Tool | Modern Tool |
| Performance | Slower | Faster |
| Large Systems | Less Efficient | More Efficient |
| Availability | Legacy Systems | Modern Linux |
| Recommended Today | Sometimes | Yes |

---

## Production Usage

Common uses:

- Verify listening ports
- Debug connectivity issues
- Investigate port conflicts
- Monitor active sessions
- Validate application startup

These are among the most frequently used Linux troubleshooting tools.

---

## Common Interview Questions

- What is netstat?
- What is ss?
- Why is ss preferred today?
- How do you find open ports?
- How do you find which process owns a port?
- What does LISTEN mean?
- What does ESTABLISHED mean?
- How would you troubleshoot connection refused errors?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| netstat | Legacy Network Tool |
| ss | Modern Network Tool |
| LISTEN | Waiting For Connections |
| ESTABLISHED | Active Connection |
| TIME_WAIT | Recently Closed Connection |
| Port Check | ss -tulpn |
| Active Connections | ss -ant |
| Process Lookup | Port → PID Mapping |
| Common Failure | Port Not Listening |
| Core Goal | Inspect Network Connections |