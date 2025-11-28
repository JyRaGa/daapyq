
***

# Operating Systems Question Bank: Sorted by Syllabus Units

## Table of Contents

1. [Unit 1: Introduction to Operating Systems](#unit-1-introduction-to-operating-systems)
2. [Unit 2: Concurrent Processes \& CPU Scheduling](#unit-2-concurrent-processes--cpu-scheduling)
3. [Unit 3: Deadlock](#unit-3-deadlock)
4. [Unit 4: Memory Management](#unit-4-memory-management)
5. [Unit 5: I/O Management \& Disk Scheduling](#unit-5-io-management--disk-scheduling)
6. [Unit 6: Case Studies (Windows, Linux, Unix)](#unit-6-case-studies-windows-linux-unix)

***

## Unit 1: Introduction to Operating Systems

*Focus: OS Functions, Evolution, Structure, System Calls, Protection*

### Questions

* **Basic Concepts:**
    * Define the term operating system and also write various characteristics of an operating system.
    * What are the basic functions of an operating system? Explain each in brief.
    * What is the utility of having an operating system in a computer system architecture?
    * Identify key components of an operating system and their roles in system management.
    * Discuss the role of the operating system in process management, memory management, and storage management.
    * Briefly describe the two main categories of functions and services provided by an operating system and discuss how they differ.
* **Evolution \& Types:**
    * Differentiate between batch operating system and real-time operating system.
    * Give some application areas of batch operating system and real-time operating system.
    * Compare and contrast real-time and time-sharing operating systems with an example.
    * Write down the major difference between Real Time and Time-shared operating systems with a suitable example.
    * Differentiate between parallel and distributed systems. What are their advantages and disadvantages?
    * Describe Distributed Operating System and Network Operating System in detail along with their advantages and disadvantages.
    * What are the advantages of a multiprocessor system?
    * Differentiate between symmetric and asymmetric multiprocessing.
    * Explain why layered and microkernel architectures are more suitable for specific applications and environments.
    * Compare the role of an operating system in a distributed system vs. a centralized system, focusing on unique challenges.
* **System Structure \& Protection:**
    * Differentiate between kernel mode and user mode.
    * When power is first turned on, in which mode does a computer start and why?
    * What are system programs? Give an example.
    * What is the purpose of system programs?
    * Explain fork system call.
    * How is an interrupt different from a trap?
    * What is graceful degradation? How is it different from fault tolerance?
    * How does an operating system work as a resource manager and a virtual machine?
    * Explain monolithic operating system and microkernel architecture.

***

## Unit 2: Concurrent Processes \& CPU Scheduling

*Focus: Processes, Threads, IPC, Synchronization, CPU Scheduling Algorithms*

### Questions

* **Process Concepts:**
    * What is a Process? Explain PCB (Process Control Block) using a suitable example.
    * Explain the need for a Process Control Block (PCB).
    * Enumerate the various information that is stored in a Process Control Block (PCB).
    * What is a process control block and how does it facilitate context switching between processes?
    * Discuss different states of a process with the help of a state transition diagram.
    * What causes a process/thread to change state?
    * Differentiate between Multiprogramming and Multitasking.
    * Explain the difference between multiprogramming, multitasking, multiprocessing, and multi-threading systems.
    * What are the advantages of multiprogramming?
    * What are the advantages and disadvantages of multiprogramming?
* **Synchronization \& IPC:**
    * What is meant by inter-process communication? Explain the two fundamental models of inter-process communication (Message passing model and shared memory model).
    * List and describe various inter-process communication methods.
    * What are interacting processes? Explain any two methods of implementing interacting processes.
    * What are cooperating processes? What are the reasons that justify their existence?
    * **Critical Section \& Race Conditions:**
        * What is a race condition? Explain how a critical section avoids this condition.
        * Give an example of the arising of a race condition in concurrent processing.
        * What is the Critical Section problem? Mention the requirements to be satisfied by a solution to the critical section problem.
        * Elaborate on the term “critical section” in process synchronization with the help of a real-time example.
        * What are the properties which a data item should possess to implement a critical section?
        * Describe how the `compare_and_swap()` instruction can be used to provide mutual exclusion that satisfies the bounded-waiting requirement.
    * **Algorithms \& Problems:**
        * Explain Peterson's solution.
        * In Peterson's algorithm, what should be the predicate P in `while (P)` to guarantee mutual exclusion?
        * Explain why interrupts are not appropriate for implementing synchronization primitives in multiprocessor systems.
        * Describe a solution to the Dining philosopher problem so that no races arise.
        * Illustrate the Producer-Consumer problem and explain how semaphores solve it.
        * Explain the bounded buffer problem and its solution using semaphores.
        * What is the Readers-Writers problem? Explain how synchronization is achieved.
        * Provide a solution for the Readers/Writers problem using semaphores with no busy waiting.
    * **Semaphores:**
        * What are semaphores?
        * Define Race condition. How does the `signal()` operation associated with monitors differ from the corresponding operation for semaphores?
* **CPU Scheduling:**
    * Explain various types of schedulers available and their differences.
    * Differentiate between Long-term, short-term, and medium-term schedulers.
    * What is a medium-term scheduler? How do its functions differ from the long-term scheduler?
    * What are the objectives of CPU scheduling?
    * Differentiate between preemptive and non-preemptive scheduling.
    * What is preemption in process scheduling? What are its drawbacks?
    * Compare pre-emptive and non-pre-emptive scheduling methods and recommend one for a high-performance computing environment.
    * **Algorithms (FCFS, SJF, Round Robin, Priority):**
        * Explain the differences in how FCFS, Round Robin, and Multiple feedback queues scheduling algorithms discriminate in favor of short processes.
        * What happens if the time allocated in a Round Robin Scheduling is very large or very low?
        * Explain the Convoy effect with an example.
        * Suggest a modification to the SJF algorithm to overcome starvation.
        * Differentiate between Multilevel Queue Scheduling and Multilevel Feedback Queue Scheduling algorithms.
        * How is scheduling done in multiprocessor systems?


### Problems

**Problem 1: Scheduling Metrics**
Consider the following set of processes:


| Process | Arrival Time | Burst Time | Priority |
| :--: | :--: | :--: | :--: |
| 1 | 0 | 3 | 5 |
| 2 | 1 | 1 | 2 |
| 3 | 3 | 4 | 1 |
| 4 | 5 | 2 | 3 |
| 5 | 5 | 1 | 4 |

* Draw Gantt charts to illustrate the execution.
* Find the average waiting time and average turnaround time for **Round-Robin** and **Preemptive Priority** scheduling.

**Problem 2: General Scheduling**
Consider a set of processes with the following details:


| Process | CPU burst time | Arrival time | Priority |
| :-- | :-- | :-- | :-- |
| P1 | 5 | 0 | 2 |
| P2 | 15 | 1 | 3 |
| P3 | 10 | 2 | 1 |

* Calculate average waiting time, average turnaround time, and system throughput using **FCFS**, **Preemptive SJF**, **Preemptive Priority**, and **Round Robin** algorithms.

**Problem 3: Uniprocessor System**


| Process | Priority | CPU request | Arrival Time |
| :-- | :-- | :-- | :-- |
| P1 | 10 (highest) | 20 sec | 00:00:05 |
| P2 | 9 | 10 sec | 00:00:03 |
| P3 | 8 (lowest) | 15 sec | 00:00:00 |

* What are the turnaround times of P1, P2, and P3 using **preemptive** and **non-preemptive** scheduling respectively?

***

## Unit 3: Deadlock

*Focus: Characterization, Prevention, Avoidance, Detection, Recovery*

### Questions

* **Fundamentals:**
    * What is a deadlock?
    * List the four conditions that raise a deadlock (necessary conditions).
    * What are the necessary conditions to hold a deadlock in a system?
    * What are the schemes used in the operating system to handle deadlocks?
    * Evaluate the pros and cons of deadlock detection versus avoidance strategies.
    * Explain the trade-offs between deadlock avoidance algorithms and deadlock detection techniques in high-resource systems.
    * Explain the implications of deadlock recovery strategies on system performance.
* **Prevention \& Avoidance:**
    * What are the conditions that must hold for deadlock prevention?
    * Describe the Banker's algorithm for safe allocation.
    * Explain Banker's deadlock-avoidance algorithm with an illustration.
    * Explain the significance of calculating the Matrix 'Need' to determine a safe/unsafe state with the help of an example.
    * Explain the Resource-Allocation-Graph algorithm for deadlock avoidance.
* **Detection:**
    * What is the optimistic assumption made in the deadlock-detection algorithm? How can this assumption be violated?
    * Show that a system is deadlock-free if the maximum need of each process is between one and m resources, and the sum of all maximum needs is 'm+n'.


### Problems

**Problem 1: Banker's Algorithm (Safe State)**
Given the following system snapshot:


| Process | Allocation (A, B, C) | Request (A, B, C) | Available (A, B, C) |
| :-- | :-- | :-- | :-- |
| P0 | 0, 1, 0 | 0, 0, 0 | 0, 0, 0 |
| P1 | 2, 0, 0 | 2, 0, 2 |  |
| P2 | 3, 0, 3 | 0, 0, 0 |  |
| P3 | 2, 1, 1 | 1, 0, 0 |  |
| P4 | 0, 0, 2 | 0, 0, 2 |  |

* Is the system in a deadlock state?
* If process P2 makes an additional request, what will be the effect on the system?

**Problem 2: Resource Allocation**
Given a total of 10 units of a resource type and a safe state shown below:


| Process | Used | Max Need |
| :-- | :-- | :-- |
| P1 | 2 | 5 |
| P2 | 1 | 6 |
| P3 | 2 | 6 |
| P4 | 1 | 2 |
| P5 | 1 | 4 |

* Should process 2 be granted a request of 2 additional resources?
* Is the system in an unsafe state? Explain.

***

## Unit 4: Memory Management

*Focus: Paging, Segmentation, Virtual Memory, Page Replacement*

### Questions

* **Basics:**
    * List the major activities of an operating system with respect to memory management.
    * On a system with 224 bytes of total memory and fixed partitions, all of size 65536 bytes, how many bits must the limit register have?
    * Differentiate between Internal and External Fragmentation.
    * Given memory partitions, how would First-fit, Best-fit, and Worst-fit algorithms place processes of different sizes? Which algorithm makes the most efficient use of memory?
    * How does page size determine the size of internal fragmentation? Can this problem be solved?
* **Paging \& Segmentation:**
    * Compare and contrast paging and segmentation.
    * Why is paging faster than segmentation?
    * Compare paging and segmentation in terms of memory management efficiency.
    * Why is segmented paging important?
    * What are the different pieces of the virtual address in a segmented paging system?
    * Why are page sizes always a power of 2?
    * For a computer system with a 32-bit logical address and 4KB page size supporting up to 512MB of physical memory, how many entries will be there in a conventional single-level page table and in an inverted page table?
    * What is the purpose of paging the page tables?
* **Virtual Memory \& Thrashing:**
    * Define Virtual Memory.
    * What is meant by locality of reference?
    * What is Demand Paging?
    * Which page size is optimal in demand paging, small page size or large page size? Give reasons.
    * What is Thrashing? How does the system detect and eliminate it?
    * How is Thrashing related to degree of multiprogramming and page fault rate? Explain with a graph.
    * What is a working set model? List the parameters that help in deciding the size of the working set window.
    * Why are Translation Look-aside Buffers (TLBs) important?
    * In a paging scheme with a TLB, what is the effective access time if the TLB hit ratio is 90%?


### Problems

**Problem 1: Paging Performance**

* Consider a system with a 2-level paging scheme.
* Regular memory access takes 150 ns.
* Serving a page fault takes 8 ms.
* TLB hit ratio is 90%.
* Page fault rate is one in every 10,000 instructions.
* **Calculate:** Average instruction execution time.

**Problem 2: Page Replacement**

* Given a program with a reference string of pages and three available frames in memory.
* **Calculate:** How many page faults will occur using **FIFO**, **LRU**, and **Optimal** page replacement algorithms?

**Problem 3: Segmentation**
Given the following Segment Table:


| Segment | Base | Length |
| :-- | :-- | :-- |
| 0 | 219 | 600 |
| 1 | 230 | 014 |
| 2 | 90 | 100 |
| 3 | 1327 | 580 |
| 4 | 1952 | 96 |

* **Calculate:** The physical addresses for given logical addresses. Explain in detail.

***

## Unit 5: I/O Management \& Disk Scheduling

*Focus: Disk Scheduling, File Systems, I/O Buffering*

### Questions

* **Disk Management:**
    * What is meant by seek time and rotational latency in the case of a disk drive?
    * Explain constant linear velocity and constant angular velocity concepts of a disk drive.
    * Compare the functionalities of FCFS, CSCAN, SSTF, and C-LOOK disk scheduling algorithms.
    * Discuss various issues involved in selecting an appropriate disk scheduling algorithm.
    * Compare the throughput of RAID level 5 and RAID level 1 for read operations on a single block and multiple continuous blocks.
    * Explain the organization and role of I/O buffering in the operating system.
    * Explain in detail about Device Management policies.
* **File Systems:**
    * Discuss the Contiguous, Linked, and Indexed file allocation schemes. Which allocation scheme will minimize the amount of space required in the directory structure and why?
    * Evaluate the strengths and weaknesses of different file access methods (sequential, indexed, direct) in cloud storage systems.
    * What type of conflicts can arise in simultaneous accessing a file by multiple users and how can they be resolved?
    * What criteria should be adopted for choosing the type of file organization?
    * Explain various file access methods with suitable examples.
    * Briefly discuss the various directory structures.
    * Describe any two methods of free space management.
    * Enlist different file operations.
    * What is Spooling? How does it help in increasing the performance of the system?
    * Explain why logging metadata updates ensures the recovery of a file system after a crash.


### Problems

**Problem 1: Disk Scheduling**

* **Situation:** A disk read/write head is at track 45 (of 0-255) moving in the positive direction.
* **Requests:** 40, 67, 11, 240, ...
* **Calculate:** The order of service and total head movement for **C-SCAN**.
* **Calculate:** Total head movement for **Shortest Seek Time First (SSTF)**.

**Problem 2: Disk Arm Movement**

* Suppose a moving head disk with 200 tracks is currently serving a request for track 143.
* **Calculate:** Total head movement for **FCFS**, **SSTF**, and **C-SCAN** scheduling schemes.

***

## Unit 6: Case Studies(Windows, Linux, Unix)

*Focus: Windows, Linux, Unix & their differences*

* Compare process management in Windows, Linux, and Unix. Which operating system would be more efficient for real-time applications? Justify your answer.
* Explain fork system call. (Specific to Unix/Linux process creation)
*Explain monolithic operating system and microkernel architecture. (Key architectural difference between Linux and Windows NT kernels)
*Explain why layered and microkernel architectures are more suitable for specific applications and environments.
*What is the utility of having an operating system in a computer system architecture?
