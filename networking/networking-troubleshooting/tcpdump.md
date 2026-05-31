# tcpdump

## Why tcpdump Matters

Many networking problems cannot be solved using ping, DNS tools, or port checks alone.

Question:

```text
Are Packets Actually Leaving?

Are Responses Returning?

What Is Happening On The Wire?
```

tcpdump helps answer these questions.

---

## What Is tcpdump?

`tcpdump` is a packet capture and packet analysis tool.

Purpose:

```text
Network Interface
        ↓
Capture Packets
        ↓
Inspect Traffic
```

It allows engineers to see real network traffic.

---

## The Engineering Problem

Suppose:

```text
Application Timeout
```

Question:

```text
Did The Request Leave?

Did The Response Return?
```

Packet captures provide evidence.

---

## How tcpdump Works

```text
Network Interface
        ↓
Packets
        ↓
tcpdump
        ↓
Human Analysis
```

It captures traffic directly from the network interface.

---

## Basic Packet Capture

Capture packets:

```bash
tcpdump
```

Capture on specific interface:

```bash
tcpdump -i eth0
```

---

## Capture Specific Host

```bash
tcpdump host 10.0.0.5
```

Useful when troubleshooting communication with a specific system.

---

## Capture Specific Port

```bash
tcpdump port 443
```

Example:

```text
HTTPS Traffic
```

---

## Capture TCP Traffic

```bash
tcpdump tcp
```

Capture UDP traffic:

```bash
tcpdump udp
```

---

## Save Capture To File

```bash
tcpdump -i eth0 -w capture.pcap
```

The capture can later be opened in Wireshark.

---

## Read Existing Capture

```bash
tcpdump -r capture.pcap
```

Useful for offline analysis.

---

## Common Troubleshooting Scenarios

### Application Timeout

Question:

```text
Did The Request Leave?
```

Verify using packet capture.

---

### DNS Failure

Capture:

```bash
tcpdump port 53
```

Verify DNS queries and responses.

---

### HTTPS Problems

Capture:

```bash
tcpdump port 443
```

Inspect TLS traffic flow.

---

### Connection Refused

Verify:

```text
TCP Handshake
```

and server responses.

---

## TCP Three-Way Handshake

tcpdump is frequently used to inspect:

```text
SYN
 ↓
SYN-ACK
 ↓
ACK
```

Missing packets often reveal the root cause.

---

## Production Usage

tcpdump is commonly used for:

- Network troubleshooting
- DNS debugging
- Application connectivity issues
- Kubernetes networking investigations
- Cloud networking incidents
- Security investigations

It is one of the most valuable networking tools available.

---

## Common Production Failures Revealed By tcpdump

### No Response Packets

Symptoms:

```text
Timeouts
```

---

### DNS Failures

Symptoms:

```text
Name Resolution Problems
```

---

### Firewall Blocking Traffic

Symptoms:

```text
Requests Leave
Responses Never Return
```

---

### Packet Loss

Symptoms:

```text
Retransmissions
```

---

## Safety Considerations

Packet captures may contain:

- Sensitive information
- Authentication tokens
- Internal network details

Always handle capture files carefully.

---

## Common Interview Questions

- What is tcpdump?
- Why is tcpdump useful?
- How do you capture traffic on a specific interface?
- How do you capture DNS traffic?
- How do you capture HTTPS traffic?
- What is a PCAP file?
- How would you troubleshoot a timeout using tcpdump?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| tcpdump | Packet Capture Tool |
| Purpose | Inspect Real Traffic |
| Interface Capture | -i |
| Save Capture | -w |
| Read Capture | -r |
| DNS Analysis | Port 53 |
| HTTPS Analysis | Port 443 |
| TCP Debugging | Handshake Analysis |
| Common Failure | Missing Responses |
| Core Goal | Observe Network Traffic |