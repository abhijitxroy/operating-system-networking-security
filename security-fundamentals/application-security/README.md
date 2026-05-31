

# Application Security

## Why Application Security Exists

Early security efforts focused primarily on networks and infrastructure.

Over time, attackers realized applications were often the easiest path into systems.

Examples:

- SQL Injection
- Authentication bypasses
- Remote code execution
- Sensitive data exposure
- Business logic abuse

Application security emerged to reduce risk within the software itself.

---

## The Engineering Problem

Applications process:

- User input
- Business transactions
- Sensitive data
- Authentication requests
- API traffic

Attackers interact with the same interfaces used by legitimate users.

```text
User
  ↓
Application
  ↓
Data

Attacker
  ↓
Application
  ↓
Data
```

The challenge is ensuring the application behaves securely regardless of input.

---

## Security Must Be Built In

Security cannot be added at the end of development.

Modern engineering requires security throughout:

```text
Design
  ↓
Development
  ↓
Testing
  ↓
Deployment
  ↓
Operations
```

This approach reduces security debt and operational risk.

---

## Common Application Security Goals

Applications must protect:

- Confidentiality
- Integrity
- Availability
- Authentication
- Authorization
- Auditability

A failure in any area can become a production incident.

---

## Authentication vs Authorization

### Authentication

Answers:

```text
Who Are You?
```

Examples:

- Passwords
- MFA
- SSO
- OAuth

### Authorization

Answers:

```text
What Are You Allowed To Do?
```

Examples:

- RBAC
- Permissions
- Policies

Many security vulnerabilities occur because these concepts are confused.

---

## Input Validation

Applications should never trust input.

Sources include:

- Browsers
- APIs
- Mobile applications
- External integrations

Validation helps prevent:

- Injection attacks
- Data corruption
- Unexpected behavior

---

## Secure Data Handling

Sensitive information requires protection.

Examples:

- Passwords
- Tokens
- Secrets
- Personal information

Common controls:

- Encryption
- Hashing
- Access controls
- Secret management

---

## Production Impact

Application security directly affects:

- Customer trust
- Regulatory compliance
- Platform reliability
- Incident response costs
- Business continuity

Many major breaches originate from application vulnerabilities rather than infrastructure failures.

---

## Common Production Failures

### Broken Authentication

Symptoms:

- Unauthorized access
- Account compromise

### Broken Authorization

Symptoms:

- Privilege escalation
- Data exposure

### Injection Vulnerabilities

Symptoms:

- Database compromise
- Unexpected query execution

### Sensitive Data Exposure

Symptoms:

- Leaked credentials
- Compliance violations

### Security Misconfiguration

Symptoms:

- Expanded attack surface
- Unexpected access paths

---

## Security Investigation Mindset

When analyzing a security issue:

```text
Identify Asset
      ↓
Identify Entry Point
      ↓
Understand Trust Boundary
      ↓
Determine Impact
      ↓
Identify Root Cause
      ↓
Implement Mitigation
```

Focus on evidence rather than assumptions.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Strong Security | Additional Development Effort |
| Better User Experience | Increased Security Risk |
| Faster Delivery | Higher Security Debt |
| Extensive Validation | Additional Processing Cost |
| Strict Controls | Operational Complexity |

---

## Interview Thinking

- Why does application security exist?
- Authentication vs Authorization?
- Why should applications never trust input?
- What causes injection vulnerabilities?
- How would you secure sensitive data?
- Why is security a development responsibility?
- How would you investigate unauthorized access?
- Security vs usability tradeoffs?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Application Security | Protect Software From Abuse |
| Authentication | Verify Identity |
| Authorization | Control Access |
| Input Validation | Never Trust Input |
| Encryption | Protect Data |
| Hashing | One-Way Protection |
| Secret Management | Protect Credentials |
| Injection | Untrusted Input Execution |
| Least Privilege | Minimum Required Access |
| Defense In Depth | Multiple Security Layers |