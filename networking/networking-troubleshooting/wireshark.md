

# Wireshark

## Why Wireshark Matters

Sometimes engineers need deeper visibility than simple packet capture.

Question:

```text
What Exactly Happened
Inside The Network Traffic?
```

Wireshark provides detailed packet analysis.

---

## What Is Wireshark?

Wireshark is a graphical packet analysis tool.

Purpose:

```text
Packet Capture
      ↓
Protocol Analysis
      ↓
Root Cause Investigation
```

It is one of the most widely used networking tools.

---

## The Engineering Problem

Suppose:

```text
Application Timeout
DNS Failure
TLS Error
Connection Reset
```

Question:

```text
What Packets
Were Actually Exchanged?
```

Wireshark helps answer this question.

---

## High-Level Workflow

```text
Network Traffic
       ↓
Packet Capture
       ↓
Wireshark
       ↓
Analysis
```

Packet captures are typically stored as:

```text
PCAP Files
```

---

## Relationship With tcpdump

Common workflow:

```text
tcpdump
    ↓
Capture Packets
    ↓
Save PCAP
    ↓
Open In Wireshark
```

Wireshark complements tcpdump.

---

## Protocol Analysis

Wireshark can decode:

- TCP
- UDP
- DNS
- HTTP
- HTTPS
- TLS
- ICMP
- Kubernetes traffic
- Many other protocols

---

## TCP Troubleshooting

Example:

```text
SYN
 ↓
SYN-ACK
 ↓
ACK
```

Wireshark helps verify:

```text
Did The Handshake Complete?
```

---

## DNS Troubleshooting

Inspect:

```text
DNS Query
      ↓
DNS Response
```

Useful for:

- NXDOMAIN errors
- Incorrect responses
- DNS latency issues

---

## TLS Troubleshooting

Inspect:

```text
TLS Handshake
```

Common investigations:

- Certificate problems
- TLS negotiation failures
- Protocol mismatches

---

## HTTP Troubleshooting

Analyze:

```text
Requests
Responses
Headers
Status Codes
```

Useful for application debugging.

---

## Useful Filters

DNS:

```text
dns
```

TCP:

```text
tcp
```

HTTP:

```text
http
```

HTTPS/TLS:

```text
tls
```

Specific IP:

```text
ip.addr == 10.0.0.5
```

Filters help isolate relevant traffic.

---

## Common Troubleshooting Scenarios

### Application Timeout

Verify:

```text
Request Sent?
Response Received?
```

---

### DNS Failure

Verify:

```text
Query
Response
```

---

### Connection Reset

Verify:

```text
RST Packets
```

---

### Packet Loss

Verify:

```text
Retransmissions
```

---

## Production Usage

Wireshark is commonly used for:

- Deep network analysis
- Security investigations
- Performance troubleshooting
- DNS debugging
- TLS debugging
- Kubernetes networking analysis

It is often the final step when simpler tools cannot identify the problem.

---

## Safety Considerations

Packet captures may contain:

- Credentials
- Tokens
- Internal addresses
- Sensitive traffic

Always protect PCAP files appropriately.

---

## tcpdump vs Wireshark

| Feature | tcpdump | Wireshark |
|----------|----------|----------|
| Interface | CLI | GUI |
| Capture Packets | Yes | Yes |
| Deep Analysis | Limited | Excellent |
| Large Capture Investigation | Moderate | Excellent |
| Learning Curve | Lower | Higher |

---

## Common Interview Questions

- What is Wireshark?
- Why use Wireshark instead of tcpdump?
- What is a PCAP file?
- How do you analyze DNS traffic?
- How do you troubleshoot TLS failures?
- What are Wireshark filters?
- How do you investigate packet loss?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Wireshark | Packet Analysis Tool |
| Input | PCAP Files |
| DNS Analysis | Query/Response Inspection |
| TCP Analysis | Handshake Verification |
| TLS Analysis | Certificate Troubleshooting |
| HTTP Analysis | Request/Response Debugging |
| Filters | Traffic Isolation |
| Common Companion Tool | tcpdump |
| Common Use | Root Cause Investigation |
| Core Goal | Understand Network Traffic |