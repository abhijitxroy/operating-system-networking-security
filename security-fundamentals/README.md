

# Security Fundamentals

Security is a core engineering discipline that protects systems, applications, infrastructure, networks, and data from unauthorized access, attacks, misuse, and operational risks.

Every software engineer, platform engineer, cloud engineer, SRE, and architect should understand fundamental security concepts because security is a shared responsibility across the entire technology stack.

## Why Security Matters

### Production Usage

- Application security
- Cloud security
- Infrastructure protection
- Identity and access management
- Secure software development
- Data protection
- Network security
- Compliance and governance
- Incident response
- Risk management

### Interview Importance

High

Common interview areas:

- CIA Triad
- Authentication vs Authorization
- Encryption vs Hashing
- TLS/SSL
- OAuth and SSO
- JWT
- OWASP Top 10
- Security Best Practices
- Network Security
- Zero Trust Concepts

---

## Learning Roadmap

### Security Foundations

- CIA Triad
- Security Principles
- Threat Modeling
- Risk Assessment
- Defense in Depth
- Least Privilege

### Identity and Access Management

- Authentication
- Authorization
- RBAC
- ABAC
- Multi-Factor Authentication
- Single Sign-On
- OAuth
- OpenID Connect

### Cryptography Fundamentals

- Encryption
- Symmetric Encryption
- Asymmetric Encryption
- Public Key Infrastructure
- Certificates
- Hashing
- Digital Signatures
- TLS/SSL

### Application Security

- Secure Coding Practices
- Input Validation
- Output Encoding
- Secrets Management
- Session Security
- API Security

### Web Security

- SQL Injection
- Cross Site Scripting (XSS)
- Cross Site Request Forgery (CSRF)
- Authentication Attacks
- Authorization Failures
- OWASP Top 10

### Infrastructure Security

- Network Security
- Firewalls
- VPN
- Security Groups
- Zero Trust
- Endpoint Security

### Cloud Security

- Shared Responsibility Model
- IAM
- Secret Management
- Encryption at Rest
- Encryption in Transit
- Cloud Security Best Practices

### Incident Response

- Detection
- Investigation
- Containment
- Recovery
- Postmortem Analysis

---

## Directory Structure

```text
security-fundamentals
├── README.md
├── fundamentals
├── identity-access-management
├── cryptography
├── web-security
├── application-security
├── infrastructure-security
├── cloud-security
├── secure-development
└── incident-response
```

---

## Suggested Study Order

| Phase | Topic | Priority |
|----------|----------|----------|
| 1 | Security Fundamentals | Critical |
| 2 | Authentication & Authorization | Critical |
| 3 | Cryptography Basics | Critical |
| 4 | TLS & Certificates | Critical |
| 5 | Web Security | Critical |
| 6 | OWASP Top 10 | Critical |
| 7 | Application Security | High |
| 8 | Infrastructure Security | High |
| 9 | Cloud Security | High |
| 10 | Incident Response | High |

---

## Quick Revision Topics

Must know before interviews:

- CIA Triad
- Authentication vs Authorization
- RBAC vs ABAC
- Encryption vs Hashing
- Symmetric vs Asymmetric Encryption
- TLS Handshake
- Digital Certificates
- OAuth Flow
- JWT Structure
- SQL Injection
- XSS
- CSRF
- OWASP Top 10
- Principle of Least Privilege
- Zero Trust

---

## Real-World Engineering Focus

Engineers commonly encounter:

- Credential leaks
- Secret exposure
- Misconfigured IAM permissions
- TLS certificate failures
- Vulnerable dependencies
- API abuse
- Unauthorized access attempts
- Network attacks
- Security compliance requirements
- Production security incidents

Security failures often originate from simple configuration mistakes, excessive permissions, poor secret management, or insecure application design.

---

## Related Repository Sections

- Networking → TLS, firewalls, VPNs, secure communication
- Linux → Permissions, users, groups, hardening
- Operating Systems → Isolation, access control, processes
- Troubleshooting → Incident investigation and root cause analysis

---

## Goal

Build practical security knowledge that helps with:

- Software engineering interviews
- Secure application development
- Cloud and platform engineering
- DevSecOps practices
- Security-aware system design
- Production incident handling
- Infrastructure protection
- Long-term engineering growth
# Security Fundamentals

## Why This Section Exists

Security is no longer a specialized domain owned only by security teams.

Modern engineers routinely work with:

- Cloud platforms
- Kubernetes clusters
- APIs
- Identity systems
- CI/CD pipelines
- Internet-facing applications

Every engineering decision influences security.

This section focuses on understanding security from an engineering perspective rather than memorizing security terminology.

---

## The Engineering Problem

Every system contains assets that must be protected.

Examples:

- Customer data
- Credentials
- Infrastructure
- Intellectual property
- Financial information
- Business operations

Attackers continuously search for weaknesses.

Engineers must reduce risk while maintaining usability, performance and delivery speed.

```text
Assets
   ↓
Threats
   ↓
Security Controls
   ↓
Risk Reduction
```

---

## Security Philosophy

Security is not about preventing every attack.

The goal is:

```text
Reduce Risk
      ↓
Limit Impact
      ↓
Improve Recovery
```

Strong security programs focus on:

- Prevention
- Detection
- Response
- Recovery

---

## What Engineers Should Learn

Every topic in this section should answer:

- Why was this security control created?
- What problem does it solve?
- What attacks does it prevent?
- What tradeoffs exist?
- What fails in production?
- How do engineers investigate incidents?
- How do interviewers evaluate understanding?

The focus is practical engineering security.

---

## Knowledge Map

| Topic | Why It Exists | Production Relevance |
|----------|----------|----------|
| Fundamentals | Security Principles And Risk Management | Foundation For Everything |
| Identity & Access Management | Control Access To Resources | Cloud And Enterprise Security |
| Cryptography | Protect Data And Trust | TLS, Secrets, Certificates |
| Application Security | Secure Software Behavior | Product Security |
| Web Security | Protect Internet-Facing Systems | OWASP And APIs |
| Infrastructure Security | Secure Platforms And Systems | Cloud And Kubernetes |
| Cloud Security | Secure Dynamic Infrastructure | Modern Platforms |
| Secure Development | Build Security Into Software | DevSecOps |
| Incident Response | Recover From Security Events | Operations And Resilience |

---

## Directory Structure

```text
security-fundamentals
├── README.md
├── fundamentals
├── identity-access-management
├── cryptography
├── application-security
├── web-security
├── infrastructure-security
├── cloud-security
├── secure-development
└── incident-response
```

---

## Recommended Learning Order

```text
Security Fundamentals
         ↓
Identity & Access Management
         ↓
Cryptography
         ↓
Infrastructure Security
         ↓
Application Security
         ↓
Web Security
         ↓
Cloud Security
         ↓
Secure Development
         ↓
Incident Response
```

---

## Production Failure Areas Covered

This section focuses on understanding:

- Credential compromise
- Excessive permissions
- Authentication failures
- Authorization failures
- Data exposure
- Vulnerable dependencies
- Cloud misconfigurations
- Infrastructure compromise
- Secret leakage
- Web application attacks
- Supply chain risks
- Security incidents and recovery

---

## Relationship With Other Repository Sections

### Linux

Focuses on permissions, hardening, users, groups and operating system security.

### Networking

Focuses on secure communication, network boundaries and transport security.

### Operating Systems

Explains isolation, processes, resource ownership and security foundations.

### Troubleshooting

Provides investigation methodologies used during incidents and root cause analysis.

---

## Interview Focus Areas

Topics frequently evaluated in engineering interviews:

- CIA Triad
- Authentication vs Authorization
- RBAC vs ABAC
- Least Privilege
- Defense In Depth
- Zero Trust
- Encryption vs Hashing
- Symmetric vs Asymmetric Encryption
- TLS
- OAuth
- JWT
- OWASP Top 10
- Secure SDLC
- Incident Response

---

## Goal

Build practical security knowledge that helps engineers:

- Design secure systems
- Protect infrastructure
- Secure cloud environments
- Investigate incidents
- Reduce operational risk
- Understand modern attack paths
- Perform well in security-focused interviews

The objective is understanding how security behaves in production systems rather than memorizing security terminology.