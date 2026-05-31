

# Virtualization

## Why Virtualization Was Invented

Before virtualization became mainstream, applications were typically deployed directly on physical servers.

This created several problems:

- Low hardware utilization
- Expensive infrastructure
- Difficult capacity planning
- Slow provisioning
- Environment inconsistencies
- Poor workload isolation

A physical server often ran a single application while most CPU and memory resources remained unused.

Virtualization was created to solve the resource utilization and infrastructure efficiency problem.

---

## The Engineering Problem

Organizations wanted:

- Better hardware utilization
- Faster provisioning
- Strong workload isolation
- Easier disaster recovery
- Flexible infrastructure management

Without virtualization:

```text
Application
      ↓
Operating System
      ↓
Physical Server
```

Only one operating system effectively controlled the machine.

Virtualization introduced a layer that allowed multiple operating systems to share the same hardware.

```text
Virtual Machine
Virtual Machine
Virtual Machine
        ↓
Hypervisor
        ↓
Physical Hardware
```

---

## What Virtualization Actually Does

Virtualization creates the illusion that multiple independent machines exist on the same physical hardware.

Each virtual machine receives:

- Virtual CPU
- Virtual memory
- Virtual storage
- Virtual networking
- Virtual devices

Applications believe they are running on dedicated infrastructure.

---

## How Infrastructure Evolved

### Physical Servers

One workload per server.

Problems:

- Wasteful utilization
- High costs
- Slow scaling

### Virtual Machines

Multiple workloads per server.

Solved:

- Better utilization
- Faster provisioning
- Improved isolation

### Containers

Engineers later discovered many workloads did not require a complete operating system.

Containers reduced overhead further.

Important:

Containers did not replace virtualization.

Most cloud platforms run containers on virtual machines.

---

## Hypervisors

The hypervisor is the core virtualization component.

Responsibilities:

- CPU allocation
- Memory allocation
- Device virtualization
- Isolation enforcement
- Resource scheduling

Examples:

- KVM
- VMware ESXi
- Hyper-V
- Xen

---

## Type 1 vs Type 2 Hypervisors

### Type 1

Runs directly on hardware.

Examples:

- VMware ESXi
- Hyper-V
- Xen

Benefits:

- Better performance
- Strong isolation
- Enterprise usage

### Type 2

Runs on top of an operating system.

Examples:

- VirtualBox
- VMware Workstation

Benefits:

- Easy development environments

Tradeoff:

- Additional overhead

---

## Why Cloud Computing Depends On Virtualization

Modern cloud providers depend heavily on virtualization.

Virtualization enables:

- Multi-tenancy
- Resource pooling
- Elastic scaling
- Infrastructure abstraction
- Rapid provisioning

Without virtualization, modern cloud platforms would be significantly more expensive and less flexible.

---

## Production Impact

Virtualization affects:

- Cloud infrastructure
- Kubernetes clusters
- Enterprise data centers
- Disaster recovery
- Platform engineering
- Infrastructure automation

Understanding virtualization helps engineers understand how cloud infrastructure actually works beneath managed services.

---

## Common Production Failures

### CPU Overcommitment

Symptoms:

- High latency
- Slow virtual machines
- Unpredictable performance

Investigation:

- Host CPU utilization
- Hypervisor metrics
- VM scheduling statistics

### Memory Pressure

Symptoms:

- Slow workloads
- Increased swapping
- Resource contention

Investigation:

- Host memory metrics
- VM memory allocation

### Noisy Neighbor Problem

Symptoms:

- One workload impacts another
- Performance degradation

Investigation:

- Resource consumption analysis
- Host utilization review

### Storage Bottlenecks

Symptoms:

- Slow VM startup
- Slow applications
- High I/O latency

Investigation:

- Storage metrics
- Hypervisor monitoring
- I/O analysis

---

## Virtual Machines vs Containers

| Area | Virtual Machines | Containers |
|----------|----------|----------|
| Isolation | Strong | Moderate |
| Startup Time | Slower | Faster |
| Resource Usage | Higher | Lower |
| Guest OS | Required | Not Required |
| Density | Lower | Higher |
| Security Boundary | Stronger | Weaker |

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Strong Isolation | Higher Resource Usage |
| Better Utilization | More Complexity |
| Multi-Tenancy | Resource Contention Risk |
| Flexibility | Operational Overhead |
| Scalability | Additional Management Layers |

---

## Interview Thinking

- Why was virtualization invented?
- What problems did virtualization solve?
- What is a hypervisor?
- Type 1 vs Type 2 hypervisor?
- Why does cloud computing depend on virtualization?
- Virtual Machines vs Containers?
- What is the noisy neighbor problem?
- Why does overcommitment create performance issues?
- How would you investigate a slow virtual machine?
- Why do cloud providers use virtualization?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Virtualization | Hardware Resource Abstraction |
| Virtual Machine | Software Defined Computer |
| Hypervisor | Virtualization Manager |
| Type 1 Hypervisor | Runs On Hardware |
| Type 2 Hypervisor | Runs On OS |
| Multi-Tenancy | Shared Infrastructure |
| Overcommitment | Allocate More Than Available |
| Noisy Neighbor | Workloads Affect Each Other |
| VM | Strong Isolation |
| Container | Lightweight Isolation |