

# traceroute

## Why traceroute Matters

Sometimes a host is unreachable even though DNS works.

Question:

```text
Where Is Traffic Failing?

Which Network Device
Is Dropping Packets?
```

traceroute helps identify the path traffic takes through a network.

---

## What Is traceroute?

`traceroute` is a network diagnostic tool that shows the path packets travel to reach a destination.

Purpose:

```text
Source
  ↓
Router 1
  ↓
Router 2
  ↓
Router 3
  ↓
Destination
```

It reveals each hop between source and destination.

---

## The Engineering Problem

Suppose:

```text
Application Timeout
```

Question:

```text
Is The Destination Down?

Or Is Traffic Failing
Somewhere In Between?
```

traceroute helps answer this.

---

## How traceroute Works

The tool sends packets with gradually increasing:

```text
TTL
(Time To Live)
```

Example:

```text
TTL = 1
TTL = 2
TTL = 3
```

Each router decreases TTL.

When TTL reaches zero:

```text
Router Responds
```

This reveals the path.

---

## Basic Usage

```bash
traceroute google.com
```

Example output:

```text
1  Router-A
2  Router-B
3  Router-C
4  Destination
```

---

## Understanding Hops

Each line represents:

```text
One Network Hop
```

Example:

```text
Laptop
  ↓
Home Router
  ↓
ISP Router
  ↓
Cloud Network
  ↓
Destination
```

---

## Measuring Latency

traceroute also displays:

```text
Response Time Per Hop
```

Example:

```text
2 ms
10 ms
25 ms
```

Useful for identifying slow network segments.

---

## Common Results

### Successful Trace

```text
Destination Reached
```

Traffic path is visible.

---

### Asterisk (*)

Example:

```text
* * *
```

Possible causes:

- Router blocks responses
- Firewall filtering
- Temporary network issue

Not always a failure.

---

### Trace Stops Midway

Possible causes:

- Routing issue
- Firewall restriction
- Network outage

---

## Troubleshooting Scenarios

### Application Timeout

Question:

```text
How Far Does Traffic Travel?
```

Use:

```bash
traceroute <host>
```

---

### Cloud Connectivity Issue

Verify where traffic leaves:

```text
Corporate Network
      ↓
ISP
      ↓
Cloud Provider
```

---

### Routing Problems

Symptoms:

```text
Destination Unreachable
```

Traceroute often identifies the failing hop.

---

## traceroute vs ping

| Feature | ping | traceroute |
|----------|----------|----------|
| Connectivity Test | Yes | Yes |
| Path Visibility | No | Yes |
| Hop Analysis | No | Yes |
| Latency Per Hop | No | Yes |
| Routing Investigation | Limited | Excellent |

---

## Production Usage

Common uses:

- Routing analysis
- Connectivity debugging
- ISP investigations
- Cloud networking troubleshooting
- Performance analysis

It is often the second command used after ping.

---

## Limitations

Some routers:

```text
Do Not Respond
To Traceroute Requests
```

Therefore:

```text
Missing Hop
≠
Network Failure
```

Interpret results carefully.

---

## Common Interview Questions

- What is traceroute?
- How does traceroute work?
- What is TTL?
- What is a network hop?
- Why do asterisks appear?
- How do you troubleshoot routing issues?
- traceroute vs ping?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| traceroute | Path Discovery Tool |
| TTL | Time To Live |
| Hop | Intermediate Router |
| Purpose | Identify Traffic Path |
| Latency | Per-Hop Delay |
| Asterisks | No Response |
| Common Use | Routing Analysis |
| Often Used After | ping |
| Common Failure | Routing Problem |
| Core Goal | Find Where Traffic Stops |