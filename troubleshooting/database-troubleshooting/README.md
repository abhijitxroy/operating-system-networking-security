# Database Troubleshooting

## Why Database Troubleshooting Exists

Databases sit on the critical path of most applications.

When databases become slow or unavailable:

- APIs fail
- Applications timeout
- Transactions stop
- Customer impact increases rapidly

Database troubleshooting exists to identify the real bottleneck before it becomes a major outage.

---

## The Engineering Problem

Applications often appear to be the source of failures.

However the underlying issue may actually be:

- Slow queries
- Lock contention
- Connection exhaustion
- Resource starvation
- Replication lag
- Storage bottlenecks

```text
Application Timeout
        ↓
Database Symptom
        ↓
Actual Root Cause
```

Engineers must investigate beyond the visible symptom.

---

## Common Database Failure Domains

### Query Performance

Poorly optimized queries.

### Connections

Exhausted connection pools.

### Locking

Concurrent transactions competing for resources.

### Replication

Primary and replica synchronization issues.

### Storage

Disk latency and capacity problems.

### Infrastructure

CPU, memory and network bottlenecks.

---

## A Practical Investigation Workflow

```text
Identify Impact
      ↓
Check Database Health
      ↓
Review Slow Queries
      ↓
Review Connections
      ↓
Review Locks
      ↓
Review Resources
      ↓
Find Root Cause
```

---

## Query Troubleshooting

Many incidents originate from inefficient queries.

Common symptoms:

- High latency
- Increased CPU usage
- Timeouts

Investigation:

- Query execution plans
- Slow query logs
- Missing indexes
- Full table scans

Always verify whether performance problems originate from workload changes.

---

## Lock Contention Troubleshooting

Concurrent workloads can block each other.

Symptoms:

- Hanging transactions
- Slow responses
- Application timeouts

Investigation:

- Active locks
- Blocking sessions
- Long-running transactions

Locking issues often appear as application instability.

---

## Connection Troubleshooting

Applications communicate through connections.

Common failures:

- Connection exhaustion
- Pool misconfiguration
- Idle connection accumulation

Symptoms:

- Connection errors
- Intermittent failures
- Request backlog

---

## Replication Troubleshooting

Distributed databases depend on synchronization.

Common issues:

- Replication lag
- Replica inconsistency
- Failover problems

Symptoms:

- Stale reads
- Data inconsistency
- Recovery delays

---

## Resource Troubleshooting

Database performance is heavily influenced by infrastructure.

Review:

- CPU utilization
- Memory pressure
- Disk IOPS
- Network latency

A database issue may actually be a platform issue.

---

## Production Impact

Database incidents affect:

- Application availability
- Transaction processing
- Revenue
- Customer experience
- Platform stability

Because databases are central dependencies, failures often have large blast radii.

---

## Common Production Failures

### Slow Queries

Symptoms:

- Increased latency
- Timeout errors

### Missing Indexes

Symptoms:

- Full table scans
- High CPU usage

### Connection Pool Exhaustion

Symptoms:

- Request failures
- Service instability

### Deadlocks

Symptoms:

- Transaction failures
- Application errors

### Replication Lag

Symptoms:

- Inconsistent reads
- Delayed updates

---

## Investigation Mindset

```text
Symptom
   ↓
Query Analysis
   ↓
Lock Analysis
   ↓
Resource Analysis
   ↓
Dependency Analysis
   ↓
Root Cause
```

Avoid assuming the database is the problem simply because it is visible in the failure path.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Faster Queries | More Index Storage |
| Strong Consistency | Reduced Performance |
| High Availability | Increased Complexity |
| Large Connection Pools | More Resource Usage |
| Rich Monitoring | Additional Cost |

---

## Interview Thinking

- How would you troubleshoot a slow database?
- What causes lock contention?
- How would you investigate connection exhaustion?
- Why do missing indexes hurt performance?
- How would you analyze a slow query?
- What causes replication lag?
- Database issue vs application issue?
- How would you perform database RCA?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Database Troubleshooting | Performance And Availability Investigation |
| Slow Query | Common Performance Bottleneck |
| Index | Query Optimization Mechanism |
| Lock Contention | Concurrent Resource Competition |
| Connection Pool | Database Access Management |
| Deadlock | Circular Transaction Waiting |
| Replication Lag | Synchronization Delay |
| Query Plan | Execution Strategy |
| Blast Radius | Scope Of Impact |
| RCA | Root Cause Identification |