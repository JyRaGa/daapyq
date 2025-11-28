# UNIT 1: INTRODUCTION TO OPERATING SYSTEMS — EXAM REVISION SHEET

---

## DEFINITION & CHARACTERISTICS

**Operating System (OS):**
System software that acts as an intermediary between users and computer hardware. It manages hardware resources, provides common services to application programs, and creates abstractions (processes, files, virtual memory) that hide hardware complexity.

**Key Characteristics:**
- **Resource management:** CPU, memory, I/O devices, files.
- **Concurrency:** Support multiprogramming/multitasking.
- **Protection & security:** Isolation between users and processes; access control enforcement.
- **Error detection & accounting:** System monitoring, crash recovery, performance metrics.
- **User interface:** CLI (shell) or GUI for user convenience.
- **Abstraction:** Virtual machine model; high-level primitives hide low-level details.

---

## FUNCTIONS OF AN OS

**1. Process Management**
- Create, schedule, suspend, resume, and terminate processes/threads.
- Maintain Process Control Block (PCB) for each process.
- Facilitate context switching and synchronization.
- Implement interprocess communication (IPC) and coordination.

**2. Memory Management**
- Allocate and deallocate main memory to processes.
- Enforce memory protection (isolation between address spaces).
- Implement paging, segmentation, and virtual memory.
- Manage TLBs, caches, and page replacement.

**3. File System Management**
- Organize data into logical units (files, directories).
- Implement file naming, access methods (sequential, indexed, random), and access control.
- Manage free space and file metadata (size, timestamps, permissions).
- Ensure data persistence and consistency.

**4. I/O and Device Management**
- Control and coordinate all I/O devices via drivers.
- Buffer I/O operations for efficiency.
- Manage device queues and handle interrupts.

**5. Protection & Security**
- Enforce user authentication and authorization.
- Implement access control lists (ACLs) and isolation.
- Detect and respond to security violations.

**6. Error Detection & Accounting**
- Detect hardware/software errors and malfunction.
- Keep usage statistics (CPU time, memory, I/O, file access).
- Report system performance and user activity.

---

## UTILITY OF AN OS

**Why an OS is necessary:**
- **Hides hardware complexity:** Applications need not manage registers, disk I/O, or interrupts directly.
- **Arbitrates resource conflicts:** Ensures fair and efficient sharing of CPU, memory, and devices among multiple users/processes.
- **Improves system utilization:** Multiprogramming keeps CPU and I/O devices busy; scheduling reduces idle time.
- **Enforces protection & isolation:** Prevents one process from corrupting another or accessing unauthorized memory/files.
- **Enables convenience:** Shell, file abstractions, and system calls make programming and usage practical.

Without an OS, each user program would need low-level code for every operation—impractical, error-prone, and extremely inefficient.

---

## KEY COMPONENTS & THEIR ROLES

| Component | Role |
|-----------|------|
| **Kernel** | Core privileged code managing CPU, memory, and process scheduling. |
| **Process Manager** | Handles PCB creation, context switching, scheduling, and synchronization. |
| **Memory Manager** | Allocates/deallocates memory, manages paging, handles page faults. |
| **File System** | Manages file naming, storage, retrieval, and access permissions. |
| **I/O Subsystem** | Interfaces with devices via drivers; buffers and schedules I/O requests. |
| **Protection Module** | Enforces kernel/user mode distinction, handles traps and exceptions. |
| **Shell/Command Interpreter** | Provides user interface for launching programs and issuing commands. |
| **System Programs** | Compilers, loaders, linkers, utilities (cp, ls, grep) that run on top of kernel. |

---

## ROLES IN PROCESS, MEMORY & STORAGE MANAGEMENT

**Process Management:**
- Maintains PCB (state, PID, registers, memory pointers, open files, priority).
- Schedules CPU time fairly and efficiently via schedulers.
- Handles process state transitions (new → ready → running → waiting → terminated).
- Facilitates synchronization (locks, semaphores) to avoid race conditions.

**Memory Management:**
- Tracks which memory regions are allocated/free.
- Assigns memory to new processes; deallocates on termination.
- Implements virtual memory via paging/segmentation so processes see private address spaces.
- Handles page faults by bringing pages from disk (swapping).
- Protects one process's memory from access by others.

**Storage Management:**
- Organizes disk into files and directories with hierarchical naming.
- Chooses file allocation scheme (contiguous, linked, indexed).
- Manages free-space using bitmaps or free lists.
- Caches frequently accessed blocks; ensures consistency on disk.
- Enforces access control (read, write, execute permissions).

---

## TWO MAIN CATEGORIES OF OS FUNCTIONS/SERVICES

### User-Oriented (Convenience) Services:
- **Program execution:** Loading and running user programs.
- **I/O operations:** Reading/writing files and device interaction.
- **File system operations:** Create, delete, rename, search files.
- **Communication:** Network access, message passing between processes.
- **User interface:** Command line or graphical interface for usability.

**Difference:** Directly support user programs and applications; focus on ease of use and functionality.

### System-Oriented (System/Efficiency) Functions:
- **Resource allocation:** Distributing CPU, memory, and I/O fairly.
- **Accounting:** Tracking resource usage for auditing and billing.
- **Protection & security:** Enforcing access control and data isolation.
- **Error detection:** Detecting hardware faults and correcting corrupted data.
- **Performance optimization:** Maximizing throughput and minimizing idle time.

**Difference:** Internal OS operations focused on efficient hardware utilization, system stability, and security enforcement; hidden from users but essential for safe, shared computing.

---

## OPERATING SYSTEM TYPES & EVOLUTION

### Batch Operating System
- **Mechanism:** Jobs collected and processed without user interaction.
- **Characteristics:** Non-preemptive, high turnaround time, high throughput for bulk processing.
- **Applications:** Payroll systems, billing, end-of-day bank reconciliation, large report generation, batch backups.
- **Advantage:** Efficient for large offline jobs.
- **Disadvantage:** No interactive response; slow turnaround for individual jobs.

### Real-Time Operating System (RTOS)
- **Mechanism:** Must respond to external events or complete tasks within strict, predictable time bounds.
- **Types:** Hard RTOS (deadline misses are failures), soft RTOS (occasional misses acceptable).
- **Characteristics:** Deterministic scheduling, priority-based, minimal context switching, bounded latency.
- **Applications:** Flight control, anti-lock braking (ABS), industrial robot control, medical monitoring, telecom switching, real-time audio/video.
- **Advantage:** Guaranteed response times; predictable behavior.
- **Disadvantage:** Complex scheduling; reduced resource utilization.

### Time-Sharing Operating System
- **Mechanism:** Preemptive scheduling; each user gets a small CPU time quantum; rapid context switching creates illusion of parallelism.
- **Characteristics:** Interactive, fair turnaround for multiple users, rapid response.
- **Examples:** UNIX, Linux multiuser systems, university computing servers.
- **Advantage:** Good responsiveness; multiple interactive users.
- **Disadvantage:** Context switching overhead; less predictable than batch for throughput.

### Real-Time vs Time-Sharing:
- **Real-time:** Deadline/event-driven; predictable timing; few interactive users; used in control systems.
- **Time-sharing:** Fairness and responsiveness to many concurrent interactive users; no strict deadlines.
- **Example:** Air-traffic-control RTOS vs university UNIX login server.

---

## PARALLEL & DISTRIBUTED SYSTEMS

### Parallel System (Multiprocessor)
- **Architecture:** Multiple CPUs on same machine; shared main memory, single OS.
- **Tightly coupled:** Fast inter-CPU communication via shared memory.
- **Synchronization challenges:** Complex locking, cache coherence issues.

**Advantages:**
- Increased throughput (multiple CPUs execute simultaneously).
- Improved reliability (graceful degradation if one CPU fails).
- Cost-effective per-unit performance (cheaper than one super-fast CPU).
- Better I/O device utilization.

**Disadvantages:**
- Shared memory synchronization complexity.
- Limited scalability due to memory contention.
- More expensive than single CPU.

### Distributed System
- **Architecture:** Collection of independent computers connected by network; each has own memory and OS.
- **Loosely coupled:** Communication via message passing over network; higher latency.

**Advantages:**
- Scalability: Add more machines to increase capacity.
- Fault tolerance: One machine's failure doesn't stop others; data replication improves availability.
- Resource sharing: Distributed resources (compute, storage) efficiently utilized.
- Performance: Potential for parallel computation across nodes.

**Disadvantages:**
- Network communication overhead and delays.
- Consistency challenges (distributed consensus, eventual consistency).
- Difficult to debug and manage.
- Security: Multiple entry points, distributed authentication.

### Multiprocessor Systems: SMP vs AMP

**Symmetric Multiprocessing (SMP):**
- All processors identical, running same OS.
- Shared ready queue; any processor can execute any process.
- Flexible and load-balanced.
- Used in modern servers and desktops.

**Asymmetric Multiprocessing (AMP):**
- One master processor controls task distribution.
- Slave processors execute assigned tasks; cannot run OS.
- Simpler to implement but less flexible.
- Historical or specialized systems.

---

## DISTRIBUTED OS vs NETWORK OS

### Distributed Operating System (DOS)
- **Goal:** Provide single-system image; make networked machines appear as one coherent system.
- **Transparency:** Users unaware of network; location, replication, and access are transparent.
- **Global resource management:** Single process manager, file manager, memory manager across all machines.
- **Advantages:** Seamless resource sharing; high transparency; uniform API.
- **Disadvantages:** Extremely complex; difficult to implement correctly; single point of failure risk.
- **Examples:** Amoeba, Plan 9 (research systems).

### Network Operating System (NOS)
- **Goal:** Connect independent machines with their own OS; provide explicit networking services.
- **User awareness:** Users aware of network; must explicitly access remote resources.
- **Local autonomy:** Each machine maintains its own OS and resource management.
- **Services:** Remote login (ssh, rlogin), file sharing (NFS, SMB), print sharing, email, web services.
- **Advantages:** Easier to implement; each machine retains control; familiar to users.
- **Disadvantages:** Tighter integration required for transparency; explicit network commands.
- **Examples:** Windows with file sharing, traditional UNIX with NFS, modern enterprise networks.

---

## KERNEL MODE vs USER MODE

### Definitions:
- **Kernel mode:** CPU has access to all instructions (privileged set), all memory, and all devices. Used by OS only.
- **User mode:** CPU has restricted instruction set; cannot directly access I/O, memory protection registers, or privileged instructions. Used by user applications.

### Purpose:
- Enforce protection and security; prevent user programs from corrupting kernel or other processes.
- Isolate processes; one crash cannot affect the kernel or other processes.

### Mode Switching:
- **User to kernel:** Via interrupt (hardware signal), trap/exception (software-generated error or system call).
- **Kernel to user:** At end of interrupt/trap handler; restore user registers and resume user instruction stream.

### Boot Sequence:
- **Power-on:** CPU starts in privileged/kernel mode.
- **Why:** Bootloader/firmware (privileged code) initializes hardware (memory controllers, I/O devices, interrupt tables).
- **Next:** Bootloader loads OS kernel into memory and transfers control to kernel.
- **User processes:** Launched by OS in user mode after kernel initialization.

**Security principle:** User code cannot directly modify system state; must request OS services via well-defined system call interface.

---

## INTERRUPTS vs TRAPS

### Interrupt
- **Origin:** External hardware device (timer, disk, network adapter, keyboard).
- **Timing:** Asynchronous; can occur at any point during instruction execution.
- **Cause:** Hardware event (timer expired, I/O complete, data available).
- **Response:** CPU suspends current instruction, saves state, executes interrupt handler (in kernel mode).
- **Return:** After handling, resume interrupted instruction (usually same point).
- **Example:** Timer interrupt signals OS to perform context switch; disk interrupt signals I/O completion.

### Trap (Exception)
- **Origin:** Synchronous; generated by currently executing instruction.
- **Timing:** Predictable; at specific instruction.
- **Causes:** System call (software interrupt), illegal instruction, division by zero, page fault, invalid memory access.
- **Response:** CPU transfers to trap handler (kernel mode); may terminate process or fix condition.
- **Return:** If recoverable (e.g., page fault), resume instruction; if not (e.g., segfault), terminate process.
- **Example:** `int 0x80` on x86 triggers system call trap; invalid memory access generates page-fault trap.

### Summary Table:
| Aspect | Interrupt | Trap |
|--------|-----------|------|
| **Origin** | External hardware | Current instruction |
| **Timing** | Asynchronous | Synchronous |
| **Example** | Timer, disk, network | Syscall, page fault, div by zero |
| **Predictability** | Unpredictable | Predictable |

---

## SYSTEM PROGRAMS

### Definition:
Programs that sit on top of the kernel and provide a convenient execution environment; not part of the kernel itself but essential for usability.

### Examples:
- **Shells:** bash, sh, zsh (command interpreters).
- **Compilers/Assemblers:** gcc, clang, nasm (program translation).
- **Loaders/Linkers:** ld (load executable into memory, resolve symbols).
- **Utilities:** cp, mv, rm, ls, grep, find (file and system operations).
- **Editors:** vim, nano, gedit (text editing).
- **Debuggers:** gdb (program debugging).

### Purpose:
- Bridge gap between low-level OS primitives and high-level user needs.
- Provide standard tools for program development, execution, and system management.
- Make the OS usable; without them, users would directly call system calls (inconvenient).
- Enable productivity through familiar interfaces.

---

## FORK SYSTEM CALL

### Definition:
`fork()` creates a new process by duplicating the calling process.

### Mechanism:
- **Return value:** Parent receives child PID; child receives 0.
- **Address space:** Child gets a copy of parent's entire memory (code, data, stack, heap).
- **PCB:** Child gets its own PCB with unique PID, parent PID (PPID), and initial state "ready."
- **File descriptors:** Child inherits copies (same open files as parent initially).
- **Execution:** Both parent and child continue from the same point after `fork()` returns.

### Typical usage:
```c
pid_t pid = fork();
if (pid == 0) {
    // Child process
    exec(...);  // Replace memory image with new program
} else {
    // Parent process
    wait(...);  // Wait for child to finish
}
```

### Why important:
- Fundamental to process creation in UNIX/Linux.
- Enables shell to launch programs (shell forks, child execs the program, parent waits).
- Enables server processes to spawn children for concurrent client handling.
- Basis for daemons and background processes.

---

## GRACEFUL DEGRADATION vs FAULT TOLERANCE

### Graceful Degradation
- **Definition:** System continues to operate with reduced performance or functionality when components fail or under heavy load.
- **Mechanism:** Shed load, reduce service quality, deactivate non-critical features.
- **Example:** Web server reducing page caching when memory is low; router dropping low-priority packets during congestion.
- **Benefit:** System stays up; better than crashing.
- **User impact:** Slower but functional; acceptable temporary loss of non-critical features.

### Fault Tolerance
- **Definition:** System continues to provide correct service despite presence of certain faults.
- **Mechanism:** Redundancy (hardware, software, data) and recovery; may mask faults entirely.
- **Example:** RAID storage (disk failure masked by redundancy); dual-redundant flight control (if one fails, backup takes over seamlessly).
- **Benefit:** No visible service interruption; correct operation maintained.
- **User impact:** Transparent; users unaware of fault.

### Key Difference:
- **Graceful degradation** = reduced but continuous service (quality degraded).
- **Fault tolerance** = full correct service despite faults (transparent).
- **Cost:** Fault tolerance more expensive (requires redundancy and recovery logic).

---

## OS AS RESOURCE MANAGER vs VIRTUAL MACHINE

### Resource Manager Role
- **Function:** Allocates CPU, memory, I/O devices, and files fairly and efficiently.
- **Policies:** Scheduling (CPU fairness), memory allocation (free space management), I/O queuing, file access control.
- **Objectives:** Maximize throughput, minimize idle time, enforce priority/fairness, prevent starvation.
- **Implementation:** Schedulers, memory allocators, device drivers, file system.

### Virtual Machine Role
- **Function:** Provides abstraction; each process behaves as if it has its own CPU, memory, and I/O devices.
- **Abstractions:** Process (private execution context), virtual address space (private memory), files (named data storage).
- **Mechanism:** CPU sharing via scheduling (each process gets time slices), memory protection via page tables, device virtualization via device drivers.
- **User perspective:** Application programs need not worry about hardware details; they program to high-level abstractions.

**Example:** Two processes running simultaneously; each "sees" a complete machine (full CPU, full memory address space, full file system)—OS multiplexes hardware resources to create this illusion.

---

## LAYERED ARCHITECTURE

### Structure:
OS divided into layers (0 to N), where layer N relies only on layers 0 to N-1.

**Example layers (simplified):**
- Layer 0: Hardware (CPU, memory, devices).
- Layer 1: Kernel mode primitives (interrupts, context switch).
- Layer 2: Process/thread management.
- Layer 3: Memory management.
- Layer 4: File system.
- Layer 5: I/O buffering.
- Layer 6: User interface (shell).
- Layer 7: User programs.

### Advantages:
- **Modularity:** Each layer has clear, well-defined interface.
- **Easier debugging:** Isolate bugs to specific layer; lower layers can be tested independently.
- **Easier verification:** Formal proof possible for each layer.
- **Maintainability:** Changes to one layer don't affect others if interface is stable.
- **Reusability:** Layers can be reused in different OS designs.

### Disadvantages:
- **Performance overhead:** Extra layer-crossing increases context switches and function calls.
- **Less flexible:** Strict layer boundaries can prevent optimizations.

### Suitability:
- **Ideal for:** Safety-critical systems (aerospace, medical), systems requiring high reliability, embedded systems with known constraints.
- **Less ideal for:** High-performance systems where efficiency is paramount.

---

## MONOLITHIC vs MICROKERNEL ARCHITECTURE

### Monolithic Kernel
- **Design:** Entire OS (process management, memory management, file system, device drivers, networking) in single large kernel running in one address space.
- **Advantages:**
  - Fast system calls (no context switching required).
  - Efficient data sharing between subsystems.
  - Good performance for traditional systems.
- **Disadvantages:**
  - Large kernel (millions of lines of code); hard to maintain and debug.
  - One bug can crash entire system.
  - Less extensible; adding features requires recompiling kernel.
  - Large Trusted Computing Base (TCB).
- **Examples:** Linux (partially), older UNIX, DOS.

### Microkernel Architecture
- **Design:** Kernel contains only essential services (address space management, low-level IPC, basic scheduling). Other services (file system, device drivers, networking, user authentication) run as user-space servers via message passing.
- **Advantages:**
  - Smaller kernel; easier to verify and maintain.
  - Fault isolation: One server crash doesn't crash kernel.
  - More extensible: New services added as new user-space servers.
  - Better security: Limited attack surface.
  - Suitable for embedded and safety-critical systems.
- **Disadvantages:**
  - More context switching and IPC overhead (slower system calls).
  - Added complexity in message-passing coordination.
  - Debugging harder due to distributed nature.
- **Examples:** Windows NT (partially), Minix, QNX (RTOS).

### Comparison Table:
| Aspect | Monolithic | Microkernel |
|--------|-----------|------------|
| **Kernel size** | Large | Small |
| **System call speed** | Fast | Slower (IPC overhead) |
| **Extensibility** | Recompile kernel | Add user-space servers |
| **Fault isolation** | Poor (one crash = system crash) | Good (server crash isolated) |
| **Performance** | Better | Worse (IPC cost) |
| **Maintainability** | Harder (large codebase) | Easier (modular) |
| **TCB** | Large | Small |

---

## WHY LAYERED & MICROKERNEL ARE SUITABLE FOR SPECIFIC ENVIRONMENTS

### Layered Architecture:
- **Best for:** Medical devices (pacemakers, ventilators), aerospace systems (avionics), safety-critical controllers where reliability and verifiability are paramount.
- **Reason:** Clear layer boundaries enable formal verification; testing each layer independently reduces risk of cascading failures.

### Microkernel:
- **Best for:** Real-time embedded systems (QNX in automotive, robotics), systems requiring high availability (telecom switches), distributed systems where modularity and fault isolation are critical.
- **Reason:** Small TCB and process isolation make RT guarantees possible; independent servers enable fault tolerance and incremental updates.

### Monolithic (for contrast):
- **Best for:** General-purpose systems (desktops, servers) where performance and bulk processing matter more than modularity (Linux on web servers achieves both with good design).

---

## CENTRALIZED vs DISTRIBUTED OS ROLE

### Centralized System:
- **Scope:** Single machine with local hardware (CPU, memory, disks, I/O devices).
- **OS role:** Manage CPU scheduling, memory allocation, local I/O, and file storage.
- **Challenges:** Single point of failure; limited scalability; resource exhaustion under heavy load.
- **Design focus:** Fairness, efficiency, error recovery for local resources.

### Distributed System:
- **Scope:** Multiple independent machines interconnected by network.
- **OS role (unique challenges):**
  - **Naming & transparency:** Hide network; users need not know where resources/services are located.
  - **Replication & consistency:** Data copied across nodes for fault tolerance; must ensure consistency (strong vs eventual).
  - **Partial failure handling:** Network partitions, node crashes, message loss; OS must continue operation.
  - **Consensus & coordination:** Distributed locks, leader election, transaction coordination.
  - **Performance & latency:** Network delays add latency to all operations; minimize message overhead.

**Design focus:** Availability, consistency, partition tolerance (CAP theorem); trade-offs between these.

---

## SUMMARY TABLE: OS TYPES AT A GLANCE

| Type | Primary Goal | CPU Use | User Interaction | Example |
|------|--------------|---------|------------------|---------|
| **Batch** | Throughput | High | None | Payroll processing |
| **Time-sharing** | Response time | Fair | Interactive | UNIX server |
| **Real-time** | Deadline meet | Predictable | Embedded | Flight control |
| **Parallel** | Speedup | Multicore | Varies | SMP desktop |
| **Distributed** | Scalability | Network nodes | Transparent | Cloud OS |

---

## QUICK REFERENCE: KEY DEFINITIONS

- **Process:** Active instance of a program with its own PCB, memory, and resources.
- **System call:** Interface allowing user-mode programs to invoke kernel services.
- **Context switch:** Saving one process's state and loading another's to give CPU time to different processes.
- **Virtual memory:** Abstraction allowing processes to use more memory than physically available (paging/swapping).
- **I/O buffering:** Temporary storage of data during input/output to smooth timing differences between CPU and devices.
- **Race condition:** Concurrent access to shared data by multiple processes leading to unpredictable results.
- **Multiprogramming:** Multiple processes in memory; OS switches between them (may execute only one at a time).
- **Multitasking:** Rapid context switching to give illusion of concurrent execution of multiple tasks.

---

**Exam tips:**
- Define terms clearly with examples.
- Use comparison tables for differentiation questions.
- Emphasize "why" and purpose in answers.
- Draw diagrams (e.g., process states, layer diagram, mode switching) when applicable.
- State advantages and disadvantages explicitly; examiners check understanding, not just memorization.
