

# Zero Trust Networking

## Why Zero Trust Exists

Traditional security assumed that systems inside a network could generally be trusted.

Example:

```text
Inside Network
      ↓
Trusted
```

Modern environments changed this assumption.

Examples:

- Cloud infrastructure
- Remote work
- Mobile devices
- SaaS platforms
- Hybrid environments

Question:

```text
What If The Network
Itself Cannot Be Trusted?
```

Zero Trust addresses this challenge.

---

## What Is Zero Trust?

Zero Trust is a security model based on:

```text
Never Trust
Always Verify
```

Every user, device, and service must continuously prove its identity.

Trust is not granted simply because something is inside the network.

---

## The Engineering Problem

Suppose an attacker compromises:

```text
Employee Laptop
```

In a traditional model:

```text
Compromised Device
        ↓
Internal Network Access
```

Potentially leading to widespread compromise.

Zero Trust limits what the attacker can access.

---

## Core Principles

### Verify Explicitly

Always validate:

- User identity
- Device identity
- Location
- Risk signals

Before granting access.

---

### Least Privilege Access

Provide only the minimum required permissions.

```text
User
  ↓
Required Resources Only
```

This reduces blast radius.

---

### Assume Breach

Design systems assuming compromise is possible.

Question:

```text
What Happens If
An Attacker Is Already Inside?
```

Security controls should continue limiting movement.

---

## Identity-Centric Security

Identity becomes the primary security boundary.

Examples:

- Users
- Services
- Devices
- Workloads

Authentication and authorization become critical.

---

## Multi-Factor Authentication (MFA)

Zero Trust strongly encourages:

```text
Password
    +
Additional Verification
```

Examples:

- Authenticator apps
- Hardware keys
- Biometrics

---

## Microsegmentation

Resources are divided into small security zones.

Example:

```text
Service A
    ↓
Allowed
    ↓
Service B

Everything Else
      ↓
Blocked
```

Limits lateral movement.

---

## Continuous Verification

Access decisions are not made only once.

Systems continuously evaluate:

- Identity
- Device health
- User behavior
- Risk levels

---

## Zero Trust And Network Access

Traditional Model:

```text
Connect To Network
        ↓
Access Resources
```

Zero Trust Model:

```text
Request Resource
        ↓
Verify Identity
        ↓
Authorize Access
```

Every access request is evaluated.

---

## Cloud And Kubernetes Relevance

Zero Trust is common in:

- Cloud platforms
- Kubernetes clusters
- Service Mesh architectures
- Multi-cloud environments
- Enterprise SaaS platforms

Examples:

```text
mTLS
Network Policies
Identity-Based Access
```

---

## Production Benefits

### Reduced Attack Surface

Less implicit trust.

### Improved Security

Stronger access control.

### Better Visibility

More auditing and monitoring.

### Stronger Compliance

Supports regulatory requirements.

---

## Common Production Failures

### Excessive Permissions

Symptoms:

- Large blast radius

### Weak Identity Controls

Symptoms:

- Unauthorized access

### Missing MFA

Symptoms:

- Credential compromise risk

### Incomplete Segmentation

Symptoms:

- Lateral movement possible

---

## Common Interview Questions

- What is Zero Trust?
- What does 'Never Trust, Always Verify' mean?
- Why is Zero Trust important?
- What is microsegmentation?
- How does Zero Trust differ from traditional security?
- What role does MFA play?
- How does Zero Trust reduce lateral movement?
- How is Zero Trust used in cloud environments?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Zero Trust | Never Trust, Always Verify |
| Verify Explicitly | Validate Every Request |
| Least Privilege | Minimum Required Access |
| Assume Breach | Design For Compromise |
| MFA | Strong Authentication |
| Identity-Centric Security | Identity As Security Boundary |
| Microsegmentation | Fine-Grained Isolation |
| Continuous Verification | Ongoing Validation |
| Main Benefit | Reduced Attack Surface |
| Core Goal | Secure Access To Resources |