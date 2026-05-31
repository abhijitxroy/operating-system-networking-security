

# Session Persistence (Sticky Sessions)

## Why Session Persistence Exists

Load balancers distribute requests across multiple servers.

Example:

```text
User
  ↓
Server A

Next Request
  ↓
Server B
```

Question:

```text
What Happens If User State
Exists Only On Server A?
```

The user may experience failures.

Session Persistence solves this problem.

---

## What Is Session Persistence?

Session Persistence (Sticky Sessions) ensures requests from the same user are consistently routed to the same backend server.

Purpose:

```text
User
  ↓
Server A
  ↓
Server A
  ↓
Server A
```

The user's session remains associated with a specific server.

---

## The Engineering Problem

Suppose a user logs in.

Session data exists on:

```text
Server A
```

Next request reaches:

```text
Server B
```

Server B does not have the session.

Possible result:

```text
User Logged Out
```

or

```text
Session Not Found
```

---

## High-Level Flow

Without persistence:

```text
Request 1 → Server A
Request 2 → Server B
Request 3 → Server C
```

With persistence:

```text
Request 1 → Server A
Request 2 → Server A
Request 3 → Server A
```

---

## Common Persistence Methods

### Cookie-Based Persistence

Most common approach.

```text
Load Balancer Cookie
        ↓
Server Mapping
```

Future requests use the cookie.

---

### Source IP Affinity

Uses:

```text
Client IP Address
```

Example:

```text
IP Address
      ↓
Hash
      ↓
Server Selection
```

Simple but less accurate.

---

### Session Identifier Routing

Application session IDs determine routing.

Useful for application-aware load balancing.

---

## Benefits

### Session Continuity

Users maintain application state.

### Simpler Applications

Less need for shared session storage.

### Better User Experience

Fewer authentication issues.

---

## Limitations

### Uneven Traffic Distribution

Some servers may receive more traffic.

### Reduced Scalability

Traffic cannot be distributed completely freely.

### Server Dependency

A user becomes dependent on a specific backend.

---

## Modern Alternative

Instead of sticky sessions:

```text
Shared Session Store
```

Examples:

- Redis
- Database-backed sessions
- Distributed caches

Benefits:

```text
Any Server
Can Serve Any Request
```

Preferred in many modern cloud architectures.

---

## Production Usage

Session persistence is common in:

- Legacy applications
- Web applications
- Authentication systems
- E-commerce platforms

Still widely used despite distributed session storage becoming more common.

---

## Common Production Failures

### Lost Session

Symptoms:

- Unexpected logout

### Incorrect Persistence Configuration

Symptoms:

- Random authentication failures

### Backend Failure

Symptoms:

- User session unavailable

### Traffic Imbalance

Symptoms:

- Some servers overloaded

---

## Common Interview Questions

- What is session persistence?
- What are sticky sessions?
- Why are sticky sessions needed?
- Cookie-based persistence vs IP affinity?
- What are the limitations of sticky sessions?
- Why do modern systems prefer shared session stores?
- How does session persistence affect scalability?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Session Persistence | Same User → Same Server |
| Sticky Session | Persistent Backend Selection |
| Cookie-Based Persistence | Most Common Method |
| IP Affinity | Source IP Based Routing |
| Main Benefit | Session Continuity |
| Main Limitation | Uneven Distribution |
| Alternative | Shared Session Store |
| Common Store | Redis |
| Production Risk | Session Loss |
| Core Goal | Preserve User State |