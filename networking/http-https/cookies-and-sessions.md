

# Cookies And Sessions

## Why Cookies And Sessions Exist

HTTP is a stateless protocol.

Meaning:

```text
Request 1
      ↓
Request 2
      ↓
Request 3
```

Each request is independent.

The server does not automatically remember users.

Question:

```text
How Does A Website Remember
That You Are Logged In?
```

Cookies and Sessions solve this problem.

---

## The Engineering Problem

Suppose a user logs into:

```text
amazon.com
```

After successful authentication:

```text
Username
Password
      ↓
Login Success
```

If HTTP is stateless:

```text
How Does The Server Know
Future Requests Belong
To The Same User?
```

Cookies and Sessions provide user state management.

---

## What Is A Cookie?

A cookie is a small piece of data stored in the browser.

Example:

```text
session_id=abc123
```

The browser stores it and sends it with future requests.

---

## Cookie Flow

Server Response:

```text
Set-Cookie:
session_id=abc123
```

Browser Stores Cookie.

Future Requests:

```text
Cookie:
session_id=abc123
```

The server can identify the user.

---

## What Is A Session?

A session is server-side user state.

Example:

```text
Session ID
      ↓
User Data
```

Stored on:

- Application Server
- Database
- Redis
- Session Store

---

## Session Flow

User Logs In:

```text
Credentials
      ↓
Server Creates Session
      ↓
Session ID Generated
```

Example:

```text
abc123
```

Server sends:

```text
Set-Cookie:
session_id=abc123
```

Browser stores the cookie.

---

## How Cookies And Sessions Work Together

```text
User Login
      ↓
Session Created
      ↓
Session ID Generated
      ↓
Cookie Stored In Browser
      ↓
Future Requests Send Cookie
      ↓
Server Loads Session Data
```

This is the traditional authentication model.

---

## Cookie Types

### Session Cookies

Exist only while the browser is open.

Used for:

- Login sessions
- Temporary state

---

### Persistent Cookies

Remain after browser restart.

Used for:

- Remember Me
- User Preferences
- Analytics

---

### Secure Cookies

Sent only over:

```text
HTTPS
```

Improves security.

---

### HttpOnly Cookies

Cannot be accessed by JavaScript.

Helps reduce:

```text
XSS Attacks
```

---

### SameSite Cookies

Control cross-site cookie behavior.

Protect against:

```text
CSRF Attacks
```

---

## Session Storage Options

### In-Memory

Fast but not scalable.

### Database

Persistent but slower.

### Redis

Very common in production systems.

Provides:

- Speed
- Scalability
- Centralized session storage

---

## Stateless Authentication

Modern systems often use:

```text
JWT
```

instead of traditional sessions.

Benefits:

- Easier horizontal scaling
- Reduced server-side state

However sessions remain widely used.

---

## Production Impact

Cookies and sessions affect:

- Authentication
- Authorization
- User experience
- API security
- Web applications
- E-commerce platforms

Nearly every web application depends on them.

---

## Common Production Problems

### Session Expiration

Symptoms:

- Unexpected logouts

### Missing Cookies

Symptoms:

- Login loops
- Authentication failures

### Load Balancer Issues

Symptoms:

- Session inconsistency

### Session Store Failure

Symptoms:

- Users logged out suddenly

### Cookie Security Issues

Symptoms:

- Account compromise

---

## Security Best Practices

Use:

```text
Secure
HttpOnly
SameSite
```

Always prefer:

```text
HTTPS
```

Protect session identifiers carefully.

---

## Useful Browser Tools

Inspect cookies using:

```text
Developer Tools
      ↓
Application
      ↓
Cookies
```

Useful during authentication troubleshooting.

---

## Common Interview Questions

- Why are cookies needed?
- Why are sessions needed?
- HTTP stateless vs stateful?
- Cookie vs Session?
- What is a Session ID?
- What is HttpOnly?
- What is SameSite?
- Why use Secure cookies?
- Session vs JWT?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Cookie | Browser-Side Data |
| Session | Server-Side State |
| Session ID | User Identifier |
| Set-Cookie | Server Creates Cookie |
| HttpOnly | Blocks JavaScript Access |
| Secure | HTTPS Only |
| SameSite | CSRF Protection |
| Redis | Common Session Store |
| JWT | Stateless Authentication |
| Core Purpose | Maintain User State Across Requests |