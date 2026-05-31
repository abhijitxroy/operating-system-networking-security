

# Identity And Access Management (IAM)

## Why IAM Exists

Early systems focused heavily on network security.

The assumption was:

```text
Inside Network = Trusted
Outside Network = Untrusted
```

Modern systems no longer operate this way.

Cloud platforms, APIs, containers, remote work and distributed systems have made identity the primary security boundary.

IAM exists to answer two critical questions:

```text
Who Are You?
What Are You Allowed To Do?
```

---

## The Engineering Problem

Modern environments contain:

- Users
- Applications
- Services
- Containers
- Kubernetes workloads
- CI/CD pipelines
- Cloud resources

All require controlled access.

Without IAM:

```text
Everyone
     ↓
Access Everything
     ↓
Security Failure
```

IAM provides structured access control.

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
- Certificates
- SSO
- Biometrics

### Authorization

Answers:

```text
What Can You Access?
```

Examples:

- Roles
- Permissions
- Policies
- Access Controls

Many security incidents occur when authorization controls are weaker than authentication controls.

---

## Why Identity Became The New Perimeter

Traditional network boundaries are increasingly blurred.

Modern systems operate across:

- Cloud providers
- SaaS platforms
- Hybrid infrastructure
- Remote work environments

As a result:

```text
Identity
      ↓
Primary Trust Boundary
```

Compromised identities are often more dangerous than compromised servers.

---

## Least Privilege

One of the most important IAM principles.

```text
Grant Only Required Access
```

Benefits:

- Reduced blast radius
- Better compliance
- Lower security risk

Most large-scale breaches become worse because permissions are overly broad.

---

## Role-Based Access Control (RBAC)

Managing permissions individually does not scale.

RBAC solves this problem.

Example:

```text
Developer Role
      ↓
Assigned Permissions
      ↓
Multiple Users
```

Benefits:

- Simpler administration
- Consistent access management
- Easier auditing

---

## Service Identities

Humans are not the only identities.

Modern systems use:

- Service accounts
- IAM roles
- Workload identities
- Application identities

Production systems increasingly rely on machine-to-machine authentication.

---

## Single Sign-On (SSO)

SSO allows users to authenticate once and access multiple systems.

Benefits:

- Better user experience
- Centralized identity management
- Improved security visibility

SSO is a foundational capability in large enterprises.

---

## Multi-Factor Authentication (MFA)

Passwords alone are often insufficient.

MFA introduces additional verification.

Examples:

- Authenticator apps
- Hardware tokens
- Biometrics

MFA significantly reduces account compromise risk.

---

## Production Impact

IAM directly affects:

- Cloud security
- Kubernetes security
- Enterprise security
- Compliance programs
- Incident response
- Platform operations

Identity failures frequently become major security incidents.

---

## Common Production Failures

### Excessive Permissions

Symptoms:

- Large blast radius
- Unauthorized access potential

### Shared Accounts

Symptoms:

- Poor accountability
- Audit challenges

### Missing MFA

Symptoms:

- Increased credential theft risk

### Stale Accounts

Symptoms:

- Unnecessary access exposure

### Overprivileged Service Accounts

Symptoms:

- Infrastructure compromise risk

---

## Security Investigation Mindset

```text
Identify Identity
       ↓
Review Permissions
       ↓
Review Access Path
       ↓
Determine Exposure
       ↓
Reduce Privileges
```

Focus on what the identity can actually do.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Strong Security | Additional Administration |
| Least Privilege | More Configuration |
| Better User Experience | Increased Risk |
| Fine-Grained Access | Higher Complexity |
| Centralized Identity | Platform Dependency |

---

## Interview Thinking

- Why is identity considered the new perimeter?
- Authentication vs Authorization?
- What is least privilege?
- Why does RBAC exist?
- Why are service accounts important?
- What problem does SSO solve?
- Why is MFA important?
- How would you investigate excessive permissions?
- What risks do shared accounts create?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| IAM | Identity And Access Control |
| Authentication | Verify Identity |
| Authorization | Determine Permissions |
| Least Privilege | Minimum Required Access |
| RBAC | Role-Based Access Control |
| SSO | Single Sign-On |
| MFA | Multi-Factor Authentication |
| Service Account | Non-Human Identity |
| Blast Radius | Scope Of Potential Impact |
| Identity Perimeter | Modern Security Boundary |