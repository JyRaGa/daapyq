

# UNIT 4: MEMORY MANAGEMENT — EXAM REVISION SHEET (Enhanced)

## BASICS OF MEMORY MANAGEMENT

### Major Activities of OS in Memory Management

Think of the OS as a **librarian managing books (memory) for readers (processes)**:

1. **Keep track of memory (The Inventory):**
   - Maintain data structures (bitmaps, linked lists) showing which memory regions are free/occupied.
   - Example: Bitmap where 1 = occupied, 0 = free.

2. **Allocate memory (Check Out Books):**
   - When process starts, assign it memory space.
   - Choose allocation strategy: contiguous (all together), paging (split into pages), segmentation (logical chunks).

3. **Deallocate memory (Return Books):**
   - When process terminates, reclaim its memory.
   - Coalesce adjacent free blocks to prevent fragmentation.

4. **Manage swapping (Storage Room):**
   - Move inactive processes to disk (swap space) when RAM full.
   - Bring them back when needed (like storing rarely-read books in the basement).

5. **Protect memory (Access Control):**
   - Prevent Process A from reading/writing Process B's memory.
   - Use hardware: base/limit registers, page table protection bits (read/write/execute).

6. **Implement virtual memory (Magic Library):**
   - Each process thinks it has unlimited memory starting at address 0.
   - OS maps virtual addresses to actual physical locations.

7. **Optimize performance (Efficient Management):**
   - Minimize fragmentation (wasted space).
   - Reduce page faults (disk accesses).
   - Exploit locality (keep frequently-used pages in RAM).

***

### Numerical: Limit Register Bits

**Memory Aid:** "Limit register stores the SIZE (or max offset) of the partition, not the number of partitions."

**Question:** System has 2²⁴ bytes total memory with fixed partitions of size 65536 bytes. How many bits for limit register?

**Step-by-step Solution:**
```
Total memory = 2²⁴ bytes = 16 MB
Partition size = 65536 bytes = 2¹⁶ bytes = 64 KB

Limit register stores: Maximum offset within a partition
Maximum offset = 65536 - 1 = 65535 (if 0-indexed)

To represent 65535: Need ⌈log₂(65535)⌉ = 16 bits
To represent 65536: Need ⌈log₂(65536)⌉ = 17 bits

Answer: 16 bits (if storing last valid offset)
        17 bits (if storing partition size exactly)
```

**Practical Answer:** Most systems use **16 bits** (storing offsets 0-65535).

**Intuition:** Think "2¹⁶ = 65536, so 16 bits covers the range 0 to 65535."

***

### Internal vs External Fragmentation (With Examples)

**Memory Aid: "IN-ternal = IN-side a block; EX-ternal = EX-posed gaps between blocks"**

#### Internal Fragmentation

**Definition:** Wasted space **inside** an allocated memory block because the block is larger than needed.

**Concrete Example:**
```
Process needs: 18 KB
System allocates: 20 KB page (fixed size)
Wasted (internal): 2 KB inside that page
```

**Visual:**
```
┌─────────────────────┐
│ Used: 18 KB         │
│ - - - - - - - - - - │  ← Internal waste (2 KB)
│ Wasted: 2 KB        │
└─────────────────────┘
    20 KB Page
```

**Where it occurs:** Fixed-size allocation (paging, fixed partitions).

***

#### External Fragmentation

**Definition:** Wasted space **between** allocated blocks; total free space is sufficient but not contiguous.

**Concrete Example:**
```
Memory layout:
[Process A: 10 KB] [Free: 5 KB] [Process B: 15 KB] [Free: 3 KB] [Process C: 8 KB] [Free: 4 KB]

Total free: 5 + 3 + 4 = 12 KB
New process needs: 10 KB contiguous
Result: Cannot allocate! (No single 10 KB block)
```

**Visual:**
```
┌────────┬──────┬────────┬─────┬────────┬─────┐
│Process │ Free │Process │Free │Process │Free │
│   A    │ 5 KB │   B    │3 KB │   C    │4 KB │
└────────┴──────┴────────┴─────┴────────┴─────┘
          ↑ Too small    ↑       ↑
          Can't fit 10 KB process anywhere!
```

**Where it occurs:** Variable-size allocation (segmentation, dynamic partitioning).

***

#### Comparison Table (Enhanced)

| Aspect | Internal Fragmentation | External Fragmentation |
|--------|----------------------|----------------------|
| **Location** | Inside allocated blocks | Between allocated blocks |
| **Cause** | Block size > actual need | Many small scattered holes |
| **Occurs in** | Paging, fixed partitions | Segmentation, dynamic partitioning |
| **Visibility** | Hidden (process doesn't see it) | Visible in memory map |
| **Example** | 18 KB process gets 20 KB page → 2 KB wasted | Three 5 KB holes can't fit 10 KB process |
| **Solution** | Smaller page sizes (↑ overhead) | Compaction (move processes to consolidate) |
| **Formula** | Avg waste = Page Size / 2 per process | No simple formula; depends on pattern |

**Memory Trick:** "Internal = Like empty seats in your reserved train compartment. External = Like multiple short train segments that can't be joined."

***

### First-fit, Best-fit, Worst-fit (With Scenarios)

**Scenario:** Free holes of sizes: [5 KB, 12 KB, 8 KB, 20 KB]. Process needs **10 KB**.

#### First-fit: "Take the FIRST hole that fits"
```
Scan: 5 KB (too small) → 12 KB (fits!) → Allocate here.
Result: Allocate in 12 KB hole → leaves 2 KB hole.
Speed: ⚡ Fast (stops searching early)
```

#### Best-fit: "Find the SMALLEST hole that fits"
```
Scan all: 5 KB (no), 12 KB (fits, waste=2), 8 KB (no), 20 KB (fits, waste=10)
Choose: 12 KB hole (minimum waste)
Result: Allocate in 12 KB → leaves 2 KB hole
Speed: 🐢 Slow (must scan entire list)
Problem: Creates many tiny holes (2 KB) → hard to use later
```

#### Worst-fit: "Find the LARGEST hole"
```
Scan all: max = 20 KB
Choose: 20 KB hole
Result: Allocate in 20 KB → leaves 10 KB hole
Speed: 🐢 Slow (must scan entire list)
Idea: Larger leftover (10 KB) might be useful for next process
Reality: Large holes disappear quickly; not effective
```

***

#### Performance Comparison

| Algorithm | Speed | Space Efficiency | Practical Use |
|-----------|-------|------------------|---------------|
| **First-fit** | **Fast** (early stop) | Good | ✅ Most commonly used |
| **Best-fit** | Slow (full scan) | Poor (tiny fragments) | ❌ Rarely used |
| **Worst-fit** | Slow (full scan) | Poor | ❌ Rarely used |

**Memory Trick:** "First-fit is FIRST choice in practice!"

**Why Best-fit is worst:** Ironic name! It creates a "dust" of tiny unusable holes.

***

### Page Size and Internal Fragmentation (Detailed)

#### The Mathematics

**Average internal fragmentation per process:**
```
Process needs X bytes.
System allocates ⌈X / Page Size⌉ pages.
Last page is partially filled.

Average waste in last page = Page Size / 2

Example:
Page Size = 4 KB = 4096 bytes
Average waste per process = 2 KB
```

**Why we can't just use tiny pages:**

| Page Size | Internal Frag ↓ | Page Table Size ↑ | I/O Operations ↑ | Translation Speed ↓ |
|-----------|----------------|-------------------|------------------|---------------------|
| **1 KB** | 0.5 KB waste | 4× entries | 4× disk ops | Slower |
| **4 KB** | 2 KB waste | Standard | Normal | Normal |
| **16 KB** | 8 KB waste | ÷4 entries | ÷4 disk ops | Faster |

#### Real-World Trade-off

**Modern systems use 4 KB as "sweet spot":**
- Not too much internal fragmentation (2 KB avg).
- Page table size manageable.
- Disk I/O reasonable (4 KB blocks match disk sectors).
- Hardware optimized for 4 KB (TLB entries, cache lines).

**Special cases:**
- **Huge pages (2 MB, 1 GB):** For databases, HPC applications to reduce TLB misses.
- **Tiny pages (512 B):** Historically on embedded systems with small RAM.

**Can internal fragmentation be solved completely?**  
❌ **No.** It's an inherent trade-off. You can only minimize it by choosing appropriate page sizes for your workload.

**Memory Analogy:** "Like packing books in boxes. Small boxes = less empty space but more boxes to manage. Large boxes = fewer boxes but more empty space."

***

## PAGING & SEGMENTATION (Enhanced Explanations)

### Paging vs Segmentation: The Big Picture

**Think of your house:**
- **Paging:** Divide your house into uniform-sized rooms (each 10×10 feet), regardless of function. Put furniture wherever it fits across rooms.
- **Segmentation:** Divide by function: bedroom, kitchen, bathroom (different sizes). Each room holds related items.

#### Detailed Comparison Table

| Aspect | Paging | Segmentation |
|--------|--------|--------------|
| **Philosophy** | Physical division (hardware view) | Logical division (programmer view) |
| **Size** | Fixed (e.g., 4 KB) | Variable (code=50KB, data=20KB, stack=10KB) |
| **User Awareness** | Invisible; hardware handles it | Visible; programmer sees segments |
| **Address Space** | Single linear space | Multiple address spaces (one per segment) |
| **Address Format** | `[Page# | Offset]` | `[Segment# | Offset]` |
| **Fragmentation** | ✅ Internal only (avg PageSize/2 per process) | ❌ External (gaps between segments) |
| **Table Size** | ❌ Large (one entry per page; 2²⁰ entries for 4GB space with 4KB pages) | ✅ Small (one entry per segment; typically <10 segments) |
| **Protection** | Per-page (R/W/X bits) | Per-segment (natural units: code=RX, data=RW) |
| **Sharing** | ❌ Hard (page boundaries arbitrary) | ✅ Easy (share entire code segment) |
| **Translation Speed** | ⚡ Fast (bit shift for offset) | 🐌 Slower (needs bounds checking) |
| **Modern Use** | ✅ Dominant (Linux, Windows) | ❌ Rare (mostly legacy) |

***

### Why Paging is Faster (Detailed)

#### Address Translation Comparison

**Paging:**
```c
// Given: Logical Address = 0x1234 (4660 decimal), Page Size = 4KB (4096 = 2¹²)
Page Number = 0x1234 >> 12 = 0x1      // Right shift 12 bits (single CPU cycle)
Offset      = 0x1234 & 0xFFF = 0x234  // Mask lower 12 bits (single CPU cycle)

// Hardware does:
Frame = PageTable[PageNumber];  // One memory access (or TLB hit)
Physical Address = (Frame << 12) | Offset;  // Bit shift + OR
```

**Segmentation:**
```c
// Given: Logical Address = (seg=2, offset=500)
// Must access segment table
SegmentEntry = SegmentTable;  // Memory access

// Bounds checking (extra step!)
if (offset >= SegmentEntry.limit) {
    TRAP(SEGMENTATION_FAULT);  // Trap to OS
}

Physical Address = SegmentEntry.base + offset;  // Addition
```

#### Why Paging Wins

1. **No division needed:** Page size = 2ⁿ → address split is just bit manipulation.
2. **No bounds checking:** Offset is implicitly valid (can't exceed page size).
3. **Uniform table:** All entries same size → predictable cache behavior.
4. **TLB optimization:** Modern CPUs have dedicated TLB hardware for paging.

**Segmentation loses because:**
- Requires division (slow) if segment sizes aren't powers of 2.
- Bounds checking adds CPU cycle.
- Variable-size entries → less cache-friendly.

**Speed difference:** Paging ~10× faster in practice.

***

### Segmented Paging: Best of Both Worlds

**Problem:** Paging ignores program structure. Segmentation wastes memory.

**Solution:** **Segmented Paging** = Logical segments, each divided into pages.

#### Architecture

```
Logical Address: [Segment# | Page# | Offset]
                    (s)        (p)      (d)

Example (x86 with 4KB pages):
Address: 0x12345678
│
├─ Segment# (s) = 0x1
├─ Page# (p)    = 0x234
└─ Offset (d)   = 0x678
```

#### Translation Process (3 Steps)

```
1. Segment Table Lookup:
   SegmentTable[s] → Base of segment's page table

2. Page Table Lookup:
   PageTable[Base + p] → Frame number

3. Construct Physical Address:
   PhysicalAddr = (Frame << offset_bits) | Offset
```

#### Visual Example

```
Logical: Segment 2, Page 5, Offset 123

Step 1:
┌─────────────────┐
│ Segment Table   │
├─────────────────┤
│ Seg 0: PT_base0 │
│ Seg 1: PT_base1 │
│ Seg 2: PT_base2 │◄─── s=2 → base of segment 2's page table
│ Seg 3: PT_base3 │
└─────────────────┘

Step 2:
┌──────────────────┐
│ Page Table (S2)  │
├──────────────────┤
│ Page 0: Frame 10 │
│ Page 1: Frame 23 │
│ ...              │
│ Page 5: Frame 47 │◄─── p=5 → Frame 47
└──────────────────┘

Step 3:
Physical Address = Frame 47, Offset 123
```

#### Why It's Important

✅ **Advantages:**
- Logical organization (segments = code, data, stack).
- Protection at segment level (e.g., code segment = read-only).
- Sharing at segment level (multiple processes share code segment).
- No external fragmentation (paging handles physical memory).
- Smaller page tables (each segment has its own, and unused segments have no tables).

❌ **Disadvantages:**
- More complex hardware.
- Three memory accesses for translation (mitigated by TLB).

**Memory Trick:** "Seg-Paging = Organize logically (segments), allocate physically (pages)."

***

### Why Page Sizes are Powers of 2 (Deeper Explanation)

#### The Hardware Perspective

**With Power-of-2 Page Size (e.g., 4 KB = 2¹²):**

```
Logical Address (32-bit): 0x12345678

Binary: 0001 0010 0011 0100 0101 0110 0111 1000
        └─────────────┬─────────────┘ └────┬────┘
           Page Number (20 bits)      Offset (12 bits)

Extraction (single cycle):
Page# = LogicalAddr >> 12        // Right shift
Offset = LogicalAddr & 0xFFF     // Bitwise AND with mask
```

**With Non-Power-of-2 Page Size (e.g., 5 KB = 5120 bytes):**

```
Logical Address: 0x12345678 (305,419,896 decimal)

Must perform division:
Page# = 305419896 / 5120 = 59652.324...  // Integer division (multi-cycle!)
Offset = 305419896 % 5120 = 1656         // Modulo operation (multi-cycle!)
```

#### Performance Impact

| Operation | Power of 2 | Non-Power of 2 |
|-----------|-----------|----------------|
| **Extract page#** | 1 CPU cycle (shift) | ~40 cycles (division) |
| **Extract offset** | 1 CPU cycle (mask) | ~40 cycles (modulo) |
| **Hardware complexity** | Simple (wires) | Complex (divider circuit) |

#### Memory Alignment Benefits

**Power of 2 pages align on natural boundaries:**
```
Page 0: 0x00000000 - 0x00000FFF (4096 bytes)
Page 1: 0x00001000 - 0x00001FFF
Page 2: 0x00002000 - 0x00002FFF
...
        └─ Lower 12 bits always 0 for page start
```

This simplifies:
- Cache line alignment
- DMA transfers
- Memory protection checking

**Bottom line:** Non-power-of-2 pages would make computers ~40× slower for memory access!

***

### Numerical: Page Table Entries (Detailed Walkthrough)

**Given:**
- Logical address: 32 bits (4 GB address space)
- Page size: 4 KB = 2¹² bytes
- Physical memory: 512 MB = 2²⁹ bytes

#### Conventional Single-Level Page Table

**Step 1: Calculate number of pages in logical space**
```
Pages = Logical Address Space / Page Size
      = 2³² bytes / 2¹² bytes
      = 2²⁰ pages
      = 1,048,576 pages
```

**Step 2: One entry per page**
```
Page Table Entries = 2²⁰ = 1,048,576 entries
```

**Step 3: Calculate page table size**
```
Each entry needs:
- Frame number: log₂(512MB / 4KB) = log₂(2²⁹ / 2¹²) = 17 bits
- Protection bits: ~3 bits (R/W/X)
- Valid bit: 1 bit
- Reference bit: 1 bit
- Dirty bit: 1 bit
Total: ~24 bits ≈ 4 bytes per entry

Page Table Size = 1,048,576 entries × 4 bytes = 4 MB per process!
```

#### Inverted Page Table

**Step 1: Calculate number of frames in physical memory**
```
Frames = Physical Memory / Page Size
       = 2²⁹ bytes / 2¹² bytes
       = 2¹⁷ frames
       = 131,072 frames
```

**Step 2: One entry per frame (not per page!)**
```
Inverted Page Table Entries = 2¹⁷ = 131,072 entries
```

**Step 3: Calculate inverted page table size**
```
Each entry needs:
- PID (process ID): ~16 bits
- Page number: 20 bits
- Protection bits: ~3 bits
Total: ~5 bytes per entry

Inverted PT Size = 131,072 entries × 5 bytes ≈ 640 KB (system-wide!)
```

#### Comparison

| Scheme | Entries | Size | Per-Process? | Lookup |
|--------|---------|------|--------------|--------|
| **Conventional** | 2²⁰ (1M) | 4 MB | ✅ Yes | Fast (direct index) |
| **Inverted** | 2¹⁷ (131K) | 640 KB | ❌ No (global) | Slow (hash/search) |

**Memory Trick:** "Conventional = one entry per **PAGE** (logical). Inverted = one entry per **FRAME** (physical)."

***

### Purpose of Paging the Page Tables (Multi-Level Paging Explained)

#### The Problem

**64-bit system with 4 KB pages:**
```
Logical address space = 2⁶⁴ bytes
Page size = 2¹² bytes
Number of pages = 2⁶⁴ / 2¹² = 2⁵² pages

Single-level page table = 2⁵² entries × 8 bytes = 32 million TB!
```

This is impossible to store in physical memory!

#### The Solution: Hierarchical (Multi-Level) Page Tables

**2-Level Paging Example (32-bit address, 4 KB pages):**

```
Logical Address (32 bits):
┌────────────┬────────────┬──────────────┐
│   P1 (10)  │   P2 (10)  │  Offset (12) │
└────────────┴────────────┴──────────────┘
 Outer table  Inner table   Page offset

Translation:
1. Use P1 to index outer page directory
2. Get base of inner page table
3. Use P2 to index inner page table
4. Get frame number
5. Combine frame + offset
```

#### Visual Representation

```
         Logical Address
              │
              ▼
    ┌─────────────────┐
    │ Page Directory  │ ◄── Outer table (always in memory)
    │  (1024 entries) │
    └─────────┬───────┘
              │ P1 index
              ▼
    ┌─────────────────┐
    │  Page Table     │ ◄── Inner table (paged in on demand)
    │  (1024 entries) │
    └─────────┬───────┘
              │ P2 index
              ▼
    ┌─────────────────┐
    │  Physical Frame │
    │  (4096 bytes)   │
    └─────────────────┘
```

#### Key Benefits

**1. Space Savings:**
```
Single-level: 2²⁰ entries × 4 bytes = 4 MB (always allocated)

Two-level:
- Outer table: 2¹⁰ entries × 4 bytes = 4 KB (always allocated)
- Inner tables: 2¹⁰ entries × 4 bytes = 4 KB each (allocated on demand)

If process uses only 4 MB of address space:
- 4 MB / 4 KB pages = 1024 pages
- Need only 1 outer entry + 1 inner table
- Total: 4 KB (outer) + 4 KB (inner) = 8 KB vs 4 MB! (500× savings)
```

**2. Lazy Allocation:**
- Create inner page tables only when that region of address space is used.
- Unused regions (e.g., unallocated heap) don't consume page table memory.

**3. Enables Large Address Spaces:**
- 64-bit systems use 4-level or 5-level paging.
- Example: Linux x86-64 uses 4-level paging (PML4 → PDP → PD → PT → Frame).

**Memory Trick:** "Multi-level paging = Index pages, like index in a book → chapter → section → page."

***

## VIRTUAL MEMORY & THRASHING (Detailed)

### Virtual Memory: The Complete Picture

**Analogy:** Your smartphone shows "storage almost full" at 60 GB, but you have a 128 GB cloud backup. You can access all 128 GB seamlessly, even though only 60 GB fits on device.

#### How Virtual Memory Works

```
Process thinks:
┌───────────────────────────────────┐
│ My Address Space (0 to 4 GB)     │
│                                   │
│ 0x00000000 ─► Code                │
│ 0x10000000 ─► Data                │
│ 0x20000000 ─► Heap                │
│ 0xBFFFFFFF ─► Stack               │
└───────────────────────────────────┘

Reality (Physical Memory: 1 GB):
┌─────────┬─────────┬─────────┬─────────┐
│ Frame 0 │ Frame 1 │ Frame 2 │ Frame 3 │ ...
│ Proc A  │ Proc B  │ Proc A  │ Proc C  │
│ Page 0  │ Page 5  │ Page 3  │ Page 0  │
└─────────┴─────────┴─────────┴─────────┘

Disk (Swap Space):
┌──────────────────────────────────────┐
│ Swapped out pages: A.P1, A.P2, B.P3 │
└──────────────────────────────────────┘
```

#### Page Table Entries (PTE) Structure

```
┌────────┬─────┬─────┬─────┬─────┬─────┬──────────────┐
│ Frame# │  V  │  R  │  W  │  X  │  D  │   Accessed   │
└────────┴─────┴─────┴─────┴─────┴─────┴──────────────┘
    ↓       ↓     ↓     ↓     ↓     ↓          ↓
  Physical Valid Read Write Exec  Dirty  Reference bit
  location bit            permission  (modified)  (recently used)

V=0: Page not in memory (triggers page fault)
V=1: Page in physical memory at Frame#
```

***

### Locality of Reference (With Concrete Examples)

#### Temporal Locality: "If you used it recently, you'll use it again soon"

**Example 1: Loop**
```c
for (int i = 0; i < 1000000; i++) {
    sum += array[i];  // Variable 'sum' accessed repeatedly
}
// 'sum' has high temporal locality (used 1M times)
```

**Example 2: Function Calls**
```c
void processData() {
    // Called 1000 times
    helper();  // This function's code has high temporal locality
}
```

***

#### Spatial Locality: "If you used this, you'll use nearby addresses soon"

**Example 1: Array Traversal**
```c
int array[1000];
for (int i = 0; i < 1000; i++) {
    array[i] = 0;  // Accessing consecutive memory locations
}
// Elements array[0], array, array... are spatially close
```

**Example 2: Sequential Instruction Execution**
```
Address   Instruction
0x1000:   MOV R1, R2      ← Execute this
0x1004:   ADD R1, #5      ← Then this (next address)
0x1008:   JMP 0x2000      ← Then this
```

***

#### Why Locality Matters

**Without locality:**
```
Access pattern: [Page 1] [Page 500] [Page 3] [Page 750] ...
Result: Every access misses → constant page faults → thrashing
```

**With locality:**
```
Access pattern: [Page 1] [Page 1] [Page 1] [Page 2] [Page 2] ...
Result: Most accesses hit same page → few page faults → good performance
```

**Cache hit rates** (real system):
- With locality: 95-99% hit rate
- Without locality: 10-20% hit rate

**Memory Trick:** "Temporal = TIME (use again soon). Spatial = SPACE (nearby locations)."

***

### Demand Paging (Step-by-Step)

#### Initial State: Process Starts

```
Process created, page table initialized:
┌────┬───────┬───────┐
│ P# │ Frame │ Valid │
├────┼───────┼───────┤
│ 0  │   -   │   0   │ ◄─ All pages marked invalid
│ 1  │   -   │   0   │
│ 2  │   -   │   0   │
│ 3  │   -   │   0   │
└────┴───────┴───────┘

Physical Memory: Empty (for this process)
Disk: Has entire program
```

#### Step 1: Process Accesses Page 0

```
1. CPU generates logical address in Page 0
2. MMU checks page table: Valid=0 → PAGE FAULT!
3. Trap to OS page fault handler
```

#### Step 2: OS Page Fault Handler

```
OS actions:
1. Check if access is legal (within process's address space)
   - If illegal → SEGMENTATION FAULT (kill process)
2. Find free frame (or evict a page if memory full)
3. Read Page 0 from disk into free frame
   - Disk I/O: ~5 ms (slow!)
4. Update page table:
   ┌────┬───────┬───────┐
   │ P# │ Frame │ Valid │
   ├────┼───────┼───────┤
   │ 0  │   7   │   1   │ ◄─ Now valid, points to frame 7
   │ 1  │   -   │   0   │
   │ 2  │   -   │   0   │
   │ 3  │   -   │   0   │
   └────┴───────┴───────┘
5. Restart the faulting instruction
```

#### Step 3: Instruction Restart

```
1. CPU re-executes the same instruction
2. MMU checks page table: Valid=1 → translate to frame 7
3. Access succeeds!
```

#### Subsequent Accesses to Page 0

```
1. CPU generates address in Page 0
2. MMU checks: Valid=1 → frame 7
3. Direct memory access (no fault, no OS involvement)
4. Fast! (~100 ns)
```

**Performance:**
- First access: ~5 ms (page fault)
- Subsequent accesses: ~100 ns (50,000× faster!)

**Memory Trick:** "Demand Paging = Lazy loading. Bring pages only when DEMANDED (accessed)."

***

### Optimal Page Size: The Engineering Trade-off

#### Trade-off Analysis

**Small Pages (e.g., 1 KB):**

✅ **Pros:**
- Less internal fragmentation (avg 512 bytes waste per process)
- Better working set resolution (finer granularity)
- Less wasted memory when loading pages

❌ **Cons:**
- Huge page tables (4× entries vs 4 KB pages)
- More TLB misses (TLB has fixed entry count)
- More page faults (working set spans more pages)
- More disk I/Os (4× operations)
- Slower address translation (larger page table to search)

***

**Large Pages (e.g., 16 KB):**

✅ **Pros:**
- Smaller page tables (¼ entries vs 4 KB pages)
- Fewer TLB misses
- Fewer page faults (working set fits in fewer pages)
- Better disk I/O (fewer, larger transfers)
- Faster translation

❌ **Cons:**
- More internal fragmentation (avg 8 KB waste per process)
- Poor resolution (bring in 16 KB when only need 1 KB)
- Wasted memory bandwidth

***

#### Mathematical Analysis

**Total overhead:**
\[
\text{Overhead} = \frac{\text{Page Table Size}}{P} + \frac{P}{2} + \frac{S \times E}{P}
\]

Where:
- \(P\) = Page size
- \(S\) = Average process size
- \(E\) = Page table entry size

**Optimal page size:** Differentiate and set to 0 → \(P = \sqrt{2SE}\)

**For typical values** (S=1MB, E=4 bytes): \(P = \sqrt{2 \times 10^6 \times 4} \approx 2800\) bytes ≈ **4 KB** (practical compromise).

***

#### Real-World Strategy

**Modern systems use adaptive approach:**
1. **Standard pages (4 KB):** Default for most processes.
2. **Huge pages (2 MB, 1 GB):** Opt-in for:
   - Databases (large working sets)
   - Scientific computing (matrix operations)
   - Virtual machines (reduce nested paging overhead)

**Memory Trick:** "4 KB = sweet spot, like Goldilocks' porridge (not too hot, not too cold)."

***

### Thrashing: The Death Spiral (Detailed)

#### What is Thrashing?

**Definition:** System spends more time swapping pages in/out than executing useful work.

**Concrete Example:**
```
System has: 100 MB RAM
Running: 10 processes, each needs 15 MB

Total needed: 10 × 15 = 150 MB
Available: 100 MB
Deficit: 50 MB

What happens:
1. Process A runs, needs page → page fault
2. OS swaps out Process B's page to make room
3. Process B runs, needs its page back → page fault
4. OS swaps out Process A's page
5. Repeat indefinitely → CPU sits idle waiting for I/O!
```

***

#### CPU Utilization vs Multiprogramming (Detailed Graph)

```
CPU
Utilization
   100% ┤
        │        ╱‾‾‾‾╲                Thrashing
        │       ╱      ╲               Region
    80% ┤      ╱        ╲              (Death
        │     ╱          ╲___           Spiral)
    60% ┤    ╱               ╲___
        │   ╱                    ╲___
    40% ┤  ╱                         ╲___
        │ ╱                              ╲
    20% ┤╱                                ╲___
        │                                     ╲___
     0% └──────────────────────────────────────────►
        0    2    4    6    8   10   12   14   16
              Degree of Multiprogramming

Zone 1 (0-4): Too few processes → CPU often idle
Zone 2 (4-6): Optimal → CPU busy, low page faults
Zone 3 (6+):  Too many → page fault rate explodes
```

**Page Fault Rate Graph:**

```
Page
Fault
Rate
  High ┤                           ___╱‾‾
       │                      ___╱‾
       │                 ___╱‾
       │            ___╱‾
   Med ┤       ___╱‾
       │  ___╱‾
       │╱‾
   Low ┤
       └──────────────────────────────────►
       0    2    4    6    8   10   12
          Degree of Multiprogramming
```

***

#### How to Detect Thrashing

**Monitoring metrics:**

| Metric | Normal | Thrashing |
|--------|--------|-----------|
| **CPU Utilization** | 70-90% | < 20% |
| **Page Fault Rate** | < 100/sec | > 10,000/sec |
| **Disk I/O** | 10-20% | > 90% |
| **Response Time** | milliseconds | seconds |
| **Throughput** | High | Near zero |

**System symptoms:**
- Hard disk light constantly on
- Programs "freeze" for seconds
- Mouse cursor stutters
- System becomes unresponsive

***

#### How to Eliminate Thrashing

**1. Reduce Multiprogramming (Immediate Fix)**
```
Before: 10 processes × 15 MB = 150 MB needed, 100 MB available
Action: Suspend 4 processes (swap them out completely)
After: 6 processes × 15 MB = 90 MB needed, 100 MB available
Result: Remaining 6 processes run smoothly
```

**2. Local Page Replacement Policy**
```
Global replacement:
- Process A faults → steals from Process B
- Process B faults → steals from Process C
- Cascading faults → thrashing

Local replacement:
- Process A faults → replaces its own page
- Other processes unaffected
- Limits damage to faulting process
```

**3. Working Set Model (Proactive)**
```
Algorithm:
1. Calculate each process's working set size (WSS)
2. If Σ WSS > Available RAM:
   - Suspend lowest-priority process
   - Repeat until Σ WSS ≤ Available RAM
```

**4. Page Fault Frequency (PFF) Scheme**
```
Monitor each process's page fault rate:

If PFF too high (> upper threshold):
    → Allocate more frames to this process

If PFF too low (< lower threshold):
    → Reclaim frames from this process

If cannot allocate more frames:
    → Suspend this process
```

**5. Buy More RAM (Ultimate Fix)**
```
Cost-benefit:
- RAM upgrade: $50
- Productivity loss from thrashing: $1000/day
→ Always worth it!
```

***

### Working Set Model (Complete Explanation)

#### Formal Definition

**Working Set WS(t, Δ):**  
The set of pages referenced by a process in the time interval **[t - Δ, t]**.

- **t:** Current virtual time (not wall-clock; counts memory references)
- **Δ:** Working set window (number of page references)

**Example:**
```
Reference string: 1, 2, 5, 1, 5, 2, 3, 5, 1, 2, 5, 3, 3
                                           ↑
                                       Current time t

If Δ = 10 (look back 10 references):
References in window: [2, 5, 1, 2, 5, 3, 3, 2, 5, 1]
Unique pages: {1, 2, 3, 5}
Working Set Size (WSS) = 4 pages
```

***

#### How Δ Affects WSS

```
                    WSS
                     ↑
                    8│         ╱‾‾‾‾‾‾‾‾‾
                     │        ╱
                    6│       ╱
                     │      ╱
                    4│     ╱
                     │    ╱
                    2│   ╱
                     │__╱
                    0└─────────────────────► Δ
                     0   5K  10K  50K 100K
                         (window size)

Too small Δ (< 5K):  WSS too small → frequent page faults
Optimal Δ (10K-50K): WSS stable → good performance
Too large Δ (> 100K): WSS includes cold pages → wasted memory
```

***

#### Working Set Implementation

**Algorithm:**
```
For each process P:
    1. Monitor page references over last Δ references
    2. Maintain set of unique pages accessed
    3. WSS[P] = size of this set

System-wide check:
    Total_WSS = Σ WSS[P] for all processes

    If Total_WSS > Available_Frames:
        → Suspend lowest-priority process
        → Repeat until Total_WSS ≤ Available_Frames
    
    If Total_WSS << Available_Frames:
        → Can admit new process (increase multiprogramming)
```

***

#### Parameters for Window Size

**1. Δ (Window Size):**

**Too small (Δ < 1000):**
- WSS doesn't capture locality
- Frequent page faults
- Under-allocation of frames

**Optimal (Δ = 10,000 - 100,000):**
- Captures active pages
- Stable WSS
- Good performance

**Too large (Δ > 1,000,000):**
- Includes stale pages
- Over-allocation (wasted frames)
- Reduces multiprogramming

**Typical value:** Δ = 10,000 to 50,000 memory references

***

**2. Sampling Interval (τ):**
- How often to recalculate WSS
- **Too frequent:** High overhead
- **Too infrequent:** Stale estimates
- **Typical:** Every 100-1000 page references

***

**3. Process Priority:**
- High-priority processes get frames first
- Low-priority processes suspended first when memory tight

***

#### Working Set vs Page Fault Frequency

| Approach | Working Set Model | Page Fault Frequency (PFF) |
|----------|------------------|---------------------------|
| **Philosophy** | Proactive (allocate enough frames) | Reactive (adjust based on faults) |
| **Measurement** | WSS = pages in window Δ | PFF = faults per unit time |
| **Action** | Give process WSS frames | Increase/decrease frames based on PFF |
| **Overhead** | Track all references | Track only faults (cheaper) |
| **Accuracy** | More accurate | Good approximation |

**Memory Trick:** "Working Set = pages you're WORKING with right now (based on recent past)."

***

### Translation Lookaside Buffer (TLB): The Speed Savior

#### Why TLBs Exist

**Problem without TLB:**
```
For every memory access (e.g., fetch instruction):
1. Access page table in memory → 100 ns
2. Access actual data in memory → 100 ns
Total: 200 ns per access (2× slower!)

Program with 1 billion instructions = 1B × 200 ns = 200 seconds!
```

**Solution: TLB (Hardware Cache)**
```
TLB = Small, fast cache (SRAM, on CPU die)
Stores recently used page table entries
Access time: ~1 ns (100× faster than RAM)
```

***

#### TLB Structure

```
┌─────────────────────────────────────────────┐
│              TLB (64-256 entries)           │
├───────────┬─────────┬────────┬──────┬──────┤
│ Page#     │ Frame#  │ Valid  │ R/W  │ PID  │
├───────────┼─────────┼────────┼──────┼──────┤
│ 0x123     │   47    │   1    │ R/W  │  5   │
│ 0x456     │   92    │   1    │  R   │  5   │
│ 0x789     │   15    │   1    │ R/W  │  7   │
│ ...       │  ...    │  ...   │ ...  │ ...  │
└───────────┴─────────┴────────┴──────┴──────┘
        Fully associative (can match any entry)
```

**Key features:**
- **Fast:** Parallel comparison of all entries (CAM = Content Addressable Memory)
- **Small:** 64-256 entries (vs millions in page table)
- **Per-process:** PID (Process ID) disambiguates entries from different processes

***

#### Address Translation with TLB

```
┌─────────────────────────────────────────────────────┐
│         Logical Address (Page# + Offset)            │
└──────────────────────┬──────────────────────────────┘
                       ▼
              ┌─────────────────┐
              │   Check TLB     │
              └────────┬─────────┘
                       │
           ┌───────────┴───────────┐
           │                       │
        TLB Hit                 TLB Miss
        (~99%)                  (~1%)
           │                       │
           ▼                       ▼
    ┌──────────────┐      ┌─────────────────┐
    │ Get Frame#   │      │ Access Page     │
    │ from TLB     │      │ Table in Memory │
    │ (1 ns)       │      │ (100 ns)        │
    └──────┬───────┘      └────────┬─────────┘
           │                       │
           │                       ▼
           │              ┌─────────────────┐
           │              │ Update TLB      │
           │              │ (evict old      │
           │              │  entry if full) │
           │              └────────┬─────────┘
           │                       │
           └───────────┬───────────┘
                       ▼
            ┌──────────────────────┐
            │ Construct Physical   │
            │ Address              │
            │ = Frame# + Offset    │
            └──────────┬───────────┘
                       ▼
            ┌──────────────────────┐
            │ Access Physical      │
            │ Memory (100 ns)      │
            └──────────────────────┘
```

***

#### TLB Performance Example

**Given:**
- Memory access time: 100 ns
- TLB access time: 1 ns (negligible)
- TLB hit ratio: 98%

**Effective Access Time:**
```
TLB Hit (98%):
    TLB lookup (1 ns) + Memory access (100 ns) = 101 ns

TLB Miss (2%):
    TLB lookup (1 ns) + Page table access (100 ns) + Memory access (100 ns) = 201 ns

EAT = 0.98 × 101 + 0.02 × 201
    = 98.98 + 4.02
    = 103 ns

Overhead = 3% (vs 100 ns with perfect TLB)
Without TLB = 200 ns → TLB gives ~2× speedup!
```

***

#### TLB Management

**On Context Switch:**
```
Option 1: Flush TLB
- Clear all entries (set Valid=0)
- Next process starts with empty TLB → initial misses
- Simple but causes performance hit

Option 2: Tagged TLB (with PID)
- Keep entries from multiple processes
- Use PID field to distinguish
- No flush needed → better performance
- Modern CPUs use this
```

**TLB Replacement:**
- Usually **LRU** or **Random**
- Happens on TLB miss when TLB full

***

#### Why TLBs are Critical

**Real-world impact:**

| System | TLB Hit Ratio | Performance |
|--------|---------------|-------------|
| Typical workload | 98-99% | Excellent |
| Poor locality | 80-90% | Noticeable slowdown |
| Huge pages (2MB) | 99.9% | Near-perfect (fewer translations) |

**Example: Database with 2GB working set**
```
With 4 KB pages:
- 2GB / 4KB = 512K pages
- TLB (256 entries) covers: 256 × 4KB = 1 MB (0.05% of working set)
- TLB hit ratio: ~60% → slow!

With 2 MB huge pages:
- 2GB / 2MB = 1K pages
- TLB (256 entries) covers: 256 × 2MB = 512 MB (25% of working set)
- TLB hit ratio: ~95% → much faster!
```

**Memory Trick:** "TLB = Turbo-Loader Buffer (speeds up translation)."

Continuing the enhanced Unit 4 revision sheet:

***

## WORKED PROBLEMS (Detailed Solutions)

### Problem 1: Paging Performance (Complete Breakdown)

**Given:**
- 2-level paging scheme
- Regular memory access: 150 ns
- Page fault service time: 8 ms = 8,000,000 ns
- TLB hit ratio: 90% = 0.9
- Page fault rate: 1/10,000 = 0.0001 (0.01%)

**Goal:** Calculate average instruction execution time

***

#### Step 1: Understand 2-Level Paging Without TLB

**Address translation requires 3 memory accesses:**
```
Access 1: Outer page table (page directory)
Access 2: Inner page table
Access 3: Actual data/instruction

Total time = 3 × 150 ns = 450 ns
```

**Visual:**
```
Logical Address
     │
     ▼
┌─────────────┐
│ Outer Table │ ◄── Access 1 (150 ns)
└──────┬──────┘
       ▼
┌─────────────┐
│ Inner Table │ ◄── Access 2 (150 ns)
└──────┬──────┘
       ▼
┌─────────────┐
│    Data     │ ◄── Access 3 (150 ns)
└─────────────┘
```

***

#### Step 2: Calculate EAT with TLB (No Page Faults Yet)

**TLB Hit (90% of time):**
```
TLB contains complete translation → skip both page tables
Time = TLB access (negligible) + Data access = 0 + 150 = 150 ns
```

**TLB Miss (10% of time):**
```
Must walk both page tables, then access data
Time = Outer table + Inner table + Data
     = 150 + 150 + 150 = 450 ns
```

**Effective Memory Access Time (EMAT):**
```
EMAT = P(TLB hit) × Time(hit) + P(TLB miss) × Time(miss)
     = 0.9 × 150 + 0.1 × 450
     = 135 + 45
     = 180 ns
```

**Memory Trick:** "TLB saves you from walking the page table tree!"

***

#### Step 3: Include Page Fault Overhead

**Page fault happens 0.01% of accesses (1 in 10,000).**

**When page fault occurs:**
```
1. Trap to OS (negligible compared to disk I/O)
2. OS finds victim page to evict (if memory full)
3. Write victim page to disk if dirty (8 ms worst case)
4. Read required page from disk (8 ms)
5. Update page table
6. Restart instruction
7. Now perform normal memory access (180 ns)

Total page fault time ≈ 8,000,000 ns (disk dominates)
```

**Note:** We count the fault time + the eventual successful access.

***

#### Step 4: Final Calculation

**Average Access Time with Page Faults:**
```
EAT_total = P(no fault) × EMAT + P(fault) × (Fault_time + EMAT)

P(no fault) = 1 - 0.0001 = 0.9999
P(fault) = 0.0001

EAT_total = 0.9999 × 180 + 0.0001 × (8,000,000 + 180)
          = 179.982 + 0.0001 × 8,000,180
          = 179.982 + 800.018
          = 980 ns
          ≈ 1 microsecond
```

***

#### Step 5: Analysis

**Performance breakdown:**
```
Normal access contribution: 180 ns × 99.99% = 179.98 ns (18%)
Page fault contribution: 8 ms × 0.01% = 800 ns (82%)

Even though page faults are rare (0.01%), they dominate total time!
```

**Intuition:**
```
Without page faults: 180 ns per access
With page faults: 980 ns per access
Overhead: 980/180 = 5.4× slower!

Page faults are 44,000× slower than normal access
(8,000,000 ns / 180 ns = 44,444×)
```

**Key Insight:** Even very low page fault rates (< 0.1%) drastically impact performance. This is why avoiding thrashing is critical!

***

### Problem 2: Page Replacement Algorithms (Step-by-Step)

**Scenario:**
- **3 frames available** in physical memory
- **Reference string:** 7, 0, 1, 2, 0, 3, 0, 4, 2, 3, 0, 3, 2
- Initially, all frames empty

***

#### Algorithm 1: FIFO (First-In, First-Out)

**Strategy:** Replace the oldest page in memory (queue order).

**Detailed Walkthrough:**

```
Reference: 7
Frames: [7, -, -]
Action: Cold start → Page fault (1)
Explanation: Empty frame, load page 7

Reference: 0
Frames: [7, 0, -]
Action: Cold start → Page fault (2)
Explanation: Empty frame, load page 0

Reference: 1
Frames: [7, 0, 1]
Action: Cold start → Page fault (3)
Explanation: Empty frame, load page 1
Queue: 7 (oldest) → 0 → 1 (newest)

Reference: 2
Frames: [2, 0, 1]
Action: Page fault (4)
Explanation: All frames full. 7 is oldest → replace 7 with 2
Queue: 0 (oldest) → 1 → 2 (newest)

Reference: 0
Frames: [2, 0, 1]
Action: Hit!
Explanation: 0 already in memory (no queue change in FIFO)

Reference: 3
Frames: [2, 3, 1]
Action: Page fault (5)
Explanation: 0 is oldest → replace 0 with 3
Queue: 1 (oldest) → 2 → 3 (newest)

Reference: 0
Frames: [2, 3, 0]
Action: Page fault (6)
Explanation: 1 is oldest → replace 1 with 0
Queue: 2 (oldest) → 3 → 0 (newest)

Reference: 4
Frames: [4, 3, 0]
Action: Page fault (7)
Explanation: 2 is oldest → replace 2 with 4
Queue: 3 (oldest) → 0 → 4 (newest)

Reference: 2
Frames: [4, 2, 0]
Action: Page fault (8)
Explanation: 3 is oldest → replace 3 with 2
Queue: 0 (oldest) → 4 → 2 (newest)

Reference: 3
Frames: [4, 2, 3]
Action: Page fault (9)
Explanation: 0 is oldest → replace 0 with 3
Queue: 4 (oldest) → 2 → 3 (newest)

Reference: 0
Frames: [0, 2, 3]
Action: Page fault (10)
Explanation: 4 is oldest → replace 4 with 0
Queue: 2 (oldest) → 3 → 0 (newest)

Reference: 3
Frames: [0, 2, 3]
Action: Hit!
Explanation: 3 already in memory

Reference: 2
Frames: [0, 2, 3]
Action: Hit!
Explanation: 2 already in memory
```

**FIFO Summary:**
- **Total Page Faults: 10**
- **Hit Ratio: 3/13 = 23%**
- **Miss Ratio: 10/13 = 77%**

**Drawback:** FIFO can suffer from **Belady's Anomaly** (more frames → more faults in some cases).

***

#### Algorithm 2: LRU (Least Recently Used)

**Strategy:** Replace the page that hasn't been used for the longest time.

**Track:** Maintain access timestamp or access order for each page.

**Detailed Walkthrough:**

```
Reference: 7
Frames: [7, -, -]
Action: Page fault (1)
Access order: 7 (most recent)

Reference: 0
Frames: [7, 0, -]
Action: Page fault (2)
Access order: 7 → 0 (most recent)

Reference: 1
Frames: [7, 0, 1]
Action: Page fault (3)
Access order: 7 → 0 → 1 (most recent)

Reference: 2
Frames: [2, 0, 1]
Action: Page fault (4)
Explanation: All full. 7 is LRU (least recently used) → replace with 2
Access order: 0 → 1 → 2 (most recent)

Reference: 0
Frames: [2, 0, 1]
Action: Hit!
Explanation: 0 found. Update access order.
Access order: 2 → 1 → 0 (most recent, just accessed)

Reference: 3
Frames: [2, 3, 1]
Action: Page fault (5)
Explanation: 0 just accessed. 2 is now LRU → replace 2 with 3
Wait, let me recalculate. After accessing 0:
Previous order: 0 → 1 → 2
But 2 was most recent before 0. After accessing 0:
New order: 1 → 2 → 0
So 1 is LRU? No wait, let me track this more carefully.

Let me restart with explicit time tracking:
```

**Restart with Time Tracking:**

| Ref | 7 | 0 | 1 | 2 | 0 | 3 | 0 | 4 | 2 | 3 | 0 | 3 | 2 |
|-----|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **Time** | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10| 11| 12| 13|

```
Time 1: Reference 7
Frames: [7(t=1), -, -]
Fault (1)

Time 2: Reference 0
Frames: [7(t=1), 0(t=2), -]
Fault (2)

Time 3: Reference 1
Frames: [7(t=1), 0(t=2), 1(t=3)]
Fault (3)

Time 4: Reference 2
Frames: [2(t=4), 0(t=2), 1(t=3)]
LRU = 7(t=1) → Replace with 2
Fault (4)

Time 5: Reference 0 (HIT)
Frames: [2(t=4), 0(t=5), 1(t=3)]
Update timestamp of 0
LRU now = 1(t=3)

Time 6: Reference 3
Frames: [2(t=4), 0(t=5), 3(t=6)]
LRU = 1(t=3) → Replace with 3
Fault (5)

Time 7: Reference 0 (HIT)
Frames: [2(t=4), 0(t=7), 3(t=6)]
Update timestamp of 0
LRU now = 2(t=4)

Time 8: Reference 4
Frames: [4(t=8), 0(t=7), 3(t=6)]
LRU = 2(t=4) → Replace with 4
Fault (6)

Time 9: Reference 2
Frames: [4(t=8), 0(t=7), 2(t=9)]
LRU = 3(t=6) → Replace with 2
Fault (7)

Time 10: Reference 3
Frames: [4(t=8), 3(t=10), 2(t=9)]
LRU = 0(t=7) → Replace with 3
Fault (8)

Time 11: Reference 0
Frames: [0(t=11), 3(t=10), 2(t=9)]
LRU = 4(t=8) → Replace with 0
Fault (9)

Time 12: Reference 3 (HIT)
Frames: [0(t=11), 3(t=12), 2(t=9)]
Update timestamp of 3
LRU now = 2(t=9)

Time 13: Reference 2 (HIT)
Frames: [0(t=11), 3(t=12), 2(t=13)]
Update timestamp of 2
```

**LRU Summary:**
- **Total Page Faults: 9**
- **Hit Ratio: 4/13 = 31%**
- **Miss Ratio: 9/13 = 69%**
- **Better than FIFO** by 1 fault

**Key Advantage:** LRU respects temporal locality (recently used pages likely to be used again).

***

#### Algorithm 3: Optimal (Belady's Algorithm)

**Strategy:** Replace the page that will **NOT** be used for the longest time in the future.

**Note:** Requires knowing future references → **not implementable in practice**, but provides theoretical lower bound.

**Detailed Walkthrough:**

```
Reference string: 7, 0, 1, 2, 0, 3, 0, 4, 2, 3, 0, 3, 2
Index:            0  1  2  3  4  5  6  7  8  9 10 11 12

Time 0: Reference 7
Frames: [7, -, -]
Fault (1)

Time 1: Reference 0
Frames: [7, 0, -]
Fault (2)

Time 2: Reference 1
Frames: [7, 0, 1]
Fault (3)

Time 3: Reference 2
Need to evict one of: [7, 0, 1]
Future use:
  - 7: Never used again
  - 0: Used at index 4 (next use in 1 step)
  - 1: Never used again
Choose: Evict 7 (or 1, both never used; pick 7)
Frames: [2, 0, 1]
Fault (4)

Time 4: Reference 0 (HIT)
Frames: [2, 0, 1]

Time 5: Reference 3
Need to evict one of: [2, 0, 1]
Future use:
  - 2: Used at index 8 (3 steps away)
  - 0: Used at index 6 (1 step away)
  - 1: Never used again
Choose: Evict 1 (furthest in future = never)
Frames: [2, 0, 3]
Fault (5)

Time 6: Reference 0 (HIT)
Frames: [2, 0, 3]

Time 7: Reference 4
Need to evict one of: [2, 0, 3]
Future use:
  - 2: Used at index 8 (1 step away)
  - 0: Used at index 10 (3 steps away)
  - 3: Used at index 9 (2 steps away)
Choose: Evict 0 (furthest: 3 steps)
Wait, let me reconsider. We're at index 7.
  - 2: next at index 8 (distance = 1)
  - 0: next at index 10 (distance = 3)
  - 3: next at index 9 (distance = 2)
Evict the one used furthest in future = 0 (distance 3)
Frames: [2, 4, 3]
Fault (6)

Time 8: Reference 2 (HIT)
Frames: [2, 4, 3]

Time 9: Reference 3 (HIT)
Frames: [2, 4, 3]

Time 10: Reference 0
Need to evict one of: [2, 4, 3]
Future use:
  - 2: Used at index 12 (2 steps away)
  - 4: Never used again
  - 3: Used at index 11 (1 step away)
Choose: Evict 4 (never used again)
Frames: [2, 0, 3]
Fault (7)

Time 11: Reference 3 (HIT)
Frames: [2, 0, 3]

Time 12: Reference 2 (HIT)
Frames: [2, 0, 3]
```

**Optimal Summary:**
- **Total Page Faults: 7**
- **Hit Ratio: 6/13 = 46%**
- **Miss Ratio: 7/13 = 54%**
- **Best possible** for this reference string

***

#### Algorithm Comparison

| Algorithm | Page Faults | Hit Ratio | Implementable? | Complexity |
|-----------|-------------|-----------|----------------|------------|
| **FIFO** | 10 | 23% | ✅ Yes | Simple (queue) |
| **LRU** | 9 | 31% | ✅ Yes (approx.) | Medium (timestamps/stack) |
| **Optimal** | 7 | 46% | ❌ No (needs future) | Theoretical |

**Key Insights:**
1. **FIFO is simple but suboptimal:** Doesn't consider usage patterns.
2. **LRU is practical and effective:** Approximates optimal by using past to predict future.
3. **Optimal is theoretical gold standard:** Used to evaluate other algorithms.

**Real-world implementations:**
- **LRU approximations:** Clock algorithm, Second-chance algorithm (cheaper to implement).
- **Working Set:** Combines LRU with time windows.

**Memory Trick:** "Optimal looks into the FUTURE (impossible). LRU looks at the PAST (practical)."

***

### Problem 3: Segmentation Address Translation (Detailed)

**Given Segment Table:**

| Segment | Base | Length |
|:-------:|:----:|:------:|
| 0 | 219 | 600 |
| 1 | 230 | 14 |
| 2 | 90 | 100 |
| 3 | 1327 | 580 |
| 4 | 1952 | 96 |

**Address Format:** (Segment #, Offset)

**Translation Rule:**
1. Check: `Offset < Segment Length`? If NO → **TRAP (Segmentation Fault)**
2. If YES: `Physical Address = Base + Offset`

***

#### Example 1: Valid Address (2, 53)

```
Logical Address: (Segment=2, Offset=53)

Step 1: Look up Segment 2 in table
  Base = 90
  Length = 100

Step 2: Bounds check
  Is Offset < Length?
  53 < 100? YES ✓

Step 3: Calculate physical address
  Physical = Base + Offset
          = 90 + 53
          = 143

Result: Physical Address = 143
```

**Visual:**
```
Segment 2 in Physical Memory:
Address: 90   91   92  ...  142  143  144  ...  189
         └────────────────────┬────────────────────┘
                        100 bytes (length)
                              ↑
                         Offset 53
```

***

#### Example 2: Valid Address (3, 500)

```
Logical Address: (Segment=3, Offset=500)

Step 1: Segment 3 lookup
  Base = 1327
  Length = 580

Step 2: Bounds check
  500 < 580? YES ✓

Step 3: Calculate
  Physical = 1327 + 500 = 1827

Result: Physical Address = 1827
```

***

#### Example 3: Invalid Address (1, 20) - Segmentation Fault!

```
Logical Address: (Segment=1, Offset=20)

Step 1: Segment 1 lookup
  Base = 230
  Length = 14

Step 2: Bounds check
  20 < 14? NO ✗

Result: TRAP TO OS - SEGMENTATION FAULT!
```

**What happens:**
```
1. CPU detects: Offset ≥ Length
2. Hardware raises exception
3. Trap to OS interrupt handler
4. OS checks if this is malicious or programmer error
5. Typically: Kill the process
6. User sees: "Segmentation fault (core dumped)"
```

**Why this happens:**
```
Segment 1 is only 14 bytes long (addresses 230-243)
Trying to access offset 20 means address 230+20=250
But 250 is BEYOND the segment boundary (243)
This is illegal → protection violation
```

**Visual:**
```
Segment 1: [230 ... 243] (14 bytes)
                         ↑
                    End boundary

Attempt: 230 + 20 = 250
                    ↑
               Outside segment!
               Not allowed!
```

***

#### Example 4: Edge Case (4, 0)

```
Logical Address: (Segment=4, Offset=0)

Step 1: Segment 4 lookup
  Base = 1952
  Length = 96

Step 2: Bounds check
  0 < 96? YES ✓

Step 3: Calculate
  Physical = 1952 + 0 = 1952

Result: Physical Address = 1952 (first byte of segment)
```

***

#### Example 5: Edge Case (4, 95)

```
Logical Address: (Segment=4, Offset=95)

Step 1: Segment 4 lookup
  Base = 1952
  Length = 96

Step 2: Bounds check
  95 < 96? YES ✓ (last valid offset)

Step 3: Calculate
  Physical = 1952 + 95 = 2047

Result: Physical Address = 2047 (last byte of segment)
```

***

#### Example 6: Invalid Address (4, 96) - Just Beyond Limit

```
Logical Address: (Segment=4, Offset=96)

Step 1: Segment 4 lookup
  Base = 1952
  Length = 96

Step 2: Bounds check
  96 < 96? NO ✗ (96 is NOT less than 96)

Result: SEGMENTATION FAULT!
```

**Important:** Valid offsets are `0` to `Length-1`. Offset equal to length is already out of bounds.

***

#### Summary Table: All Examples

| Logical Addr | Segment | Offset | Base | Length | Offset < Length? | Physical Addr | Status |
|:------------:|:-------:|:------:|:----:|:------:|:----------------:|:-------------:|:------:|
| (2, 53) | 2 | 53 | 90 | 100 | 53 < 100 ✓ | 143 | ✅ Valid |
| (3, 500) | 3 | 500 | 1327 | 580 | 500 < 580 ✓ | 1827 | ✅ Valid |
| (1, 20) | 1 | 20 | 230 | 14 | 20 < 14 ✗ | — | ❌ Fault |
| (4, 0) | 4 | 0 | 1952 | 96 | 0 < 96 ✓ | 1952 | ✅ Valid |
| (4, 95) | 4 | 95 | 1952 | 96 | 95 < 96 ✓ | 2047 | ✅ Valid |
| (4, 96) | 4 | 96 | 1952 | 96 | 96 < 96 ✗ | — | ❌ Fault |
| (0, 599) | 0 | 599 | 219 | 600 | 599 < 600 ✓ | 818 | ✅ Valid |
| (0, 600) | 0 | 600 | 219 | 600 | 600 < 600 ✗ | — | ❌ Fault |

**Key Takeaway:** Segmentation provides **variable-size logical units** with **built-in bounds checking** for protection.

***

## EXAM TIPS & MEMORY AIDS

### Quick Reference Formulas

**1. Page Number & Offset Extraction (Page Size = 2ⁿ):**
```
Page Number = Logical Address >> n  (right shift)
Offset = Logical Address & (2ⁿ - 1)  (mask lower n bits)
```

**2. Number of Page Table Entries:**
```
Entries = Logical Address Space / Page Size
        = 2^(address_bits) / 2^(page_bits)
        = 2^(address_bits - page_bits)
```

**3. Internal Fragmentation (Average per process):**
```
Avg = Page Size / 2
```

**4. Effective Access Time (with TLB):**
```
EAT = h × (ε + m) + (1 - h) × (ε + 2m)
where: h = hit ratio, ε = TLB time, m = memory time

If ε ≈ 0:
EAT = m(2 - h)
```

**5. Effective Access Time (with Page Faults):**
```
EAT_total = (1 - p) × EAT + p × (Page_Fault_Time + EAT)
where: p = page fault rate
```

***

### Memory Mnemonics

**Fragmentation:**
- **IN**ternal = **IN**side blocks (paging)
- **EX**ternal = **EX**posed gaps (segmentation)

**Page Replacement:**
- **FIFO** = First In, First Out (queue, simple, suboptimal)
- **LRU** = **L**ook at **R**ecent **U**sage (past predicts future)
- **Optimal** = **O**racleknows future (impossible)

**TLB:**
- **T**ranslation **L**ookaside **B**uffer = Turbo Loader Buffer

**Thrashing:**
- **THR**ashing = **T**oo many processes **H**itting disk **R**epeatedly

**Working Set:**
- WS = **W**hat you're **W**orking with now (recent pages)

***

### Common Exam Mistakes to Avoid

❌ **Mistake 1:** Confusing page faults with TLB misses
- **TLB miss** = Translation not in cache → access page table (100 ns)
- **Page fault** = Page not in memory → disk I/O (8 ms = 80,000× slower!)

❌ **Mistake 2:** Thinking internal fragmentation happens in segmentation
- Segmentation has **EXTERNAL** fragmentation (gaps between segments)
- Paging has **INTERNAL** fragmentation (waste inside pages)

❌ **Mistake 3:** Forgetting to include the final memory access after page fault
- Page fault time = Fault service time **+ Normal access time**

❌ **Mistake 4:** In segmentation, allowing offset = length
- Valid offsets: 0 to (Length - 1)
- Offset = Length → TRAP!

❌ **Mistake 5:** Counting TLB as a memory access
- TLB is on-chip cache, often counted as 0 or 1 ns (negligible)

❌ **Mistake 6:** Thinking more frames always reduces page faults
- Usually true, but FIFO can have Belady's Anomaly!

***

### Exam Pattern Recognition

**"Calculate effective access time" → Use EAT formula**
- Identify: TLB hit ratio, memory time, page fault rate
- Apply: Two-stage formula (TLB first, then page faults)

**"Is this address valid in segmentation?" → Check bounds**
- Offset < Length? Yes → Valid, No → Trap

**"How many page table entries?" → Address space / Page size**
- Watch units! Convert everything to same unit (bytes)

**"Compare paging vs segmentation" → Use comparison table**
- Fragmentation type, protection, sharing, speed

**"What is thrashing?" → Death spiral description**
- Too many processes → page faults → swapping → CPU idle

**"Working set size?" → Count unique pages in window Δ**
- Not total references, just unique pages

***

### Quick Calculation Tricks

**Power of 2 Shortcuts:**
```
2¹⁰ = 1 KB (1024 ≈ 1000)
2²⁰ = 1 MB (1 million)
2³⁰ = 1 GB (1 billion)
2⁴⁰ = 1 TB

Example: 2³² bytes = 2³² = 2² × 2³⁰ = 4 GB
```

**Bit Calculations:**
```
To represent N values: Need ⌈log₂(N)⌉ bits
To represent addresses 0 to N-1: Need ⌈log₂(N)⌉ bits

Example: 1024 frames → log₂(1024) = 10 bits
```

**Percentage to Ratio:**
```
90% = 0.9
10% = 0.1
1% = 0.01
0.1% = 0.001
0.01% = 0.0001
```

***

### Connection to Real Systems

**Linux:**
- Uses 4-level paging (5-level on newer 64-bit)
- Page size: 4 KB (default), supports huge pages (2 MB, 1 GB)
- Approximates LRU with Clock algorithm

**Windows:**
- Similar multi-level paging
- Page size: 4 KB (x86/x64)
- Uses Working Set Trimmer to prevent thrashing

**Modern CPUs:**
- TLB: 64-256 entries (L1), 512-1536 entries (L2)
- TLB hit ratio: typically 98-99%

***

### Final Checklist for Unit 4

✅ **Can you explain:**
- [ ] Internal vs external fragmentation with examples
- [ ] Why page sizes are powers of 2
- [ ] How 2-level paging saves memory
- [ ] What happens during a page fault (step-by-step)
- [ ] Why TLBs are critical for performance
- [ ] The thrashing death spiral
- [ ] How LRU approximates Optimal

✅ **Can you calculate:**
- [ ] Number of page table entries given address space and page size
- [ ] Physical address in segmentation (with bounds checking)
- [ ] Effective access time with TLB and page faults
- [ ] Page faults for FIFO/LRU/Optimal given reference string
- [ ] Working set size given reference string and window Δ

✅ **Can you compare:**
- [ ] Paging vs segmentation (5 key differences)
- [ ] First-fit vs best-fit vs worst-fit
- [ ] Single-level vs multi-level page tables
- [ ] Conventional vs inverted page tables
- [ ] Small vs large page sizes

***