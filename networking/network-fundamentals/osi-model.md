

# OSI Model

## Why Was The OSI Model Created?

Early computer networks were built by different vendors.

Problems:

- Proprietary protocols
- Vendor lock-in
- Poor interoperability
- Difficult troubleshooting

Engineers needed a common way to describe network communication.

The OSI Model was created to standardize networking concepts.

---

## The Engineering Problem

Imagine troubleshooting a production issue.

```text
Application Cannot Reach Database
```

Possible causes:

- DNS failure
- Routing issue
- Firewall block
- TCP problem
- Application error

Without a layered model, troubleshooting becomes guesswork.

OSI provides a structured way to isolate failures.

---

## What Is The OSI Model?

OSI stands for:

```text
Open Systems Interconnection
```

It divides network communication into seven layers.

```text
7 Application
6 Presentation
5 Session
4 Transport
3 Network
2 Data Link
1 Physical
```

Each layer solves a specific problem.

---

## Layer 7 – Application

Closest to users and applications.

Examples:

- HTTP
- HTTPS
- DNS
- SMTP
- FTP

Questions answered:

```text
What Service Is Being Used?
```

---

## Layer 6 – Presentation

Responsible for:

- Encryption
- Compression
- Data formatting

Examples:

- TLS
- SSL
- Data encoding

Questions answered:

```text
How Should Data Be Represented?
```

---

## Layer 5 – Session

Responsible for:

- Session establishment
- Session management
- Session termination

Examples:

- Authentication sessions
- Remote connections

Questions answered:

```text
How Is Communication Maintained?
```

---

## Layer 4 – Transport

Responsible for end-to-end communication.

Protocols:

- TCP
- UDP

Responsibilities:

- Reliability
- Flow control
- Error recovery
- Segmentation

Questions answered:

```text
How Does Data Reach The Correct Process?
```

---

## Layer 3 – Network

Responsible for routing traffic between networks.

Protocols:

- IPv4
- IPv6
- ICMP

Devices:

- Routers

Questions answered:

```text
How Does Data Reach The Destination Network?
```

---

## Layer 2 – Data Link

Responsible for local network communication.

Concepts:

- MAC Address
- Ethernet
- VLAN
- ARP

Devices:

- Switches

Questions answered:

```text
How Does Data Reach The Correct Device?
```

---

## Layer 1 – Physical

Responsible for physical transmission.

Examples:

- Fiber
- Copper
- Wireless signals
- Network cables

Questions answered:

```text
How Do Bits Travel?
```

---

## Data Flow Through The OSI Model

Sending data:

```text
Application
    ↓
Presentation
    ↓
Session
    ↓
Transport
    ↓
Network
    ↓
Data Link
    ↓
Physical
```

Receiving data:

```text
Physical
    ↓
Data Link
    ↓
Network
    ↓
Transport
    ↓
Session
    ↓
Presentation
    ↓
Application
```

---

## Why Engineers Still Learn OSI

The Internet does not strictly use all seven layers.

Modern networking primarily follows the TCP/IP model.

However OSI remains valuable because:

- Easier troubleshooting
- Common industry language
- Interview relevance
- Layered thinking

---

## Production Troubleshooting Examples

### DNS Failure

```text
Layer 7
```

### TLS Certificate Error

```text
Layer 6
```

### TCP Connection Reset

```text
Layer 4
```

### Routing Failure

```text
Layer 3
```

### VLAN Misconfiguration

```text
Layer 2
```

### Cable Failure

```text
Layer 1
```

---

## Common Interview Questions

- Why was the OSI model created?
- OSI vs TCP/IP?
- Which layer does TCP belong to?
- Which layer does IP belong to?
- Which layer does DNS belong to?
- Which layer does TLS belong to?
- Which layer uses MAC addresses?
- Which layer uses IP addresses?
- Why do engineers still use OSI?

---

## Quick Revision

| Layer | Purpose |
|----------|----------|
| 7 Application | User Services |
| 6 Presentation | Encryption And Formatting |
| 5 Session | Connection Management |
| 4 Transport | End-To-End Communication |
| 3 Network | Routing |
| 2 Data Link | Local Delivery |
| 1 Physical | Signal Transmission |

### Memory Trick

```text
All
People
Seem
To
Need
Data
Processing
```