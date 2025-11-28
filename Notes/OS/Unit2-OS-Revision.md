## Processes, PCB, and states

A **process** is a program in execution with its own address space, resources, and execution context (registers, PC, stack, etc.). The OS represents each process using a **Process Control Block (PCB)**, which is essential for context switching and scheduling.

- **Need for PCB:** Without PCB, the OS could not save/restore a process’s state on a context switch, nor track its resources, scheduling info, or status.  
- **Typical PCB fields:** PID, process state (new/ready/running/waiting/terminated), program counter, CPU registers, stack pointer, memory pointers (page table base), open file table, CPU scheduling info (priority, CPU burst), accounting info (CPU time used), and I/O status.
- **Process states:** new → ready → running → waiting (blocked) → ready → terminated; sometimes suspended-ready / suspended-blocked are added.
- **Causes of state change:**  
  - ready → running: scheduler dispatches.  
  - running → ready: preemption (time quantum expired, higher priority ready).  
  - running → waiting: I/O request, wait on event/semaphore.  
  - waiting → ready: I/O completion or event/signal.  
  - running → terminated: normal exit or error.  

- **Multiprogramming:** Multiple processes in memory; OS switches between them to keep CPU busy → aims to maximize CPU utilization.
- **Multitasking (time-sharing):** Multiprogramming with rapid preemption to give interactive responsiveness to many users/programs.  
- **Multiprocessing:** More than one CPU; parallel execution on shared memory system.  
- **Multithreading:** Multiple threads (lightweight processes) within one process share address space but have separate PC and stack.  
- **Advantages of multiprogramming:** Better CPU and I/O utilization, higher throughput.  
- **Disadvantages:** More complex OS design; higher overhead for scheduling and memory management; increased chance of deadlocks and race conditions.  

***

## IPC, cooperating processes, and critical section basics

Processes interact via **Inter-Process Communication (IPC)** to share data and coordinate actions. IPC models and cooperating processes are central to Unit 2.

- **IPC models:**  
  - **Message passing:** Processes communicate by sending and receiving messages via OS primitives (send/receive), using direct (process to process) or indirect (mailboxes/ports) addressing; useful for distributed systems and no shared memory.
  - **Shared memory:** Processes share a region of memory and use synchronization (locks, semaphores) to coordinate access; very fast for large data exchange but requires careful synchronization.

- **Interacting/cooperating processes:** Two or more processes that can affect each other’s execution or share data; reasons include information sharing (shared DB), computation speedup (divide work), modularity (pipeline), and convenience (separate UI and worker).
- **Common IPC methods:** Shared memory segments, pipes, message queues, sockets, signals, remote procedure calls (RPC).  
- **Race condition:** Situation where outcome depends on the non-deterministic interleaving of concurrent accesses to shared data; arises when at least one write occurs without proper synchronization.
- **Critical section:** Code region where shared data is accessed/updated; must be executed atomically by one process/thread at a time to avoid race conditions.

- **Critical section problem requirements:** Any correct solution must ensure  
  - **Mutual exclusion:** At most one process in critical section (CS) at any time.  
  - **Progress:** If no process is in CS, some waiting process must be able to enter; decision cannot be postponed indefinitely.  
  - **Bounded waiting:** There is a limit on how many times other processes can enter CS after a process has requested to enter, before it is allowed in (no starvation).

- **Properties a “data item/lock” should have for CS:** Supports atomic read–modify–write, visible to all competing processes, and used in such a way that the algorithm satisfies mutual exclusion, progress, and bounded waiting.  

***

## Synchronization algorithms, semaphores, and classical problems

Synchronization mechanisms and classical problems (Peterson, Dining Philosophers, Producer–Consumer, Readers–Writers) are core exam topics.

- **Peterson’s solution (two processes):**  
  - Uses shared variables: `flag` (intention to enter CS) and `turn` (whose turn).  
  - Process i: set `flag[i]=true; turn=j;` then wait while `flag[j]==true && turn==j`; once loop exits, enter CS; on exit set `flag[i]=false`.
  - Predicate `P` in `while (P)` is typically `(flag[j] && turn == j)` to guarantee mutual exclusion and bounded waiting.

- **Why interrupts are not suitable for synchronization in multiprocessors:**  
  - Disabling interrupts on one CPU only prevents preemption there; other CPUs can still run and access the same shared data concurrently, so race conditions remain.
  - Global disabling on all CPUs would be highly inefficient, hurt responsiveness, and is complex to implement; modern systems instead use atomic instructions (test-and-set, compare-and-swap) and locks.

- **Hardware instructions (compare_and_swap):**  
  - `compare_and_swap(addr, expected, new)` atomically compares the value at `addr` with `expected`; if equal, writes `new` and returns old value; otherwise just returns old value.
  - For mutual exclusion: spin in a loop while the CAS indicates the lock is held; when it returns “unlocked” you acquire the lock; proper design of lock/unlock and queueing can ensure **mutual exclusion, progress, and bounded waiting**.  

- **Semaphores:**  
  - Integer variable with two atomic operations: `wait(P)` decrements and may block if negative; `signal(V)` increments and may wake a waiting process.
  - **Binary semaphore (mutex):** values 0/1; used for mutual exclusion.  
  - **Counting semaphore:** value ≥ 0; counts available instances of a resource.  
  - **Race condition vs monitor `signal()`:** In semaphores, `signal()` simply increments and may wake an arbitrary waiting process; if misused (extra/missing signals) can cause lost wakeups or deadlock; in monitors, `signal()` wakes exactly one waiting thread on that condition and control rules (like Hoare vs Mesa semantics) define whether signaller or signalled runs first, with the monitor guaranteeing mutual exclusion.

- **Dining Philosophers problem:**  
  - K philosophers alternate thinking/eating; need two chopsticks (shared resources) to eat; naive solution leads to deadlock and starvation.
  - Typical semaphore solution: each chopstick = binary semaphore; philosophers use `wait(left); wait(right); eat; signal(left); signal(right);`.  
  - To avoid deadlock: for example allow only **N−1 philosophers** to try to pick up chopsticks at once (room semaphore), or impose an ordering (one philosopher picks right first, others left first).

- **Producer–Consumer / Bounded Buffer:**  
  - Producer inserts items into a finite buffer; consumer removes; must avoid overfill and underflow.
  - Semaphores:  
    - `mutex` (binary) for mutual exclusion on buffer.  
    - `empty` (counting) = number of empty slots.  
    - `full` (counting) = number of filled slots.
  - Producer: `wait(empty); wait(mutex); add item; signal(mutex); signal(full);`.  
  - Consumer: `wait(full); wait(mutex); remove item; signal(mutex); signal(empty);`.  

- **Readers–Writers problem (no busy waiting):**  
  - Readers can access shared object concurrently; writers need exclusive access.
  - Use semaphores and integer `readcount`, with semaphores for mutual exclusion on `readcount` and for controlling writer access; structure P/V so that waiting occurs via semaphore blocking, not spin loops, to avoid busy waiting.  

***

## CPU schedulers, objectives, and preemption

Scheduling theory questions revolve around scheduler types, objectives, and preemption trade-offs.

- **Types of schedulers:**  
  - **Long-term (job scheduler):** Decides which jobs/processes to admit to the system; controls degree of multiprogramming (mix of CPU-bound and I/O-bound jobs).
  - **Short-term (CPU scheduler):** Chooses which ready process to run next on CPU; runs very frequently (on interrupts, I/O completion, quantum expiry).  
  - **Medium-term scheduler:** Swaps processes in/out of memory to control the multiprogramming level; suspends/resumes processes (used in systems with swapping).

- **Objectives of CPU scheduling:**  
  - Maximize CPU utilization and throughput; minimize response time (interactive), turnaround time (batch), and waiting time; avoid starvation; enforce fairness and priority policies.

- **Preemptive vs non-preemptive scheduling:**  
  - **Preemptive:** OS can take CPU away before a process voluntarily yields (e.g., time quantum expiry, higher priority arrival).  
  - **Non-preemptive:** Once a process gets CPU, it runs until completion or blocking.  
  - **Preemption advantages:** Better responsiveness, supports priorities, good for time-sharing and real-time.  
  - **Drawbacks:** More context-switch overhead; shared data must be carefully protected; priority inversion/starvation possible if priorities not managed (priority inheritance / aging often used).

- **For high-performance environments:** Preemptive scheduling (e.g., preemptive priority or round-robin with good quantum) is usually preferred because it improves responsiveness and allows fine-grained control over CPU allocation, especially on multiprocessors.  

***

## Scheduling algorithms and phenomena

Understanding how algorithms favor short jobs, the convoy effect, starvation, and multiprocessor scheduling completes Unit 2 theory.

- **FCFS vs RR vs Multilevel Feedback Queue (MLFQ):**  
  - **FCFS:** Simple, non-preemptive; suffers from **convoy effect** where one long CPU-bound job at front makes many short jobs wait, increasing average waiting time.
  - **Round Robin (RR):** Preemptive; each process gets time quantum q; favors short jobs because they finish in few quanta, while long ones get fragmented over time.  
  - **MLFQ:** Multiple ready queues with different priorities and quanta; new or I/O-bound (short CPU bursts) processes stay in higher-priority queues; long CPU-bound jobs gradually drop to lower queues; strongly biases toward short and interactive jobs.  

- **Effect of time quantum in RR:**  
  - **Very large q:** RR behaves like FCFS; poor responsiveness, less discrimination in favor of short jobs.  
  - **Very small q:** Too many context switches; high overhead; CPU time wasted on switching instead of useful work.  

- **Starvation and SJF modification:**  
  - **SJF/SRTF (Shortest Job First / Remaining Time First):** Optimal for average waiting time but can cause starvation of long jobs if short jobs keep arriving.
  - **Typical fix:** Use **aging** – gradually increase the effective priority of waiting processes (or gradually decrease their “effective burst time”) so long-waiting processes eventually run.  

- **Multilevel Queue vs Multilevel Feedback Queue:**  
  - **Multilevel Queue:** Fixed set of ready queues (e.g., system, interactive, batch), each with its own scheduling algorithm; strict queue priorities (higher-class queues always served before lower); processes are permanently assigned to a queue – no movement between queues.
  - **Multilevel Feedback Queue (MLFQ):** Processes can move between queues; new or I/O-bound get high priority, CPU-bound migrate downward over time; allows adaptation to observed behavior and reduces starvation through aging-like movement.  

- **Multiprocessor scheduling:**  
  - Can use **global queue** (all CPUs pull from one ready queue) or **per-CPU queues** with load balancing.
  - Must consider processor affinity (keep a process on same CPU to benefit from cache), avoid contention on global ready queue, and handle priorities across CPUs.  
  - Preemptive algorithms (e.g., preemptive priority, RR) are extended with either centralized or distributed decision-making about which CPU schedules which process.  
