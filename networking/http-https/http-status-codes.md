

# HTTP Status Codes

## Why HTTP Status Codes Exist

After a server processes a request, it must communicate the result back to the client.

Question:

```text
Was The Request Successful?

Did Something Fail?

Should The Client Retry?
```

HTTP Status Codes provide standardized answers.

---

## What Are HTTP Status Codes?

HTTP Status Codes are numeric values returned by servers.

Example:

```http
HTTP/1.1 200 OK
```

Purpose:

```text
Describe Request Outcome
```

---

## Status Code Categories

| Range | Category |
|----------|----------|
| 1xx | Informational |
| 2xx | Success |
| 3xx | Redirection |
| 4xx | Client Errors |
| 5xx | Server Errors |

A common interview topic.

---

## 1xx Informational

Meaning:

```text
Request Received
Continue Processing
```

Common example:

```text
100 Continue
```

Rarely encountered in normal application development.

---

## 2xx Success

Request completed successfully.

### 200 OK

Most common response.

Meaning:

```text
Request Successful
```

---

### 201 Created

Meaning:

```text
Resource Created
```

Common with:

```http
POST /users
```

---

### 204 No Content

Meaning:

```text
Success
But No Response Body
```

Common for DELETE operations.

---

## 3xx Redirection

Client must take additional action.

### 301 Moved Permanently

Meaning:

```text
Resource Permanently Moved
```

SEO-friendly redirect.

---

### 302 Found

Meaning:

```text
Temporary Redirect
```

---

### 304 Not Modified

Meaning:

```text
Use Cached Version
```

Improves performance.

---

## 4xx Client Errors

The client request is invalid.

### 400 Bad Request

Meaning:

```text
Malformed Request
```

---

### 401 Unauthorized

Meaning:

```text
Authentication Required
```

Often caused by:

- Missing token
- Invalid token

---

### 403 Forbidden

Meaning:

```text
Authenticated
But Access Denied
```

---

### 404 Not Found

Meaning:

```text
Resource Not Found
```

One of the most common status codes.

---

### 429 Too Many Requests

Meaning:

```text
Rate Limit Exceeded
```

Common in APIs.

---

## 5xx Server Errors

The server failed while processing a valid request.

### 500 Internal Server Error

Meaning:

```text
Unexpected Server Failure
```

---

### 502 Bad Gateway

Common with:

- Load Balancers
- Reverse Proxies
- API Gateways

Meaning:

```text
Invalid Upstream Response
```

---

### 503 Service Unavailable

Meaning:

```text
Service Temporarily Unavailable
```

Common during maintenance.

---

### 504 Gateway Timeout

Meaning:

```text
Upstream Service Too Slow
```

Common in distributed systems.

---

## Common Production Mapping

| Status Code | Typical Cause |
|----------|----------|
| 200 | Success |
| 201 | Resource Created |
| 301 | Permanent Redirect |
| 400 | Invalid Request |
| 401 | Authentication Failure |
| 403 | Permission Problem |
| 404 | Missing Resource |
| 429 | Rate Limiting |
| 500 | Application Failure |
| 503 | Service Unavailable |
| 504 | Timeout |

---

## Production Impact

Status codes help engineers quickly identify:

- Client problems
- Authentication failures
- Application bugs
- Infrastructure issues
- Upstream service failures

Monitoring systems often track status code distributions.

---

## Common Interview Questions

- Difference between 401 and 403?
- Difference between 301 and 302?
- Difference between 500 and 503?
- What causes 502?
- What causes 504?
- Why is 429 important?
- Which status code should POST return after creation?

---

## Quick Revision

| Code | Meaning |
|----------|----------|
| 200 | Success |
| 201 | Created |
| 204 | No Content |
| 301 | Permanent Redirect |
| 302 | Temporary Redirect |
| 304 | Use Cache |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 429 | Rate Limited |
| 500 | Internal Server Error |
| 502 | Bad Gateway |
| 503 | Service Unavailable |
| 504 | Gateway Timeout |