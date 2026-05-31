# HTTP/1 vs HTTP/2 vs HTTP/3

## Why New HTTP Versions Were Created

The web evolved dramatically.

Modern applications require:

- Lower latency
- Faster page loads
- Better mobile performance
- Higher scalability

HTTP/1 eventually became a bottleneck.

HTTP/2 and HTTP/3 were created to improve performance.

---

## Evolution Of HTTP

```text
HTTP/1.0
    ↓
HTTP/1.1
    ↓
HTTP/2
    ↓
HTTP/3
```

Each version attempts to solve limitations of the previous version.

---

## HTTP/1.1

Released in 1997.

Characteristics:

- Text-based protocol
- One request per connection at a time
- Head-of-line blocking
- Multiple TCP connections often required

Example:

```text
Browser
   ↓
Request 1
Wait
   ↓
Request 2
Wait
```

This creates inefficiencies.

---

## Problems With HTTP/1.1

### Head-Of-Line Blocking

A slow request blocks later requests.

### Multiple TCP Connections

Browsers open many connections.

### Increased Latency

Additional connection overhead.

These limitations became significant for modern websites.

---

## HTTP/2

Released in 2015.

Major improvements:

- Multiplexing
- Header compression
- Stream prioritization
- Single connection efficiency

Goal:

```text
More Work
Less Overhead
```

---

## HTTP/2 Multiplexing

Multiple requests share one TCP connection.

```text
Connection
     ↓
Request 1
Request 2
Request 3
Request 4
```

Requests can be processed concurrently.

This significantly improves performance.

---

## HTTP/2 Header Compression

HTTP headers are often repetitive.

HTTP/2 compresses headers using:

```text
HPACK
```

Benefits:

- Reduced bandwidth
- Faster communication

---

## HTTP/2 Limitations

Although improved:

```text
Still Uses TCP
```

TCP head-of-line blocking can still impact performance.

This motivated HTTP/3.

---

## HTTP/3

Released using a new transport protocol.

Key change:

```text
HTTP/3
      ↓
QUIC
      ↓
UDP
```

Instead of:

```text
HTTP
      ↓
TCP
```

---

## What Is QUIC?

QUIC is a modern transport protocol.

Provides:

- Multiplexing
- Encryption
- Faster connection establishment
- Reduced latency

Built on UDP.

---

## HTTP/3 Benefits

### Reduced Latency

Faster connection setup.

### Better Mobile Performance

Handles network changes more efficiently.

### Reduced Head-Of-Line Blocking

Independent streams improve responsiveness.

### Improved User Experience

Faster page loads.

---

## Version Comparison

| Feature | HTTP/1.1 | HTTP/2 | HTTP/3 |
|----------|----------|----------|----------|
| Transport | TCP | TCP | QUIC/UDP |
| Multiplexing | No | Yes | Yes |
| Header Compression | No | Yes | Yes |
| Head-Of-Line Blocking | High | Reduced | Much Lower |
| Connection Efficiency | Low | High | Very High |
| Mobile Performance | Moderate | Good | Excellent |

---

## Production Impact

Modern platforms commonly use:

- HTTP/2
- HTTP/3

Examples:

- Cloud providers
- CDNs
- SaaS platforms
- Large web applications

Performance gains directly affect user experience.

---

## Common Interview Questions

- Why was HTTP/2 created?
- What is multiplexing?
- What is head-of-line blocking?
- Why was HTTP/3 created?
- What is QUIC?
- HTTP/2 vs HTTP/3?
- TCP vs QUIC?
- Which HTTP version is fastest?

---

## Quick Revision

| Version | Key Improvement |
|----------|----------|
| HTTP/1.1 | Standard Web Protocol |
| HTTP/2 | Multiplexing |
| HTTP/3 | QUIC Over UDP |
| Major HTTP/1 Issue | Head-Of-Line Blocking |
| Major HTTP/2 Feature | Single Connection Multiplexing |
| Major HTTP/3 Feature | QUIC |
| Transport (HTTP/1.1) | TCP |
| Transport (HTTP/2) | TCP |
| Transport (HTTP/3) | UDP via QUIC |
| Core Goal | Lower Latency And Better Performance |
