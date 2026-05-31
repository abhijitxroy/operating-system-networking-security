

# Web Security

## Why Web Security Exists

The web became the primary interface between users and applications.

Today, web applications handle:

- Authentication
- Payments
- Banking
- Healthcare data
- Enterprise operations
- Cloud management

As web adoption increased, attackers shifted focus toward browsers, APIs and web applications.

Web security exists to protect these systems from abuse and compromise.

---

## The Engineering Problem

Web applications operate in hostile environments.

Anyone with internet access can interact with them.

This creates unique challenges:

- Untrusted input
- Session management
- Authentication risks
- Browser security concerns
- API abuse

Without proper controls:

```text
Internet
    ↓
Application
    ↓
Sensitive Data
```

Attackers exploit weaknesses within that path.

---

## Why Web Applications Are Frequent Targets

Web applications often provide direct access to:

- Customer information
- Financial systems
- Business processes
- Administrative functions

Successful exploitation can provide significant attacker value.

This makes web applications one of the most targeted technology layers.

---

## Trust Boundaries

A critical web security concept.

Examples:

```text
Browser
    ↓
Application
    ↓
Database
```

Every boundary introduces risk.

Engineers should always ask:

```text
Can This Input Be Trusted?
```

The answer is usually no.

---

## Authentication Security

Authentication protects identity.

Common controls:

- Strong passwords
- MFA
- Session protection
- Token validation

Weak authentication often leads directly to account compromise.

---

## Authorization Security

Authentication identifies users.

Authorization controls access.

Examples:

- RBAC
- Permission checks
- Resource ownership validation

Many web vulnerabilities result from broken authorization rather than broken authentication.

---

## Input Validation

Web applications should never trust input.

Input can originate from:

- Browsers
- APIs
- Mobile applications
- Third-party integrations

Proper validation reduces risk from numerous attack classes.

---

## Common Web Vulnerabilities

### SQL Injection

Attackers manipulate database queries.

Impact:

- Data theft
- Data modification
- System compromise

### Cross-Site Scripting (XSS)

Attackers inject malicious scripts.

Impact:

- Session theft
- User impersonation
- Browser compromise

### Cross-Site Request Forgery (CSRF)

Attackers trick users into performing unintended actions.

Impact:

- Unauthorized operations
- Account abuse

### Broken Access Control

Users gain access to unauthorized resources.

Impact:

- Data exposure
- Privilege escalation

### Sensitive Data Exposure

Data is insufficiently protected.

Impact:

- Compliance violations
- Customer impact

---

## API Security

Modern applications rely heavily on APIs.

Security concerns include:

- Authentication
- Authorization
- Rate limiting
- Input validation
- Token security

API security has become a major focus area in modern architectures.

---

## Production Impact

Web security directly affects:

- Customer trust
- Revenue
- Compliance
- Brand reputation
- Business continuity

Many major breaches originate from web application vulnerabilities.

---

## Common Production Failures

### Missing Authorization Checks

Symptoms:

- Unauthorized data access

### Weak Session Management

Symptoms:

- Session hijacking

### Improper Input Validation

Symptoms:

- Injection vulnerabilities

### Exposed APIs

Symptoms:

- Data leakage
- Abuse of business functions

### Security Misconfiguration

Symptoms:

- Expanded attack surface

---

## Security Review Mindset

```text
Identify Asset
      ↓
Identify Entry Point
      ↓
Identify Trust Boundary
      ↓
Validate Controls
      ↓
Assess Risk
      ↓
Implement Mitigation
```

Focus on attack paths rather than isolated vulnerabilities.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Strong Security | Increased Development Effort |
| Better User Experience | Increased Risk |
| Extensive Validation | Additional Processing Cost |
| Strict Controls | Reduced Flexibility |
| Faster Delivery | Higher Security Debt |

---

## Interview Thinking

- Why does web security exist?
- Why are web applications frequent targets?
- Authentication vs Authorization?
- What is a trust boundary?
- What causes SQL Injection?
- What is XSS?
- What is CSRF?
- Why is broken access control dangerous?
- How would you secure a public API?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Web Security | Protect Internet-Facing Applications |
| Authentication | Verify Identity |
| Authorization | Control Access |
| Trust Boundary | Transition Between Trust Levels |
| SQL Injection | Database Query Manipulation |
| XSS | Script Injection |
| CSRF | Unauthorized User Actions |
| API Security | Protect Service Interfaces |
| Session Management | Maintain User Identity |
| Input Validation | Never Trust User Input |