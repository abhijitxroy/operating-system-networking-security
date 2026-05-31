

# HTTP Request Response Lifecycle

## Why This Topic Matters

A user clicks a link and a web page appears.

What happens in between?

Understanding the complete request-response lifecycle is essential for:

- Backend engineering
- API development
- Networking
- Cloud platforms
- Production troubleshooting

---

## The Engineering Problem

A user opens:

```text
https://example.com
```

Question:

```text
How Does The Request Reach The Server?

How Does The Response Return?
```

Many systems participate before the page is displayed.

---

## High-Level Lifecycle

```text
User
 ↓
Browser
 ↓
DNS Resolution
 ↓
TCP Connection
 ↓
TLS Handshake (HTTPS)
 ↓
HTTP Request
 ↓
Load Balancer
 ↓
Application Server
 ↓
Database/Services
 ↓
HTTP Response
 ↓
Browser Rendering
```

---

## Step 1: User Enters URL

Example:

```text
https://example.com/products
```

The browser begins processing the request.

---

## Step 2: DNS Resolution

The browser needs an IP address.

Example:

```text
example.com
      ↓
104.x.x.x
```

DNS translates the domain name into an IP address.

---

## Step 3: TCP Connection

HTTP communication typically uses TCP.

TCP establishes a connection using:

```text
SYN
 ↓
SYN-ACK
 ↓
ACK
```

This is the TCP Three-Way Handshake.

---

## Step 4: TLS Handshake (HTTPS)

For HTTPS:

```text
Client
   ↔
Server
```

exchange cryptographic information.

Goals:

- Encryption
- Authentication
- Secure communication

---

## Step 5: HTTP Request Sent

Example:

```http
GET /products HTTP/1.1
Host: example.com
```

The request contains:

- Method
- URL
- Headers
- Optional Body

---

## Step 6: Load Balancer Processing

In production systems:

```text
Client
   ↓
Load Balancer
   ↓
Application Server
```

The load balancer selects a backend server.

---

## Step 7: Application Processing

The application:

- Validates request
- Authenticates user
- Executes business logic
- Calls internal services

Example:

```text
API
 ↓
Service
 ↓
Database
```

---

## Step 8: Database Access

Many requests require data retrieval.

Example:

```text
Application
      ↓
Database Query
      ↓
Results Returned
```

Database latency often affects overall response time.

---

## Step 9: HTTP Response Generated

Example:

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

The response contains:

- Status Code
- Headers
- Response Body

---

## Step 10: Response Returned To Browser

```text
Server
   ↑
Response
   ↑
Browser
```

The browser receives the response.

---

## Step 11: Browser Rendering

The browser:

- Parses HTML
- Loads CSS
- Executes JavaScript
- Renders UI

The user finally sees the page.

---

## Performance Bottlenecks

Common delays:

### DNS Latency

Slow name resolution.

### Network Latency

Slow communication.

### TLS Overhead

Handshake delays.

### Application Latency

Slow business logic.

### Database Latency

Slow queries.

---

## Production Impact

Every web application depends on this lifecycle.

Understanding each step helps engineers troubleshoot:

- Slow APIs
- Website outages
- Authentication issues
- Load balancer failures
- Database bottlenecks

---

## Common Production Failures

### DNS Failure

Symptoms:

- Name resolution errors

### TCP Failure

Symptoms:

- Connection timeout

### TLS Failure

Symptoms:

- Certificate errors

### Application Failure

Symptoms:

- 5xx responses

### Database Failure

Symptoms:

- Slow or failed requests

---

## Common Interview Questions

- What happens when you enter a URL?
- Explain the HTTP request lifecycle.
- Where does DNS fit into the lifecycle?
- Why is TCP required?
- Why is TLS required?
- What role does a load balancer play?
- What causes slow response times?
- How would you troubleshoot latency?

---

## Quick Revision

| Step | Purpose |
|----------|----------|
| DNS | Domain To IP |
| TCP | Reliable Connection |
| TLS | Secure Communication |
| HTTP Request | Client Request |
| Load Balancer | Traffic Distribution |
| Application | Business Logic |
| Database | Data Retrieval |
| HTTP Response | Server Reply |
| Browser Rendering | User Experience |
| Core Goal | Deliver Content To User |