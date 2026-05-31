

# Security Fundamentals

## Why Security Exists

As systems became interconnected, a fundamental problem emerged.

```text
How Do We Trust Systems Operating In Untrusted Environments?
```

Modern infrastructure constantly faces:

- Malicious actors
- Human mistakes
- Misconfigurations
- Software vulnerabilities
- Insider threats
- Supply chain risks

Security exists to reduce risk while allowing systems to remain usable.

---

## The Engineering Problem

Every system contains valuable assets.

Examples:

- Customer data
- Financial information
- Source code
- Credentials
- Infrastructure
- Intellectual property

Attackers want access.

Engineers want protection.

Security is the discipline of managing this conflict.

---

## Security Is About Risk Management

A common misconception:

```text
Security = Prevent Every Attack
```

In reality:

```text
Security = Reduce Risk To Acceptable Levels
```

Absolute security does not exist.

Every security decision involves tradeoffs.

---

## The CIA Triad

One of the most important security models.

### Confidentiality

Protect information from unauthorized access.

Examples:

- Encryption
- Access controls
- Secret management

### Integrity

Ensure information cannot be modified without detection.

Examples:

- Hashing
- Digital signatures
- Audit trails

### Availability

Ensure systems remain accessible when needed.

Examples:

- Redundancy
- Disaster recovery
- DDoS protection

Most security incidents impact one or more of these areas.

---

## Authentication And Authorization

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

### Authorization

Answers:

```text
What Are You Allowed To Do?
```

Examples:

- RBAC
- IAM Policies
- Access controls

Confusing these concepts creates security vulnerabilities.

---

## Security Principles Engineers Should Know

### Least Privilege

Grant only the access required.

### Defense In Depth

Use multiple layers of protection.

### Zero Trust

Never automatically trust users, devices or workloads.

### Secure By Default

Safer configurations should be the default choice.

### Assume Breach

Design systems assuming attackers may gain access.

---

## Threats, Vulnerabilities And Risk

### Threat

Potential source of harm.

### Vulnerability

Weakness that can be exploited.

### Risk

Likelihood and impact of exploitation.

Understanding the difference is important during security reviews.

---

## Modern Security Landscape

Security now spans:

- Applications
- Cloud platforms
- Containers
- Kubernetes
- Networks
- Identity systems
- Software supply chains

Modern attacks often cross multiple domains.

---

## Production Impact

Security directly affects:

- Customer trust
- Compliance
- Revenue
- Availability
- Brand reputation
- Business continuity

Many organizations spend more recovering from incidents than preventing them.

---

## Common Production Failures

### Excessive Permissions

Symptoms:

- Large blast radius
- Unauthorized access

### Credential Exposure

Symptoms:

- Account compromise
- Infrastructure takeover

### Security Misconfiguration

Symptoms:

- Unexpected exposure
- Public access paths

### Missing Patching

Symptoms:

- Exploitable vulnerabilities
- Compliance failures

### Weak Monitoring

Symptoms:

- Late incident detection
- Limited visibility

---

## Security Investigation Mindset

```text
Identify Asset
      ↓
Identify Threat
      ↓
Identify Vulnerability
      ↓
Determine Risk
      ↓
Implement Control
      ↓
Verify Mitigation
```

Security decisions should be evidence driven.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Strong Security | Increased Complexity |
| Better Usability | Increased Risk |
| Faster Delivery | Higher Security Debt |
| Extensive Monitoring | Additional Cost |
| Strict Controls | Operational Overhead |

---

## Interview Thinking

- Why does security exist?
- What is the CIA triad?
- Authentication vs Authorization?
- What is least privilege?
- What is defense in depth?
- What is Zero Trust?
- Vulnerability vs Threat vs Risk?
- Why is security a risk management problem?
- Security vs usability tradeoffs?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Security | Risk Reduction |
| Confidentiality | Prevent Unauthorized Access |
| Integrity | Prevent Undetected Modification |
| Availability | Ensure Accessibility |
| Authentication | Verify Identity |
| Authorization | Control Access |
| Least Privilege | Minimum Required Permissions |
| Defense In Depth | Multiple Security Layers |
| Zero Trust | Trust Nothing By Default |
| Risk | Likelihood × Impact |