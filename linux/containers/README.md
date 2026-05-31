

# Linux Containers

## Why Containers Were Invented

Before containers became popular, applications were commonly deployed in virtual machines.

Virtual machines solved important problems:

- Isolation
- Multi-tenancy
- Infrastructure sharing

However, they introduced new challenges:

- High resource consumption
- Slow startup times
- Larger operational overhead
- Lower workload density

Engineers wanted a way to isolate applications without running an entire operating system for every workload.

Containers were created to solve this problem.

---

## The Engineering Problem

Organizations wanted:

- Faster deployments
- Better resource utilization
- Consistent environments
- Portable workloads
- Strong isolation

Virtual machines provide isolation through virtualization.

Containers provide isolation through Linux kernel features.

```text
Application
      ↓
Container
      ↓
Linux Kernel
      ↓
Hardware
```

This removes the need for a separate guest operating system.

---

## Containers Are A Linux Story

Many engineers learn Docker before understanding Linux.

In reality, containers are built on Linux kernel capabilities.

The most important technologies are:

- Namespaces
- Cgroups
- Union File Systems
- Capabilities
- Seccomp

Docker, containerd, Podman and Kubernetes build on top of these Linux features.

---

## Namespaces

### Why They Exist

Processes need isolation.

Namespaces make a process believe it owns a dedicated environment.

Examples:

- Process namespace
- Network namespace
- Mount namespace
- User namespace
- PID namespace

Result:

```text
Container A
Sees Its Own World

Container B
Sees Its Own World
```

Even though both share the same kernel.

---

## Cgroups

### Why They Exist

Isolation alone is not enough.

A single workload could consume all resources.

Cgroups control:

- CPU
- Memory
- Disk I/O
- Network resources

Without cgroups, multi-tenant container platforms would be unstable.

---

## Why Containers Became Popular

Containers solved several operational problems.

### Environment Consistency

```text
Works On My Machine
        ↓
Container Image
        ↓
Works Everywhere
```

### Faster Deployment

Containers start significantly faster than virtual machines.

### Higher Density

More workloads can run on the same hardware.

### Better CI/CD Integration

Containers fit naturally into modern delivery pipelines.

---

## Containers vs Virtual Machines

| Area | Containers | Virtual Machines |
|----------|----------|----------|
| Startup Time | Fast | Slower |
| Resource Usage | Low | Higher |
| Guest OS | Not Required | Required |
| Density | Higher | Lower |
| Isolation | Kernel Based | Hypervisor Based |
| Portability | High | Moderate |

---

## Production Impact

Containers power:

- Kubernetes
- Cloud platforms
- CI/CD pipelines
- Platform engineering
- Microservices architectures
- AI/ML workloads

Modern infrastructure teams interact with containers almost daily.

---

## Common Production Failures

### Container OOM Kill

Symptoms:

- Container restarts
- Unexpected termination

Investigation:

```bash
docker inspect
kubectl describe pod
journalctl
```

### CPU Throttling

Symptoms:

- Slow application response
- High latency

Cause:

- Cgroup CPU limits

### Image Bloat

Symptoms:

- Slow deployments
- Large storage consumption

Investigation:

```bash
docker images
```

### Namespace Misconfiguration

Symptoms:

- Unexpected network behavior
- Access issues

Investigation:

```bash
ip netns
nsenter
```

---

## Linux Troubleshooting Commands

```bash
docker ps
docker stats
docker inspect
ctr containers list
crictl ps
systemctl status containerd
```

Useful for investigating container runtime issues.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Higher Density | Shared Kernel Risk |
| Faster Startup | Reduced Isolation |
| Simplicity | Additional Orchestration Complexity |
| Portability | Image Management Overhead |
| Resource Efficiency | Operational Complexity |

---

## Interview Thinking

- Why were containers invented?
- Why are containers lighter than virtual machines?
- What Linux features make containers possible?
- What problem do namespaces solve?
- What problem do cgroups solve?
- Containers vs Virtual Machines?
- Why does Kubernetes depend on containers?
- What causes container OOM kills?
- How would you investigate container resource issues?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Container | Isolated Linux Process |
| Namespace | Isolation Mechanism |
| Cgroup | Resource Control Mechanism |
| Container Image | Portable Application Package |
| Container Runtime | Executes Containers |
| OOM Kill | Memory Limit Exceeded |
| CPU Throttling | CPU Limit Enforcement |
| Docker | Container Platform |
| containerd | Container Runtime |
| Kubernetes | Container Orchestration Platform |