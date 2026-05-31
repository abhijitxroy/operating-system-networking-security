# Linux Users And Groups

## Why Users And Groups Were Invented

Early systems were often used by a single person.

As computing evolved, multiple users started sharing the same machine.

This created new challenges:

- Access control
- Resource isolation
- Security boundaries
- Accountability
- Administration

Linux users and groups were introduced to solve these problems.

They provide the foundation for authentication, authorization and system ownership.

---

## The Engineering Problem

A Linux server may host:

- Administrators
- Developers
- Applications
- Databases
- Services
- Automation tools

Without identity separation:

```text
Everyone
    ↓
Access Everything
    ↓
Security Risk
```

Users and groups create boundaries that allow systems to remain secure and manageable.

---

## What A Linux User Represents

A user is an identity.

Examples:

- Human user
- Service account
- Application account
- Automation account

Every user has:

- Username
- UID
- Home directory
- Default shell
- Permissions

Linux uses these attributes to determine what actions are allowed.

---

## What A Linux Group Represents

Groups simplify access management.

Instead of assigning permissions individually:

```text
User A
User B
User C
```

Engineers can create:

```text
Developers Group
```

And assign permissions once.

Benefits:

- Easier administration
- Consistent access control
- Reduced operational effort

---

## Why Service Accounts Exist

Applications should not run as root.

Instead:

```text
Application
      ↓
Dedicated Service Account
```

Benefits:

- Reduced blast radius
- Better auditing
- Stronger security

Most production services use dedicated users.

---

## Root User

The root account has unrestricted access.

Capabilities:

- Manage users
- Modify system files
- Install software
- Control services

Because root is extremely powerful:

```text
Use Only When Required
```

Modern environments typically prefer sudo-based administration.

---

## Sudo

### Why It Exists

Engineers occasionally require elevated privileges.

Instead of sharing root credentials:

```text
User
   ↓
sudo
   ↓
Privileged Operation
```

Benefits:

- Accountability
- Auditing
- Controlled privilege escalation

---

## Production Impact

Users and groups directly affect:

- Application security
- Compliance requirements
- Service deployments
- Secret management
- Access governance
- Incident investigations

Many production outages occur because applications run under incorrect identities.

---

## Common Production Failures

### Permission Denied

Symptoms:

- Service startup failures
- Access errors

Investigation:

```bash
id
ls -l
```

### Incorrect Service User

Symptoms:

- Application cannot access files
- Startup failures

Investigation:

```bash
ps -ef
systemctl status
```

### Excessive Privileges

Symptoms:

- Security findings
- Compliance violations

Investigation:

```bash
sudo -l
```

### Group Misconfiguration

Symptoms:

- Unexpected access failures

Investigation:

```bash
groups
id
```

---

## Linux Troubleshooting Commands

### Current User

```bash
whoami
```

### User Information

```bash
id
```

### Group Memberships

```bash
groups
```

### Logged In Users

```bash
who
```

### Sudo Privileges

```bash
sudo -l
```

### User Database

```bash
cat /etc/passwd
```

### Group Database

```bash
cat /etc/group
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Strong Security | Additional Administration |
| Least Privilege | More Configuration |
| Shared Access | Reduced Isolation |
| Simplicity | Broader Permissions |
| Fine-Grained Control | Increased Complexity |

---

## Interview Thinking

- Why were users and groups invented?
- What is the difference between authentication and authorization?
- Why should applications avoid running as root?
- What problem does sudo solve?
- Why are service accounts important?
- What is least privilege?
- How would you investigate a permission denied error?
- Why do enterprises prefer role-based access?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| User | System Identity |
| Group | Shared Access Boundary |
| UID | User Identifier |
| Root | Superuser Account |
| Sudo | Controlled Privilege Escalation |
| Service Account | Application Identity |
| Authentication | Verify Identity |
| Authorization | Determine Access |
| Least Privilege | Minimum Required Permissions |
| id | User And Group Information |