

# Network Access Control (NAC)

## Why Network Access Control Exists

Not every device should be allowed to connect to a network.

Question:

```text
How Do We Verify
Who Or What
Can Access The Network?
```

Without access control:

- Unauthorized devices may connect
- Security risks increase
- Compliance becomes difficult
- Sensitive resources may be exposed

Network Access Control helps solve these problems.

---

## What Is Network Access Control?

Network Access Control (NAC) is a security approach that controls which users and devices can access network resources.

Purpose:

```text
User Or Device
       ↓
Authentication
       ↓
Authorization
       ↓
Network Access
```

Only approved entities receive access.

---

## The Engineering Problem

Suppose an employee laptop connects to a corporate network.

Question:

```text
Is The Device Trusted?

Is The User Authorized?

Should Full Access Be Allowed?
```

NAC provides the answer.

---

## Core Components

### Authentication

Verifies identity.

Examples:

- Username and password
- Certificates
- Multi-factor authentication

---

### Authorization

Determines what access is allowed.

Example:

```text
Engineering Team
       ↓
Engineering Resources
```

---

### Accounting

Tracks access activity.

Examples:

- Login events
- Device connections
- Resource usage

---

## AAA Model

A common NAC foundation.

```text
Authentication
      ↓
Authorization
      ↓
Accounting
```

Often called:

```text
AAA
```

---

## Device Validation

NAC can evaluate device posture.

Checks may include:

- Antivirus installed
- OS patches applied
- Disk encryption enabled
- Security policies enforced

Non-compliant devices may be restricted.

---

## 802.1X Authentication

A common NAC standard.

Flow:

```text
User Device
      ↓
Switch/Wi-Fi Access Point
      ↓
Authentication Server
```

Access is granted only after successful authentication.

---

## Role-Based Access Control (RBAC)

Permissions based on role.

Example:

```text
Developer
     ↓
Development Resources

Finance User
     ↓
Finance Resources
```

Simplifies security management.

---

## Least Privilege Principle

Users should receive only the access they require.

```text
Minimum Required Access
```

This reduces security risk.

---

## Production Usage

NAC is common in:

- Enterprise networks
- Corporate Wi-Fi
- Data centers
- Universities
- Government environments
- Zero Trust architectures

---

## Common Production Failures

### Authentication Failure

Symptoms:

- User unable to connect

### Authorization Misconfiguration

Symptoms:

- Access denied incorrectly

### Certificate Problems

Symptoms:

- Device authentication failure

### Over-Permissive Access

Symptoms:

- Security exposure

---

## Common Interview Questions

- What is Network Access Control?
- What is AAA?
- What is 802.1X?
- Authentication vs Authorization?
- What is RBAC?
- What is least privilege?
- Why is NAC important?
- How does NAC support Zero Trust?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| NAC | Control Network Access |
| Authentication | Verify Identity |
| Authorization | Grant Permissions |
| Accounting | Track Activity |
| AAA | Authentication, Authorization, Accounting |
| 802.1X | Network Access Authentication |
| RBAC | Role-Based Permissions |
| Device Posture | Security Validation |
| Least Privilege | Minimum Required Access |
| Core Goal | Secure Network Access |