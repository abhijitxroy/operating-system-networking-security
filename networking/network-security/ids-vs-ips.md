

# IDS vs IPS

## Why IDS And IPS Exist

Firewalls control traffic using predefined rules.

Question:

```text
What If Malicious Traffic
Looks Like Normal Traffic?
```

Examples:

- Exploitation attempts
- Malware activity
- Port scanning
- Suspicious behavior

IDS and IPS help detect and prevent such threats.

---

## The Security Problem

Suppose an attacker sends:

```text
Malicious Request
      ↓
Allowed Port
      ↓
Application
```

A firewall may allow the traffic because the port itself is permitted.

Question:

```text
How Can Suspicious Activity
Be Detected?
```

IDS and IPS provide the answer.

---

## What Is IDS?

IDS stands for:

```text
Intrusion Detection System
```

Purpose:

```text
Monitor Traffic
      ↓
Detect Threats
      ↓
Generate Alerts
```

IDS identifies suspicious activity but does not block traffic.

---

## IDS High-Level Flow

```text
Network Traffic
        ↓
IDS
        ↓
Alert
```

Traffic continues flowing.

The IDS only reports potential threats.

---

## What Is IPS?

IPS stands for:

```text
Intrusion Prevention System
```

Purpose:

```text
Monitor Traffic
      ↓
Detect Threats
      ↓
Block Threats
```

IPS actively prevents malicious activity.

---

## IPS High-Level Flow

```text
Network Traffic
        ↓
IPS
        ↓
Allow Or Block
```

Traffic passes through the IPS.

---

## Detection Methods

### Signature-Based Detection

Compares traffic against known attack patterns.

Example:

```text
Known Malware Signature
```

Benefits:

- Fast
- Accurate for known threats

Limitations:

- Cannot detect unknown attacks

---

### Anomaly-Based Detection

Looks for unusual behavior.

Example:

```text
Normal Traffic Pattern
       ↓
Unexpected Activity
```

Benefits:

- Can identify unknown threats

Limitations:

- More false positives

---

## IDS vs IPS Comparison

| Feature | IDS | IPS |
|----------|----------|----------|
| Full Form | Intrusion Detection System | Intrusion Prevention System |
| Detect Threats | Yes | Yes |
| Block Threats | No | Yes |
| Traffic Path | Out Of Band | Inline |
| Alerting | Yes | Yes |
| Prevention | No | Yes |

---

## Common Deployment Model

```text
Internet
    ↓
Firewall
    ↓
IPS
    ↓
Servers
```

IDS may be deployed alongside the traffic path for monitoring.

---

## Production Usage

IDS and IPS are common in:

- Data centers
- Corporate networks
- Cloud environments
- Government systems
- Financial institutions
- Security operations centers

They provide an additional layer of defense.

---

## Common Production Failures

### False Positives

Symptoms:

- Legitimate traffic blocked

### False Negatives

Symptoms:

- Attack traffic missed

### Outdated Signatures

Symptoms:

- New threats undetected

### Performance Bottlenecks

Symptoms:

- Increased latency

---

## Common Tools

Examples:

- Snort
- Suricata
- Zeek

Widely used in enterprise environments.

---

## Common Interview Questions

- What is IDS?
- What is IPS?
- IDS vs IPS?
- Signature-based vs anomaly-based detection?
- Why can't firewalls stop every attack?
- What are false positives and false negatives?
- Where should an IPS be deployed?
- What security layer do IDS and IPS provide?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| IDS | Detect And Alert |
| IPS | Detect And Block |
| Signature Detection | Known Threat Matching |
| Anomaly Detection | Unusual Behavior Detection |
| IDS Placement | Monitoring Path |
| IPS Placement | Inline Traffic Path |
| False Positive | Legitimate Traffic Flagged |
| False Negative | Attack Missed |
| Main Benefit | Threat Visibility |
| Core Goal | Detect And Prevent Intrusions |