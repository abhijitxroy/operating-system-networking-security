# TCP/IP Model

## Why Was The TCP/IP Model Created?

The OSI model provides a conceptual view of networking.

However the Internet needed a practical communication model.

Problems that needed solving:

- Communication across different networks
- Vendor interoperability
- Scalable routing
- Reliable data transfer
- Internet growth

The TCP/IP model became the foundation of the modern Internet.

---

## The Engineering Problem

Computers must communicate across:

- Different operating systems
- Different hardware vendors
- Different countries
- Different network technologies

A common communication framework was required.

```text
Application
      ↓
Internet Communication
      ↓
Reliable Delivery
```

TCP/IP solved this problem.

---

## What Is The TCP/IP Model?

TCP/IP stands for:

```text
Transmission Control Protocol
/
Internet Protocol
```

The model contains four layers.

```text
Application
Transport
Internet
Network Access
```

Unlike OSI, TCP/IP is used directly in real-world networking.

---

## Application Layer

Combines multiple OSI layers.

Examples:

- HTTP
- HTTPS
- DNS
- SMTP
- SSH
- FTP

Responsibilities:

- User communication
- Data formatting
- Application protocols

---

## Transport Layer

Responsible for end-to-end communication.

Protocols:

- TCP
- UDP

Responsibilities:

- Reliability
- Segmentation
- Flow control
- Error handling
- Port management

---

## Internet Layer

Responsible for routing traffic between networks.

Protocols:

- IPv4
- IPv6
- ICMP

Responsibilities:

- Addressing
- Routing
- Packet forwarding

Routers primarily operate here.

---

## Network Access Layer

Responsible for local network communication.

Examples:

- Ethernet
- Wi-Fi
- ARP
- VLANs

Responsibilities:

- Frame delivery
- MAC addressing
- Physical transmission

---

## TCP/IP vs OSI

| OSI Model | TCP/IP Model |
|----------|----------|
| Application | Application |
| Presentation | Application |
| Session | Application |
| Transport | Transport |
| Network | Internet |
| Data Link | Network Access |
| Physical | Network Access |

TCP/IP is simpler and closer to real implementations.

---

## Data Flow Through TCP/IP

Sending:

```text
Application Data
        ↓
TCP Segment
        ↓
IP Packet
        ↓
Ethernet Frame
        ↓
Network
```

Receiving:

```text
Network
      ↓
Frame
      ↓
Packet
      ↓
Segment
      ↓
Application Data
```

---

## Why TCP/IP Won

Reasons:

- Practical implementation
- Internet adoption
- Vendor neutrality
- Scalability
- Simplicity

Today almost all Internet communication relies on TCP/IP.

---

## Production Examples

### DNS Lookup

```text
Application Layer
```

### TCP Handshake

```text
Transport Layer
```

### Routing Decision

```text
Internet Layer
```

### Ethernet Communication

```text
Network Access Layer
```

---

## Production Impact

Engineers use TCP/IP concepts when troubleshooting:

- DNS failures
- TCP connection issues
- Routing problems
- Packet loss
- Network latency
- Cloud networking incidents

Understanding TCP/IP is essential for debugging production systems.

---

## Common Interview Questions

- TCP/IP vs OSI?
- Why did TCP/IP become dominant?
- Which layer handles routing?
- Which layer contains TCP?
- Which layer contains IP?
- Which layer contains DNS?
- Which layer contains Ethernet?
- Why is TCP/IP more practical than OSI?

---

## Quick Revision

| Layer | Responsibility |
|----------|----------|
| Application | User Services And Protocols |
| Transport | Reliable Communication |
| Internet | Routing And Addressing |
| Network Access | Local Delivery |

### Memory Trick

```text
Application
Transport
Internet
Network Access
```

### Most Important Mapping

```text
TCP
   ↓
Transport Layer

IP
   ↓
Internet Layer

Ethernet
   ↓
Network Access Layer
```