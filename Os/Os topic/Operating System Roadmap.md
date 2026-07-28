
# Operating System Roadmap

## 1. Introduction to Operating Systems ⭐⭐⭐

Learn:

- What is an Operating System?
- Goals of an OS
- Functions of an OS
- Types of Operating Systems
    - Batch OS
    - Multiprogramming OS
    - Multitasking OS
    - Multiprocessing OS
    - Distributed OS
    - Real-Time OS (Hard & Soft)
    - Network OS

Interview Questions

- What is an Operating System?
- Why do we need an OS?
- Difference between Multiprogramming and Multitasking.
- Difference between Process and Program.
- Kernel vs Operating System.

---

# 2. Process Management ⭐⭐⭐⭐⭐ (Most Important)

Learn:

- Process
- Process States
- Process Control Block (PCB)
- Context Switching
- Threads
- User Thread vs Kernel Thread
- Multithreading
- Process Creation
- Process Termination

Interview Questions

- What is a Process?
- Explain Process Life Cycle.
- What is PCB?
- What is Context Switching?
- What is a Thread?
- Process vs Thread.

---

# 3. CPU Scheduling ⭐⭐⭐⭐⭐

Algorithms:

- FCFS
- SJF
- SRTF
- Priority Scheduling
- Round Robin
- Multilevel Queue
- Multilevel Feedback Queue

Learn:

- Waiting Time
- Turnaround Time
- Response Time
- Throughput
- CPU Utilization

Numericals

- Gantt Chart
- Average Waiting Time
- Average Turnaround Time

Interview Questions

- Why is SJF optimal?
- Why is Round Robin used?
- Difference between Preemptive and Non-Preemptive Scheduling.

---

# 4. Synchronization ⭐⭐⭐⭐⭐

Learn:

- Critical Section
- Race Condition
- Mutual Exclusion
- Semaphore
- Mutex
- Monitor
- Spinlock
- Producer Consumer
- Reader Writer
- Dining Philosophers
- Sleeping Barber

Interview Questions

- What is Race Condition?
- Semaphore vs Mutex.
- Binary Semaphore vs Counting Semaphore.
- Why is synchronization needed?

---

# 5. Deadlock ⭐⭐⭐⭐⭐

Learn:

- Deadlock
- Coffman Conditions
- Resource Allocation Graph
- Deadlock Prevention
- Deadlock Avoidance
- Banker's Algorithm
- Deadlock Detection
- Recovery

Interview Questions

- What is Deadlock?
- Four Necessary Conditions.
- Explain Banker's Algorithm.
- Prevention vs Avoidance.

---

# 6. Memory Management ⭐⭐⭐⭐⭐

Learn:

- Logical Address
- Physical Address
- Swapping
- Paging
- Segmentation
- Fragmentation
- Virtual Memory
- Demand Paging
- Thrashing

Interview Questions

- Paging vs Segmentation.
- Internal vs External Fragmentation.
- What is Virtual Memory?
- Why is Paging used?

---

# 7. Page Replacement Algorithms ⭐⭐⭐⭐

Algorithms:

- FIFO
- LRU
- Optimal
- Second Chance
- Clock Algorithm

Numericals

- Page Fault Calculation

Interview Questions

- Why is LRU better than FIFO?
- Belady's Anomaly.
- What is Page Fault?

---

# 8. Disk Scheduling ⭐⭐⭐⭐

Algorithms:

- FCFS
- SSTF
- SCAN
- C-SCAN
- LOOK
- C-LOOK

Numericals

- Head Movement Calculation

Interview Questions

- SCAN vs LOOK.
- Why is SSTF not always preferred?

---

# 9. File System ⭐⭐⭐⭐

Learn:

- File
- Directory
- File Allocation
    - Contiguous
    - Linked
    - Indexed
- Free Space Management
- File Access Methods

Interview Questions

- Contiguous vs Linked Allocation.
- Indexed Allocation advantages.
- What is an Inode?

---

# 10. I/O Management ⭐⭐⭐

Learn:

- Interrupt
- Polling
- DMA
- Buffering
- Caching
- Spooling

Interview Questions

- Interrupt vs Polling.
- What is DMA?
- What is Spooling?

---

# 11. Virtual Memory ⭐⭐⭐⭐

Learn:

- Demand Paging
- TLB
- Address Translation
- Working Set
- Thrashing

Interview Questions

- Why is TLB used?
- Explain Address Translation.
- What is Thrashing?

---

# 12. System Calls ⭐⭐⭐

Learn:

- fork()
- exec()
- wait()
- exit()
- open()
- close()
- read()
- write()

Interview Questions

- What are System Calls?
- fork() vs exec().
- User Mode vs Kernel Mode.

---

# 13. Security & Protection ⭐⭐⭐

Learn:

- Authentication
- Authorization
- Access Control
- Protection Ring
- Privileged Instructions

Interview Questions

- Authentication vs Authorization.
- Kernel Mode vs User Mode.

---

# 14. Miscellaneous Important Topics ⭐⭐⭐

- Boot Process
- Kernel
- Shell
- Monolithic Kernel
- Microkernel
- Hybrid Kernel
- Device Drivers
- Interrupt Handling
- IPC
    - Shared Memory
    - Pipes
    - Message Queues
    - Sockets

---

# 15. Important Comparisons (Very Frequently Asked)

|Topic|Comparison|
|---|---|
|Process|Thread|
|Program|Process|
|Semaphore|Mutex|
|Paging|Segmentation|
|Internal|External Fragmentation|
|Deadlock|Starvation|
|User Thread|Kernel Thread|
|FCFS|SJF|
|SCAN|C-SCAN|
|Monolithic|Microkernel|
|Interrupt|Polling|
|User Mode|Kernel Mode|
|Logical Address|Physical Address|
|Multiprogramming|Multitasking|
|Concurrency|Parallelism|
|Blocking|Non-blocking|

---

# Numericals to Practice

- CPU Scheduling
- Banker's Algorithm
- Page Replacement
- Disk Scheduling
- Address Translation
- Paging
- Segmentation

---

# OS Interview Questions (Top 30)

1. What is an Operating System?
2. What is a Process?
3. Process vs Thread.
4. What is Context Switching?
5. What is PCB?
6. Explain Process States.
7. What is Scheduling?
8. FCFS vs SJF.
9. What is Round Robin?
10. What is Critical Section?
11. Race Condition?
12. Semaphore vs Mutex.
13. What is Deadlock?
14. Four Deadlock Conditions.
15. Banker's Algorithm.
16. Paging vs Segmentation.
17. Virtual Memory.
18. Thrashing.
19. FIFO vs LRU.
20. Belady's Anomaly.
21. SCAN vs LOOK.
22. What is DMA?
23. Interrupt vs Polling.
24. System Calls.
25. fork() vs exec().
26. User Mode vs Kernel Mode.
27. Authentication vs Authorization.
28. Monolithic vs Microkernel.
29. What is TLB?
30. Explain Address Translation.

## Recommended Study Order (Best for Placements)

1. Introduction to OS
2. Process & Thread
3. CPU Scheduling
4. Synchronization
5. Deadlock
6. Memory Management
7. Virtual Memory
8. Page Replacement
9. File Systems
10. Disk Scheduling
11. System Calls
12. I/O Management
13. Security & Protection
14. Miscellaneous Concepts