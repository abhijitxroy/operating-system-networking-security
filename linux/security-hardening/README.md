

# Linux Security Hardening

## Why Security Hardening Exists

A default Linux installation is designed to be functional.

Production systems must be secure.

These are not the same goal.

As Linux became the foundation for servers, cloud platforms, containers and enterprise infrastructure, engineers needed additional controls to reduce risk.

Security hardening is the process of reducing the attack surface while maintaining operational requirements.

---

## The Engineering Problem

Every running system exposes potential attack paths.

Examples:

- Open network ports
- Unnecessary services
- Weak authentication
- Excessive permissions
- Unpatched software
- Misconfigurations

Without hardening:

```text
More Exposure
      ↓
Higher Risk
      ↓
Greater Attack Surface
```

The goal is not perfect security.

The goal is risk reduction.

---

## Security Hardening Philosophy

Strong security is usually achieved through layers.

Common principles:

### Least Privilege

Grant only the access required.

### Defense In Depth

Multiple security controls protect the same asset.

### Minimize Attack Surface

Remove what is unnecessary.

### Secure By Default

Prefer safer configurations.

---

## User And Access Security

Key controls include:

- Strong authentication
- Multi-factor authentication
- Restricted sudo access
- Account lifecycle management
- Password policies

Useful commands:

```bash
id
sudo -l
passwd
```

---

## Service Hardening

Every running service increases exposure.

Questions engineers should ask:

- Is this service required?
- Is it internet accessible?
- Is it patched?
- Is it monitored?

Investigation:

```bash
systemctl list-units
ss -tulpn
```

---

## Network Hardening

Common controls:

- Firewalls
- Network segmentation
- Port restrictions
- TLS encryption
- Access control lists

Useful commands:

```bash
ss -tulpn
ip addr
```

---

## File System Security

Security frequently begins with permissions.

Engineers should review:

- Ownership
- Permissions
- Sensitive files
- Secret locations

Useful commands:

```bash
ls -l
stat
find
```

---

## Patch Management

Many security incidents occur because known vulnerabilities remain unpatched.

A mature patching process includes:

- Risk assessment
- Testing
- Rollout strategy
- Verification
- Rollback planning

Security and stability must be balanced.

---

## Logging And Auditing

You cannot investigate what you cannot observe.

Security visibility depends on:

- System logs
- Authentication logs
- Audit trails
- Monitoring systems

Useful commands:

```bash
journalctl
last
```

---

## Production Impact

Security hardening affects:

- Compliance
- Platform engineering
- Cloud infrastructure
- Kubernetes clusters
- Enterprise operations
- Incident response

Hardening is an operational responsibility, not merely a security team responsibility.

---

## Common Production Failures

### Excessive Permissions

Symptoms:

- Security findings
- Compliance violations

Investigation:

```bash
find / -perm -777
```

### Unnecessary Services

Symptoms:

- Larger attack surface
- Increased exposure

Investigation:

```bash
systemctl list-units
```

### Unpatched Systems

Symptoms:

- Vulnerability findings
- Security incidents

Investigation:

- Patch inventory
- Version review

### Weak Access Controls

Symptoms:

- Unauthorized access
- Privilege escalation risk

Investigation:

```bash
sudo -l
id
```

---

## Linux Troubleshooting Commands

### Active Services

```bash
systemctl list-units
```

### Listening Ports

```bash
ss -tulpn
```

### Authentication Information

```bash
id
who
last
```

### Security Logs

```bash
journalctl
```

### Sudo Permissions

```bash
sudo -l
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Strong Security | Increased Administration |
| Least Privilege | Additional Configuration |
| Extensive Logging | Higher Storage Cost |
| Rapid Patching | Change Risk |
| Strict Controls | Reduced Operational Flexibility |

---

## Interview Thinking

- Why is security hardening necessary?
- What is least privilege?
- What is defense in depth?
- Why is patch management important?
- Why can excessive permissions become dangerous?
- How would you investigate unauthorized access?
- How would you reduce Linux attack surface?
- Security vs operational flexibility?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Security Hardening | Attack Surface Reduction |
| Least Privilege | Minimum Required Access |
| Defense In Depth | Multiple Security Layers |
| Patch Management | Vulnerability Reduction |
| Firewall | Network Access Control |
| sudo | Privileged Access Control |
| Audit Trail | Activity Visibility |
| Attack Surface | Exposed Resources |
| Compliance | Security Governance |
| Risk Reduction | Primary Hardening Goal |