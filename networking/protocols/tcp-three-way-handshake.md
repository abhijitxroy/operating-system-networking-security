

# TCP Three-Way Handshake

## Why Does TCP Need A Handshake?

TCP provides:

- Reliable communication
- Ordered delivery
- Connection-oriented communication

Before data transfer begins, both systems must agree on:

```text
Who Is Communicating?
Can Data Be Sent?
Is The Connection Alive?
```

The TCP Three-Way Handshake solves this problem.

---

## The Engineering Problem

Suppose:

```text
Client
   ↓
Server
```

The client wants to send data.

Questions:

```text
Is The Server Reachable?
Is TCP Available?
Can Both Sides Communicate?
```

TCP establishes a connection before transferring data.

---

## What Is The TCP Three-Way Handshake?

The TCP Three-Way Handshake is the process used to establish a TCP connection.

Steps:

```text
SYN
 ↓
SYN-ACK
 ↓
ACK
```

After these three messages:

```text
Connection Established
```

---

## Step 1: SYN

Client sends:

```text
SYN
```

Meaning:

```text
I Want To Establish A Connection
```

Example:

```text
Client
   ↓ SYN
Server
```

The client also sends an Initial Sequence Number (ISN).

---

## Step 2: SYN-ACK

Server responds:

```text
SYN + ACK
```

Meaning:

```text
I Received Your Request
And I Am Ready
```

Example:

```text
Client
   ↑ SYN-ACK
Server
```

The server provides its own sequence number.

---

## Step 3: ACK

Client sends:

```text
ACK
```

Meaning:

```text
Connection Confirmed
```

Example:

```text
Client
   ↓ ACK
Server
```

Connection is now established.

---

## Complete Flow

```text
Client                     Server

SYN --------------------->

     <---------------- SYN-ACK

ACK --------------------->

Connection Established
```

---

## Why Three Steps?

A common interview question.

TCP needs to verify:

```text
Client → Server Works
Server → Client Works
Both Sides Are Ready
```

Two messages are insufficient for full verification.

The third ACK confirms bidirectional communication.

---

## Sequence Numbers

TCP tracks data using sequence numbers.

Purpose:

- Ordered delivery
- Reliability
- Loss detection
- Retransmissions

The handshake initializes these sequence numbers.

---

## Connection State Flow

Client:

```text
CLOSED
  ↓
SYN-SENT
  ↓
ESTABLISHED
```

Server:

```text
LISTEN
  ↓
SYN-RECEIVED
  ↓
ESTABLISHED
```

These states appear frequently during troubleshooting.

---

## Production Impact

Every TCP-based application uses the handshake.

Examples:

- HTTP
- HTTPS
- SSH
- Databases
- APIs
- Kubernetes Services

Billions of TCP handshakes occur every day.

---

## Common Production Problems

### SYN Flood Attack

Attackers send large numbers of:

```text
SYN
```

but never complete the connection.

Impact:

- Resource exhaustion
- Service degradation

---

### Packet Loss During Handshake

Symptoms:

- Connection timeouts
- Slow application startup

---

### Firewall Blocking SYN

Symptoms:

- Unable to connect
- Connection timeout

---

### Server Not Listening

Symptoms:

```text
Connection Refused
```

---

## Troubleshooting Commands

Linux:

```bash
ss -tulpn
```

```bash
tcpdump tcp
```

```bash
netstat -an
```

Useful for observing handshake behavior.

---

## Common Interview Questions

- What is the TCP Three-Way Handshake?
- Why are three steps required?
- What is SYN?
- What is ACK?
- What is SYN-ACK?
- Why does TCP use sequence numbers?
- What is a SYN flood attack?
- What causes connection timeout?
- Connection refused vs timeout?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| SYN | Connection Request |
| SYN-ACK | Request Accepted |
| ACK | Connection Confirmed |
| Three-Way Handshake | TCP Connection Establishment |
| Sequence Number | Reliability Tracking |
| ESTABLISHED | Active TCP Connection |
| SYN Flood | Resource Exhaustion Attack |
| Connection Refused | Service Not Listening |
| Timeout | Traffic Not Reaching Target |
| Core Purpose | Reliable Connection Setup |