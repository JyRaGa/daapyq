# UNIT 3: DEADLOCK — EXAM REVISION SHEET

## FUNDAMENTALS

### What is a Deadlock?

A deadlock is a situation in which a set of processes are blocked because each process is holding resources and waiting for other resources that are currently held by other processes in the set. No process can proceed, and the system is stuck in a circular waiting condition where every process needs a resource held by another process in the cycle.

**Example:** Process P1 holds resource A and waits for resource B; Process P2 holds resource B and waits for resource A.

***

### Four Necessary Conditions for Deadlock

All four conditions must hold simultaneously for a deadlock to occur:

1. **Mutual Exclusion:** At least one resource must be held in a non-shareable mode (only one process can use the resource at a time).
2. **Hold and Wait:** A process must be holding at least one resource and waiting to acquire additional resources currently held by other processes.
3. **No Preemption:** Resources cannot be forcibly taken away from a process; they can only be released voluntarily by the process holding them.
4. **Circular Wait:** A circular chain of processes exists, where each process holds at least one resource needed by the next process in the chain.

If any one of these conditions is broken, deadlock cannot occur.

***

### Schemes to Handle Deadlocks

Operating systems use four main approaches:

1. **Deadlock Ignorance (Ostrich Algorithm):**
   - Assume deadlocks will never occur or are extremely rare.
   - Used in systems where deadlock cost is low compared to prevention/detection overhead.
   - Example: Many versions of UNIX/Linux.

2. **Deadlock Prevention:**
   - Design the system to ensure at least one of the four necessary conditions cannot hold.
   - Restricts how resources are requested to eliminate the possibility of deadlock.

3. **Deadlock Avoidance:**
   - Use algorithms (like Banker's Algorithm) to dynamically check resource allocation.
   - Grant resources only if the system will remain in a "safe state."
   - Requires advance knowledge of maximum resource needs.

4. **Deadlock Detection and Recovery:**
   - Allow deadlocks to occur.
   - Periodically run detection algorithms to identify deadlocked processes.
   - Recover by killing processes or preempting resources.

***

### Deadlock Detection vs Avoidance: Pros and Cons

| Aspect | Deadlock Avoidance (Banker's Algorithm) | Deadlock Detection |
|--------|----------------------------------------|-------------------|
| **When applied** | Before granting resources | After deadlock occurs |
| **Resource utilization** | Conservative; lower utilization (safe state requirement) | Optimistic; higher utilization |
| **Overhead** | Runtime overhead on every resource request | Periodic detection algorithm overhead |
| **Advance info needed** | Requires maximum resource needs in advance (often unrealistic) | No advance information needed |
| **Recovery cost** | None (deadlock never happens) | High (process termination, rollback) |
| **User impact** | May deny valid requests to stay safe | Processes may be killed unexpectedly |
| **Best for** | Systems with predictable resource needs, critical applications | General-purpose systems, unpredictable workloads |

**Trade-offs in high-resource systems:**
- **Avoidance:** Safer but wastes resources by being overly conservative; impractical when maximum needs are unknown or highly variable (e.g., cloud environments).
- **Detection:** Allows better resource utilization but recovery (killing processes, rolling back transactions) disrupts service and may cause data loss; detection algorithm itself consumes CPU and memory.

***

### Implications of Deadlock Recovery on System Performance

Recovery strategies include:

1. **Process Termination:**
   - **Abort all deadlocked processes:** Simple but costly (all partial work lost).
   - **Abort one process at a time:** Expensive overhead (rerun detection after each termination).
   - **Selection criteria:** Terminate lowest priority, least CPU time used, fewest resources held, or longest time to completion.

2. **Resource Preemption:**
   - Forcibly take resources from deadlocked processes.
   - Requires rollback to a safe state (checkpoint).
   - Risk of starvation if same process is repeatedly preempted.

**Performance implications:**
- **Throughput reduction:** Terminated processes must restart, wasting CPU cycles.
- **Turnaround time increase:** Affected processes experience delays.
- **User dissatisfaction:** Loss of work, unpredictable service.
- **Detection overhead:** Frequent detection consumes system resources.

***

## PREVENTION & AVOIDANCE

### Conditions for Deadlock Prevention

To prevent deadlock, **negate at least one** of the four necessary conditions:

1. **Negate Mutual Exclusion:**
   - Make resources shareable (e.g., read-only files).
   - Not always possible (e.g., printers, tape drives).

2. **Negate Hold and Wait:**
   - **Protocol 1:** Process must request all resources at once before execution starts.
   - **Protocol 2:** Process must release all held resources before requesting new ones.
   - **Drawback:** Low resource utilization; starvation possible; processes may not know all needs in advance.

3. **Negate No Preemption:**
   - Allow OS to preempt resources from a waiting process.
   - Preempted process releases all its resources and is added to the waiting queue.
   - **Drawback:** Applicable only to resources with easily saved/restored state (CPU registers, memory); not applicable to printers, tape drives.

4. **Negate Circular Wait:**
   - Impose a total ordering on resource types.
   - Each process requests resources in increasing order of enumeration.
   - If process holds resource \(R_i\), it can request only \(R_j\) where \(j > i\).
   - **Drawback:** Restricts flexibility; may not match actual resource usage patterns.

***

### Banker's Algorithm for Safe Allocation

Banker's Algorithm is a deadlock avoidance algorithm that checks if granting a resource request will leave the system in a **safe state**.

**Key Concepts:**
- **Safe State:** A state where there exists a sequence of processes such that each process can obtain its remaining needed resources, finish, and release its resources, allowing the next process to proceed.
- **Unsafe State:** A state that *may* lead to deadlock (but not necessarily).

**Data Structures:**
- `Available[m]`: Number of available instances of each resource type.
- `Max[n][m]`: Maximum demand of each process for each resource.
- `Allocation[n][m]`: Currently allocated resources to each process.
- `Need[n][m]`: Remaining resource need = `Max - Allocation`.

**Algorithm Steps:**

**Request Handling:**
1. When process \(P_i\) requests resources `Request_i`:
   - Check if `Request_i ≤ Need_i` (else error; exceeds max claim).
   - Check if `Request_i ≤ Available` (else wait).
2. **Tentatively allocate** resources:
   - `Available = Available - Request_i`
   - `Allocation_i = Allocation_i + Request_i`
   - `Need_i = Need_i - Request_i`
3. **Run Safety Algorithm** to check if the new state is safe.
4. If safe, grant request permanently; else rollback and make \(P_i\) wait.

**Safety Algorithm:**
1. Initialize `Work = Available` and `Finish[i] = false` for all \(i\).
2. Find an index \(i\) such that:
   - `Finish[i] == false`
   - `Need_i ≤ Work`
3. If found:
   - `Work = Work + Allocation_i` (process finishes and releases resources).
   - `Finish[i] = true`.
   - Repeat step 2.
4. If `Finish[i] == true` for all \(i\), the state is **safe**; else **unsafe**.

***

### Significance of the Need Matrix

The **Need Matrix** (`Need = Max - Allocation`) is critical for determining whether a process *can* complete with the currently available resources.

**Why it matters:**
- The Banker's Algorithm uses `Need` to identify which processes can finish with `Available` resources.
- A process \(P_i\) can proceed if `Need_i ≤ Available`.
- By checking `Need` iteratively, the algorithm constructs a **safe sequence** (an execution order where no process starves).

**Example:**
Given:
- `Available = [3, 3, 2]`
- Process P0: `Allocation = [0, 1, 0]`, `Max = [7, 5, 3]` → `Need = [7, 4, 3]`
- Process P1: `Allocation = [2, 0, 0]`, `Max = [3, 2, 2]` → `Need = [1, 2, 2]`

**Analysis:**
- P0 needs `[7, 4, 3]` but `Available = [3, 3, 2]`; **cannot proceed**.
- P1 needs `[1, 2, 2]`; **can proceed** (since `[1, 2, 2] ≤ [3, 3, 2]`).
- After P1 finishes, it releases `[2, 0, 0]`, so `Available = [5, 3, 2]`.
- Now check P0 again: `[7, 4, 3]` still > `[5, 3, 2]`; **still cannot proceed**.

This iterative check determines safety.

***

### Resource-Allocation Graph (RAG) Algorithm

The **RAG algorithm** is used for deadlock avoidance in systems with **single instances** of each resource type.

**Graph Elements:**
- **Vertices:** Processes (circles) and Resources (squares).
- **Edges:**
  - **Request edge:** Directed from process to resource (process requests resource).
  - **Assignment edge:** Directed from resource to process (resource allocated to process).
  - **Claim edge (dashed):** From process to resource (future request; used only in avoidance).

**Deadlock Avoidance Logic:**
- Before granting a request, convert the **claim edge** to a **request edge** and then to an **assignment edge**.
- Check if this creates a **cycle** in the graph.
- **If cycle exists:** System would enter an unsafe state; **deny request**.
- **If no cycle:** Grant request.

**Limitation:** Works only for single-instance resources. For multiple instances, use Banker's Algorithm.

***

## DETECTION

### Optimistic Assumption in Deadlock Detection

The deadlock detection algorithm makes the **optimistic assumption** that any process not currently requesting resources (i.e., `Request_i = 0`) will eventually finish its execution and release all its currently held resources.

**Assumption:** "A running process will require no more resources and will soon terminate, returning all allocated resources."

**How it can be violated:**
- A process may be in an **infinite loop** or waiting for an event that will never occur (e.g., faulty I/O device).
- The process may request more resources later but hasn't issued the request yet.
- If such a process never releases its resources, the detection algorithm's optimistic projection of future resource availability is wrong, leading to false negatives (deadlock exists but is not detected).

***

### Proof: Deadlock-Free Condition (Max Need Between 1 and m, Sum < m+n)

**Given:**
- \(m\) = total number of resource instances (of one type).
- \(n\) = number of processes.
- Each process has maximum need \(1 \leq \text{Max}_i \leq m\).
- Sum of all maximum needs: \(\sum_{i=1}^{n} \text{Max}_i < m + n\).

**To Prove:** The system is deadlock-free.

**Proof by Contradiction:**

1. **Assume deadlock occurs.**
   - All \(n\) processes are waiting for resources.
   - Let `Allocation_i` be the resources currently held by process \(i\).
   - Let `Need_i` be the remaining need of process \(i\) (since it's waiting, \(\text{Need}_i \geq 1\)).

2. **Resource accounting:**
   - Total resources allocated: \(\sum_{i=1}^{n} \text{Allocation}_i = m - \text{Available}\).
   - In the worst case (deadlock with no available resources): \(\sum_{i=1}^{n} \text{Allocation}_i = m\) and \(\text{Available} = 0\).

3. **Maximum need relation:**
   - \(\text{Max}_i = \text{Allocation}_i + \text{Need}_i\).
   - Summing over all processes:
     \[
     \sum_{i=1}^{n} \text{Max}_i = \sum_{i=1}^{n} \text{Allocation}_i + \sum_{i=1}^{n} \text{Need}_i
     \]
   - Substitute \(\sum \text{Allocation}_i = m\):
     \[
     \sum_{i=1}^{n} \text{Max}_i = m + \sum_{i=1}^{n} \text{Need}_i
     \]

4. **Need constraint in deadlock:**
   - Since each process is waiting (deadlock), \(\text{Need}_i \geq 1\) for all \(i\).
   - Therefore: \(\sum_{i=1}^{n} \text{Need}_i \geq n\).

5. **Combine:**
   \[
   \sum_{i=1}^{n} \text{Max}_i = m + \sum_{i=1}^{n} \text{Need}_i \geq m + n
   \]

6. **Contradiction:**
   - We were given \(\sum \text{Max}_i < m + n\).
   - But we derived \(\sum \text{Max}_i \geq m + n\).
   - **Contradiction!**

**Conclusion:** The assumption that deadlock occurs is false. Therefore, the system is **deadlock-free**. ✓

***

## WORKED PROBLEMS

### Problem 1: Banker's Algorithm (Safe State Detection)

**Given Snapshot:**

| Process | Allocation (A, B, C) | Request (A, B, C) | Available (A, B, C) |
|:-------:|:--------------------:|:-----------------:|:-------------------:|
| P0      | 0, 1, 0              | 0, 0, 0           | 0, 0, 0             |
| P1      | 2, 0, 0              | 2, 0, 2           |                     |
| P2      | 3, 0, 3              | 0, 0, 0           |                     |
| P3      | 2, 1, 1              | 1, 0, 0           |                     |
| P4      | 0, 0, 2              | 0, 0, 2           |                     |

**Note:** "Request" column here represents "Need" (remaining resource requirement).

**Question 1: Is the system in a deadlock state?**

**Solution:**

We apply the **safety algorithm** to find a safe sequence.

**Step-by-step:**

1. **Initialize:**
   - `Work = Available = [0, 0, 0]`
   - `Finish = [False, False, False, False, False]`

2. **Iteration 1:**
   - Find process \(i\) where `Finish[i] == False` and `Need_i ≤ Work`.
   - **P0:** `Need = [0, 0, 0] ≤ [0, 0, 0]` → **Yes!**
   - Execute P0: `Work = [0, 0, 0] + [0, 1, 0] = [0, 1, 0]`
   - `Finish[P0] = True`

3. **Iteration 2:**
   - Check remaining processes against `Work = [0, 1, 0]`.
   - **P1:** `Need = [2, 0, 2]` → `2 > 0` (A), **No**.
   - **P2:** `Need = [0, 0, 0] ≤ [0, 1, 0]` → **Yes!**
   - Execute P2: `Work = [0, 1, 0] + [3, 0, 3] = [3, 1, 3]`
   - `Finish[P2] = True`

4. **Iteration 3:**
   - Check against `Work = [3, 1, 3]`.
   - **P1:** `Need = [2, 0, 2] ≤ [3, 1, 3]` → **Yes!**
   - Execute P1: `Work = [3, 1, 3] + [2, 0, 0] = [5, 1, 3]`
   - `Finish[P1] = True`

5. **Iteration 4:**
   - Check against `Work = [5, 1, 3]`.
   - **P3:** `Need = [1, 0, 0] ≤ [5, 1, 3]` → **Yes!**
   - Execute P3: `Work = [5, 1, 3] + [2, 1, 1] = [7, 2, 4]`
   - `Finish[P3] = True`

6. **Iteration 5:**
   - Check against `Work = [7, 2, 4]`.
   - **P4:** `Need = [0, 0, 2] ≤ [7, 2, 4]` → **Yes!**
   - Execute P4: `Work = [7, 2, 4] + [0, 0, 2] = [7, 2, 6]`
   - `Finish[P4] = True`

**Safe Sequence:** **P0 → P2 → P1 → P3 → P4**

**Answer:** **No, the system is NOT in a deadlock state.** A safe sequence exists.

***

**Question 2: If process P2 makes an additional request, what will be the effect?**

**Analysis:**

- Currently, P2 has `Need = [0, 0, 0]`, meaning it is either running or about to finish.
- `Available = [0, 0, 0]` initially (before any process finishes).
- P0 will finish first and release `[0, 1, 0]`, making `Available = [0, 1, 0]`.

**Scenarios:**

1. **If P2 requests resources ≤ ** (e.g., `[0, 1, 0]`):
   - Request can be satisfied after P0 finishes.
   - System remains safe.

2. **If P2 requests resources > ** (e.g., `[1, 0, 0]` or `[0, 0, 1]`):
   - P2 must wait.
   - P2 holds resources `[3, 0, 3]` which are needed by others.
   - **Check if others can proceed:**
     - P3 needs `[1, 0, 0]`; `Available = [0, 1, 0]` → **Cannot proceed** (A = 0 < 1).
     - P4 needs `[0, 0, 2]`; `Available = [0, 1, 0]` → **Cannot proceed** (C = 0 < 2).
     - P1 needs `[2, 0, 2]` → **Cannot proceed**.
   - **Result:** P2 waits for resources held by no one (or never available). Other processes wait for resources held by P2.
   - **Circular wait → Deadlock.**

**Answer:** **If P2 requests more resources than, the system will likely enter a deadlock state** because P2 will block while holding critical resources needed by P1, P3, and P4, and those processes cannot proceed with the available resources.

***

### Problem 2: Resource Allocation (10 Units Total)

**Given:**

| Process | Used | Max Need |
|:-------:|:----:|:--------:|
| P1      | 2    | 5        |
| P2      | 1    | 6        |
| P3      | 2    | 6        |
| P4      | 1    | 2        |
| P5      | 1    | 4        |

- **Total resources:** 10 units.
- **Used (allocated):** \(2 + 1 + 2 + 1 + 1 = 7\)
- **Available:** \(10 - 7 = 3\)

**Calculate Need:**

| Process | Used | Max | Need (Max - Used) |
|:-------:|:----:|:---:|:-----------------:|
| P1      | 2    | 5   | 3                 |
| P2      | 1    | 6   | 5                 |
| P3      | 2    | 6   | 4                 |
| P4      | 1    | 2   | 1                 |
| P5      | 1    | 4   | 3                 |

***

**Question 1: Check if initial state is safe.**

**Solution:**

1. **Initialize:** `Work = 3`, `Finish = [F, F, F, F, F]`.

2. **Iteration 1:**
   - P4: `Need = 1 ≤ 3` → **Yes.**
   - Execute P4: `Work = 3 + 1 = 4`, `Finish[P4] = True`.

3. **Iteration 2:**
   - P1: `Need = 3 ≤ 4` → **Yes.**
   - Execute P1: `Work = 4 + 2 = 6`, `Finish[P1] = True`.

4. **Iteration 3:**
   - P5: `Need = 3 ≤ 6` → **Yes.**
   - Execute P5: `Work = 6 + 1 = 7`, `Finish[P5] = True`.

5. **Iteration 4:**
   - P3: `Need = 4 ≤ 7` → **Yes.**
   - Execute P3: `Work = 7 + 2 = 9`, `Finish[P3] = True`.

6. **Iteration 5:**
   - P2: `Need = 5 ≤ 9` → **Yes.**
   - Execute P2: `Work = 9 + 1 = 10`, `Finish[P2] = True`.

**Safe Sequence:** **P4 → P1 → P5 → P3 → P2**

**Answer:** **Yes, the initial system is in a SAFE state.**

***

**Question 2: Should P2 be granted a request of 2 additional resources?**

**Solution:**

**Check 1:** `Request ≤ Need`?
- P2 requests 2.
- P2's Need = 5.
- `2 ≤ 5` → **Yes.**

**Check 2:** `Request ≤ Available`?
- Available = 3.
- `2 ≤ 3` → **Yes.**

**Tentatively grant:**
- `Available = 3 - 2 = 1`
- P2: `Used = 1 + 2 = 3`, `Need = 5 - 2 = 3`

**New state:**

| Process | Used | Need |
|:-------:|:----:|:----:|
| P1      | 2    | 3    |
| P2      | 3    | 3    |
| P3      | 2    | 4    |
| P4      | 1    | 1    |
| P5      | 1    | 3    |

**Safety check with Available = 1:**

1. **Iteration 1:**
   - P4: `Need = 1 ≤ 1` → **Yes.**
   - Execute P4: `Work = 1 + 1 = 2`, `Finish[P4] = True`.

2. **Iteration 2:**
   - Check remaining processes against `Work = 2`.
   - P1: `Need = 3 > 2` → **No.**
   - P2: `Need = 3 > 2` → **No.**
   - P3: `Need = 4 > 2` → **No.**
   - P5: `Need = 3 > 2` → **No.**

**No process can proceed!**

**Answer:** **No, P2 should NOT be granted the request of 2 additional resources** because the resulting state is **UNSAFE**. After P4 finishes, no other process can obtain enough resources to complete, leading to potential deadlock.

***

**Question 3: Is the system in an unsafe state (after granting)? Explain.**

**Answer:** **Yes, if the request is granted, the system enters an UNSAFE state.** 

**Explanation:** After granting P2's request, only P4 can finish (needing 1 unit). After P4 releases its 1 unit, the available resources become 2 units. However, all remaining processes (P1, P2, P3, P5) need at least 3 units to complete. Since no process can proceed, the system cannot guarantee that all processes will finish, defining an unsafe state. While not immediately deadlocked, any future request could trigger actual deadlock.

***

## EXAM TIPS

- **Define deadlock clearly:** Circular waiting + all four conditions.
- **Four conditions:** Use mnemonic **"MH-NP-CW"** (Mutual exclusion, Hold-wait, No Preemption, Circular Wait).
- **Banker's Algorithm steps:** Memorize the safety check loop (find process with `Need ≤ Work`).
- **RAG:** Only for single-instance resources; cycle = unsafe.
- **Detection vs Avoidance:** Detection = higher utilization, recovery cost; Avoidance = safer, lower utilization.
- **Need matrix = Max - Allocation:** Critical for determining if a process can finish.
- **Proof questions:** Use contradiction method (assume deadlock, derive impossibility).

**Connection to OSTEP:** This maps to OSTEP Chapter 32 (Concurrency: Deadlock).

***
