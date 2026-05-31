

# HTTP Headers

## Why HTTP Headers Exist

HTTP requests and responses need more information than just:

```text
URL
+
Data
```

Questions:

```text
Who Is Sending The Request?
What Content Type Is Used?
Can Responses Be Cached?
How Should Authentication Work?
```

HTTP Headers carry this metadata.

---

## What Are HTTP Headers?

HTTP Headers are key-value pairs exchanged between clients and servers.

Example:

```http
Content-Type: application/json
```

Purpose:

```text
Provide Metadata
About Requests And Responses
```

---

## High-Level Request Structure

```http
GET /users HTTP/1.1
Host: api.company.com
Authorization: Bearer token
Accept: application/json
```

Headers appear between:

```text
Request Line
      ↓
Headers
      ↓
Body
```

---

## High-Level Response Structure

```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 120
```

Headers describe the response.

---

## Request Headers

Sent by the client.

Examples:

- Host
- User-Agent
- Accept
- Authorization
- Cookie
- Content-Type

---

## Response Headers

Sent by the server.

Examples:

- Content-Type
- Content-Length
- Cache-Control
- Set-Cookie
- Location
- Server

---

## Important HTTP Headers

### Host

Identifies the target host.

Example:

```http
Host: api.company.com
```

Required in modern HTTP requests.

---

### User-Agent

Identifies the client.

Example:

```http
User-Agent: Chrome
```

Useful for analytics and compatibility.

---

### Accept

Indicates acceptable response formats.

Example:

```http
Accept: application/json
```

---

### Content-Type

Specifies data format.

Example:

```http
Content-Type: application/json
```

Common values:

- application/json
- text/html
- text/plain
- multipart/form-data

---

### Authorization

Used for authentication.

Example:

```http
Authorization: Bearer token
```

Common in APIs.

---

### Cookie

Sends browser cookies.

Example:

```http
Cookie: session_id=abc123
```

---

### Set-Cookie

Server instructs browser to store a cookie.

Example:

```http
Set-Cookie: session_id=abc123
```

---

### Cache-Control

Controls caching behavior.

Example:

```http
Cache-Control: max-age=300
```

---

### Location

Used during redirects.

Example:

```http
Location: https://example.com
```

---

## Content Negotiation

Clients and servers can negotiate formats.

Example:

```http
Accept: application/json
```

Server returns:

```http
Content-Type: application/json
```

---

## Security Headers

Common security headers:

### Strict-Transport-Security

Forces HTTPS.

### X-Content-Type-Options

Prevents MIME sniffing.

### Content-Security-Policy

Mitigates XSS attacks.

### X-Frame-Options

Mitigates clickjacking.

These are important production security controls.

---

## Production Impact

Headers influence:

- Authentication
- Authorization
- Caching
- Security
- Content delivery
- API communication

Incorrect headers frequently cause production issues.

---

## Common Production Problems

### Wrong Content-Type

Symptoms:

- Parsing failures
- API errors

### Missing Authorization Header

Symptoms:

- 401 Unauthorized

### Cache Misconfiguration

Symptoms:

- Stale responses

### Missing Security Headers

Symptoms:

- Security vulnerabilities

---

## Troubleshooting Tools

```bash
curl -I https://example.com
```

```bash
curl -v https://example.com
```

Browser Developer Tools are also heavily used.

---

## Common Interview Questions

- What are HTTP headers?
- Content-Type vs Accept?
- What is Authorization header?
- What is Cache-Control?
- Cookie vs Set-Cookie?
- Why is Host header required?
- What are security headers?
- How do you inspect headers?

---

## Quick Revision

| Header | Purpose |
|----------|----------|
| Host | Target Host |
| User-Agent | Client Information |
| Accept | Expected Response Type |
| Content-Type | Data Format |
| Authorization | Authentication |
| Cookie | Send Cookie |
| Set-Cookie | Create Cookie |
| Cache-Control | Cache Rules |
| Location | Redirect Target |
| CSP/HSTS | Security Controls |