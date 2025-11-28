# UNIT 5: I/O MANAGEMENT & DISK SCHEDULING — EXAM REVISION SHEET

## DISK FUNDAMENTALS

### Seek Time and Rotational Latency

Understanding disk mechanics is crucial for optimizing I/O performance.

#### Seek Time

**Definition:** Time taken for the disk **read/write head** to move from its current position to the desired **track (cylinder)**.

**Components:**
```
Seek Time = Startup time + (Distance × per-track movement time) + Settling time

Startup time: Initial acceleration of arm
Movement time: Proportional to distance traveled
Settling time: Final positioning (1-2 ms)
```

**Typical values:**
- **Minimum seek time:** 0-1 ms (adjacent tracks)
- **Average seek time:** 8-12 ms (modern HDDs)
- **Maximum seek time:** 15-20 ms (innermost to outermost track)

**Visual:**
```
Disk Platters
     │
     ├── Track 0 (outermost)
     ├── Track 10
     ├── Track 20  ◄── Current position
     │     ...
     ├── Track 50  ◄── Target position
     └── Track 99 (innermost)

Seek distance = |50 - 20| = 30 tracks
Seek time ≈ 0.5 ms (startup) + 30 × 0.2 ms + 1 ms (settling) = 7.5 ms
```

***

#### Rotational Latency (Rotational Delay)

**Definition:** Time taken for the desired **sector** to rotate under the read/write head after the head reaches the correct track.

**Formula:**
```
Rotational Latency = (Degrees to rotate / 360°) × Time per rotation

Average Rotational Latency = 0.5 × Time per rotation
```

**Typical values (7200 RPM disk):**
```
RPM = 7200 rotations per minute
RPS = 7200 / 60 = 120 rotations per second
Time per rotation = 1 / 120 = 8.33 ms

Average rotational latency = 8.33 / 2 = 4.17 ms
Worst case = 8.33 ms (just missed the sector)
Best case = 0 ms (sector already under head)
```

**Visual:**
```
Track with 8 sectors:
        ┌───────┐
    7   │   0   │  1
        └───────┘
    6       ●       2    ← ● = Read/Write Head
            ↑
    5       3       Target sector: 6
        4           Current under head: 0

Must rotate: 6 sectors = (6/8) × 360° = 270°
Rotational latency = 0.75 × 8.33 ms = 6.25 ms
```

***

#### Total Access Time

**Complete formula:**
```
Total Access Time = Seek Time + Rotational Latency + Transfer Time

Transfer Time = (Data Size / Transfer Rate)

Example:
- Seek time: 10 ms
- Rotational latency: 4 ms (avg)
- Data size: 4 KB
- Transfer rate: 100 MB/s
- Transfer time: 4 KB / 100 MB/s = 0.04 ms

Total = 10 + 4 + 0.04 = 14.04 ms
```

**Memory Trick:** "**S**eek moves the arm, **R**otation spins the platter, **T**ransfer reads the data = **SRT**"

***

### CLV vs CAV: Disk Recording Methods

#### Constant Linear Velocity (CLV)

**Principle:** Maintain **constant data density** across all tracks by varying rotation speed.

**How it works:**
```
Outer tracks (larger circumference):
- Spin SLOWER to maintain constant linear speed
- More data per track

Inner tracks (smaller circumference):
- Spin FASTER to maintain constant linear speed
- Less data per track (but same density)
```

**Visual:**
```
Outer Track: ═══════════════════ (Long circumference, slow RPM)
Inner Track: ═══════ (Short circumference, fast RPM)

Both have same data density (bits per cm)
```

**Advantages:**
- ✅ Maximum storage capacity (constant density)
- ✅ Uniform data transfer rate

**Disadvantages:**
- ❌ Complex electronics (variable speed motor)
- ❌ Longer seek times (motor must adjust speed)

**Used in:** CD-ROMs, DVDs (optimizes read speed and capacity)

***

#### Constant Angular Velocity (CAV)

**Principle:** Disk spins at **constant RPM** regardless of head position.

**How it works:**
```
Outer tracks (larger circumference):
- More sectors per track (more data)
- Higher linear velocity

Inner tracks (smaller circumference):
- Fewer sectors per track (less data)
- Lower linear velocity
```

**Visual:**
```
┌───────────────────────────────────┐
│ Outer Track: 100 sectors          │ ← More data
├───────────────────────────────────┤
│ Middle Track: 80 sectors           │
├───────────────────────────────────┤
│ Inner Track: 60 sectors            │ ← Less data
└───────────────────────────────────┘

All rotate at same RPM (e.g., 7200)
```

**Advantages:**
- ✅ Simple electronics (fixed speed motor)
- ✅ Fast seek times (no speed adjustment)
- ✅ Predictable timing

**Disadvantages:**
- ❌ Lower capacity (wasted space on inner tracks)
- ❌ Variable data transfer rate (faster on outer tracks)

**Used in:** Hard disk drives (HDDs), floppy disks

***

#### Comparison Table

| Aspect | CLV | CAV |
|--------|-----|-----|
| **RPM** | Variable | Constant |
| **Data density** | Constant (all tracks) | Variable (decreases inward) |
| **Storage capacity** | Higher | Lower |
| **Transfer rate** | Constant | Variable |
| **Seek complexity** | High (adjust speed) | Low (fixed speed) |
| **Typical use** | Optical media (CD/DVD) | Magnetic disks (HDD) |
| **Example** | CD-ROM: 200-500 RPM (outer), 200-500 RPM (inner, adjusted) | HDD: 7200 RPM (all tracks) |

**Memory Trick:** 
- **CLV** = **C**onstant **L**inear speed → **V**ariable RPM (like a CD player adjusting speed)
- **CAV** = **C**onstant **A**ngular speed → Fixed **V**elocity (like a record player)

***

## DISK SCHEDULING ALGORITHMS

Disk scheduling algorithms determine the **order** in which disk I/O requests are serviced to minimize seek time and improve throughput.

### Key Metrics

1. **Total head movement:** Sum of seek distances (in tracks)
2. **Average seek time:** Total movement / Number of requests
3. **Throughput:** Requests serviced per unit time
4. **Response time:** Time from request arrival to completion
5. **Fairness:** All requests eventually serviced (no starvation)

***

### Algorithm 1: FCFS (First-Come, First-Served)

**Strategy:** Service requests in the **order they arrive** (queue order).

**Algorithm:**
```
Service requests in arrival order: R1, R2, R3, ...
Head moves: Current → R1 → R2 → R3 → ...
```

**Example:**
```
Current head position: 50
Request queue: [95, 180, 34, 119, 11, 124]

Head movement:
50 → 95 (45 tracks)
95 → 180 (85 tracks)
180 → 34 (146 tracks)
34 → 119 (85 tracks)
119 → 11 (108 tracks)
11 → 124 (113 tracks)

Total: 45 + 85 + 146 + 85 + 108 + 113 = 582 tracks
```

**Visual:**
```
Tracks: 0 ─────────────────────────────────────── 199

Movement: 50 →→→→ 95 →→→→→→→→→→→ 180 ←←←←←←←←←←←←←←←← 34
              →→→→→→→→→→ 119 ←←←←←←←←←←←← 11 →→→→→→→→→→→→→ 124
```

**Advantages:**
- ✅ Simple to implement (just a queue)
- ✅ Fair (no starvation; FIFO order)
- ✅ No overhead

**Disadvantages:**
- ❌ High seek time (wild head swings)
- ❌ Poor throughput
- ❌ No optimization

**Use case:** Simple systems, low I/O load

**Memory Trick:** "FCFS = **F**air but **C**haotic arm **F**lailing **S**lowly"

***

### Algorithm 2: SSTF (Shortest Seek Time First)

**Strategy:** Service the request **closest** to the current head position (greedy algorithm).

**Algorithm:**
```
Repeat:
    Among pending requests, pick the one with minimum seek distance
    Move head to that track
    Service request
```

**Example (same requests):**
```
Current: 50
Queue: [95, 180, 34, 119, 11, 124]

Step 1: Closest to 50? → 34 (distance 16)
50 → 34 (16 tracks)

Step 2: Closest to 34? → 11 (distance 23)
34 → 11 (23 tracks)

Step 3: Closest to 11? → 95 (distance 84)
11 → 95 (84 tracks)

Step 4: Closest to 95? → 119 (distance 24)
95 → 119 (24 tracks)

Step 5: Closest to 119? → 124 (distance 5)
119 → 124 (5 tracks)

Step 6: Only 180 left
124 → 180 (56 tracks)

Total: 16 + 23 + 84 + 24 + 5 + 56 = 208 tracks
```

**Visual:**
```
Tracks: 0 ─────────────────────────────────────── 199

Movement: 50 ← 34 ← 11 →→→→→→→→→→→→ 95 → 119 → 124 →→→→→ 180
```

**Advantages:**
- ✅ Much better throughput than FCFS
- ✅ Lower average seek time
- ✅ Good for high I/O loads

**Disadvantages:**
- ❌ **Starvation possible:** Requests at disk extremes may wait indefinitely if middle tracks keep getting requests
- ❌ Not fair (nearby requests always prioritized)
- ❌ Variance in response time (some requests wait very long)

**Use case:** When throughput is priority over fairness

**Memory Trick:** "SSTF = **S**elect **S**hortest first, but may **S**tarve edge **T**racks **F**orever"

***

### Algorithm 3: SCAN (Elevator Algorithm)

**Strategy:** Head moves in **one direction**, servicing requests along the way, then **reverses direction** at disk end.

**Algorithm:**
```
1. Choose initial direction (e.g., toward higher tracks)
2. Service all requests in current direction
3. Reverse direction at end
4. Service requests in opposite direction
5. Repeat
```

**Example:**
```
Current: 50, Direction: toward 0 (left)
Queue: [95, 180, 34, 119, 11, 124]

Moving left (toward 0):
50 → 34 → 11 → 0 (end)

Reverse, moving right:
0 → 95 → 119 → 124 → 180 → 199 (end)

Total: (50-34) + (34-11) + (11-0) + (95-0) + (119-95) + (124-119) + (180-124) + (199-180)
     = 16 + 23 + 11 + 95 + 24 + 5 + 56 + 19
     = 249 tracks
```

**Visual:**
```
Tracks: 0 ─────────────────────────────────────── 199

Initial: →→→→→→→→→→→→→→→→→→→→→→→→→→→→→→→→ 50 ←←←←←← 34 ← 11 ← 0
Reverse: 0 →→→→→→→→→→→→ 95 → 119 → 124 →→→→ 180 →→ 199
```

**Advantages:**
- ✅ No starvation (all requests eventually serviced)
- ✅ More uniform wait times
- ✅ Predictable behavior

**Disadvantages:**
- ❌ Requests at middle get serviced faster (head passes middle twice per cycle)
- ❌ Unnecessary movement to disk ends (even if no requests there)

**Memory Trick:** "SCAN = Like an elevator, goes up, goes down"

***

### Algorithm 4: C-SCAN (Circular SCAN)

**Strategy:** Head moves in **one direction only**, servicing requests. Upon reaching the end, it **immediately returns to the beginning** (without servicing) and repeats.

**Algorithm:**
```
1. Service requests in one direction (e.g., 0 → 199)
2. At end (199), jump back to start (0) without servicing
3. Repeat
```

**Example:**
```
Current: 50, Direction: toward 199
Queue: [95, 180, 34, 119, 11, 124]

Moving right (toward 199):
50 → 95 → 119 → 124 → 180 → 199 (end)

Jump back (no service):
199 → 0

Moving right again:
0 → 11 → 34

Total: (95-50) + (119-95) + (124-119) + (180-124) + (199-180) + (199-0) + (11-0) + (34-11)
     = 45 + 24 + 5 + 56 + 19 + 199 + 11 + 23
     = 382 tracks
```

**Wait, that seems high because of the return jump. Let me recalculate actual disk head movement:**

**Actual head movement (exclude jump):**
```
Forward pass: 50 → 95 → 119 → 124 → 180 → 199
Movement: 149 tracks

Return (instant repositioning, minimal seek):
199 → 0 (this is a seek, but in C-SCAN we count it)

Second pass: 0 → 11 → 34
Movement: 34 tracks

Total counted: 149 + 199 + 34 = 382 tracks
OR
Total without return: 149 + 34 = 183 tracks (if return not counted)
```

**Note:** In practice, the "return" jump is often not counted or treated as minimal overhead since it's a single long seek without servicing.

**Visual:**
```
Tracks: 0 ─────────────────────────────────────── 199

Pass 1: 50 →→→→ 95 → 119 → 124 →→→→ 180 →→ 199
Return: 199 ⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺ 0 (jump)
Pass 2: 0 → 11 → 34 →→→→...
```

**Advantages:**
- ✅ More **uniform wait times** than SCAN (no middle bias)
- ✅ No starvation
- ✅ Better for high-load systems

**Disadvantages:**
- ❌ Return jump overhead (though minimal)
- ❌ Still services one direction at a time

**Use case:** Systems with uniformly distributed requests, real-time systems

**Memory Trick:** "C-SCAN = **C**ircular like a **C**arousel; always goes one way"

***

### Algorithm 5: C-LOOK (Circular LOOK)

**Strategy:** Like C-SCAN, but head only goes **as far as the last request** in each direction (doesn't go to disk end unnecessarily).

**Algorithm:**
```
1. Service requests in one direction up to last request
2. Jump back to first request in opposite direction
3. Repeat
```

**Example:**
```
Current: 50, Direction: toward higher tracks
Queue: [95, 180, 34, 119, 11, 124]

Moving right (up to last request):
50 → 95 → 119 → 124 → 180 (last request, stop here)

Jump back to first request:
180 → 11 (lowest request)

Moving right again:
11 → 34

Total: (95-50) + (119-95) + (124-119) + (180-124) + (180-11) + (34-11)
     = 45 + 24 + 5 + 56 + 169 + 23
     = 322 tracks

OR (if return not counted as heavily):
Forward: 45 + 24 + 5 + 56 = 130
Return: 169
Second: 23
Total: 322 tracks
```

**Visual:**
```
Tracks: 0 ─────────────────────────────────────── 199

Pass 1: 50 →→→→ 95 → 119 → 124 →→→→ 180 (stop, don't go to 199)
Return: 180 ⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺ 11 (jump to lowest)
Pass 2: 11 → 34 →→→→→...
```

**Advantages:**
- ✅ No unnecessary movement to disk ends
- ✅ Better than C-SCAN in terms of head movement
- ✅ Uniform wait times

**Disadvantages:**
- ❌ Slightly more complex logic (track min/max requests)

**Use case:** Modern disk drives, operating systems (Linux uses variants of this)

**Memory Trick:** "C-LOOK = C-SCAN but **LOOK** ahead to see where to stop"

***

### Algorithm Comparison Table

| Algorithm | Total Seek | Fairness | Starvation? | Complexity | Best For |
|-----------|------------|----------|-------------|------------|----------|
| **FCFS** | Very High | Perfect | No | Low | Light loads |
| **SSTF** | Low | Poor | Yes (edges) | Medium | Heavy loads, non-critical |
| **SCAN** | Medium | Good | No | Medium | General purpose |
| **C-SCAN** | Medium-High | Excellent | No | Medium | Uniform workloads |
| **C-LOOK** | Low-Medium | Excellent | No | Medium-High | Modern systems (best overall) |

***

### Factors in Selecting Disk Scheduling Algorithm

**1. Workload Characteristics:**
- **Random access pattern:** SSTF or C-LOOK
- **Sequential access:** FCFS acceptable
- **Uniform distribution:** C-SCAN or C-LOOK

**2. Fairness Requirements:**
- **Critical systems:** Avoid SSTF (can starve)
- **Real-time:** C-SCAN or C-LOOK with priorities

**3. Performance Goals:**
- **Maximize throughput:** SSTF or C-LOOK
- **Minimize variance:** C-SCAN or C-LOOK
- **Balance both:** C-LOOK (modern default)

**4. System Load:**
- **Light load:** FCFS sufficient (low overhead)
- **Heavy load:** C-LOOK or SSTF

**5. Hardware Constraints:**
- **Slow seeks:** Favor algorithms minimizing movement (C-LOOK)
- **Fast seeks:** FCFS may be adequate

**6. Application Type:**
- **Databases:** SSTF or C-LOOK (random I/O)
- **File servers:** C-SCAN (sequential + random mix)
- **Video streaming:** SCAN or C-SCAN (predictable timing)

**Modern Default:** Linux uses **deadline scheduler** or **CFQ (Completely Fair Queuing)**, which combines C-LOOK with I/O priorities and deadlines.

***

## I/O BUFFERING

**Buffering:** Using a **temporary memory area** (buffer) to hold data during transfer between devices with different speeds.

### Why Buffering is Needed

**Problem:**
```
CPU speed: GHz (nanoseconds)
RAM speed: 100 ns
Disk speed: 10 ms (100,000× slower!)
Network speed: Variable (ms)

Without buffering: CPU must wait for slow I/O → massive waste
```

**Solution:** Buffer decouples producer and consumer speeds.

***

### Types of Buffering

#### 1. Single Buffering

**Mechanism:**
```
┌─────────┐      ┌────────┐      ┌──────────┐
│  Input  │ ───► │ Buffer │ ───► │   CPU    │
│ Device  │      │ (RAM)  │      │ Process  │
└─────────┘      └────────┘      └──────────┘

Step 1: Device fills buffer (CPU can do other work)
Step 2: Buffer full → CPU processes data
Step 3: While CPU processes, device waits
```

**Timing:**
```
T = max(C, M)
where:
C = Time to consume (process) data
M = Time to move (input) next block
```

**Advantage:** CPU doesn't wait for device during input.
**Disadvantage:** Device idle while CPU processes.

***

#### 2. Double Buffering (Buffer Swapping)

**Mechanism:**
```
┌─────────┐      ┌──────────┐      ┌──────────┐
│  Input  │ ───► │ Buffer 1 │ ───► │   CPU    │
│ Device  │      └──────────┘      │ Process  │
│         │      ┌──────────┐      │          │
│         │ ───► │ Buffer 2 │ ───► │          │
└─────────┘      └──────────┘      └──────────┘

Step 1: Device fills Buffer 1
Step 2: CPU processes Buffer 1, device simultaneously fills Buffer 2
Step 3: Swap: CPU processes Buffer 2, device fills Buffer 1
```

**Timing:**
```
T = max(C, M)  (overlapped)

If C > M: CPU-bound (device always has data ready)
If M > C: I/O-bound (CPU always has data to process)
```

**Advantage:** True parallelism; neither CPU nor device idles (if balanced).
**Disadvantage:** Uses 2× buffer memory.

***

#### 3. Circular Buffering (Multiple Buffers)

**Mechanism:**
```
┌─────────┐      ┌────────────────────────────┐
│         │ ───► │ B1 → B2 → B3 → ... → Bn   │ ───► ┌─────┐
│  Input  │      │  ↑                    ↓    │      │ CPU │
│ Device  │      │  └────────────────────┘    │      └─────┘
└─────────┘      └────────────────────────────┘
                 (Ring buffer / Circular queue)

Producer (device) and consumer (CPU) work independently
```

**Advantage:** Smooths out bursts; decouples variable rates.
**Use case:** Network packet buffering, audio/video streaming.

***

### Benefits of Buffering

1. **Speed Matching:** Bridge gap between fast and slow devices.
2. **Asynchronous I/O:** Device and CPU work in parallel.
3. **Copy Semantics:** Data can be modified without affecting I/O.
4. **Batch Efficiency:** Accumulate small I/Os into larger blocks.
5. **Error Recovery:** Can resend buffered data on transmission error.

**Memory Trick:** "Buffering = **B**ridge **U**nequal speeds, **F**acilitate **F**ast **E**xecution, **R**educe **I**dle **N**anoseconds, **G**uarantee smooth operation"

***

## DEVICE MANAGEMENT POLICIES

Device management involves **allocating, scheduling, and controlling** I/O devices.

### Key Policies

#### 1. Device Allocation

**Dedicated Devices:**
- Assigned exclusively to one process (e.g., tape drive, printer)
- Simple but underutilized
- **Policy:** FCFS allocation, deadlock avoidance needed

**Shared Devices:**
- Multiple processes interleave access (e.g., disk)
- Requires scheduling and synchronization
- **Policy:** Time-slicing, request queuing

**Virtual Devices:**
- Simulate dedicated device using shared resource (e.g., spooling)
- Combines benefits of both
- **Policy:** Spooling (see below)

***

#### 2. Device Scheduling

**Goals:**
- Fairness: All processes get service
- Throughput: Maximize I/O operations per second
- Response time: Minimize wait time

**Strategies:**
- FCFS, SSTF, SCAN (discussed above)
- Priority-based: Real-time tasks first
- Deadline-based: Meet time constraints

***

#### 3. Buffering Policy

**When to use:**
- **Always buffer** for speed mismatch
- **Double buffer** for streaming (audio/video)
- **Circular buffer** for networks

**Size tuning:**
- Too small: Frequent I/O, overhead
- Too large: Memory waste, cache pollution
- **Optimal:** Match typical I/O size (e.g., 4 KB page size)

***

#### 4. Error Handling

**Transient Errors:** Retry (e.g., network timeout)
**Permanent Errors:** Report to application (e.g., disk bad sector)
**Silent Errors:** Detect with checksums, ECC

**Policy:**
- Retry N times (typically 3-5)
- Log errors for analysis
- Fail gracefully (return error code, don't crash)

***

#### 5. Device Driver Management

**Responsibilities:**
- Initialize device
- Translate OS commands to device-specific operations
- Handle interrupts
- Manage DMA transfers
- Implement buffering

**Policy:**
- Modular architecture (drivers as loadable modules)
- Standard interface (uniform API for similar devices)
- Isolation (driver crash shouldn't crash kernel)

***

## RAID LEVELS: Throughput Analysis

**RAID (Redundant Array of Independent Disks):** Combines multiple disks for performance, capacity, and/or reliability.

### RAID 1 (Mirroring)

**Organization:**
```
┌─────┐   ┌─────┐
│Disk │   │Disk │
│  A  │   │  A' │  (Mirror/Copy)
└─────┘   └─────┘

Every write goes to both disks
Every read can come from either disk
```

**Read Operations:**

**Single Block Read:**
```
Can read from EITHER disk → no advantage
Throughput = 1 disk's speed
```

**Multiple Continuous Blocks:**
```
Blocks B1, B2, B3, B4...

Option 1: Read all from one disk
Throughput = 1 disk's speed

Option 2: Alternate between disks
Read B1 from Disk A, B2 from Disk A'simultaneously (if physically separate locations)
Theoretical throughput ≈ 2× (if requests independent)
```

**Practical Throughput:**
- Single block: **1×**
- Multiple blocks (sequential): **1×** (can't parallelize sequential reads from same stream)
- Multiple blocks (random, different streams): **2×** (can parallelize independent requests)

***

### RAID 5 (Striping with Distributed Parity)

**Organization (3 disks example):**
```
┌──────┬──────┬──────┐
│ D0   │ D1   │ P0   │  Row 0
├──────┼──────┼──────┤
│ D2   │ P1   │ D3   │  Row 1
├──────┼──────┼──────┤
│ P2   │ D4   │ D5   │  Row 2
└──────┴──────┴──────┘
Disk A  Disk B  Disk C

D = Data block
P = Parity block (XOR of data blocks)
```

**Read Operations:**

**Single Block Read:**
```
Read directly from data disk (ignore parity)
Throughput = 1 disk's speed (same as single disk)
```

**Multiple Continuous Blocks:**
```
Blocks B1, B2, B3, B4... are STRIPED across disks

Read B1 from Disk A
Read B2 from Disk B  } Parallel!
Read B3 from Disk C  }

Throughput ≈ N disks' speed (where N = # data disks)
For 3 disks: ~3× single disk
For 5 disks: ~5× single disk
```

**Formula:**
```
RAID 5 Throughput = (N - 1) × Single Disk Throughput
where N = total number of disks
(N-1 because one disk's worth of capacity used for parity)
```

***

### RAID 1 vs RAID 5: Throughput Comparison

| Operation | RAID 1 (2 disks) | RAID 5 (3 disks) | RAID 5 (5 disks) |
|-----------|------------------|------------------|------------------|
| **Single block read** | 1× | 1× | 1× |
| **Multiple continuous blocks** | 1× (sequential) | ~3× | ~5× |
| **Multiple random blocks** | ~2× | ~3× | ~5× |
| **Single block write** | 1× (both disks) | 0.25× (read-modify-write) | 0.25× |
| **Multiple continuous blocks write** | 1× | ~2-3× | ~4-5× |

**Key Insight:**
- **RAID 1:** Better for **write-heavy** workloads and **high reliability** (simple mirroring).
- **RAID 5:** Better for **read-heavy** workloads with **multiple continuous blocks** (striping parallelizes reads).

**Read Throughput Winner:**
- Single block: **Tie** (both 1×)
- Multiple continuous blocks: **RAID 5 wins** (N-1 times faster)

***

## FILE SYSTEMS

### File Allocation Methods

#### 1. Contiguous Allocation

**Concept:** Each file occupies a **contiguous set of blocks** on disk.

**Directory Entry:**
```
File Name | Start Block | Length
File.txt  |     100     |   5
```

**Visual:**
```
Blocks: ... [98][99][100][101][102][103][104][105][106] ...
                    └──── File.txt (5 blocks) ────┘
```

**Advantages:**
- ✅ **Simple:** Only need start + length
- ✅ **Fast sequential access:** No seeks between blocks
- ✅ **Fast random access:** Block = Start + Offset (direct computation)
- ✅ **Minimal directory space**

**Disadvantages:**
- ❌ **External fragmentation:** Holes between files waste space
- ❌ **File growth problem:** Can't extend file if next block occupied
- ❌ **Allocation challenge:** Need to know max file size in advance

**Use case:** CD-ROMs, DVDs (write-once media where files don't grow)

***

#### 2. Linked Allocation

**Concept:** Each block contains a **pointer to the next block**; file is a linked list of blocks.

**Directory Entry:**
```
File Name | Start Block | End Block
File.txt  |     100     |    104
```

**Visual:**
```
Block 100: [Data | → 103]
           ↓
Block 103: [Data | → 107]
           ↓
Block 107: [Data | → 115]
           ↓
Block 115: [Data | → 104]
           ↓
Block 104: [Data | NULL]  (End)
```

**Advantages:**
- ✅ **No external fragmentation:** Any free block can be used
- ✅ **File growth easy:** Just link new block at end
- ✅ **No pre-allocation needed**

**Disadvantages:**
- ❌ **Slow random access:** Must traverse list from start (O(n))
- ❌ **Pointer overhead:** Each block wastes space for pointer (e.g., 4 bytes per block)
- ❌ **Reliability:** One corrupted pointer breaks entire file
- ❌ **Poor sequential performance:** Blocks scattered → lots of seeks

**Variant: FAT (File Allocation Table):**
- Store all pointers in a centralized table (FAT) in memory
- Faster access, better reliability
- Used in: FAT16, FAT32, exFAT

***

#### 3. Indexed Allocation

**Concept:** Each file has an **index block** containing pointers to all data blocks.

**Directory Entry:**
```
File Name | Index Block
File.txt  |     200
```

**Visual:**
```
Index Block 200:
┌───────────────┐
│ Block Pointers│
├───────────────┤
│ 0: → 105      │
│ 1: → 217      │
│ 2: → 309      │
│ 3: → 412      │
│ 4: → 508      │
│ ... (rest NULL)│
└───────────────┘

Data Blocks:
Block 105: [Data]
Block 217: [Data]
Block 309: [Data]
...
```

**Advantages:**
- ✅ **Fast random access:** Index[i] directly gives block number (O(1))
- ✅ **No external fragmentation**
- ✅ **Supports file growth** (until index block full)

**Disadvantages:**
- ❌ **Index block overhead:** Extra block per file (wasted for small files)
- ❌ **File size limited** by index block size
  - Example: 4KB block, 4-byte pointers → 1024 pointers → max 4MB file

**Solutions for large files:**
- **Linked index blocks:** Index block points to another index block
- **Multi-level index:** Like multi-level page tables
- **Combined scheme (UNIX inode):** Direct + indirect + double indirect + triple indirect

***

#### Comparison Table

| Aspect | Contiguous | Linked | Indexed |
|--------|-----------|--------|---------|
| **Directory space** | **Minimal** (start + length) | Small (start + end) | Small (index block#) |
| **Random access** | **Fast** (direct) | Slow (traverse list) | **Fast** (direct via index) |
| **Sequential access** | **Fast** (no seeks) | Slow (scattered blocks) | Medium (1 seek per block) |
| **Fragmentation** | External | None | None |
| **File growth** | Difficult | **Easy** | **Easy** |
| **Overhead** | None | Pointer per block | Index block |
| **Reliability** | High | Low (pointer corruption) | Medium |

**Which minimizes directory space?**  
**Contiguous allocation** (only 2 values: start + length)

***

### File Access Methods

#### 1. Sequential Access

**Definition:** Read/write file from beginning to end, in order.

**Operations:**
```
read_next()  // Read next byte/record
write_next() // Write next byte/record
reset()      // Go back to beginning
```

**Example (tape analogy):**
```
File: [Block 0][Block 1][Block 2][Block 3][Block 4]
Read:    ↓        ↓        ↓        ↓        ↓
      Pos 0    Pos 1    Pos 2    Pos 3    Pos 4

Must read in order; can't skip
```

**Use cases:**
- Log files (always append at end)
- Tape backups
- Streaming media (video playback)

**Advantages:**
- Simple, efficient for linear processing
- Works on any storage (even tape)

**Disadvantages:**
- Can't skip to middle efficiently

***

#### 2. Direct (Random) Access

**Definition:** Read/write any block/record directly by position.

**Operations:**
```
read(n)   // Read block n
write(n)  // Write block n
seek(n)   // Position to block n
```

**Example:**
```
File: [Block 0][Block 1][Block 2][Block 3][Block 4]
Direct access: Read Block 3 immediately (no need to read 0,1,2 first)
```

**Use cases:**
- Databases (query specific records)
- Virtual memory (page files)
- Executable files (load specific code sections)

**Advantages:**
- Fast access to any part of file
- Efficient for large files

**Disadvantages:**
- Requires addressable storage (disk, not tape)
- More complex implementation

***

#### 3. Indexed Access

**Definition:** Create an **index** of keys; access records via index lookup.

**Structure:**
```
Index File:
┌──────────┬─────────────┐
│   Key    │  Block Ptr  │
├──────────┼─────────────┤
│ "Alice"  │     10      │
│ "Bob"    │     25      │
│ "Charlie"│     47      │
└──────────┴─────────────┘

Data File:
Block 10: [Alice's record]
Block 25: [Bob's record]
Block 47: [Charlie's record]
```

**Operations:**
```
search(key)    // Find record with given key
read_by_key(k) // Read record with key k
```

**Use cases:**
- Databases with indices (B-trees, hash tables)
- Phone directories
- Library card catalogs

**Advantages:**
- **Very fast search** (O(log n) with B-tree)
- Efficient for queries

**Disadvantages:**
- Index overhead (extra storage)
- Index must be maintained on updates

***

#### Evaluation in Cloud Storage

| Method | Strengths (Cloud) | Weaknesses (Cloud) |
|--------|------------------|-------------------|
| **Sequential** | - Simple streaming<br>- Low bandwidth<br>- Good for large transfers | - Poor for random queries<br>- Must download entire file |
| **Direct** | - Fast queries<br>- Partial file access<br>- Good for VMs | - Requires byte-range requests<br>- Latency per access |
| **Indexed** | - **Best for databases**<br>- Fast queries<br>- Distributed indices | - Index consistency in distributed system<br>- Replication overhead |

**Cloud Best Practices:**
- **Object storage (S3):** Sequential + Direct (byte-range GET)
- **Databases (DynamoDB):** Indexed (distributed indices)
- **File systems (EFS):** Direct (POSIX access)

***

Continuing Unit 5 revision sheet:

***

### Directory Structures

A directory is a container that organizes files and provides a **namespace** for file identification.

#### 1. Single-Level Directory

**Structure:**
```
┌────────────────────────────────────────────┐
│  Root Directory                            │
├────────────────────────────────────────────┤
│ File1.txt  File2.exe  File3.doc  File4.mp3│
└────────────────────────────────────────────┘

All files in ONE directory
```

**Advantages:**
- ✅ Simplest to implement
- ✅ Fast lookup (single level)
- ✅ Easy to understand

**Disadvantages:**
- ❌ **Naming conflicts:** All files must have unique names (users can't have same filename)
- ❌ No organization (all files together)
- ❌ Not scalable

**Use case:** Early operating systems (DOS 1.0), embedded systems

***

#### 2. Two-Level Directory

**Structure:**
```
┌───────────────────────────────────────┐
│          Root Directory               │
├─────────┬─────────┬─────────┬─────────┤
│  User1  │  User2  │  User3  │  User4  │
└────┬────┴────┬────┴────┬────┴────┬────┘
     │         │         │         │
  ┌──┴──┐   ┌─┴──┐   ┌──┴──┐   ┌──┴──┐
  │Files│   │Files│   │Files│   │Files│
  │ for │   │ for │   │ for │   │ for │
  │User1│   │User2│   │User3│   │User4│
  └─────┘   └─────┘   └─────┘   └─────┘

Each user has their own directory
```

**Advantages:**
- ✅ **Isolates users:** User1 and User2 can both have "file.txt"
- ✅ Efficient search (only search your directory)
- ✅ Simple protection (user directories separate)

**Disadvantages:**
- ❌ No subdirectories (can't organize within user directory)
- ❌ No grouping of related files
- ❌ Can't share files easily between users

**Use case:** Early multi-user systems

***

#### 3. Tree-Structured Directory

**Structure:**
```
                    Root (/)
                      │
        ┌─────────────┼─────────────┐
        │             │             │
      home          etc            usr
        │             │             │
    ┌───┴───┐     ┌───┴───┐     ┌───┴───┐
    │       │     │       │     │       │
  user1  user2  passwd  hosts  bin    lib
    │       │
 ┌──┴──┐ ┌─┴──┐
docs code file1 file2

Example paths:
/home/user1/docs
/etc/passwd
/usr/bin
```

**Advantages:**
- ✅ **Hierarchical organization:** Natural grouping
- ✅ Efficient search (path-based)
- ✅ Can have same filename in different directories
- ✅ Supports both absolute and relative paths

**Disadvantages:**
- ❌ **No sharing:** Can't easily share files between directories (must copy or use absolute path)
- ❌ Traversal time increases with depth

**Use case:** Most modern operating systems (Unix, Windows, macOS)

***

#### 4. Acyclic Graph Directory

**Structure:**
```
              Root (/)
                │
        ┌───────┼───────┐
        │       │       │
      home    shared   usr
        │       │       │
    ┌───┴───┐   │   ┌───┴───┐
    │       │   │   │       │
  user1  user2  │  bin    lib
    │       │   │
    └───────┼───┘
            │
        project.txt  ◄─── Shared file (multiple links)
```

**Mechanism:**
- **Links (pointers):** Multiple directory entries point to same file
- **Hard links:** Multiple directory entries, same inode (Unix)
- **Symbolic links:** Directory entry points to pathname of another file

**Advantages:**
- ✅ **File sharing:** Multiple users can access same file
- ✅ No duplication (one copy, multiple references)
- ✅ Flexible organization

**Disadvantages:**
- ❌ **Complex:** Must handle deletion carefully (reference counting)
- ❌ Dangling pointers (if original deleted, symlink breaks)
- ❌ Traversal algorithms more complex (must detect cycles... wait, acyclic means no cycles)

**Use case:** Unix/Linux (hard links, symbolic links), Windows (shortcuts)

***

#### 5. General Graph Directory (with Cycles)

**Structure:**
```
         /
         │
    ┌────┼────┐
    │    │    │
   A     B    C
   │     │    │
   └──►  D  ◄─┘
         │
         └──► A  (Cycle: A → D → A)
```

**Mechanism:** Allows arbitrary links, including cycles.

**Advantages:**
- ✅ Maximum flexibility
- ✅ Can model complex relationships

**Disadvantages:**
- ❌ **Garbage collection needed:** How to delete files with circular references?
- ❌ **Infinite loops:** Traversal algorithms must detect cycles
- ❌ Very complex to implement correctly

**Solutions:**
- Prohibit cycles (use acyclic graph)
- Garbage collection (mark and sweep)
- Bypass links during traversal

**Use case:** Rarely used in practice (too complex)

***

#### Comparison Summary

| Type | Levels | Name Conflicts | Sharing | Complexity | Use |
|------|--------|----------------|---------|------------|-----|
| **Single-Level** | 1 | Always | No | Simplest | Embedded |
| **Two-Level** | 2 | Per-user only | No | Simple | Old multi-user |
| **Tree** | Many | Per-directory | Hard | Medium | **Most common** |
| **Acyclic Graph** | Many | Per-directory | **Easy** | High | Unix/Linux |
| **General Graph** | Many | Per-directory | Easy | **Highest** | Rare |

**Memory Trick:** "Tree → most practical. Acyclic Graph → adds sharing. General Graph → too complex."

***

### Free Space Management

Operating systems must track which disk blocks are **free** vs **allocated**.

#### Method 1: Bit Vector (Bitmap)

**Concept:** One bit per block: 0 = free, 1 = allocated (or vice versa).

**Example:**
```
Blocks:  0  1  2  3  4  5  6  7  8  9 10 11 12
Bitmap:  1  1  0  1  0  0  0  1  1  0  1  0  0
         ↑  ↑  ↑  ↑  ↑  ↑  ↑  ↑  ↑  ↑  ↑  ↑  ↑
         Busy   Free   Free     Busy  Free

Free blocks: 2, 4, 5, 6, 9, 11, 12
```

**Finding first free block:**
```c
// Scan bitmap from start
for (i = 0; i < n_blocks; i++) {
    if (bitmap[i] == 0) {
        allocate(i);
        bitmap[i] = 1;
        return i;
    }
}
```

**Advantages:**
- ✅ **Simple and efficient**
- ✅ **Fast lookup:** Hardware can quickly find first 0 bit (CLZ instruction)
- ✅ **Compact:** 1 bit per block
  - Example: 1 TB disk, 4 KB blocks → 256M blocks → 32 MB bitmap
- ✅ **Easy to allocate contiguous blocks** (look for consecutive 0s)

**Disadvantages:**
- ❌ Must keep entire bitmap in memory (or swap frequently)
- ❌ Bit manipulation overhead
- ❌ For sparse allocation, many bits wasted

**Use case:** Linux ext2/ext3/ext4, Windows NTFS

***

#### Method 2: Linked List (Free List)

**Concept:** Chain all free blocks in a linked list.

**Structure:**
```
Head → Block 5 → Block 9 → Block 14 → Block 27 → NULL
       [Next=9]  [Next=14]  [Next=27]  [Next=NULL]
```

**Allocation:**
```c
free_block = head;
head = free_block->next;  // Remove from list
return free_block;
```

**Deallocation:**
```c
freed_block->next = head;
head = freed_block;  // Add to front of list
```

**Advantages:**
- ✅ No wasted space for allocated blocks
- ✅ Simple to implement

**Disadvantages:**
- ❌ **Slow:** Must traverse list to find N contiguous blocks
- ❌ **Poor locality:** Free blocks scattered, pointers all over disk
- ❌ Pointer overhead in each free block
- ❌ Can't easily find contiguous space

**Optimization: Grouping:**
- First free block contains addresses of N free blocks
- Last of those N blocks points to next group
- Reduces pointer overhead

**Use case:** Some embedded systems, older file systems

***

#### Method 3: Grouping

**Concept:** Store addresses of N free blocks in first free block; repeat recursively.

**Structure:**
```
Block 100 (Index Block):
┌────────────────────┐
│ Free blocks:       │
│  - 105             │
│  - 217             │
│  - 309             │
│  - ...             │
│  - 500 (next index)│  ◄── Points to another index block
└────────────────────┘

Block 500 (Next Index):
┌────────────────────┐
│ Free blocks:       │
│  - 502             │
│  - 610             │
│  - ...             │
└────────────────────┘
```

**Advantages:**
- ✅ Fast to find large number of free blocks
- ✅ Less overhead than pure linked list

**Disadvantages:**
- ❌ Still requires traversal for contiguous allocation
- ❌ Index blocks must be managed

***

#### Method 4: Counting

**Concept:** Instead of storing every free block, store **(start, count)** pairs for contiguous free regions.

**Structure:**
```
Free Space List:
┌───────────┬───────┐
│   Start   │ Count │
├───────────┼───────┤
│    100    │   5   │  ← Blocks 100-104 free
│    200    │  10   │  ← Blocks 200-209 free
│    500    │   3   │  ← Blocks 500-502 free
└───────────┴───────┘
```

**Advantages:**
- ✅ **Very efficient for contiguous allocation:** Directly find suitable (start, count)
- ✅ Compact if many contiguous free regions
- ✅ Fast allocation and deallocation

**Disadvantages:**
- ❌ **Requires merging:** When adjacent blocks freed, must merge entries
- ❌ Inefficient if disk heavily fragmented (many small gaps)

**Use case:** Systems with frequent contiguous allocation (databases)

***

#### Comparison Table

| Method | Space Overhead | Allocation Speed | Contiguous Alloc | Fragmentation Handling |
|--------|----------------|------------------|------------------|----------------------|
| **Bitmap** | 1 bit/block | **Fast** (bit scan) | **Easy** (find consecutive 0s) | Good |
| **Linked List** | 1 pointer/free block | Slow | Hard | Poor |
| **Grouping** | Medium | Medium | Medium | Medium |
| **Counting** | Small (if contiguous) | **Fast** | **Very easy** | **Best** |

**Modern choice:** **Bitmap** for general-purpose file systems (ext4, NTFS). **Counting** for databases and specialized systems.

***

### File Operations

Common operations provided by file systems:

#### 1. Create
```c
fd = create("filename");
```
- Allocate directory entry
- Allocate inode (metadata structure)
- Initialize attributes (size=0, timestamps, owner)

***

#### 2. Open
```c
fd = open("filename", mode);  // mode: read, write, append
```
- Search directory for filename
- Load inode into memory
- Create file descriptor (entry in open file table)
- Check permissions
- Return file descriptor to process

**Open File Table:**
```
Per-Process:
┌────┬─────────┬─────────┬─────────┐
│ FD │ Pointer │ Mode    │ Position│
├────┼─────────┼─────────┼─────────┤
│ 0  │ stdin   │ Read    │    -    │
│ 1  │ stdout  │ Write   │    -    │
│ 2  │ stderr  │ Write   │    -    │
│ 3  │ inode X │ Read    │    0    │
│ 4  │ inode Y │ Write   │  100    │
└────┴─────────┴─────────┴─────────┘
```

***

#### 3. Read
```c
n = read(fd, buffer, count);
```
- Check current file position
- Read up to `count` bytes into `buffer`
- Advance file position by bytes read
- Return number of bytes actually read

***

#### 4. Write
```c
n = write(fd, buffer, count);
```
- Write `count` bytes from `buffer` to file
- Advance file position
- Update file size (if extended)
- Mark blocks as dirty (for write-back)
- Return bytes written

***

#### 5. Seek (Reposition)
```c
seek(fd, offset, whence);
// whence: SEEK_SET (from start), SEEK_CUR (from current), SEEK_END (from end)
```
- Change current file position without I/O
- Enables random access

***

#### 6. Close
```c
close(fd);
```
- Flush any pending writes
- Remove entry from open file table
- Decrement reference count on inode
- If count = 0, write inode back to disk

***

#### 7. Delete (Unlink)
```c
unlink("filename");
```
- Remove directory entry
- Decrement inode link count
- If link count = 0 and no process has file open:
  - Free all data blocks
  - Free inode

***

#### 8. Truncate
```c
truncate("filename", new_size);
```
- Change file size
- If shrinking: free blocks beyond new size
- If growing: may allocate new blocks or leave holes (sparse file)

***

#### 9. Append
```c
fd = open("filename", O_APPEND);
write(fd, buffer, count);
```
- Each write automatically positions at end of file
- Useful for log files (concurrent appends are atomic in many systems)

***

#### 10. Rename
```c
rename("oldname", "newname");
```
- Change directory entry
- Inode and data blocks unchanged (fast operation)
- May fail if moving across file systems

***

### Spooling (Simultaneous Peripheral Operations On-Line)

**Definition:** Use disk as a **buffer** for I/O devices, allowing multiple processes to queue I/O requests without waiting.

#### Classic Example: Printer Spooling

**Without Spooling:**
```
Process A wants to print:
1. Process A opens printer (exclusive access)
2. Process A writes data directly to printer (slow!)
3. Process A waits minutes for printing to finish
4. Process A closes printer
5. Now Process B can print

Problem: Process A blocked during entire print job!
```

**With Spooling:**
```
Process A wants to print:
1. Process A writes data to SPOOL FILE on disk (fast!)
2. Process A returns immediately to computation
3. SPOOL DAEMON reads spool file and sends to printer (background)

Process B wants to print:
1. Process B writes to DIFFERENT spool file (no conflict!)
2. Daemon queues B's job after A's job

Result: Multiple processes can "print" simultaneously!
```

***

#### Spooling System Architecture

```
┌─────────────┐  ┌─────────────┐  ┌─────────────┐
│  Process A  │  │  Process B  │  │  Process C  │
└──────┬──────┘  └──────┬──────┘  └──────┬──────┘
       │                │                │
       │ Write fast     │ Write fast     │ Write fast
       ▼                ▼                ▼
    ┌────────────────────────────────────────┐
    │         SPOOL DIRECTORY (Disk)         │
    │  ┌──────┐  ┌──────┐  ┌──────┐         │
    │  │ Job A│  │ Job B│  │ Job C│         │
    │  └──────┘  └──────┘  └──────┘         │
    └───────────────┬────────────────────────┘
                    │
                    │ Read slow
                    ▼
            ┌────────────────┐
            │  SPOOL DAEMON  │
            │   (Background  │
            │    Process)    │
            └────────┬───────┘
                     │
                     │ Serial output
                     ▼
            ┌────────────────┐
            │    PRINTER     │
            │  (Slow Device) │
            └────────────────┘
```

***

#### Benefits of Spooling

1. **Concurrency:** Multiple processes can submit I/O without blocking.
2. **Speed mismatch resolution:** Fast disk buffers slow device.
3. **Batch processing:** Daemon can optimize job order (e.g., print shortest jobs first).
4. **Resource sharing:** Many processes share one physical device.
5. **Process isolation:** Processes don't interact directly with device.

**Formula:**
```
Without spooling:
Total time = Σ (Process computation + Device I/O time)
Processes execute SERIALLY

With spooling:
Total time ≈ max(Σ Process computation, Σ Device I/O time)
Processes execute CONCURRENTLY
```

***

#### Modern Examples

- **Print spooling:** Windows Print Spooler, CUPS (Unix)
- **Email spooling:** SMTP servers queue outgoing mail
- **Batch job spooling:** Mainframe job schedulers
- **Download managers:** Queue network transfers

**Memory Trick:** "SPOOL = **S**ave to disk, **P**rocess can leave, **O**utput happens **O**ffline, **L**ater"

***

### Metadata Logging and File System Recovery

#### Why Logging Metadata Ensures Recovery

**Problem:** File system operations are **multi-step** and may be interrupted by crash.

**Example: Creating a file**
```
Step 1: Allocate inode
Step 2: Update directory entry
Step 3: Mark inode allocated in bitmap
Step 4: Initialize inode fields

CRASH during step 3! ← System is now INCONSISTENT
- Directory points to inode
- But inode not marked as allocated (bitmap says free!)
- Next file allocation might reuse same inode → corruption!
```

***

#### Solution: Journaling (Write-Ahead Logging)

**Principle:** Before modifying file system, write a **log entry** describing the change.

**Process:**
```
1. Write LOG ENTRY to journal:
   "About to: allocate inode 1234, update directory /home/user"

2. Wait for log write to complete (fsync)

3. Perform actual file system modifications:
   - Allocate inode
   - Update directory
   - Update bitmap

4. Write LOG ENTRY:
   "Completed: operation XYZ"

5. Eventually checkpoint (mark log entries as committed)
```

***

#### Recovery After Crash

```
On reboot:
1. Check journal for uncommitted operations

2. If log says "About to X" but no "Completed X":
   → REPLAY operation X (redo)

3. If log says "Completed X":
   → Operation already done, skip

4. File system is now CONSISTENT!
```

***

#### Why It Works

**Key insight:** Writing to the **log is sequential** (fast) and **atomic** (sector write is atomic on most disks).

**Guarantees:**
- **Atomicity:** Either entire operation completes or none of it (no partial updates)
- **Consistency:** File system metadata always in valid state
- **Durability:** Once "completed" logged, changes are permanent

***

#### Types of Journaling

| Type | What's Logged | Speed | Safety | Use |
|------|--------------|-------|--------|-----|
| **Metadata-only** | Only metadata (inodes, directories, bitmaps) | **Fast** | Good | ext3 default, ext4 |
| **Full (data+metadata)** | Metadata + file data | Slow | **Best** | ext4 with `data=journal` |
| **Ordered** | Metadata logged, data written before | Medium | Good | ext3 ordered mode |

**Modern file systems with journaling:**
- **ext3/ext4 (Linux):** Journaling modes (journal, ordered, writeback)
- **NTFS (Windows):** Transaction log
- **HFS+ (macOS):** Journal
- **XFS, Btrfs, ZFS:** Copy-on-write + transaction logs

***

#### Example: Deleting a File

**Without Logging:**
```
1. Remove directory entry  ← CRASH HERE!
2. Free inode
3. Free data blocks

Result: Orphaned inode and blocks (leak, wasted space)
```

**With Logging:**
```
1. Log: "Begin delete file X (inode 1234)"
2. Log: "Remove dir entry"
3. Remove directory entry
4. Log: "Free inode 1234"
5. Free inode
6. Log: "Free blocks 500-505"
7. Free blocks
8. Log: "Complete delete file X"

Recovery: Check each logged step; if incomplete, complete it.
```

***

#### Benefits

✅ **Fast recovery:** Seconds instead of hours (vs full fsck)
✅ **Consistency:** No need for exhaustive consistency checks
✅ **Durability:** Committed changes survive crashes

**Trade-off:** Slight performance overhead (~5-10%) for writing log.

**Memory Trick:** "Journaling = Write TODO list before doing task. If crash, resume from list!"

***

## WORKED PROBLEMS

### Problem 1: C-SCAN Disk Scheduling (Detailed)

**Given:**
- Current head position: **45**
- Total tracks: 0-255 (256 tracks)
- Direction: Moving toward higher tracks (positive direction)
- Request queue: **40, 67, 11, 240, 145, 120, 85, 210**

**Sort requests:** 11, 40, 67, 85, 120, 145, 210, 240

***

**C-SCAN Algorithm:**

**Step 1: Service requests in current direction (toward 255)**
```
Current: 45

Requests ahead (toward 255): 67, 85, 120, 145, 210, 240

Service order:
45 → 67 → 85 → 120 → 145 → 210 → 240 → 255 (end)

Head movement (forward):
45 to 67: 22 tracks
67 to 85: 18 tracks
85 to 120: 35 tracks
120 to 145: 25 tracks
145 to 210: 65 tracks
210 to 240: 30 tracks
240 to 255: 15 tracks

Subtotal: 22 + 18 + 35 + 25 + 65 + 30 + 15 = 210 tracks
```

**Step 2: Jump back to beginning (0)**
```
255 → 0 (return jump)
Movement: 255 tracks (or counted as repositioning)
```

**Step 3: Service remaining requests (from 0 toward 255)**
```
Remaining requests: 11, 40

0 → 11 → 40

Head movement:
0 to 11: 11 tracks
11 to 40: 29 tracks

Subtotal: 11 + 29 = 40 tracks
```

***

**Total Head Movement:**
```
Forward pass: 210 tracks
Return: 255 tracks
Second pass: 40 tracks

Total = 210 + 255 + 40 = 505 tracks

OR (if return not counted):
Total = 210 + 40 = 250 tracks
```

**Answer:** 
- **With return counted: 505 tracks**
- **Without return counted: 250 tracks**

*(Exam convention varies; clarify which to use. Most textbooks count the return.)*

***

**Visual:**
```
Tracks: 0 ─────────────────────────────────────── 255

Start at 45:
Pass 1: 45 →→ 67 → 85 →→ 120 → 145 →→→ 210 →→ 240 → 255
Return: 255 ⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺⤺ 0
Pass 2: 0 → 11 →→ 40
```

***

### Problem 2: SSTF Disk Scheduling (Same Requests)

**Given:**
- Current: 45
- Queue: 40, 67, 11, 240, 145, 120, 85, 210

**SSTF Algorithm: Choose closest request each time**

```
Step 1: Current = 45
Distances: |40-45|=5, |67-45|=22, |11-45|=34, |240-45|=195, 
           |145-45|=100, |120-45|=75, |85-45|=40, |210-45|=165
Closest: 40 (distance 5)
Move: 45 → 40 (5 tracks)

Step 2: Current = 40
Remaining: 67, 11, 240, 145, 120, 85, 210
Distances: |67-40|=27, |11-40|=29, |240-40|=200, |145-40|=105, 
           |120-40|=80, |85-40|=45, |210-40|=170
Closest: 67 (distance 27)
Move: 40 → 67 (27 tracks)

Step 3: Current = 67
Remaining: 11, 240, 145, 120, 85, 210
Distances: |11-67|=56, |240-67|=173, |145-67|=78, 
           |120-67|=53, |85-67|=18, |210-67|=143
Closest: 85 (distance 18)
Move: 67 → 85 (18 tracks)

Step 4: Current = 85
Remaining: 11, 240, 145, 120, 210
Distances: |11-85|=74, |240-85|=155, |145-85|=60, 
           |120-85|=35, |210-85|=125
Closest: 120 (distance 35)
Move: 85 → 120 (35 tracks)

Step 5: Current = 120
Remaining: 11, 240, 145, 210
Distances: |11-120|=109, |240-120|=120, |145-120|=25, |210-120|=90
Closest: 145 (distance 25)
Move: 120 → 145 (25 tracks)

Step 6: Current = 145
Remaining: 11, 240, 210
Distances: |11-145|=134, |240-145|=95, |210-145|=65
Closest: 210 (distance 65)
Move: 145 → 210 (65 tracks)

Step 7: Current = 210
Remaining: 11, 240
Distances: |11-210|=199, |240-210|=30
Closest: 240 (distance 30)
Move: 210 → 240 (30 tracks)

Step 8: Current = 240
Remaining: 11
Move: 240 → 11 (229 tracks)
```

***

**Total Head Movement:**
```
5 + 27 + 18 + 35 + 25 + 65 + 30 + 229 = 434 tracks
```

**Answer: 434 tracks**

***

**Comparison:**
- **C-SCAN:** 505 tracks (or 250 without return)
- **SSTF:** 434 tracks
- **SSTF is better** (but note the huge final jump 240→11, illustrating potential starvation)

***

### Problem 3: FCFS and C-SCAN Comparison

**Given:**
- Current head: 143
- Total tracks: 0-199 (200 tracks)
- Request queue: **125, 17, 23, 67, 90, 128, 189, 140**

***

#### FCFS (First-Come, First-Served)

**Service in arrival order:**
```
143 → 125 → 17 → 23 → 67 → 90 → 128 → 189 → 140

Head movements:
143 to 125: 18
125 to 17: 108
17 to 23: 6
23 to 67: 44
67 to 90: 23
90 to 128: 38
128 to 189: 61
189 to 140: 49

Total: 18 + 108 + 6 + 44 + 23 + 38 + 61 + 49 = 347 tracks
```

**Answer: 347 tracks**

***

#### C-SCAN

**Assume direction: toward 199 (higher tracks)**

**Sort requests:** 17, 23, 67, 90, 125, 128, 140, 189

**Pass 1: Service requests ahead**
```
Current: 143
Ahead: 189

143 → 189 → 199 (end)

Movement: (189-143) + (199-189) = 46 + 10 = 56 tracks
```

**Return:**
```
199 → 0
Movement: 199 tracks
```

**Pass 2: Service remaining**
```
0 → 17 → 23 → 67 → 90 → 125 → 128 → 140

Movement:
0 to 17: 17
17 to 23: 6
23 to 67: 44
67 to 90: 23
90 to 125: 35
125 to 128: 3
128 to 140: 12

Subtotal: 17 + 6 + 44 + 23 + 35 + 3 + 12 = 140 tracks
```

**Total:**
```
56 + 199 + 140 = 395 tracks

OR (without return counted):
56 + 140 = 196 tracks
```

**Answer: 395 tracks (with return) or 196 tracks (without)**

***

**Comparison:**
- **FCFS:** 347 tracks
- **C-SCAN:** 395 tracks (with return) or 196 tracks (without)

**Observation:** In this case, FCFS happens to be better than C-SCAN (with return counted) because requests are somewhat sequential. Without counting return, C-SCAN is much better.

***

## EXAM TIPS & MEMORY AIDS

### Quick Formulas

**Total Access Time:**
```
Access Time = Seek Time + Rotational Latency + Transfer Time
```

**Average Rotational Latency:**
```
Avg = (60 / RPM) / 2 seconds
Example: 7200 RPM → (60/7200)/2 = 0.00417 s = 4.17 ms
```

**Transfer Time:**
```
Transfer Time = Data Size / Transfer Rate
Example: 4 KB at 100 MB/s = 4096 / (100 × 1024²) = 0.039 ms
```

**Disk Capacity (CAV):**
```
Capacity = Tracks × Avg Sectors/Track × Bytes/Sector × Surfaces
```

***

### Mnemonics

**Disk Scheduling Algorithms:**
- **FCFS** = **F**air but **C**razy **F**lailing, **S**low
- **SSTF** = **S**hortest **S**eek, but may **S**tarve **T**racks **F**ar away
- **SCAN** = Like **SC**anning barcode, **A**lways **N**ext in line
- **C-SCAN** = **C**ircular like **C**onveyor belt
- **C-LOOK** = C-SCAN but **LOOK** where to stop

**File Allocation:**
- **Contiguous** = **Con**venient for reads, but **tig**ht (inflexible)
- **Linked** = **Link**ed like chain, slow random access
- **Indexed** = **Index** like book, fast lookup

**Free Space:**
- **Bitmap** = **Bit** for each block, **map** of occupancy
- **Linked** = **Link** free blocks in chain
- **Counting** = **Count** contiguous free regions

**Spooling:**
- **SPOOL** = **S**imultaneous **P**eripheral **O**perations **O**n-**L**ine

***

### Common Mistakes

❌ **Mistake 1:** Confusing seek time and rotational latency
- **Seek** = arm movement (track to track)
- **Rotation** = platter spinning (sector to sector)

❌ **Mistake 2:** Forgetting to count return in C-SCAN
- Check exam convention! Some count it, some don't.

❌ **Mistake 3:** SSTF choosing wrong "closest"
- Calculate **absolute distance** |current - request|

❌ **Mistake 4:** Thinking linked allocation is fast for random access
- Linked = O(n) random access (must traverse)
- Indexed = O(1) random access

❌ **Mistake 5:** Confusing directory structures
- Tree = hierarchical, no sharing
- Acyclic graph = hierarchical + sharing (links)

❌ **Mistake 6:** Forgetting metadata in journaling
- Journal logs **operations**, not just data

***

### Exam Pattern Recognition

**"Calculate total head movement" → Disk scheduling**
- Identify algorithm (FCFS/SSTF/SCAN/C-SCAN/C-LOOK)
- Draw diagram or list movements
- Sum distances

**"Compare CLV vs CAV" → Table with applications**
- CLV = optical (CD/DVD)
- CAV = magnetic (HDD)

**"Which file allocation minimizes directory space?" → Contiguous**
- Only 2 values: start + length

**"Explain spooling benefit" → Concurrency + speed matching**
- Multiple processes queue I/O without blocking

**"Why journaling helps recovery?" → Atomicity + consistency**
- Log operations before executing
- Replay log on crash

***

### Real-World Context

**Linux:**
- Disk scheduler: Deadline, CFQ, or BFQ (variants of C-LOOK)
- File systems: ext4 (journaling), XFS, Btrfs
- Free space: Bitmap (ext4)

**Windows:**
- Disk scheduler: Optimized for SSDs (less important with SSDs)
- File system: NTFS (journaling via USN journal)
- Free space: Bitmap

**SSDs (Solid State Drives):**
- No moving parts → seek time = 0!
- Disk scheduling less important (but still used for fairness)
- Wear leveling replaces traditional free space management

***

### Final Checklist for Unit 5

✅ **Can you explain:**
- [ ] Seek time vs rotational latency with example
- [ ] CLV vs CAV with applications
- [ ] How C-SCAN differs from SCAN
- [ ] Why SSTF can cause starvation
- [ ] Three file allocation methods with pros/cons
- [ ] How spooling improves system performance
- [ ] Why metadata logging ensures recovery
- [ ] Difference between tree and acyclic graph directories

✅ **Can you calculate:**
- [ ] Total head movement for FCFS/SSTF/SCAN/C-SCAN
- [ ] Average rotational latency given RPM
- [ ] Total access time (seek + rotation + transfer)
- [ ] Bitmap size given disk capacity and block size

✅ **Can you compare:**
- [ ] FCFS vs SSTF vs C-SCAN (3 criteria)
- [ ] Contiguous vs Linked vs Indexed allocation
- [ ] Bitmap vs Linked List free space management
- [ ] RAID 1 vs RAID 5 read throughput

