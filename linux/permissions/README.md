n
# Linux Permissions

## Why Permissions Were Invented

Early computing systems often assumed trusted users.

As multiple users started sharing systems, a new problem emerged.

How do we prevent one user from:

- Reading another user's data
- Modifying critical files
- Disrupting system operation
- Executing unauthorized actions

Linux permissions were created to provide security, isolation, and controlled access to resources.

---

## The Engineering Problem

A system contains:

- Users
- Applications
- Services
- System files
- Databases
- Sensitive information

Without access control:

```text
Any User
      ↓
Any File
      ↓
System Compromise
```

Permissions act as the first security boundary.

---

## How Linux Access Control Works

Every file and directory has:

- Owner
- Group
- Permissions

Example:

```text
-rwxr-x---
```

Permissions are evaluated against:

```text
Owner
Group
Others
```

This simple model powers most Linux authorization decisions.

---

## Permission Types

### Read (r)

Allows:

- View file contents
- Read data

### Write (w)

Allows:

- Modify files
- Delete files (directory dependent)
- Create content

### Execute (x)

Allows:

- Execute programs
- Access directories

---

## Numeric Permissions

Common production values:

| Value | Meaning |
|----------|----------|
| 777 | Full Access For Everyone |
| 755 | Common Application Permission |
| 750 | Restricted Group Access |
| 700 | Owner Only |
| 644 | Common File Permission |
| 600 | Sensitive File |

Engineers should avoid using 777 in production environments.

---

## Ownership

Ownership controls who manages resources.

View ownership:

```bash
ls -l
```

Change owner:

```bash
chown user:file file.txt
```

Change group:

```bash
chgrp developers file.txt
```

---

## Why Least Privilege Matters

A fundamental security principle:

```text
Grant Only The Access Required
```

Benefits:

- Reduced attack surface
- Lower blast radius
- Better compliance
- Improved security posture

Most production security incidents become worse because permissions were overly broad.

---

## SUID, SGID And Sticky Bit

### SUID

Allows execution with file owner's privileges.

Example:

```bash
passwd
```

### SGID

Allows execution with group privileges.

Useful for shared environments.

### Sticky Bit

Commonly used on:

```text
/tmp
```

Prevents users from deleting files they do not own.

---

## Production Impact

Permissions directly affect:

- Application security
- Service startup
- Container security
- Secret management
- Compliance requirements
- User isolation

Many outages occur because applications cannot access required resources.

---

## Common Production Failures

### Permission Denied

Symptoms:

- Application startup failures
- Access errors

Investigation:

```bash
ls -l
id
```

### Incorrect Ownership

Symptoms:

- Services fail after deployment
- Files inaccessible

Investigation:

```bash
ls -l
stat
```

### Excessive Permissions

Symptoms:

- Security findings
- Compliance violations

Investigation:

```bash
find / -perm -777
```

### Secret Exposure

Symptoms:

- Unauthorized access
- Credential leakage

Investigation:

- File ownership review
- Permission audit

---

## Linux Troubleshooting Commands

### View Permissions

```bash
ls -l
```

### View User Identity

```bash
id
```

### Change Permissions

```bash
chmod
```

### Change Ownership

```bash
chown
```

### Detailed File Information

```bash
stat
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Strong Security | Additional Administration |
| Easy Access | Higher Risk |
| Least Privilege | More Configuration |
| Shared Access | Reduced Isolation |
| Flexibility | Greater Audit Requirements |

---

## Interview Thinking

- Why were permissions invented?
- What problem do permissions solve?
- Difference between owner, group and others?
- What does chmod 755 mean?
- Why is 777 dangerous?
- What is least privilege?
- What is SUID?
- Why is the sticky bit used on /tmp?
- How would you investigate a permission denied error?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Permission | Access Control Rule |
| Owner | Primary Resource Owner |
| Group | Shared Access Boundary |
| Read | View Resource |
| Write | Modify Resource |
| Execute | Run Resource |
| chmod | Change Permissions |
| chown | Change Ownership |
| SUID | Execute As Owner |
| Least Privilege | Minimum Required Access |