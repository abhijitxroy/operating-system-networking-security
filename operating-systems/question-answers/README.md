

# Operating Systems Interview Questions And Answers

## Purpose

This section is not intended to be a collection of memorized answers.

The goal is to understand the engineering reasoning behind operating system concepts commonly discussed during interviews and production debugging.

---

## Question Categories

### Operating System Fundamentals

- Why were operating systems invented?
- What problems did operating systems solve?
- Why can't applications access hardware directly?
- What is the role of the kernel?
- Why does user space exist?

### Processes

- Process vs Program?
- Why were processes introduced?
- Why is process isolation important?
- What happens during fork()?
- What happens during exec()?
- What are zombie processes?
- What are orphan processes?

### Threads And Concurrency

- Process vs Thread?
- Why are threads faster than processes?
- What is a race condition?
- What is a mutex?
- What is a semaphore?
- What causes deadlocks?

### CPU Scheduling

- Why was CPU scheduling invented?
- FCFS vs Round Robin?
- What is starvation?
- What is priority inversion?
- Why is context switching expensive?
- How does Linux scheduling work?

### Memory Management

- Why was virtual memory invented?
- What is paging?
- What is a page fault?
- What is the TLB?
- What is swapping?
- What is the OOM Killer?

### File Systems

- Why were file systems invented?
- What is an inode?
- What is journaling?
- Why does inode exhaustion happen?
- How would you investigate storage issues?

### Production Troubleshooting

- How would you investigate high CPU usage?
- How would you investigate memory leaks?
- How would you investigate OOM events?
- How would you debug a deadlock?
- How would you investigate high I/O wait?
- Which Linux commands would you use first?

---

## Interview Philosophy

Strong operating system interviews are usually not testing definitions.

They are testing:

- Engineering reasoning
- Debugging ability
- Production awareness
- Tradeoff analysis
- Understanding of system behavior

Always understand:

- Why a feature was invented
- Which problem it solved
- What tradeoffs exist
- What breaks in production
- How engineers debug it

---

## Quick Revision

| Area | Priority |
|----------|----------|
| Processes | Critical |
| Threads | Critical |
| CPU Scheduling | Critical |
| Memory Management | Critical |
| Deadlocks | Critical |
| File Systems | High |
| Virtualization | High |
| Linux Internals | High |