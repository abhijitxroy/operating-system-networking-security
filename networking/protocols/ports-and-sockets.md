

# Ports And Sockets

## Why Ports And Sockets Exist

An IP address identifies a machine.

However a machine can run many applications simultaneously.

Example:

```text
Server
  ├── Web Server
  ├── Database
  ├── SSH Service
  └── Monitoring Agent
```

Question:

```text
How Does Traffic Reach The Correct Application?
```

Ports and sockets solve this problem.

---

## The Engineering Problem

Suppose a server has:

```text
IP: 10.0.0.10
```

Running:

```text
HTTP
SSH
Database
```

The IP address identifies the server.

It does not identify the application.

A second identifier is required.

---

## What Is A Port?

A port identifies a process or service.

Think of it as:

```text
IP Address
      ↓
Building Address

Port
      ↓
Apartment Number
```

Traffic reaches the correct application using ports.

---

## Port Range

Valid ports:

```text
0 - 65535
```

Categories:

### Well-Known Ports

```text
0 - 1023
```

Examples:

```text
22   SSH
53   DNS
80   HTTP
443  HTTPS
```

### Registered Ports

```text
1024 - 49151
```

Used by applications and vendors.

### Ephemeral Ports

```text
49152 - 65535
```

Typically used by clients.

---

## Source And Destination Ports

Example:

```text
Client: 52341
Server: 443
```

Request:

```text
52341 → 443
```

Response:

```text
443 → 52341
```

Both ports are required for communication.

---

## What Is A Socket?

A socket represents a communication endpoint.

A socket consists of:

```text
IP Address
     +
Port
```

Example:

```text
10.0.0.10:443
```

This uniquely identifies a service endpoint.

---

## TCP Socket Example

Connection:

```text
Client
10.0.0.5:52341

Server
10.0.0.10:443
```

Socket Pair:

```text
10.0.0.5:52341
        ↓
10.0.0.10:443
```

This uniquely identifies the TCP connection.

---

## Why Sockets Matter

Sockets allow:

- Applications to communicate
- Multiple simultaneous connections
- Reliable session tracking
- Network service delivery

Without sockets, operating systems could not manage network communication efficiently.

---

## Common Well-Known Ports

| Port | Service |
|----------|----------|
| 20/21 | FTP |
| 22 | SSH |
| 25 | SMTP |
| 53 | DNS |
| 80 | HTTP |
| 110 | POP3 |
| 143 | IMAP |
| 443 | HTTPS |
| 3306 | MySQL |
| 5432 | PostgreSQL |

---

## Viewing Open Ports

Linux:

```bash
ss -tulpn
```

or

```bash
netstat -tulpn
```

Useful for troubleshooting.

---

## Production Impact

Engineers frequently troubleshoot:

- Port conflicts
- Services not listening
- Firewall blocks
- Connection failures
- Socket exhaustion

Understanding ports and sockets is essential for debugging connectivity issues.

---

## Common Production Failures

### Port Already In Use

Symptoms:

- Service startup failure

### Firewall Blocking Port

Symptoms:

- Connection timeout

### Service Not Listening

Symptoms:

- Connection refused

### Socket Exhaustion

Symptoms:

- New connections fail
- Resource exhaustion

---

## Troubleshooting Commands

```bash
ss -tulpn
lsof -i
netstat -an
nc
curl
```

Useful for validating connectivity and service availability.

---

## Common Interview Questions

- What is a port?
- What is a socket?
- Difference between IP and port?
- Why are ports needed?
- What is an ephemeral port?
- How does a browser connect to HTTPS?
- What causes connection refused?
- What is socket exhaustion?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| IP Address | Identifies Host |
| Port | Identifies Process |
| Socket | IP + Port |
| Well-Known Ports | 0-1023 |
| Ephemeral Ports | Client-Side Temporary Ports |
| HTTPS | Port 443 |
| SSH | Port 22 |
| Connection Refused | Service Not Listening |
| Socket Exhaustion | Resource Limitation |
| Core Purpose | Deliver Traffic To Correct Application |