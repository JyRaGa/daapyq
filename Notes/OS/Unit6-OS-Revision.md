

# UNIT 6: CASE STUDIES (Windows, Linux, UNIX) — EXAM REVISION SHEET

## CASE STUDY 1: WINDOWS OPERATING SYSTEM

### Introduction

**Windows** is a family of proprietary operating systems developed by **Microsoft** for personal computers, laptops, and enterprise systems. Modern versions (Windows 10, 11, Server editions) are based on the **Windows NT architecture**, combining a user-friendly graphical interface with powerful background processing.

**Target Users:**
- Home users (desktop computing)
- Enterprise organizations (servers, workstations)
- Developers (Visual Studio ecosystem)

***

### Windows Architecture (6-Layer Model)

Windows uses a **layered architecture** that provides modularity and hardware independence.

```
┌─────────────────────────────────────────────┐
│   Layer 6: USER INTERFACE                  │
│   (Taskbar, Start Menu, Desktop, Explorer) │
├─────────────────────────────────────────────┤
│   Layer 5: SYSTEM PROCESSES & SUBSYSTEMS   │
│   (Win32 Subsystem, csrss.exe, smss.exe)   │
├─────────────────────────────────────────────┤
│   Layer 4: DEVICE DRIVERS                  │
│   (Hardware device communication)           │
├─────────────────────────────────────────────┤
│   Layer 3: EXECUTIVE SERVICES              │
│   (Process Control, I/O, Memory, Security)  │
├─────────────────────────────────────────────┤
│   Layer 2: KERNEL                          │
│   (Scheduling, Interrupts, Memory Mgmt)     │
├─────────────────────────────────────────────┤
│   Layer 1: HARDWARE ABSTRACTION LAYER (HAL)│
│   (Hardware Independence Interface)         │
├─────────────────────────────────────────────┤
│   Layer 0: HARDWARE                        │
│   (CPU, Memory, Disk, I/O Devices)         │
└─────────────────────────────────────────────┘
```

***

#### Layer 1: Hardware Abstraction Layer (HAL)

**Function:** Acts as an **interface between hardware and OS kernel**, providing hardware independence.

**Why it's important:**
```
Without HAL:
Windows Kernel → Must know specific details of every CPU, chipset, interrupt controller
Problem: Need different kernel for Intel, AMD, ARM, etc.

With HAL:
Windows Kernel → HAL → Hardware
Benefit: Same kernel works on different hardware platforms
```

**Key Responsibilities:**
- **Abstract hardware differences:** Hide CPU-specific details (Intel x86 vs AMD vs ARM)
- **Interrupt management:** Translate hardware interrupts to standard format
- **DMA operations:** Manage Direct Memory Access transfers
- **Timer services:** Provide standardized clock/timer interface
- **Bus communication:** Handle PCI, USB, SATA buses uniformly

**Example:**
```c
// Kernel calls HAL function (hardware-independent)
HalGetInterruptVector(interrupt_line);

// HAL translates to specific hardware
// For Intel: Maps to APIC (Advanced Programmable Interrupt Controller)
// For ARM: Maps to GIC (Generic Interrupt Controller)
```

**Memory Trick:** "HAL = **H**ardware **A**bstraction **L**ayer keeps kernel hardware-agnostic"

***

#### Layer 2: Kernel

**Function:** The **core component** managing processor scheduling, interrupt handling, and low-level memory management.

**Key Responsibilities:**

**1. Thread Scheduling:**
```
Windows Kernel Scheduler:
- Priority-based preemptive multitasking
- 32 priority levels (0-31)
  - 0: System idle
  - 1-15: Normal priority classes
  - 16-31: Real-time priority classes
- Quantum-based time slicing (default: ~10-15 ms)
```

**2. Interrupt Handling:**
```
Hardware Interrupt → HAL → Kernel Interrupt Dispatcher
                                ↓
                        Interrupt Service Routine (ISR)
                                ↓
                        Deferred Procedure Call (DPC)
```

**3. Synchronization Primitives:**
- Critical sections
- Mutexes
- Semaphores
- Events

**4. Low-Level Memory Management:**
- Virtual-to-physical address translation
- TLB management
- Page fault handling

**Kernel Mode vs User Mode:**
```
┌────────────────────────────────────────┐
│  User Mode (Ring 3)                    │
│  - Applications run here               │
│  - Limited privileges                  │
│  - Cannot access hardware directly     │
├────────────────────────────────────────┤
│  Kernel Mode (Ring 0)                  │
│  - Kernel + drivers run here           │
│  - Full hardware access                │
│  - Can execute privileged instructions │
└────────────────────────────────────────┘
```

***

#### Layer 3: Executive Services

**Function:** Manages high-level OS services including process control, I/O, memory, security, and inter-process communication.

**Components:**

**1. Process Manager:**
- Process and thread creation/termination
- Job object management

**2. Memory Manager:**
- Virtual memory allocation
- Working set management
- Page file operations

**3. I/O Manager:**
- Device I/O requests
- File system drivers
- Plug and Play

**4. Object Manager:**
- Namespace management (all OS resources are "objects")
- Object lifetime management

**5. Security Reference Monitor:**
- Access control checks
- Audit policy enforcement

**6. IPC (Inter-Process Communication) Manager:**
- Named pipes
- Mailslots
- Shared memory

***

#### Layer 4: Device Drivers

**Function:** Allow communication between hardware devices and the operating system.

**Types:**
- **Kernel-mode drivers:** Direct hardware access (disk, network)
- **User-mode drivers:** Safer, limited access (printers, scanners)

**Driver Stack Example (Disk I/O):**
```
Application
    ↓
Win32 API (ReadFile)
    ↓
I/O Manager
    ↓
File System Driver (NTFS.sys)
    ↓
Volume Manager
    ↓
Disk Class Driver
    ↓
Disk Port Driver (SATA/NVMe)
    ↓
Hardware (Physical Disk)
```

***

#### Layer 5: System Processes & Subsystems

**Function:** Includes the **Win32 subsystem** (main user interface) and critical system services.

**Key System Processes:**

**1. csrss.exe (Client/Server Runtime Subsystem):**
- Win32 console management
- Thread creation/deletion
- Shutdown coordination

**2. smss.exe (Session Manager Subsystem):**
- First user-mode process after boot
- Creates sessions for user logon
- Loads page file

**3. wininit.exe:**
- Starts critical system services
- Launches lsass.exe (security subsystem)

**4. services.exe:**
- Service Control Manager
- Manages Windows services

***

#### Layer 6: User Interface

**Function:** Provides GUI-based interaction through familiar components.

**Components:**
- **Desktop Window Manager (DWM):** Compositing window manager
- **Explorer.exe:** File manager, Start menu, taskbar
- **Shell:** GUI framework
- **Control Panel / Settings:** System configuration

***

### Key Features of Windows

#### 1. Preemptive Multitasking and Multithreading

**Preemptive Multitasking:**
```
OS can interrupt running process at any time (preempt)
Ensures no single process monopolizes CPU

Example:
Process A running → Timer interrupt (quantum expired)
→ OS switches to Process B
```

**Multithreading:**
```
Single process can have multiple threads
Each thread has own stack, registers
Threads share: code, data, heap

Example: Chrome browser
- Thread 1: UI rendering
- Thread 2: JavaScript execution
- Thread 3: Network requests
- Thread 4: Downloading files
```

***

#### 2. Security Features

**Access Tokens:**
```
Each process has security token containing:
- User SID (Security Identifier)
- Group memberships
- Privileges
- Integrity level

Example:
Normal user: Medium integrity
Administrator: High integrity
System: System integrity
```

**User Account Control (UAC):**
```
Prompts for elevation when:
- Installing software
- Modifying system files
- Changing system settings

Benefit: Prevents malware from making unauthorized changes
```

**Access Control Lists (ACLs):**
```
Each file/folder has ACL specifying:
- User/Group
- Permissions (Read, Write, Execute, Delete, etc.)
- Allow or Deny

Example ACL:
User "Alice": Allow Read, Write
Group "Developers": Allow Read, Execute
Everyone: Deny All
```

***

#### 3. NTFS File System

**Key Features:**

**Journaling:**
```
Before making changes, log them to journal
If crash occurs during operation:
→ Replay journal on reboot
→ File system remains consistent

Prevents corruption from incomplete operations
```

**Encryption (EFS - Encrypting File System):**
```
Files encrypted with user's key
Even if attacker steals disk, cannot read data
Transparent to authorized user
```

**Compression:**
```
Files compressed automatically by NTFS
Saves disk space
Decompressed on-the-fly when accessed
```

**File Streams:**
```
Main file + alternate data streams
Example: file.txt:stream1

Used for metadata, thumbnails, etc.
```

***

#### 4. Virtual Memory and Paging

**Virtual Memory:**
```
Each process gets 4 GB virtual address space (32-bit)
Or 128 TB (64-bit Windows)

Even if physical RAM = 4 GB, can run many processes
OS swaps pages between RAM and disk (page file)
```

**Demand Paging:**
```
Pages loaded only when accessed
Initial process creation: Only minimal pages loaded
As process runs: Page faults → Load pages from disk
```

**Page File (pagefile.sys):**
```
Located on disk
Acts as extension of RAM
OS swaps out inactive pages here

Example:
Physical RAM: 8 GB
Page file: 8 GB
Total virtual memory: 16 GB
```

***

#### 5. Registry

**Function:** Centralized database for system and application configuration.

**Structure:**
```
Registry Hives:
├─ HKEY_LOCAL_MACHINE (HKLM): System-wide settings
│  ├─ SOFTWARE: Installed applications
│  ├─ SYSTEM: Boot configuration, drivers
│  └─ HARDWARE: Hardware profiles
├─ HKEY_CURRENT_USER (HKCU): User-specific settings
├─ HKEY_USERS: All user profiles
└─ HKEY_CLASSES_ROOT: File associations
```

**Example:**
```
Registry path:
HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion

Key: ProductName
Value: "Windows 11 Pro"
```

***

### Windows System Calls (Win32 API)

System calls in Windows are accessed via **Win32 API** functions, not directly invoked.

#### Important System Calls Table

| Function | Purpose | Example |
|----------|---------|---------|
| **CreateProcess()** | Creates a new process | Launch notepad.exe |
| **ReadFile()** | Reads data from file/device | Read file contents |
| **WriteFile()** | Writes data to file/device | Write to log file |
| **CreateFile()** | Opens or creates a file | Open C:\data.txt |
| **VirtualAlloc()** | Allocates virtual memory | Allocate 1 MB buffer |
| **ExitProcess()** | Terminates a process | Exit with code 0 |
| **WaitForSingleObject()** | Waits for process/thread | Wait for child process |

***

#### CreateProcess() - Detailed Example

**Signature:**
```c
BOOL CreateProcess(
    LPCSTR lpApplicationName,     // Program to execute
    LPSTR lpCommandLine,          // Command line arguments
    LPSECURITY_ATTRIBUTES lpProcessAttributes,
    LPSECURITY_ATTRIBUTES lpThreadAttributes,
    BOOL bInheritHandles,
    DWORD dwCreationFlags,
    LPVOID lpEnvironment,
    LPCSTR lpCurrentDirectory,
    LPSTARTUPINFO lpStartupInfo,
    LPPROCESS_INFORMATION lpProcessInformation  // Output
);
```

**Example Code:**
```c
#include <windows.h>

int main() {
    STARTUPINFO si = {sizeof(si)};
    PROCESS_INFORMATION pi;
    
    // Create notepad.exe process
    if (CreateProcess(
        "C:\\Windows\\System32\\notepad.exe",  // Application
        NULL,                                   // Command line
        NULL, NULL,                             // Security
        FALSE,                                  // Inherit handles
        0,                                      // Creation flags
        NULL, NULL,                             // Environment, directory
        &si, &pi                                // Startup info, process info
    )) {
        printf("Process created with PID: %d\n", pi.dwProcessId);
        
        // Wait for process to finish
        WaitForSingleObject(pi.hProcess, INFINITE);
        
        // Close handles
        CloseHandle(pi.hProcess);
        CloseHandle(pi.hThread);
    }
    return 0;
}
```

**Process:**
```
1. CreateProcess() called
2. OS allocates process structures (PCB, PEB)
3. Loads executable into memory
4. Creates primary thread
5. Returns handles and IDs
```

***

### Windows Kernel: Hybrid Architecture

**Hybrid Kernel** combines monolithic kernel performance with microkernel modularity.

**Characteristics:**
```
Monolithic aspects:
✅ Core services in kernel mode (fast)
✅ Direct hardware access
✅ Minimal context switches

Microkernel aspects:
✅ Modular subsystems (Win32, POSIX)
✅ User-mode services where possible
✅ Better stability (isolated failures)
```

**Comparison:**
```
Monolithic (Linux):          Hybrid (Windows):         Microkernel (Minix):
All in kernel mode           Core + Modules            Minimal kernel
Fast but fragile             Balanced                  Slow but stable
```

***

### Windows Scheduling: Priority-Driven Preemptive

**Priority Levels:**
```
31: Critical real-time
...
16: Real-time base
15: Normal highest
...
8: Normal base
...
1: Idle
0: System idle thread
```

**Algorithm:**
```
1. Always run highest-priority ready thread
2. If multiple threads at same priority: Round-robin
3. Priority boost for:
   - Interactive processes (keyboard/mouse input)
   - I/O completion
   - Foreground window
4. Priority decay: Boosted priority gradually returns to base
```

**Example:**
```
Threads ready: T1(priority 10), T2(priority 15), T3(priority 15)

Scheduler picks: T2 (highest priority)
T2 runs for quantum (e.g., 20 ms)
→ Preempted
Scheduler picks: T3 (same priority, round-robin)
T3 runs for quantum
→ Preempted
Scheduler picks: T2 again (round-robin between T2, T3)
T1 waits until T2 and T3 block or finish
```

***

### Windows Memory Management

#### Paging and Demand Paging

**Page Size:** 4 KB (x86) or 8 KB (some architectures)

**Demand Paging Process:**
```
1. Process accesses virtual address not in RAM
2. Page fault exception
3. OS checks if address valid (in committed region)
4. If valid:
   a. Find free page frame
   b. Read page from disk (page file or executable)
   c. Update page table
   d. Resume process
5. If invalid: Access violation exception (crash)
```

**Working Set:**
```
Set of pages currently in physical memory for a process

Minimum working set: 50 pages
Maximum working set: Adjustable (default: ~500 pages)

If working set exceeded:
→ OS trims (removes) least recently used pages
```

***

### Windows Case Scenario Analysis

**Scenario:** University lab with Windows 11 systems. Students run MATLAB, Python IDEs, browsers simultaneously. Systems slow down over time.

#### Problem Identification

**1. Virtual Memory Overuse:**
```
Symptom: Hard disk constantly active (thrashing)
Cause: Limited RAM (e.g., 4 GB) insufficient for all applications
Effect: Excessive paging → disk I/O bottleneck
```

**2. Increased Disk I/O:**
```
RAM usage: 100% (all physical memory used)
Page file usage: High
Disk queue length: Long

Result: Applications wait for pages to be swapped in/out
```

**3. Background Services:**
```
Services consuming resources:
- Windows Update
- Windows Defender (real-time scanning)
- Superfetch/Prefetch
- Indexing service

Each service: ~50-200 MB RAM, periodic CPU usage
```

***

#### Solutions

**1. Increase Physical Memory:**
```
Upgrade: 4 GB → 16 GB RAM
Benefit:
- More applications fit in RAM
- Reduced paging
- Faster response times

Cost-benefit: RAM upgrade ~$50, productivity gain significant
```

**2. Disable Unnecessary Startup Services:**
```
Steps:
1. Open Task Manager (Ctrl+Shift+Esc)
2. Go to "Startup" tab
3. Disable:
   - OneDrive (if not used)
   - Cortana
   - Adobe updaters
   - Manufacturer bloatware

Services to disable (services.msc):
- Windows Search (if not needed)
- Superfetch (on systems with SSD)
```

**3. Adjust Process Priorities:**
```
Task Manager → Details tab → Right-click process → Set priority

Example:
- MATLAB (computational): High priority
- Chrome (browsing): Normal priority
- Background apps: Low priority

Effect: Critical applications get more CPU time
```

**4. Additional Optimizations:**
```
- Use SSD instead of HDD (faster paging)
- Increase page file size manually
- Close unused applications
- Use lightweight alternatives (e.g., VSCode instead of full IDE)
```

***

### Short Questions (Windows)

**Q1: Explain the architecture of the Windows operating system.**

**Answer:**
Windows uses a 6-layer architecture: (1) Hardware Abstraction Layer (HAL) provides hardware independence; (2) Kernel manages scheduling, interrupts, and memory; (3) Executive Services handle process control, I/O, memory, and security; (4) Device Drivers enable hardware communication; (5) System Processes & Subsystems include Win32 subsystem and services like csrss.exe; (6) User Interface provides GUI components (taskbar, Start menu, desktop). This layered design ensures modularity, portability, and security.

***

**Q2: What is the function of the Hardware Abstraction Layer?**

**Answer:**
The HAL acts as an interface between the OS kernel and system hardware, providing hardware independence. It abstracts CPU-specific details, interrupt controllers, timers, and buses, allowing the same Windows kernel to run on different hardware platforms (Intel, AMD, ARM). HAL translates generic kernel requests into hardware-specific operations, enabling portability without modifying the kernel.

***

**Q3: Describe the role of the Windows kernel.**

**Answer:**
The Windows kernel is the core component responsible for: (1) **Thread Scheduling** - priority-based preemptive multitasking with 32 priority levels; (2) **Interrupt Handling** - processing hardware interrupts via ISRs and DPCs; (3) **Memory Management** - virtual-to-physical address translation, TLB management, page fault handling; (4) **Synchronization** - providing mutexes, semaphores, events, and critical sections. It operates in kernel mode (Ring 0) with full hardware access.

***

**Q4: Explain process creation using CreateProcess() system call.**

**Answer:**
`CreateProcess()` creates a new process in Windows. Steps: (1) Specify executable path and command-line arguments; (2) OS allocates process structures (PCB, PEB); (3) Loads executable into virtual memory; (4) Creates primary thread; (5) Returns process/thread handles and IDs. The parent can use `WaitForSingleObject()` to wait for completion. Unlike Unix `fork()`, Windows creates a completely new process from an executable file rather than duplicating the parent.

***

**Q5: How does Windows manage virtual memory?**

**Answer:**
Windows uses **demand paging** with a page file (pagefile.sys) on disk. Each process gets a large virtual address space (4 GB on 32-bit, 128 TB on 64-bit). The Memory Manager maintains page tables mapping virtual to physical addresses. When physical RAM is low, inactive pages are swapped to the page file. Page faults trigger loading pages from disk. The **working set** (pages in RAM) is managed per-process, with trimming when memory pressure occurs, creating the illusion of unlimited memory.

***

## CASE STUDY 2: LINUX OPERATING SYSTEM

### Introduction

**Linux** is an **open-source** operating system modeled on UNIX, using a **monolithic kernel**. Widely used in servers, desktops, embedded systems, and supercomputers, Linux provides both command-line (CLI) and graphical interfaces (GUI).

**Created by:** Linus Torvalds (1991)

**Distributions:** Ubuntu, Fedora, Debian, Red Hat, CentOS, Arch, etc.

***

### Linux Architecture (5-Layer Model)

```
┌─────────────────────────────────────────────┐
│   Layer 5: USER INTERFACE                  │
│   (Shells: bash, zsh / GUI: GNOME, KDE)    │
├─────────────────────────────────────────────┤
│   Layer 4: SYSTEM UTILITIES                │
│   (File handling, process control: ls, ps) │
├─────────────────────────────────────────────┤
│   Layer 3: SYSTEM LIBRARIES                │
│   (glibc, standard functions for apps)     │
├─────────────────────────────────────────────┤
│   Layer 2: KERNEL                          │
│   (CPU scheduling, memory, devices, syscalls)│
├─────────────────────────────────────────────┤
│   Layer 1: HARDWARE                        │
│   (CPU, memory, I/O peripherals)           │
└─────────────────────────────────────────────┘
```

***

#### Layer 1: Hardware

Physical devices: CPU, RAM, storage, network cards, peripherals.

***

#### Layer 2: Kernel

**The core component** managing all system resources.

**Key Responsibilities:**

**1. CPU Scheduling:**
```
Completely Fair Scheduler (CFS) - Default since kernel 2.6.23

Algorithm:
- Tracks virtual runtime (vruntime) for each process
- Always schedules process with lowest vruntime
- Fair distribution of CPU time

Example:
Process A: vruntime = 100 ms
Process B: vruntime = 150 ms
→ Schedule A (it has less CPU time so far)
```

**2. Memory Management:**
```
- Virtual memory with paging
- Demand paging and swapping
- Buddy allocator for physical pages
- Slab allocator for kernel objects
- Memory zones: DMA, Normal, HighMem
```

**3. Device Management:**
```
Everything is a file:
- /dev/sda: Hard disk
- /dev/tty: Terminal
- /dev/null: Null device (discard data)

Unified interface: open(), read(), write(), close()
```

**4. System Call Interface:**
```
Bridge between user space and kernel space
~300+ system calls in modern Linux
Examples: fork(), exec(), read(), write(), open()
```

***

#### Layer 3: System Libraries

**glibc (GNU C Library):** Standard C library providing functions for user applications.

**Functions:**
```c
printf(), scanf()  // Standard I/O
malloc(), free()   // Memory allocation
fopen(), fread()   // File operations
pthread_create()   // Threading
```

**System Call Wrappers:**
```c
// User calls wrapper function
ssize_t read(int fd, void *buf, size_t count);

// Wrapper makes system call (via int 0x80 or syscall instruction)
// Kernel executes sys_read()
// Returns to user space
```

***

#### Layer 4: System Utilities

**Command-line tools** for system management.

**Categories:**

**File Management:**
```bash
ls    # List files
cp    # Copy
mv    # Move/rename
rm    # Remove
cat   # Display file contents
chmod # Change permissions
```

**Process Management:**
```bash
ps    # List processes
top   # Real-time process monitor
kill  # Send signal to process
nice  # Adjust priority
```

**System Monitoring:**
```bash
df    # Disk space
free  # Memory usage
uptime # System uptime
dmesg # Kernel messages
```

***

#### Layer 5: User Interface

**CLI (Command-Line Interface):**
- **Shells:** bash (Bourne Again Shell), zsh (Z Shell), fish
- **Terminal Emulators:** gnome-terminal, konsole, xterm

**GUI (Graphical User Interface):**
- **GNOME:** Default on Ubuntu, Fedora
- **KDE Plasma:** Feature-rich, customizable
- **XFCE, LXQt:** Lightweight alternatives

***

### Key Features of Linux

#### 1. Multiuser and Multitasking

**Multiuser:**
```
Multiple users can log in simultaneously
Each user has:
- Home directory: /home/username
- Own environment variables
- Separate processes
- Resource quotas

Example:
user1 logged in via SSH
user2 logged in via GUI
user3 logged in via console
```

**Multitasking:**
```
Multiple processes run concurrently
Time-slicing with CFS scheduler
Processes isolated via virtual memory
```

***

#### 2. Open Source and Customizable

**Open Source:**
```
Source code freely available
Licensed under GPL (GNU General Public License)
Anyone can:
- View code
- Modify code
- Redistribute modifications

Benefit: Transparency, security audits, community contributions
```

**Customizable:**
```
Users can:
- Choose desktop environment (GNOME, KDE, XFCE)
- Compile custom kernel
- Replace system components
- Create own distributions

Example: Android is customized Linux
```

***

#### 3. Efficient Process Management (fork() and exec())

**fork() System Call:**
```c
pid_t fork(void);

Creates child process (duplicate of parent)
Returns:
- 0 in child process
- Child's PID in parent process
- -1 on error
```

**Example:**
```c
#include <unistd.h>
#include <stdio.h>

int main() {
    pid_t pid = fork();
    
    if (pid == 0) {
        // Child process
        printf("Child process (PID: %d)\n", getpid());
    } else if (pid > 0) {
        // Parent process
        printf("Parent process (PID: %d), Child PID: %d\n", getpid(), pid);
    } else {
        // Error
        perror("fork failed");
    }
    
    return 0;
}
```

**Visual:**
```
Before fork():
┌──────────────┐
│ Parent (PID  │
│     100)     │
└──────────────┘

After fork():
┌──────────────┐
│ Parent (PID  │ ← fork() returns child's PID (e.g., 101)
│     100)     │
└──────────────┘

┌──────────────┐
│ Child (PID   │ ← fork() returns 0
│     101)     │ ← Copy of parent (own memory, file descriptors)
└──────────────┘
```

***

**exec() Family:**
```c
int execl(const char *path, const char *arg, ...);
int execv(const char *path, char *const argv[]);
// ... other variants

Replaces current process image with new program
Does NOT create new process (uses existing PID)
```

**Example:**
```c
#include <unistd.h>

int main() {
    printf("Before exec\n");
    
    // Replace current process with /bin/ls
    execl("/bin/ls", "ls", "-l", NULL);
    
    // This line never executes (unless exec fails)
    printf("After exec\n");
    
    return 0;
}
```

***

**Common Pattern: fork() + exec()**
```c
pid_t pid = fork();

if (pid == 0) {
    // Child: Execute new program
    execl("/bin/ls", "ls", "-l", NULL);
} else {
    // Parent: Wait for child
    wait(NULL);
    printf("Child finished\n");
}
```

**Process:**
```
1. Parent calls fork()
2. Child process created (copy of parent)
3. Child calls exec()
4. Child's memory replaced with new program
5. New program runs in child process
6. Parent can wait() for child to finish
```

**Why this pattern?**
```
Shell uses this to run commands:
1. bash process forks
2. Child bash calls exec() with command (e.g., "ls")
3. "ls" runs in child, parent bash waits
4. When "ls" finishes, control returns to parent bash
```

***

#### 4. Multiple File Systems

**Linux supports many file systems:**

| File System | Use Case | Key Features |
|-------------|----------|--------------|
| **ext4** | Default on most Linux | Journaling, large files (16 TB), backwards compatible |
| **XFS** | High-performance servers | Excellent for large files, parallel I/O |
| **Btrfs** | Next-generation | Copy-on-write, snapshots, compression |
| **ext3** | Legacy | Journaling, stable |
| **FAT32** | USB drives, compatibility | Simple, works on Windows/Mac |
| **NTFS** | Windows interoperability | Read/write with ntfs-3g driver |

***

#### 5. Shell Scripting and Automation

**Shell Scripts:** Automate repetitive tasks.

**Example: Backup Script**
```bash
#!/bin/bash
# backup.sh - Automated backup script

BACKUP_DIR="/backup"
SOURCE_DIR="/home/user/documents"
DATE=$(date +%Y-%m-%d)

# Create backup with date
tar -czf "$BACKUP_DIR/backup-$DATE.tar.gz" "$SOURCE_DIR"

echo "Backup completed: backup-$DATE.tar.gz"

# Delete backups older than 7 days
find "$BACKUP_DIR" -name "backup-*.tar.gz" -mtime +7 -delete
```

**Automation with cron:**
```bash
# Edit crontab
crontab -e

# Run backup daily at 2 AM
0 2 * * * /home/user/backup.sh
```

***

#### 6. Strong Security (File Permissions)

**Permission System:**
```
Every file/directory has permissions for:
- Owner (user)
- Group
- Others

Three permission types:
- r (read): 4
- w (write): 2
- x (execute): 1
```

**Example:**
```bash
$ ls -l file.txt
-rw-r--r-- 1 alice developers 1024 Nov 27 file.txt
 │││ │││ │││
 │││ │││ └──── Others: r-- (read only) = 4
 │││ └──────── Group: r-- (read only) = 4
 └──────────── Owner: rw- (read, write) = 6

Permission: 644 (octal notation)
```

**Changing Permissions:**
```bash
# Symbolic notation
chmod u+x file.sh      # Add execute for owner
chmod g-w file.txt     # Remove write for group
chmod o=r file.txt     # Set others to read-only

# Numeric notation
chmod 755 script.sh    # rwxr-xr-x (owner: all, group/others: read+execute)
chmod 600 private.key  # rw------- (owner only)
chmod 777 public.file  # rwxrwxrwx (all permissions for everyone - dangerous!)
```

***

### Linux System Calls

System calls provide the **interface between user programs and kernel**.

#### Common System Calls Table

| System Call | Purpose | Example Usage |
|-------------|---------|---------------|
| **fork()** | Creates a new process | Shell launching commands |
| **exec()** | Executes a new program | Replace process image |
| **read()** | Reads data from file descriptor | Read file contents |
| **write()** | Writes data to file descriptor | Write to log file |
| **open()** | Opens a file | Open /etc/passwd |
| **close()** | Closes a file | Clean up file descriptor |
| **wait()** | Waits for child process | Parent waits for child |
| **exit()** | Terminates a process | Exit with code 0 |
| **kill()** | Sends signal to process | kill -9 (SIGKILL) |

***

#### System Call Examples

**Example 1: Reading a File**
```c
#include <fcntl.h>
#include <unistd.h>

int main() {
    int fd = open("data.txt", O_RDONLY);  // System call: open()
    if (fd == -1) {
        perror("open failed");
        return 1;
    }
    
    char buffer[100];
    ssize_t bytes_read = read(fd, buffer, 100);  // System call: read()
    
    write(STDOUT_FILENO, buffer, bytes_read);  // System call: write()
    
    close(fd);  // System call: close()
    return 0;
}
```

**Example 2: Process Creation**
```c
#include <sys/wait.h>
#include <unistd.h>

int main() {
    pid_t pid = fork();  // System call: fork()
    
    if (pid == 0) {
        // Child
        execl("/bin/echo", "echo", "Hello from child", NULL);  // System call: exec()
    } else {
        // Parent
        wait(NULL);  // System call: wait()
        printf("Child finished\n");
    }
    
    exit(0);  // System call: exit()
}
```

***

### Linux Kernel: Monolithic with Modules

**Monolithic Kernel:**
```
All essential OS services run in kernel mode:
- Process scheduling
- Memory management
- File systems
- Device drivers
- Network stack

Benefits:
✅ Fast (no context switches between components)
✅ Efficient communication (shared address space)

Drawbacks:
❌ Large kernel size
❌ One driver crash can crash entire kernel
```

**Loadable Kernel Modules (LKMs):**
```
Kernel modules can be loaded/unloaded dynamically
WITHOUT rebooting

Examples:
- Device drivers (USB, network cards)
- File system drivers (ext4, NTFS)
- Network protocols

Commands:
lsmod                    # List loaded modules
insmod module.ko         # Load module
rmmod module             # Unload module
modprobe driver_name     # Load with dependencies
```

**Example:**
```bash
# Check if USB storage module loaded
$ lsmod | grep usb_storage
usb_storage    73728  0

# Unload it
$ sudo rmmod usb_storage

# Reload it
$ sudo modprobe usb_storage
```

***

### Linux Scheduling: Completely Fair Scheduler (CFS)

**CFS Algorithm:**
```
Goal: Fair CPU time distribution among all processes

Key Concept: Virtual Runtime (vruntime)
- Each process has vruntime (total CPU time received)
- Scheduler picks process with MINIMUM vruntime
- After running, vruntime increases
- Result: All processes get equal CPU time (over long run)
```

**Red-Black Tree:**
```
CFS uses red-black tree (self-balancing BST)
- Left-most node = process with minimum vruntime
- Insertion: O(log n)
- Pick next: O(1) (just get leftmost)

Tree structure:
            vruntime=50
           /           \
    vruntime=30    vruntime=70
    /         \
vruntime=20  vruntime=40

Leftmost = vruntime 20 → schedule this process
```

**Priority (Nice Values):**
```
Nice values: -20 (highest priority) to +19 (lowest)
Default: 0

Effect on scheduling:
- Lower nice → more CPU time
- Higher nice → less CPU time

Command:
nice -n 10 ./program    # Run with nice value 10
renice -n 5 -p 1234     # Change nice of PID 1234 to 5
```

***

### Linux Memory Management

**Virtual Memory:**
```
Each process has own virtual address space:
0x00000000 - 0xBFFFFFFF: User space (3 GB)
0xC0000000 - 0xFFFFFFFF: Kernel space (1 GB)

Process cannot access kernel space from user mode
```

**Paging and Segmentation:**
```
Linux primarily uses PAGING
Segmentation minimal (compatibility with x86)

Page size: 4 KB (default)
Huge pages: 2 MB or 1 GB (for databases, VMs)
```

**Demand Paging:**
```
Pages loaded only when accessed (like Windows)
On page fault:
1. Check if address valid
2. Allocate physical page frame
3. Load from disk (swap or binary)
4. Update page table
5. Resume process
```

**Swap Space:**
```
Dedicated partition or file for paging
Common configurations:
- Swap partition: /dev/sda2
- Swap file: /swapfile

Check swap:
$ free -h
              total        used        free
Mem:           7.7G        3.2G        4.5G
Swap:          2.0G        100M        1.9G

Enable/disable:
$ sudo swapon /swapfile     # Enable
$ sudo swapoff /swapfile    # Disable
```

***

### Linux Permission System (Detailed)

**File Permissions Breakdown:**
```
$ ls -l /bin/bash
-rwxr-xr-x 1 root root 1183448 Jun 18  2020 /bin/bash
│││││││││
│││││││└┴──── Others: r-x (read, execute) = 5
│││││└┴────── Group: r-x (read, execute) = 5
│││└┴──────── Owner: rwx (read, write, execute) = 7
││└────────── Number of hard links
│└─────────── File type: - (regular file)
              d (directory), l (symlink), c (char device), b (block device)
```

**Special Permissions:**
```
SUID (Set User ID): 4000
- Run with owner's permissions (not caller's)
- Example: /usr/bin/passwd (needs root to change passwords)
  -rwsr-xr-x (s in owner execute)

SGID (Set Group ID): 2000
- Run with group's permissions
- On directory: New files inherit directory's group
  drwxrws--- (s in group execute)

Sticky Bit: 1000
- On directory: Only owner can delete own files
- Example: /tmp
  drwxrwxrwt (t in others execute)
```

**Example:**
```bash
$ ls -ld /tmp
drwxrwxrwt 20 root root 4096 Nov 27 /tmp
         ↑
    Sticky bit: Anyone can write, but only owner can delete own files
```

***

### Linux Case Scenario Analysis

**Scenario:** Start-up deploys web server on Ubuntu Linux. During peak hours, website slows down and server becomes unresponsive.

#### Problem Identification

**1. High CPU Usage from Apache Processes:**
```
Multiple Apache worker processes handling concurrent requests
Each worker consumes CPU for request processing

Check with:
$ top
  PID USER      PR  NI    VIRT    RES  %CPU %MEM     TIME+ COMMAND
 1234 www-data  20   0  500M    50M  25.0  5.0   0:15.23 apache2
 1235 www-data  20   0  500M    50M  24.0  5.0   0:14.89 apache2
 ...
```

**2. Cached Memory Usage:**
```
Linux uses free memory for disk cache
During high load, cache fills up
Looks like "high memory usage" but it's actually cache

Check with:
$ free -h
              total        used        free      shared  buff/cache   available
Mem:           7.7G        2.0G        1.0G        100M        4.7G        5.2G

"used" = active applications (2 GB)
"buff/cache" = disk cache (4.7 GB) - reclaimable
"available" = actually available (5.2 GB)
```

**3. Inefficient Load Balancing:**
```
Single server handling all requests
No distribution across multiple backends
Bottleneck at single point
```

***

#### Solutions

**1. Configure Swap Space:**
```bash
# Create 2 GB swap file
sudo fallocate -l 2G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile

# Make permanent
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab

# Adjust swappiness (tendency to swap)
sudo sysctl vm.swappiness=10  # Low (prefer RAM)
```

**2. Use Monitoring Tools:**
```bash
# Real-time process monitoring
top          # Basic process monitor
htop         # Enhanced, colorful
glances      # More metrics

# Memory statistics
free -h      # Memory usage summary
vmstat 1     # Virtual memory stats every 1 second

# Disk I/O
iostat       # Disk statistics
iotop        # I/O by process

# Network
netstat -tuln  # Active connections
ss -tuln       # Modern alternative to netstat
```

**Example vmstat output:**
```
$ vmstat 1
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
 2  0      0 1024000  50000 4700000    0    0    10   100  500 1000 25 5 70  0  0
 ↑     ↑                              ↑    ↑                    ↑  ↑  ↑
 r: processes waiting for CPU         si: swap in              us: user CPU %
 b: processes in uninterruptible sleep so: swap out            sy: system CPU %
                                                                id: idle %
```

**3. Implement Load Balancing:**
```
Using Nginx as reverse proxy / load balancer:

Configuration (/etc/nginx/nginx.conf):
upstream backend {
    server 192.168.1.101:8080;  # Backend server 1
    server 192.168.1.102:8080;  # Backend server 2
    server 192.168.1.103:8080;  # Backend server 3
}

server {
    listen 80;
    location / {
        proxy_pass http://backend;
    }
}

Benefit:
- Distributes load across 3 servers
- If one fails, traffic goes to others (high availability)
- Can handle 3× traffic
```

**Alternative: HAProxy**
```
Configuration (/etc/haproxy/haproxy.cfg):
frontend http_front
    bind *:80
    default_backend http_back

backend http_back
    balance roundrobin
    server server1 192.168.1.101:8080 check
    server server2 192.168.1.102:8080 check
    server server3 192.168.1.103:8080 check
```

***

### Short Questions (Linux)

**Q1: Explain Linux architecture in detail.**

**Answer:**
Linux architecture has 5 layers: (1) **Hardware** - physical devices (CPU, RAM, I/O); (2) **Kernel** - monolithic core managing CPU scheduling (CFS), memory (paging), devices, and system calls; (3) **System Libraries** - glibc providing standard functions and system call wrappers; (4) **System Utilities** - command-line tools for file/process management (ls, ps, top); (5) **User Interface** - shells (bash, zsh) and GUIs (GNOME, KDE). Kernel supports loadable modules for dynamic driver loading without rebooting.

***

**Q2: Describe the functions of fork() and exec() system calls.**

**Answer:**
**fork()** creates a child process that is a duplicate of the parent, returning 0 in the child and the child's PID in the parent. Both processes continue from the next line with separate memory spaces. **exec()** replaces the current process image with a new program without creating a new process. Common pattern: fork() to create child, then exec() in child to run a different program while parent wait()s. This is how shells run commands.

***

**Q3: How does Linux implement multitasking?**

**Answer:**
Linux uses **preemptive multitasking** with the Completely Fair Scheduler (CFS). CFS tracks virtual runtime (vruntime) for each process and always schedules the process with minimum vruntime, ensuring fair CPU distribution. Processes are stored in a red-black tree for efficient O(log n) insertion and O(1) selection. Nice values (-20 to +19) adjust priority: lower values get more CPU time. Time-slicing with configurable quantum (typically 10-15 ms) allows rapid context switching, creating the illusion of parallelism.

***

**Q4: What are the advantages of the Linux file permission system?**

**Answer:**
Linux file permissions provide strong security through: (1) **Granular control** - separate permissions for owner, group, and others; (2) **Three permission types** - read, write, execute (numeric: 4, 2, 1); (3) **Special permissions** - SUID (run as owner), SGID (run as group), sticky bit (only owner can delete); (4) **Protection** - prevents unauthorized access and accidental deletion; (5) **Flexibility** - easily modified with chmod/chown. Example: chmod 755 gives owner full access while limiting others to read+execute.

***

**Q5: What is the role of shell scripting in Linux?**

**Answer:**
Shell scripting automates repetitive tasks using bash/sh scripts. Scripts combine Linux commands, control structures (if/while/for), variables, and functions to create powerful automation tools. Common uses: (1) **System administration** - automated backups, log rotation, user management; (2) **Batch processing** - processing multiple files; (3) **Monitoring** - checking system health, alerting; (4) **Deployment** - automated software installation. Scripts can be scheduled with cron for periodic execution, significantly improving efficiency and reducing human error.

***
Continuing Unit 6 revision sheet:

***

## CASE STUDY 3: UNIX OPERATING SYSTEM

### Introduction

**UNIX** is a multiuser, multitasking operating system developed at **AT&T Bell Labs in 1969** by Ken Thompson and Dennis Ritchie. It became the foundation for modern operating systems including Linux, Solaris, macOS, and BSD variants. UNIX emphasizes **simplicity, security, and portability**.

**Key Principles:**
- Everything is a file (even devices)
- Small, focused utilities that do one thing well
- Pipes for combining programs
- Portability through C language

***

### UNIX Architecture (4-Layer Model)

```
┌─────────────────────────────────────────────┐
│   Layer 4: APPLICATION LAYER                │
│   (External applications, user programs)    │
├─────────────────────────────────────────────┤
│   Layer 3: SHELL COMMANDS                   │
│   (cp, mv, cat, grep, id, wc, nroff, etc.) │
├─────────────────────────────────────────────┤
│   Layer 2: KERNEL                           │
│   (Process, Memory, File, Network Mgmt)     │
├─────────────────────────────────────────────┤
│   Layer 1: HARDWARE                         │
│   (CPU, Memory, Disk, I/O devices)          │
└─────────────────────────────────────────────┘
```

***

#### Layer 1: Hardware

**Definition:** All hardware-related information including CPU, memory, storage devices, and peripherals.

**Components:**
- **CPU:** Executes instructions
- **Memory:** RAM for active processes
- **Storage:** Hard drives, SSDs
- **I/O Devices:** Keyboard, mouse, display, network cards

***

#### Layer 2: Kernel

**Definition:** The core of the operating system acting as the **interface between hardware and software**.

**Key Responsibilities:**

**1. Process Management:**
```
- Process creation (fork())
- Process scheduling (time-sharing)
- Context switching
- Inter-process communication (IPC)
- Process termination

Each process has unique PID (Process ID)
```

**Example:**
```c
// Process hierarchy
init (PID 1)
├─ login (PID 234)
│  └─ bash (PID 567)
│     └─ ls (PID 890)
└─ sshd (PID 345)
   └─ bash (PID 678)
```

**2. Memory Management:**
```
Uses segmentation AND paging

Segmentation:
- Text segment (code)
- Data segment (initialized data)
- BSS segment (uninitialized data)
- Stack segment
- Heap segment

Paging:
- Demand paging
- Page replacement (LRU, Clock)
- Swapping to disk when memory full
```

**Virtual Address Space:**
```
High Address
┌─────────────────┐
│     Stack       │ ← Grows downward
│       ↓         │
├─────────────────┤
│   (Free space)  │
├─────────────────┤
│       ↑         │
│     Heap        │ ← Grows upward (malloc)
├─────────────────┤
│  BSS (uninit)   │
├─────────────────┤
│  Data (init)    │
├─────────────────┤
│  Text (code)    │ ← Read-only
└─────────────────┘
Low Address (0x00000000)
```

**3. File Management:**
```
Hierarchical file system with / as root

Directory structure:
/
├── bin/     (Essential binaries)
├── etc/     (Configuration files)
├── home/    (User home directories)
├── usr/     (User programs)
├── var/     (Variable data: logs)
└── dev/     (Device files)

File operations:
- Create, read, write, delete
- Permissions and ownership
- Inode-based (metadata separate from data)
```

**4. Network Management:**
```
TCP/IP stack integrated in kernel
Sockets for network communication
Network device drivers

Example:
Application → Socket API → TCP/UDP → IP → Network Driver → Hardware
```

***

#### Layer 3: Shell Commands

**Definition:** Interface between **user and kernel**. Shell interprets commands and calls programs.

**Shell Types:**
```
- Bourne Shell (sh): Original shell
- C Shell (csh): C-like syntax
- Korn Shell (ksh): Enhanced sh
- Bash: Most popular (Linux default)
```

**Common Commands:**

**File Operations:**
```bash
cp file1 file2        # Copy file
mv old new            # Move/rename file
cat file.txt          # Display file contents
grep "pattern" file   # Search in file
```

**Process Commands:**
```bash
ps                    # List processes
ps aux                # Detailed process list
kill -9 PID           # Kill process
nice -n 10 ./prog     # Run with lower priority
```

**System Commands:**
```bash
id                    # Show user/group IDs
wc file.txt           # Word count (lines, words, bytes)
nroff file.ms         # Text formatting
a.out                 # Execute compiled program
```

**Pipes and Redirection:**
```bash
# Pipe: Output of one command → Input of another
ls -l | grep ".txt" | wc -l    # Count .txt files

# Redirection
command > file.txt              # Redirect output to file (overwrite)
command >> file.txt             # Append to file
command 2> errors.txt           # Redirect errors
command < input.txt             # Read input from file
```

***

#### Layer 4: Application Layer

**Definition:** Outermost layer that executes external applications (user programs).

**Examples:**
- Text editors: vi, emacs
- Compilers: gcc, cc
- Databases: Oracle (on Solaris)
- Web servers: Apache
- Custom applications

**User programs interact with kernel via:**
```
Application → System Libraries (libc) → System Calls → Kernel
```

***

### Key Features of UNIX

#### 1. Multiuser and Multitasking

**Multiuser:**
```
Multiple users can log in and work simultaneously
Each user isolated from others

Example:
Terminal 1: user alice
Terminal 2: user bob
Terminal 3: root (admin)

All working concurrently on same system
```

**User Management:**
```bash
# User database
/etc/passwd   # User accounts
/etc/shadow   # Encrypted passwords
/etc/group    # Group memberships

# Commands
useradd username      # Add user
passwd username       # Set password
usermod -aG group user # Add user to group
userdel username      # Delete user
```

**Multitasking:**
```
Multiple processes run "simultaneously" via time-sharing
Scheduler allocates CPU slices to each process
Priority-based scheduling (nice values)

Example:
Process A: 20 ms → Process B: 20 ms → Process C: 20 ms → repeat
```

***

#### 2. Device Independence

**Key Principle:** All devices are treated as files.

**Device Files (in /dev/):**
```bash
/dev/sda        # First SATA disk (block device)
/dev/tty1       # First terminal (character device)
/dev/null       # Null device (discards all data)
/dev/zero       # Produces infinite zeros
/dev/random     # Random number generator
/dev/cdrom      # CD-ROM drive

Example:
# Write to disk like a file
echo "data" > /dev/sda1

# Read from keyboard like a file
cat < /dev/tty

# Discard output
command > /dev/null  # Send output to black hole
```

**Block vs Character Devices:**
```
Block Devices:
- Access in fixed-size blocks (e.g., 512 bytes, 4 KB)
- Buffered I/O
- Random access
- Examples: Hard disks, USB drives

Character Devices:
- Access one character/byte at a time
- Unbuffered I/O
- Sequential access
- Examples: Terminals, serial ports, keyboards
```

**Unified Interface:**
```c
// Same system calls work for ALL devices
int fd = open("/dev/sda1", O_RDONLY);  // Open disk
int fd = open("/dev/tty", O_RDWR);     // Open terminal
int fd = open("file.txt", O_RDONLY);   // Open regular file

// All use: read(), write(), close()
```

**Benefit:** Simplicity and consistency. No special APIs for different devices.

***

#### 3. Strong File and Process Security

**File Permissions:**
```
Same as Linux (UNIX is the origin)

Owner - Group - Others
rwx     rwx     rwx

Example:
-rw-r--r--  alice  staff  file.txt
Owner (alice): read, write
Group (staff): read only
Others: read only
```

**Access Control:**
```bash
chmod 600 secret.txt    # Only owner can read/write
chmod 755 script.sh     # Owner: all, others: read+execute
chown bob file.txt      # Change owner to bob
chgrp users file.txt    # Change group to users
```

**Process Security:**
```
Each process runs with:
- Real UID (user who started it)
- Effective UID (privileges it has)
- Saved UID (for privilege elevation/drop)

SUID programs:
- Run with owner's privileges (not caller's)
- Example: /bin/passwd needs root to modify /etc/shadow

Security check on every:
- File access
- Process signal
- Resource allocation
```

***

#### 4. Hierarchical File System

**Structure:**
```
Root (/) at top, everything beneath

/
├── bin/          Essential binaries (ls, cp, cat)
├── sbin/         System binaries (admin tools)
├── etc/          Configuration files
│   ├── passwd    User accounts
│   └── hosts     Hostname mappings
├── home/         User home directories
│   ├── alice/
│   └── bob/
├── usr/          User programs
│   ├── bin/      User commands
│   ├── lib/      Libraries
│   └── local/    Locally installed software
├── var/          Variable data
│   ├── log/      Log files
│   └── spool/    Print queue, mail
├── tmp/          Temporary files
└── dev/          Device files
```

**Path Types:**
```bash
# Absolute path (starts with /)
/home/alice/documents/report.pdf

# Relative path (from current directory)
documents/report.pdf
../alice/photos/pic.jpg

# Special directories
.     # Current directory
..    # Parent directory
~     # Home directory
~bob  # Bob's home directory
```

***

#### 5. Command-Line Interface and Shell Scripting

**Command-Line Interface (CLI):**
```
Primary interface for UNIX
Powerful, efficient for experienced users
Steeper learning curve than GUI
```

**Shell Scripting:**
```bash
#!/bin/sh
# Script to monitor disk usage and alert if > 80%

THRESHOLD=80
USAGE=$(df -h / | tail -1 | awk '{print $5}' | sed 's/%//')

if [ $USAGE -gt $THRESHOLD ]; then
    echo "WARNING: Disk usage is ${USAGE}%"
    echo "Disk critical!" | mail -s "Disk Alert" admin@example.com
else
    echo "Disk usage OK: ${USAGE}%"
fi
```

**Automation:**
```bash
# Schedule with cron
crontab -e

# Run disk check every hour
0 * * * * /home/admin/check_disk.sh

# Backup daily at 3 AM
0 3 * * * /home/admin/backup.sh
```

***

#### 6. Portability and Scalability

**Portability:**
```
UNIX written in C (portable language)
Can be compiled for different architectures:
- Intel x86/x64
- ARM
- SPARC
- PowerPC

Same UNIX on:
- Workstations
- Servers
- Supercomputers
- Embedded systems
```

**Scalability:**
```
Scales from:
- Single-user workstation
- Small servers (10-100 users)
- Large mainframes (1000+ users)
- Clusters and supercomputers

Example:
UNIX used on IBM mainframes handling thousands of concurrent users
```

***

### UNIX System Calls

UNIX system calls are similar to Linux (Linux evolved from UNIX).

#### System Call Table

| System Call | Purpose | Example |
|-------------|---------|---------|
| **fork()** | Creates a child process | Shell launching command |
| **exec()** | Executes a new program | Load /bin/ls |
| **wait()** | Waits for process termination | Parent waits for child |
| **open()** | Opens a file | open("data.txt", O_RDONLY) |
| **read()** | Reads from a file | Read 100 bytes |
| **write()** | Writes to a file | Write log entry |
| **close()** | Closes a file | Clean up file descriptor |
| **kill()** | Sends signals to processes | kill(pid, SIGTERM) |
| **chmod()** | Changes file permissions | Make executable |

***

#### System Call Examples

**Example 1: File I/O**
```c
#include <fcntl.h>
#include <unistd.h>

int main() {
    int fd = open("/etc/passwd", O_RDONLY);  // Open file
    if (fd == -1) {
        perror("open");
        return 1;
    }
    
    char buffer[256];
    ssize_t bytes = read(fd, buffer, sizeof(buffer));  // Read
    
    write(STDOUT_FILENO, buffer, bytes);  // Write to stdout
    
    close(fd);  // Close file
    return 0;
}
```

**Example 2: Process Control**
```c
#include <sys/types.h>
#include <sys/wait.h>
#include <unistd.h>
#include <stdio.h>

int main() {
    pid_t pid = fork();  // Create child
    
    if (pid == 0) {
        // Child process
        printf("Child PID: %d\n", getpid());
        execl("/bin/ls", "ls", "-l", NULL);  // Execute ls
        perror("exec failed");  // Only if exec fails
    } else if (pid > 0) {
        // Parent process
        printf("Parent waiting for child %d\n", pid);
        wait(NULL);  // Wait for child to finish
        printf("Child terminated\n");
    }
    
    return 0;
}
```

**Example 3: Signal Handling**
```c
#include <signal.h>
#include <unistd.h>
#include <stdio.h>

void handler(int sig) {
    printf("Caught signal %d\n", sig);
}

int main() {
    signal(SIGINT, handler);  // Register handler for Ctrl+C
    
    printf("Running... Press Ctrl+C to test\n");
    while (1) {
        sleep(1);
    }
    
    return 0;
}
```

**Example 4: chmod() - Change Permissions**
```c
#include <sys/stat.h>

int main() {
    // Set permissions to rwxr-xr-x (755)
    chmod("/path/to/script.sh", S_IRWXU | S_IRGRP | S_IXGRP | S_IROTH | S_IXOTH);
    
    // Simpler: Use octal
    chmod("/path/to/script.sh", 0755);
    
    return 0;
}
```

***

### UNIX Kernel: Monolithic with Layered Design

**Monolithic Kernel:**
```
All OS services in kernel space:
- Process management
- Memory management
- File system
- Device drivers
- Networking

Benefits:
✅ Fast (minimal context switching)
✅ Efficient (shared address space)

Drawbacks:
❌ Large kernel
❌ Less modular than microkernel
```

**Layered Design:**
```
Kernel organized in layers:

Layer N: User processes
Layer N-1: I/O buffering
Layer N-2: Console driver
Layer N-3: Memory management
Layer N-4: CPU scheduling
Layer 0: Hardware

Each layer uses services of layer below
Provides abstraction to layer above
```

***

### UNIX Process Management and Scheduling

**Process Identification:**
```
Each process has unique PID (Process ID)

Special PIDs:
PID 0: Scheduler/Swapper (kernel process)
PID 1: init (first user process, parent of all)

Process hierarchy forms tree:
init (1)
├─ getty (login prompts)
├─ cron (scheduled tasks)
└─ user shells
   └─ user processes
```

**Process States:**
```
┌─────────┐   fork()   ┌─────────┐
│ Running │──────────→ │ Created │
└────┬────┘            └────┬────┘
     │                      │
     │                      ↓
     │                 ┌─────────┐
     │                 │  Ready  │ ← Waiting for CPU
     │                 └────┬────┘
     │                      │
     │  ← Scheduled ────────┘
     │
     ├──────────→ ┌─────────┐
     │  I/O wait  │ Blocked │ (Waiting for I/O)
     │ ←──────────└─────────┘
     │
     ↓
┌──────────┐
│ Zombie   │ (Terminated, waiting for parent to read exit status)
└──────────┘
```

**Scheduling:**
```
Time-sharing system with priority scheduling

Priority Calculation:
Priority = Base_priority + Nice_value + CPU_usage

- Lower priority number = higher priority
- Processes with higher priority get more CPU
- CPU usage increases priority number (lowers priority)
  → Prevents CPU-bound processes from monopolizing

Nice values:
-20 (highest priority) to +19 (lowest)
Default: 0
```

**Context Switch:**
```
1. Save state of current process (registers, PC, SP)
2. Update process table
3. Select next process (highest priority ready)
4. Restore state of selected process
5. Resume execution

Frequency: ~100-1000 times per second
Overhead: ~1-10 microseconds
```

***

### UNIX File System Details

**Inode Structure:**
```
Inode = Index Node (metadata for file)

Inode contains:
- File type (regular, directory, device, symlink)
- Permissions (rwx for owner/group/others)
- Owner UID, Group GID
- File size
- Timestamps (atime, mtime, ctime)
- Link count (number of hard links)
- Pointers to data blocks

Inode does NOT contain:
- Filename (stored in directory entry)
```

**Directory Structure:**
```
Directory = Special file containing (filename, inode) pairs

Example /home/alice:
┌──────────────┬────────┐
│   Filename   │ Inode# │
├──────────────┼────────┤
│      .       │  1234  │  (current dir)
│      ..      │   500  │  (parent /home)
│  file.txt    │  5678  │
│  photo.jpg   │  9012  │
└──────────────┴────────┘
```

**Hard Links vs Symbolic Links:**
```
Hard Link:
- Multiple directory entries → same inode
- Delete one link, file still exists (until link count = 0)
- Cannot cross file systems
- Cannot link directories (prevents cycles)

Example:
ln /home/alice/original /home/bob/link
(Both entries point to same inode)

Symbolic Link (Symlink):
- Special file containing path to target
- Can cross file systems
- Can link directories
- If target deleted, symlink "breaks" (dangling)

Example:
ln -s /home/alice/original /home/bob/link
(Creates new file containing "/home/alice/original")
```

***

### UNIX Security

**File Permissions:**
```
Three levels: Owner, Group, Others
Three permissions: Read, Write, Execute

Example:
-rwxr-xr--  1  alice  staff  1024  Nov 27  script.sh
 ││││││││││
 │││││││││└─ Others: r-- (read only)
 ││││││└──── Group: r-x (read, execute)
 │││└──────── Owner: rwx (all permissions)
 ││└───────── Link count: 1
 │└────────── File type: - (regular file)
 
Numeric: 754
Owner: 7 (rwx)
Group: 5 (r-x)
Others: 4 (r--)
```

**User Authentication:**
```
/etc/passwd format:
username:x:UID:GID:comment:home:shell

alice:x:1001:1001:Alice Smith:/home/alice:/bin/bash
│     │  │    │    │            │            │
│     │  │    │    │            │            └─ Login shell
│     │  │    │    │            └─ Home directory
│     │  │    │    └─ Full name
│     │  │    └─ Primary group ID
│     │  └─ User ID
│     └─ Password (x = stored in /etc/shadow)
└─ Username

/etc/shadow (encrypted passwords):
alice:$6$random$encryptedpasswordhash:18500:0:99999:7:::
```

**Security via chmod, chown:**
```bash
# Change permissions
chmod 600 secret.txt     # rw------- (owner only)
chmod u+x script.sh      # Add execute for owner
chmod g-w file.txt       # Remove write for group
chmod o=r public.txt     # Set others to read-only

# Change ownership
chown alice file.txt          # Change owner
chown alice:staff file.txt    # Change owner and group
chgrp developers project.c    # Change group only

# Recursive
chmod -R 755 /var/www/html    # Apply to directory and all contents
chown -R www-data:www-data /var/www  # Recursive ownership change
```

**User Groups:**
```
Allow sharing files among team members

Example:
Group "developers" contains: alice, bob, charlie

/project/code.c  owner=alice, group=developers, permissions=rw-rw-r--
→ alice, bob, charlie can all read and write
→ Others can only read

Commands:
groups           # Show current user's groups
groups alice     # Show alice's groups
newgrp staff     # Switch primary group
```

***

### UNIX Case Scenario Analysis

**Scenario:** Research institution uses UNIX-based Solaris systems for data analysis. Multiple users execute computationally heavy programs, leading to delays and performance bottlenecks.

#### Problem Identification

**1. Multiple Processes, High CPU Load:**
```
Several users running compute-intensive tasks simultaneously

Example:
user1: MATLAB simulation (100% CPU, 2 hours)
user2: Python data analysis (100% CPU, 1 hour)
user3: R statistical modeling (100% CPU, 3 hours)

Total CPU demand: 300% of single CPU
Available: 100% (or N×100% for N cores)

Result: Processes compete for CPU, each slows down
```

**Check with:**
```bash
# Show processes sorted by CPU usage
ps aux --sort=-%cpu | head -20

# Real-time monitoring
top
# Look for processes with %CPU near 100

# System load average
uptime
# Output: load average: 8.5, 7.2, 6.8 (1, 5, 15 min averages)
# If load > number of CPUs → overloaded
```

**2. Limited Physical Memory → Excessive Swapping:**
```
Large datasets don't fit in RAM
OS constantly swaps pages between RAM and disk
Disk I/O much slower than RAM → thrashing

Example:
Physical RAM: 16 GB
user1 process: 8 GB
user2 process: 6 GB
user3 process: 5 GB
Total needed: 19 GB > 16 GB available

Result: Constant paging, system crawls
```

**Check with:**
```bash
# Memory usage
vmstat 1
# Watch "si" (swap in) and "so" (swap out)
# High values → excessive swapping

# Swap usage
swap -s
# Output: total: 8GB, used: 7.5GB (94% used!)

# Per-process memory
ps aux --sort=-%mem | head -10
```

**3. Disk Quotas Exceeded:**
```
Users store large result files
Disk fills up → new processes cannot write output
System errors, data loss risk

Example:
User quota: 50 GB
User actual usage: 52 GB → quota exceeded
New results: Cannot be saved
```

**Check with:**
```bash
# Check user quotas
quota -v username

# Check disk usage
df -h
# Look for 100% usage

# Find large files
du -sh /home/user1/*
find /home/user1 -type f -size +1G
```

***

#### Solutions

**1. Use nice and renice (Process Priority Management):**
```bash
# Run low-priority job (nice value +19)
nice -n 19 ./heavy_computation.sh

# Adjust priority of running process
renice -n 10 -p 1234  # Set PID 1234 to nice value 10

# Strategy:
# - Critical jobs: nice -20 to -10 (high priority)
# - Normal jobs: nice 0 (default)
# - Background/batch: nice 10 to 19 (low priority)

Example:
# User1's critical analysis
nice -n -5 matlab -r "critical_analysis"

# User2's exploratory work
nice -n 15 python explore.py

Result: Critical job gets more CPU time
```

**How it works:**
```
Scheduler calculates dynamic priority:
priority = base_priority + nice_value + cpu_usage

Lower priority number → higher priority → more CPU time

Example:
Process A: nice = 0,  priority = 50 + 0 = 50
Process B: nice = 10, priority = 50 + 10 = 60

Process A has lower number (50 < 60) → higher priority → scheduled more often
```

**2. Implement User Disk Quotas:**
```bash
# Enable quotas on file system
# Edit /etc/fstab
/dev/sda1  /home  ext4  defaults,usrquota,grpquota  0  2

# Remount
mount -o remount /home

# Create quota files
quotacheck -cum /home

# Turn on quotas
quotaon /home

# Set quota for user (soft: 50GB, hard: 60GB)
edquota -u username
# Edit:
# Disk quotas for user username:
# Filesystem  blocks  soft   hard  inodes  soft  hard
# /dev/sda1   10000   51200  61440  1000   0     0
#                     (50GB) (60GB)

# Grace period (7 days to reduce from soft to hard limit)
edquota -t

# Check usage
quota -v username
repquota /home
```

**Benefits:**
- Prevents single user from filling disk
- Enforces fair resource sharing
- Warns users before hitting limit (soft quota)

**3. Schedule Batch Jobs During Low-Usage Periods:**
```bash
# Use at command for one-time scheduled jobs
echo "./data_analysis.sh" | at 02:00
# Runs at 2 AM when system less busy

# Use cron for recurring jobs
crontab -e
# Add:
0 2 * * * /home/user/batch_job.sh  # Daily at 2 AM
0 3 * * 0 /home/user/weekly.sh     # Weekly on Sunday at 3 AM

# Use batch command (runs when load < threshold)
batch
./heavy_computation.sh
EOF

# Set batch load threshold
atd -l 1.5  # Run batch jobs only when load < 1.5
```

**Strategy:**
```
Peak hours (9 AM - 6 PM):
- Interactive work only
- Short jobs
- High-priority tasks

Off-peak (evenings, weekends):
- Batch processing
- Long-running computations
- Backups

Result: Better resource utilization, smoother interactive performance
```

**4. Additional Optimizations:**
```bash
# Monitor and kill runaway processes
ps aux | grep defunct  # Find zombie processes
kill -9 PID           # Kill if necessary

# Increase swap space
mkswap /dev/sdb1
swapon /dev/sdb1

# Add more physical RAM (hardware upgrade)

# Use process accounting to track usage
accton /var/log/pacct
lastcomm  # Show command history with resource usage

# Load balancing across multiple systems
# Use cluster management (Sun Grid Engine for Solaris)
```

***

### Short Questions (UNIX)

**Q1: Explain the layered architecture of UNIX.**

**Answer:**
UNIX has a 4-layer architecture: (1) **Hardware** - physical components (CPU, memory, I/O); (2) **Kernel** - core OS managing processes (via PID), memory (segmentation + paging), files (hierarchical with /), and networking (TCP/IP); (3) **Shell Commands** - interface between user and kernel, interpreting commands (cp, mv, cat, grep, ps); (4) **Application Layer** - user programs and external applications. The kernel acts as the bridge between hardware and software, providing system calls for applications to request services.

***

**Q2: Describe process management and scheduling in UNIX.**

**Answer:**
UNIX uses **time-sharing** with **priority scheduling**. Each process has a unique PID, with init (PID 1) as the parent of all user processes. Scheduling priority is calculated as base_priority + nice_value + CPU_usage. Lower priority numbers get more CPU time. Nice values range from -20 (highest priority) to +19 (lowest, default 0). The scheduler performs context switches (100-1000/sec) to multiplex CPU among processes. Administrators use `nice` to start processes with specific priority and `renice` to adjust running processes.

***

**Q3: How does UNIX treat hardware devices?**

**Answer:**
UNIX treats **all devices as files** located in `/dev/`. This provides device independence and a unified interface. Devices are either **block devices** (e.g., `/dev/sda` for disks, accessed in fixed blocks with buffering) or **character devices** (e.g., `/dev/tty` for terminals, accessed byte-by-byte without buffering). The same system calls (open, read, write, close) work for all devices, simplifying programming. Special devices like `/dev/null` (discard data) and `/dev/zero` (infinite zeros) provide utility functions. This "everything is a file" philosophy ensures simplicity and consistency.

***

**Q4: Discuss the significance of file permissions in UNIX.**

**Answer:**
File permissions provide **security and access control** at three levels: owner, group, and others, with three permission types (read=4, write=2, execute=1). This allows granular control over who can access files. Special permissions include SUID (run as owner), SGID (run as group), and sticky bit (only owner can delete in shared directories like `/tmp`). Permissions are managed with `chmod` (change mode) and `chown` (change owner). This system prevents unauthorized access, protects system files, and enables collaboration by allowing file sharing within groups while restricting others.

***

**Q5: Compare UNIX and Linux systems.**

**Answer:**
**Similarities:** Both use monolithic kernels, POSIX-compliant system calls, hierarchical file systems with `/` root, and similar command-line tools (bash, ls, ps). Both support multiuser/multitasking, have strong file permissions, and use fork()/exec() for processes.

**Differences:** 
- **Licensing:** UNIX is proprietary (commercial licenses), Linux is open-source (GPL)
- **Development:** UNIX by vendors (Oracle, IBM, HP), Linux by community + companies
- **Variants:** UNIX (Solaris, AIX, HP-UX), Linux (Ubuntu, Fedora, Red Hat)
- **Cost:** UNIX expensive (enterprise), Linux free
- **Portability:** UNIX certified, Linux more flexible

Linux is essentially a UNIX-like system, created to provide UNIX functionality freely.

***

## COMPARATIVE SUMMARY

### Feature-by-Feature Comparison

| Feature | Windows | Linux | UNIX |
|---------|---------|-------|------|
| **Type** | Proprietary (Microsoft) | Open Source (GPL) | Proprietary/Open (varies) |
| **Kernel Type** | **Hybrid** (monolithic + modular) | **Monolithic** (with loadable modules) | **Monolithic** (layered) |
| **User Interface** | **GUI-based** (primary) | **CLI + GUI** (flexible) | **CLI-based** (primary) |
| **Target Users** | Personal, business, gaming | Servers, developers, enthusiasts | Enterprise, research, servers |
| **Cost** | **Paid** (licenses ~$100-300) | **Free** (most distros) | **Paid** (Solaris, AIX) or Free (BSD) |
| **Security** | Moderate (UAC, Windows Defender) | **Strong** (permissions, SELinux) | **Strong** (permissions, auditing) |
| **File System** | **NTFS** (journaling, encryption) | **ext4**, XFS, Btrfs | **UFS** (Unix File System), ZFS |
| **Process Creation** | `CreateProcess()` (create new from exe) | `fork()` + `exec()` (clone then replace) | `fork()` + `exec()` (same as Linux) |
| **Package Management** | Windows Store, manual installers | **apt, yum, pacman** (efficient) | pkg, pkgadd (vendor-specific) |
| **Preferred Use** | Desktops, office, gaming | Servers, cloud, embedded, dev | **Enterprise**, research, mainframes |
| **Market Share** | Desktop: ~75% | Server: ~70%, Desktop: ~3% | Server: ~5% (declining) |
| **Examples** | Windows 10, 11, Server 2022 | Ubuntu, Fedora, Debian, Arch | Solaris, AIX, HP-UX, macOS (BSD-based) |

***

### Detailed Comparisons

#### Kernel Architecture

**Windows (Hybrid):**
```
Combines monolithic + microkernel benefits
Core services in kernel mode (fast)
Subsystems can be modular (Win32, POSIX)
Device drivers in kernel or user mode

Advantage: Balance of performance and stability
```

**Linux (Monolithic with modules):**
```
All services in kernel space
Loadable modules (drivers) can be added/removed
Direct function calls (no message passing)

Advantage: Fast, efficient
Disadvantage: Kernel crash affects entire system
```

**UNIX (Monolithic, layered):**
```
Traditional monolithic design
Layered for organization
All in kernel mode

Advantage: Proven, stable
Disadvantage: Less flexible than hybrid
```

***

#### Security Comparison

**Windows:**
```
UAC (User Account Control): Elevation prompts
Access Tokens: Security context for processes
ACLs (Access Control Lists): Per-file permissions
BitLocker: Disk encryption
Windows Defender: Built-in antivirus

Security Rating: Moderate
Common Target: Yes (desktop malware, ransomware)
```

**Linux:**
```
File Permissions: rwx for owner/group/others
SELinux/AppArmor: Mandatory Access Control (MAC)
Firewall: iptables, firewalld, ufw
No root by default: sudo for elevation
Open source: Community audits code

Security Rating: Strong
Common Target: No (but servers targeted)
```

**UNIX:**
```
File Permissions: Same as Linux (origin)
RBAC (Role-Based Access Control): Solaris
Trusted Computing: HP-UX Trusted Systems
Auditing: Comprehensive logging (BSM)
Certified: Government/military standards

Security Rating: Strong (enterprise-grade)
Common Target: Rare (niche usage)
```

***

#### File Systems

**Windows - NTFS:**
```
Features:
✅ Journaling (crash recovery)
✅ Encryption (EFS)
✅ Compression
✅ Alternate data streams
✅ Large file support (16 EB)
✅ Permissions (ACLs)

Limitations:
❌ Windows-only (limited Linux support)
❌ Fragmentation over time (requires defrag)
```

**Linux - ext4:**
```
Features:
✅ Journaling
✅ Large files (16 TB)
✅ Extents (better performance)
✅ Delayed allocation
✅ Fast fsck (file system check)

Alternatives:
- XFS: Better for large files, parallel I/O
- Btrfs: Snapshots, copy-on-write, compression
```

**UNIX - UFS/ZFS:**
```
UFS (Unix File System):
- Traditional UNIX FS
- Simple, reliable
- Used in BSD, Solaris

ZFS (Zettabyte File System):
- Advanced features: snapshots, RAID-Z, compression
- Copy-on-write (COW)
- Data integrity (checksums)
- Used in modern Solaris, FreeBSD
```

***

#### Process Management

**Windows:**
```
CreateProcess(exe_path, args, ...)
→ Creates NEW process from executable
→ No fork() (can't clone current process)

Threads:
CreateThread() for multithreading
Fibers for lightweight threading

Handles:
Process/thread handles for synchronization
WaitForSingleObject() to wait
```

**Linux/UNIX:**
```
fork()
→ Creates CHILD (clone of parent)
→ Returns 0 in child, child PID in parent

exec()
→ Replaces process image with new program

Typical pattern:
pid = fork();
if (pid == 0) {
    exec("/bin/program");  // Child runs new program
} else {
    wait(NULL);  // Parent waits
}

Advantage: Flexible (can fork without exec, exec without fork)
```

***

#### Use Case Recommendations

**Choose Windows if:**
- Desktop computing (office work, productivity)
- Gaming (most games Windows-only)
- Software requires it (Adobe, Microsoft Office)
- User prefers GUI
- Corporate environment (Active Directory, Exchange)

**Choose Linux if:**
- Running servers (web, database, cloud)
- Software development (compilers, tools)
- Cost-sensitive (free OS)
- Customization needed
- Learning system administration
- Embedded systems / IoT

**Choose UNIX if:**
- Enterprise mission-critical systems
- Mainframe computing
- Require vendor support (Oracle, IBM)
- Regulatory compliance (certified OS)
- Legacy systems already on UNIX
- High-end workstations (scientific computing)

***

### Case Scenario Comparison Questions

**Q1: How can UNIX administrators manage process priorities?**

**Answer:**
UNIX administrators use `nice` and `renice` commands. `nice -n <value> <command>` starts a process with specified priority (-20 to +19, where lower is higher priority). `renice -n <value> -p <PID>` adjusts priority of running process. Example: `nice -n 15 ./background_job.sh` runs a low-priority background task, while `renice -n -5 -p 1234` increases priority of PID 1234. Priority affects scheduler decisions, giving more CPU time to higher-priority processes. This balances system load, ensuring critical tasks complete quickly while background jobs don't interfere.

***

**Q2: What role do disk quotas play in performance management?**

**Answer:**
Disk quotas **prevent resource monopolization** and ensure fair disk usage. By limiting each user's storage (soft limit: warning, hard limit: enforcement), quotas prevent one user from filling the disk and causing system-wide failures. Commands: `edquota -u username` sets quotas, `quota -v` checks usage, `repquota /home` reports all users. Benefits: (1) Prevents disk-full errors; (2) Encourages users to clean up; (3) Ensures availability for all; (4) Identifies storage hogs. In the research scenario, quotas would prevent users from storing excessive result files, maintaining system stability.

***

**Q3: Suggest methods to balance workload among multiple users.**

**Answer:**
**Priority-based scheduling:** Use `nice`/`renice` to give critical users higher priority. **Time-based scheduling:** Run heavy jobs during off-peak hours using `at`, `cron`, or `batch` commands. **Resource quotas:** Limit CPU time (`ulimit -t`), memory (`ulimit -m`), disk space (`edquota`). **Process limits:** Restrict concurrent processes (`ulimit -u`). **Load monitoring:** Use `uptime`, `top`, `vmstat` to identify bottlenecks. **User communication:** Coordinate schedules, stagger intensive jobs. **Hardware upgrades:** Add CPUs, RAM, or use cluster computing (Sun Grid Engine). **Fair scheduling:** Employ fair-share scheduler that equalizes resources per user, not per process.

***

## EXAM TIPS & FINAL CHECKLIST

### Key Comparison Points to Remember

**Memory Trick - "WLU":**
- **W**indows = GUI, Gaming, Business
- **L**inux = Servers, Open source, Developers  
- **U**NIX = Enterprise, Research, Legacy

***

### Quick Reference Tables

**System Calls:**
```
Windows:  CreateProcess(), ReadFile(), WriteFile()
Linux:    fork(), exec(), read(), write()
UNIX:     Same as Linux (Linux is UNIX-like)
```

**Kernels:**
```
Windows:  Hybrid (monolithic + modular)
Linux:    Monolithic + modules
UNIX:     Monolithic + layered
```

**File Systems:**
```
Windows:  NTFS
Linux:    ext4, XFS, Btrfs
UNIX:     UFS, ZFS
```

***

### Common Exam Questions

**Q: Compare process management in Windows, Linux, and Unix. Which OS is more efficient for real-time applications?**

**Answer:**
**Windows:** Uses `CreateProcess()` to create new process from executable. Priority-based preemptive scheduling (32 levels, 0-31). Real-time priority classes (16-31) available. Good for soft real-time (multimedia).

**Linux/UNIX:** Use `fork()` to clone process, `exec()` to replace. CFS scheduler (Linux) or priority scheduler (UNIX). Real-time patches available (PREEMPT_RT). Nice values adjust priority.

**For hard real-time:** UNIX/Linux with real-time kernel extensions more efficient due to:
- Deterministic behavior
- Lower interrupt latency
- Fine-grained control
- Open source (can modify kernel)

**For soft real-time:** Windows adequate (multimedia, gaming).

***

### Mnemonics

**Windows Layers (6):** **"H-K-E-D-S-U"**
- **H**AL, **K**ernel, **E**xecutive, **D**rivers, **S**ubsystems, **U**I

**Linux Layers (5):** **"H-K-L-U-I"**
- **H**ardware, **K**ernel, **L**ibraries, **U**tilities, **I**nterface

**UNIX Layers (4):** **"H-K-S-A"**
- **H**ardware, **K**ernel, **S**hell, **A**pplications

***

### Common Mistakes to Avoid

❌ **Mistake 1:** Confusing fork() and CreateProcess()
- fork() **clones** current process
- CreateProcess() **creates new** from executable

❌ **Mistake 2:** Thinking UNIX and Linux are identical
- Linux is UNIX-**like** (not certified UNIX)
- UNIX is proprietary, Linux is open-source

❌ **Mistake 3:** Saying Windows has no CLI
- Windows has PowerShell, Command Prompt
- Just not primary interface like UNIX/Linux

❌ **Mistake 4:** Forgetting HAL's purpose
- HAL = Hardware independence (not just abstraction)

❌ **Mistake 5:** Confusing nice values
- Lower nice value = **higher** priority (counterintuitive!)
- nice -20 = highest, nice +19 = lowest

***

### Final Checklist for Unit 6

✅ **Can you explain:**
- [ ] Windows 6-layer architecture with HAL's role
- [ ] Linux monolithic kernel with loadable modules
- [ ] UNIX layered architecture and "everything is a file"
- [ ] How fork() + exec() differs from CreateProcess()
- [ ] Security mechanisms in all three OSes
- [ ] Why thrashing occurs and how to fix it (case scenarios)
- [ ] Purpose of spooling, journaling, quotas

✅ **Can you compare:**
- [ ] Hybrid vs Monolithic kernels
- [ ] Windows GUI vs UNIX CLI philosophy
- [ ] NTFS vs ext4 vs UFS/ZFS
- [ ] Process creation mechanisms
- [ ] Security models (UAC vs permissions)
- [ ] Use cases (desktop vs server vs enterprise)

✅ **Can you solve case scenarios:**
- [ ] Identify performance problems (high CPU, memory, disk)
- [ ] Suggest appropriate tools (Task Manager, top, vmstat, quota)
- [ ] Recommend solutions (upgrade RAM, adjust priorities, quotas, load balancing)

***

### Exam Pattern Recognition

**"Compare Windows, Linux, Unix for real-time" → Emphasize determinism**
- UNIX/Linux better for hard real-time (deterministic, low latency)
- Windows adequate for soft real-time (multimedia)

**"Explain architecture" → List layers with brief functions**
- Draw diagram or numbered list
- Mention key components in each layer

**"Case scenario: performance degradation" → Identify + Solutions**
1. State problems (thrashing, high CPU, disk full)
2. Suggest monitoring tools
3. Provide concrete solutions (upgrade, quotas, scheduling)

**"System calls in Windows/Linux/UNIX" → Table format**
- Function name | Purpose | Example
- Minimum 5-6 examples

***

### Connection to Previous Units

**Unit 1 (Introduction):**
- OS functions implemented in Windows/Linux/UNIX
- Kernel vs User mode (all three use this)

**Unit 2 (Processes & Scheduling):**
- Windows: Priority-based preemptive
- Linux: CFS
- UNIX: Time-sharing with priorities
- fork() and exec() in detail

**Unit 3 (Deadlock):**
- All three can experience deadlock
- Prevention/avoidance mechanisms differ

**Unit 4 (Memory):**
- Paging, virtual memory in all three
- Windows: Demand paging, page file
- Linux/UNIX: Swap space

**Unit 5 (I/O & File Systems):**
- NTFS (Windows), ext4 (Linux), UFS/ZFS (UNIX)
- Device files in UNIX/Linux (/dev/)
