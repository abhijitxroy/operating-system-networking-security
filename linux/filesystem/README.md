

# Linux File System

## Why Linux File Systems Matter

Most engineers interact with files every day.

Applications, databases, containers, logs, configurations, executables, and system services all ultimately depend on the Linux file system.

Many production incidents that appear to be application problems are actually storage or filesystem problems.

Understanding the Linux filesystem is therefore a production engineering skill rather than an operating system theory topic.

---

## The Engineering Problem

Applications need a predictable way to:

- Store data
- Retrieve data
- Organize information
- Manage permissions
- Recover after failures

Storage devices only understand blocks and sectors.

The filesystem acts as the abstraction layer between applications and physical storage.

```text
Application
      ↓
Linux File System
      ↓
Storage Layer
      ↓
Disk / SSD / NVMe
```

---

## Why Linux Uses A Hierarchical Structure

Instead of assigning drive letters like some operating systems, Linux organizes everything under a single root directory.

```text
/
├── bin
├── boot
├── dev
├── etc
├── home
├── proc
├── tmp
├── usr
└── var
```

This provides:

- Consistency
- Simplicity
- Flexible storage mounting
- Better administration

---

## Important Directories Engineers Must Know

### /etc

System configuration.

Examples:

- Application configuration
- Service configuration
- Network configuration

### /var

Frequently changing data.

Examples:

- Logs
- Databases
- Cache files

### /home

User data.

### /tmp

Temporary files.

### /proc

Virtual filesystem exposing kernel and process information.

### /usr

Applications, libraries and utilities.

---

## Inodes: The Concept Most Engineers Discover During Production Incidents

Linux does not directly store filenames with file contents.

Files are represented through inodes.

An inode stores:

- Ownership
- Permissions
- Timestamps
- Block mappings
- Metadata

Many engineers first learn about inodes after a production outage.

Example:

```text
Disk Space Available
But New Files Cannot Be Created
```

Root cause:

```text
Inodes Exhausted
```

---

## Mount Points

Linux treats storage devices as mounted filesystems.

Example:

```text
/dev/nvme0n1
        ↓
     Mounted
        ↓
      /data
```

Applications do not need to know where storage physically exists.

They access files through mount points.

---

## Production Impact

Filesystem behavior affects:

- Database performance
- Application startup time
- Container performance
- Log retention
- Backup strategies
- Disaster recovery

Storage bottlenecks often appear as application latency problems.

---

## Common Production Failures

### Disk Full

Symptoms:

- Applications fail to write
- Services stop unexpectedly
- Database errors

Investigation:

```bash
df -h
```

### Inode Exhaustion

Symptoms:

- Free space exists
- File creation fails

Investigation:

```bash
df -i
```

### Large Log Files

Symptoms:

- Rapid disk consumption

Investigation:

```bash
du -sh *
find /var/log -type f
```

### Mount Failures

Symptoms:

- Missing data
- Application startup failures

Investigation:

```bash
mount
lsblk
```

---

## Linux Troubleshooting Commands

### Disk Usage

```bash
df -h
```

### Directory Usage

```bash
du -sh *
```

### Inode Usage

```bash
df -i
```

### Block Devices

```bash
lsblk
```

### Mounted Filesystems

```bash
mount
```

### Open Files

```bash
lsof
```

---

## Engineering Tradeoffs

| Goal | Tradeoff |
|----------|----------|
| Reliability | Additional Metadata Overhead |
| Journaling | Extra Writes |
| Performance | Reduced Safety |
| Compression | CPU Consumption |
| Snapshots | Additional Storage Usage |

---

## Interview Thinking

- Why does Linux use a hierarchical filesystem?
- What is an inode?
- Why can a disk have free space but still reject file creation?
- What is a mount point?
- Why is /proc special?
- How would you investigate a full filesystem?
- How would you investigate inode exhaustion?
- Why do databases care about storage performance?

---

## Quick Revision

| Concept | Key Idea |
|----------|----------|
| Root Directory | Starting Point Of Filesystem |
| /etc | Configuration Files |
| /var | Variable Application Data |
| /proc | Kernel And Process Information |
| Inode | File Metadata Structure |
| Mount Point | Filesystem Attachment Location |
| df -h | Disk Usage |
| df -i | Inode Usage |
| lsblk | Storage Devices |
| lsof | Open Files |