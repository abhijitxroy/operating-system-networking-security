

# HTTP Overview

## Why HTTP Exists

Computers connected to a network need a standard way to exchange information.

Question:

```text
How Does A Browser
Request A Web Page?

How Does A Server
Return A Response?
```

HTTP was created to solve this problem.

---

## What Is HTTP?

HTTP stands for:

```text
HyperText Transfer Protocol
```

Purpose:

```text
Client
   ↓ Request
Server
   ↑ Response
```

HTTP defines how clients and servers communicate.

---

## The Engineering Problem

Imagine a browser wants:

```text
https://example.com
```

Questions:

```text
How Is The Request Sent?
What Format Is Used?
How Is The Response Returned?
```

HTTP provides a common communication standard.

---

## HTTP Is An Application Layer Protocol

Within the TCP/IP model:

```text
Application Layer
      ↑
HTTP
      ↑
TCP
      ↑
IP
      ↑
Network
```

HTTP focuses on application communication.

TCP handles reliable delivery.

---

## Client Server Model

HTTP follows a client-server architecture.

```text
Browser
Mobile App
API Client
       ↓
     HTTP
       ↓
Server
API
Web Service
```

The client initiates communication.

The server responds.

---

## HTTP Request

Example:

```http
GET /users HTTP/1.1
Host: api.company.com
```

A request typically contains:

- Method
- URL
- Headers
- Body (optional)

---

## HTTP Response

Example:

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

A response typically contains:

- Status Code
- Headers
- Body

---

## Request Response Model

```text
Client
   ↓ Request
Server
   ↑ Response
Client
```

HTTP communication follows this pattern.

---

## HTTP Is Stateless

A very important concept.

HTTP does not automatically remember previous requests.

Example:

```text
Request 1
Request 2
Request 3
```

Each request is treated independently.

This is why:

- Cookies exist
- Sessions exist
- JWTs exist

---

## Common HTTP Operations

### Retrieve Data

```http
GET /products
```

### Create Data

```http
POST /products
```

### Update Data

```http
PUT /products/1
```

### Delete Data

```http
DELETE /products/1
```

---

## Common HTTP Status Codes

```text
200 OK
201 Created
301 Moved Permanently
400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
500 Internal Server Error
```

Status codes communicate request results.

---

## Why HTTP Became Popular

Benefits:

- Simple
- Extensible
- Platform independent
- Internet friendly
- Supported everywhere

HTTP became the foundation of the modern web.

---

## Production Impact

HTTP is used by:

- Websites
- REST APIs
- Microservices
- Cloud platforms
- Kubernetes ingress traffic
- SaaS applications

Almost every modern application depends on HTTP.

---

## Common Production Problems

### Slow Responses

Symptoms:

- High latency
- Poor user experience

### Large Payloads

Symptoms:

- Increased bandwidth usage

### Misconfigured Headers

Symptoms:

- Authentication failures
- Caching issues

### Server Errors

Symptoms:

- 5xx responses

---

## Useful Tools

```bash
curl https://example.com
```

```bash
curl -v https://example.com
```

```bash
wget https://example.com
```

Browser Developer Tools are also widely used.

---

## Common Interview Questions

- What is HTTP?
- Why was HTTP created?
- How does HTTP work?
- What is a request?
- What is a response?
- Why is HTTP stateless?
- What are common HTTP methods?
- What are common HTTP status codes?
- Where does HTTP operate in the TCP/IP model?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| HTTP | Application Communication Protocol |
| Client | Sends Request |
| Server | Returns Response |
| Request | Method + Headers + Body |
| Response | Status + Headers + Body |
| Stateless | No Built-In Memory |
| Common Transport | TCP |
| Common Usage | Web And APIs |
| Common Failure | 4xx/5xx Errors |
| Core Purpose | Client Server Communication |