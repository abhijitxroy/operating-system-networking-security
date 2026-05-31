

# Cloud Troubleshooting

## Why Cloud Troubleshooting Exists

Cloud platforms provide abstraction, automation and scalability.

They also introduce additional complexity.

Engineers must troubleshoot:

- Virtual infrastructure
- Managed services
- IAM issues
- Networking problems
- Kubernetes workloads
- Multi-region architectures

Cloud troubleshooting exists to systematically identify failures across these layers.

---

## The Engineering Problem

A cloud outage rarely has a single obvious cause.

Symptoms often appear as:

- Application failures
- Latency spikes
- Authentication errors
- Connectivity issues
- Resource exhaustion

The actual root cause may exist elsewhere.

```text
Application Error
        ↓
Cloud Resource
        ↓
Underlying Root Cause
```

Engineers must investigate dependencies rather than assumptions.

---

## Common Cloud Failure Domains

### Compute

Examples:

- Virtual machines
- Containers
- Kubernetes nodes

### Networking

Examples:

- VPCs
- Routes
- Firewalls
- Security groups

### Identity

Examples:

- IAM roles
- Policies
- Service accounts

### Storage

Examples:

- Object storage
- Block storage
- Databases

### Managed Services

Examples:

- Message queues
- Managed databases
- Load balancers

---

## A Practical Troubleshooting Workflow

```text
Identify Impact
      ↓
Identify Affected Service
      ↓
Check Monitoring
      ↓
Review Logs
      ↓
Validate Dependencies
      ↓
Find Root Cause
```

Avoid making configuration changes before gathering evidence.

---

## IAM Troubleshooting

Many cloud incidents originate from identity issues.

Common symptoms:

- Access denied
- Authentication failures
- Service communication failures

Investigation:

- Role assignments
- Policy evaluation
- Service account permissions
- Recent IAM changes

---

## Networking Troubleshooting

Common symptoms:

- Connection timeout
- Unreachable services
- DNS failures

Investigation:

- Route tables
- Security groups
- Network ACLs
- DNS resolution
- Load balancer health

Networking remains one of the most common cloud failure areas.

---

## Resource Troubleshooting

Symptoms:

- High latency
- Slow applications
- Unstable workloads

Investigation:

- CPU utilization
- Memory utilization
- Storage performance
- Pod resource limits
- Autoscaling behavior

---

## Managed Service Troubleshooting

Cloud platforms provide abstraction.

However engineers still need visibility.

Review:

- Service health dashboards
- Cloud metrics
- Error logs
- Provider status pages

Never assume managed services cannot fail.

---

## Production Impact

Cloud failures can affect:

- Multiple applications
- Entire environments
- Regional deployments
- Disaster recovery systems

The larger the dependency graph, the larger the blast radius.

---

## Common Production Failures

### IAM Misconfiguration

Symptoms:

- Access denied errors
- Service failures

### Security Group Errors

Symptoms:

- Connectivity failures
- Timeouts

### Route Table Issues

Symptoms:

- Traffic black holes
- Intermittent communication

### Resource Exhaustion

Symptoms:

- Performance degradation
- Scaling failures

### DNS Failures

Symptoms:

- Service discovery failures
- Intermittent outages

---

## Investigation Mindset

```text
Symptom
   ↓
Evidence
   ↓
Dependency Analysis
   ↓
Root Cause
   ↓
Recovery
```

Cloud troubleshooting is primarily dependency troubleshooting.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| High Abstraction | Reduced Visibility |
| Managed Services | Less Direct Control |
| Rapid Scaling | More Complexity |
| Automation | Harder Debugging |
| Multi-Region Design | More Failure Scenarios |

---

## Interview Thinking

- How would you troubleshoot a cloud outage?
- IAM issue vs networking issue?
- How would you investigate service timeouts?
- Why are cloud incidents difficult to debug?
- How would you troubleshoot DNS failures?
- What is blast radius?
- Why should engineers analyze dependencies first?
- How would you investigate a failing managed service?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Cloud Troubleshooting | Dependency-Based Investigation |
| IAM | Identity Failure Domain |
| Networking | Connectivity Failure Domain |
| DNS | Service Discovery Layer |
| Security Group | Traffic Control |
| Route Table | Traffic Path Decision |
| Managed Service | Provider Managed Component |
| Resource Exhaustion | Capacity Problem |
| Blast Radius | Scope Of Impact |
| RCA | Root Cause Identification |