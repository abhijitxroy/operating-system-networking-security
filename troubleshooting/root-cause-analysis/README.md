

# Root Cause Analysis (RCA)

## Why Root Cause Analysis Exists

Restoring a service is not the same as solving a problem.

Many incidents appear resolved because symptoms disappear.

However:

```text
Symptom Fixed
      ↓
Root Cause Still Exists
      ↓
Incident Repeats
```

Root Cause Analysis exists to identify the actual reason a failure occurred and prevent recurrence.

---

## The Engineering Problem

Production incidents often involve multiple contributing factors.

Examples:

- Software bugs
- Infrastructure failures
- Configuration mistakes
- Human errors
- Capacity issues
- Dependency failures

The first visible failure is rarely the true root cause.

Engineers must investigate deeper.

---

## Symptoms vs Root Cause

One of the most important engineering concepts.

Example:

```text
Application Timeout
```

This is a symptom.

Potential root cause:

```text
Slow Database Query
        ↓
Connection Pool Exhaustion
        ↓
Application Timeout
```

Stopping at the symptom guarantees future incidents.

---

## What RCA Actually Does

Root Cause Analysis helps teams:

- Understand failures
- Prevent recurrence
- Improve systems
- Improve processes
- Reduce operational risk

The goal is learning, not blame.

---

## The Five Whys Technique

A simple RCA method.

Example:

```text
Why did the service fail?
```

Because requests timed out.

```text
Why did requests timeout?
```

Because database connections were exhausted.

```text
Why were connections exhausted?
```

Because a slow query held connections.

Continue until the underlying cause is identified.

---

## Timeline Analysis

Building a timeline is often critical.

Questions:

- When did the issue start?
- What changed?
- What failed first?
- What happened next?

Example:

```text
Deployment
     ↓
Increased Load
     ↓
Database Saturation
     ↓
Application Errors
```

Timelines frequently expose hidden relationships.

---

## Change Analysis

A large percentage of incidents involve change.

Examples:

- Deployments
- Configuration updates
- Infrastructure changes
- Security policy changes

Always investigate:

```text
What Changed?
```

before pursuing complex theories.

---

## Contributing Factors

Most incidents have multiple contributing factors.

Example:

```text
Software Bug
       +
Missing Monitoring
       +
Insufficient Capacity
       ↓
Production Incident
```

The root cause should not ignore contributing conditions.

---

## Production Impact

Effective RCA improves:

- Reliability
- Stability
- MTTR
- Monitoring quality
- Engineering knowledge

Weak RCA results in recurring incidents.

---

## Common RCA Failures

### Blame-Focused Analysis

Symptoms:

- Fear
- Limited learning

### Stopping At Symptoms

Symptoms:

- Repeated incidents

### Missing Evidence

Symptoms:

- Incorrect conclusions

### Ignoring System Design

Symptoms:

- Partial understanding

### Missing Corrective Actions

Symptoms:

- No long-term improvement

---

## RCA Workflow

```text
Collect Evidence
        ↓
Build Timeline
        ↓
Analyze Changes
        ↓
Identify Contributing Factors
        ↓
Determine Root Cause
        ↓
Define Corrective Actions
        ↓
Prevent Recurrence
```

---

## Corrective Actions

Strong RCA produces improvements.

Examples:

- Monitoring enhancements
- Capacity improvements
- Better testing
- Design changes
- Documentation updates
- Automation improvements

The output should improve the system.

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Deep Investigation | More Engineering Time |
| Faster Closure | Risk Of Missing Causes |
| Extensive Data Collection | Higher Operational Cost |
| Detailed RCA | Increased Effort |
| Strong Prevention | Additional Engineering Work |

---

## Interview Thinking

- What is Root Cause Analysis?
- Why is symptom fixing dangerous?
- What is the Five Whys technique?
- Why does timeline analysis matter?
- How would you perform RCA after an outage?
- Why should RCA avoid blame?
- What are contributing factors?
- How do you prevent recurring incidents?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| RCA | Identify Actual Failure Cause |
| Symptom | Visible Problem |
| Root Cause | Underlying Reason |
| Five Whys | Iterative Investigation Technique |
| Timeline Analysis | Sequence Of Events |
| Change Analysis | Investigate Recent Changes |
| Contributing Factor | Condition Supporting Failure |
| Corrective Action | Prevent Recurrence |
| MTTR | Mean Time To Recovery |
| Reliability Improvement | Primary RCA Outcome |