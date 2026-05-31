

# MTU And MSS

## Why MTU And MSS Exist

Networks cannot transmit infinitely large packets.

Every network technology has limits.

Without limits:

```text
Large Packet
      ↓
Transmission Problems
      ↓
Network Instability
```

MTU and MSS exist to ensure efficient and reliable communication.

---

## The Engineering Problem

Suppose an application generates:

```text
100 KB Data
```

Can this be placed into a single packet?

No.

Networks require data to be split into manageable units.

Questions:

```text
How Large Can A Packet Be?
```

```text
How Much Application Data Can TCP Carry?
```

MTU and MSS answer these questions.

---

## What Is MTU?

MTU stands for:

```text
Maximum Transmission Unit
```

Definition:

```text
Maximum Packet Size
Allowed On A Network Link
```

Most Ethernet networks use:

```text
1500 Bytes
```

This is the most common MTU value.

---

## MTU Example

Ethernet:

```text
MTU = 1500 Bytes
```

Meaning:

```text
Packet Size
Must Not Exceed
1500 Bytes
```

Larger packets may be fragmented or dropped.

---

## What Is MSS?

MSS stands for:

```text
Maximum Segment Size
```

Definition:

```text
Maximum TCP Payload
```

MSS represents only application data.

It excludes:

- IP Header
- TCP Header

---

## MSS Calculation

Typical Ethernet:

```text
MTU = 1500
```

IPv4 Header:

```text
20 Bytes
```

TCP Header:

```text
20 Bytes
```

Calculation:

```text
1500 - 20 - 20
```

Result:

```text
MSS = 1460 Bytes
```

This is the most common MSS value.

---

## MTU vs MSS

| Concept | Meaning |
|----------|----------|
| MTU | Maximum Packet Size |
| MSS | Maximum TCP Payload |

Relationship:

```text
MTU
 ↓
Packet Size Limit

MSS
 ↓
TCP Data Limit
```

---

## Why Fragmentation Is Bad

If packets exceed MTU:

```text
Large Packet
      ↓
Fragmentation
      ↓
Additional Processing
```

Problems:

- Performance overhead
- Packet loss risk
- Increased latency

Modern systems generally avoid fragmentation.

---

## Path MTU Discovery

Different networks may have different MTU values.

Example:

```text
Network A = 1500
Network B = 1400
```

The sender must discover the smallest MTU along the path.

This process is called:

```text
Path MTU Discovery
```

---

## MTU Mismatch Problems

A common production issue.

Symptoms:

- Intermittent connectivity
- Slow applications
- Packet drops
- Hanging connections

MTU problems are often difficult to diagnose.

---

## VPN And Tunnel Considerations

VPNs add extra headers.

Example:

```text
Original Packet
      ↓
VPN Header Added
      ↓
Packet Size Increases
```

This can exceed MTU limits.

Many VPN issues involve MTU tuning.

---

## Kubernetes And Cloud Networking

MTU becomes important in:

- Kubernetes overlays
- VXLAN
- Service meshes
- VPN tunnels
- Cloud networking

Incorrect MTU values can cause subtle production failures.

---

## Production Impact

Engineers investigate MTU when seeing:

- Packet loss
- Connection stalls
- Performance degradation
- VPN instability
- Kubernetes networking issues

MTU problems are common in distributed systems.

---

## Useful Commands

Linux:

```bash
ip link show
```

```bash
ip addr
```

```bash
ping -M do -s 1472 HOST
```

Useful for MTU validation.

---

## Common Interview Questions

- What is MTU?
- What is MSS?
- MTU vs MSS?
- Why is Ethernet MTU usually 1500?
- How is MSS calculated?
- What is fragmentation?
- Why is fragmentation undesirable?
- What is Path MTU Discovery?
- Why do VPNs create MTU problems?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| MTU | Maximum Packet Size |
| MSS | Maximum TCP Payload |
| Ethernet MTU | 1500 Bytes |
| Common MSS | 1460 Bytes |
| Fragmentation | Packet Splitting |
| Path MTU Discovery | Find Smallest MTU |
| VPN Issue | Extra Headers |
| Kubernetes Networking | MTU Sensitive |
| Performance Impact | Packet Efficiency |
| Most Common Interview Question | MTU vs MSS |