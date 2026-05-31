

# Security Groups vs NACL

## Why Security Controls Exist

Cloud resources should not accept all network traffic.

Question:

```text
Which Traffic
Should Be Allowed?

Which Traffic
Should Be Blocked?
```

Cloud platforms provide multiple layers of network security.

The two most common are:

- Security Groups
- Network ACLs (NACLs)

---

## The Engineering Problem

Suppose a web application contains:

```text
Load Balancer
Application Server
Database
```

Requirements:

```text
Allow HTTPS
Allow Application Traffic
Block Everything Else
```

Security Groups and NACLs help enforce these rules.

---

## What Is A Security Group?

A Security Group is a virtual firewall attached to resources.

Example:

```text
EC2 Instance
      ↓
Security Group
```

It controls traffic entering and leaving specific resources.

---

## Security Group Characteristics

### Resource Level

Applied directly to resources.

Examples:

- Virtual machines
- Load balancers
- Databases

---

### Stateful

If inbound traffic is allowed:

```text
Request Allowed
      ↓
Response Automatically Allowed
```

No additional outbound rule is required.

---

### Allow Rules Only

Security Groups contain:

```text
Allow Rules
```

Traffic not explicitly allowed is denied.

---

## What Is A NACL?

NACL stands for:

```text
Network Access Control List
```

A NACL acts as a firewall at the subnet level.

Example:

```text
Subnet
   ↓
NACL
```

---

## NACL Characteristics

### Subnet Level

Applied to entire subnets.

---

### Stateless

Requests and responses are evaluated separately.

Example:

```text
Inbound Rule
      ↓
Outbound Rule Required
```

---

### Allow And Deny Rules

NACLs support:

```text
Allow
Deny
```

This provides more granular filtering.

---

## High-Level Architecture

```text
Internet
    ↓
NACL
    ↓
Subnet
    ↓
Security Group
    ↓
Instance
```

Both layers work together.

---

## Security Group vs NACL

| Feature | Security Group | NACL |
|----------|----------|----------|
| Scope | Resource Level | Subnet Level |
| Stateful | Yes | No |
| Allow Rules | Yes | Yes |
| Deny Rules | No | Yes |
| Applied To | Instances/Resources | Subnets |
| Response Traffic | Automatic | Explicit Rule Required |

---

## Common Production Usage

### Security Groups

Used for:

- Application access
- Database access
- Service-to-service communication

### NACLs

Used for:

- Network boundaries
- Additional subnet protection
- Broad filtering policies

---

## Example Design

Application Server:

```text
Allow HTTPS From Load Balancer
Allow App Traffic
```

Database:

```text
Allow Database Port
From Application Servers Only
```

NACL:

```text
Block Unwanted Traffic
At Subnet Boundary
```

---

## Common Production Failures

### Missing Security Group Rule

Symptoms:

- Service unreachable

### Missing NACL Response Rule

Symptoms:

- Intermittent connectivity

### Overly Permissive Rules

Symptoms:

- Increased attack surface

### Rule Conflicts

Symptoms:

- Unexpected traffic blocking

---

## Common Interview Questions

- What is a Security Group?
- What is a NACL?
- Security Group vs NACL?
- Stateful vs stateless firewall?
- Why do NACLs support deny rules?
- Which is evaluated at subnet level?
- Which is evaluated at resource level?

---

## Quick Revision

| Concept | Security Group | NACL |
|----------|----------|----------|
| Scope | Resource | Subnet |
| Stateful | Yes | No |
| Deny Rules | No | Yes |
| Response Traffic | Automatic | Explicit Rule Needed |
| Common Usage | Resource Protection | Subnet Protection |
| Core Goal | Access Control | Boundary Protection |