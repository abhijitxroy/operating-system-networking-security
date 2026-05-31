

# Cloud Security

## Why Cloud Security Exists

Traditional security models were designed for on-premises environments.

Organizations controlled:

- Physical servers
- Network devices
- Storage systems
- Data centers

Cloud computing changed the model.

Infrastructure became:

- Dynamic
- Distributed
- API-driven
- Shared responsibility based

Cloud security emerged to address the new risks introduced by cloud platforms.

---

## The Engineering Problem

Cloud environments allow engineers to provision infrastructure in minutes.

This speed creates new challenges:

- Misconfigurations
- Excessive permissions
- Data exposure
- Identity sprawl
- Shadow infrastructure

Without proper controls:

```text
Fast Provisioning
        ↓
Fast Misconfiguration
        ↓
Security Exposure
```

Cloud security focuses on reducing this risk.

---

## The Shared Responsibility Model

One of the most important cloud security concepts.

Cloud providers secure:

- Physical infrastructure
- Data centers
- Core platform services

Customers secure:

- Identities
- Applications
- Data
- Configurations
- Access controls

Misunderstanding this model is a common source of security incidents.

---

## Identity Is The New Security Boundary

Traditional security relied heavily on network boundaries.

Cloud environments rely heavily on identity.

Examples:

- Users
- Service accounts
- IAM roles
- Workloads
- Applications

Compromised identities often lead to cloud breaches.

---

## Least Privilege

Cloud environments make it easy to grant excessive access.

Best practice:

```text
Grant Only What Is Required
```

Benefits:

- Reduced blast radius
- Better compliance
- Improved security posture

---

## Data Protection

Cloud platforms store enormous amounts of sensitive information.

Protection commonly includes:

- Encryption at rest
- Encryption in transit
- Key management
- Access controls
- Data classification

Data security remains a primary cloud security concern.

---

## Network Security In The Cloud

Common controls:

- Security Groups
- Network ACLs
- Firewalls
- Private Networks
- Segmentation

These controls reduce exposure and restrict communication paths.

---

## Production Impact

Cloud security directly affects:

- Regulatory compliance
- Customer trust
- Business continuity
- Incident response
- Platform reliability

A single misconfiguration can expose large amounts of infrastructure or data.

---

## Common Production Failures

### Excessive IAM Permissions

Symptoms:

- Large blast radius
- Unauthorized access risk

### Public Storage Exposure

Symptoms:

- Sensitive data leakage
- Compliance violations

### Credential Exposure

Symptoms:

- Account compromise
- Unauthorized activity

### Security Group Misconfiguration

Symptoms:

- Unnecessary internet exposure
- Unexpected access paths

### Unencrypted Data

Symptoms:

- Regulatory issues
- Increased breach impact

---

## Cloud Security Investigation Mindset

```text
Identify Asset
      ↓
Identify Identity
      ↓
Review Permissions
      ↓
Review Network Exposure
      ↓
Review Data Access
      ↓
Determine Root Cause
```

Security investigations should focus on evidence and access paths.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Strong Security | Increased Operational Effort |
| Least Privilege | More Administration |
| Faster Delivery | Higher Security Risk |
| Extensive Monitoring | Additional Cost |
| Multi-Region Security | Greater Complexity |

---

## Interview Thinking

- Why is cloud security different from traditional security?
- What is the shared responsibility model?
- Why is identity considered the new perimeter?
- What causes most cloud breaches?
- Why is least privilege important?
- How would you investigate exposed cloud resources?
- Security Group vs Network ACL?
- How would you secure cloud workloads?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Cloud Security | Protect Cloud Resources |
| Shared Responsibility | Provider + Customer Security Model |
| IAM | Identity And Access Control |
| Least Privilege | Minimum Required Access |
| Encryption | Data Protection |
| Security Group | Instance-Level Access Control |
| Network ACL | Subnet-Level Filtering |
| Credential Exposure | Identity Compromise Risk |
| Public Storage Exposure | Common Cloud Misconfiguration |
| Blast Radius | Scope Of Potential Impact |