

# Unit 10: Metrics & Estimation

## 1. Metrics Concepts

### 1.1 Define software metrics and classify them.
**Definition:** A quantitative measure of the degree to which a system, component, or process possesses a given attribute.
**Classification:**
1.  **Process Metrics:** Measure the **efficacy of the process** (e.g., Defect Removal Efficiency, Productivity).
2.  **Product Metrics:** Measure the **quality of the product** (e.g., Complexity, Size, Reliability).
3.  **Project Metrics:** Measure the **status of the project** (e.g., Cost, Schedule variance).

### 1.2 Define Halstead Software Science Metrics.
Halstead metrics measure **internal complexity** based on counting "Tokens" in the source code.
*   **Operators ($\eta_1$):** Keywords, math symbols (e.g., `if`, `while`, `+`, `=`).
*   **Operands ($\eta_2$):** Variables, constants (e.g., `x`, `100`, `"Error"`).

**Formulas:**
*   **Vocabulary ($\eta$):** $\eta_1 + \eta_2$ (Unique tokens)
*   **Length ($N$):** $N_1 + N_2$ (Total tokens)
*   **Volume ($V$):** $N \times \log_2(\eta)$ (Size in bits)
*   **Effort ($E$):** $D \times V$ (Mental effort required)
*   **Time ($T$):** $E / 18$ seconds (Time to write program)

### 1.3 Is Halstead significant in Component-Based Development (CBD)?
**No.**
*   Halstead focuses on **low-level code complexity** (operators/operands).
*   CBD relies on **reusing pre-built components** (Black Boxes). You don't see the internal code of a component, so you can't count its operators.
*   **Better Metric for CBD:** Function Points (measures functionality, not code).

### 1.4 What is Cyclomatic Complexity?
**Definition:** A metric ($V(G)$) that measures the **logical complexity** of a program.
**Formula:** $V(G) = E - N + 2P$
*   $E$ = Edges (flow lines)
*   $N$ = Nodes (code blocks)
*   $P$ = Connected components (usually 1)
**Purpose:** It tells you the **maximum number of independent paths** through the code. This is the *minimum* number of test cases needed for full coverage.

### 1.5 Shortcomings of LOC (Lines of Code). Does Function Point (FP) overcome them?
**Shortcomings of LOC:**
1.  **Language Dependent:** 10 lines of Python might equal 100 lines of C.
2.  **Programmer Dependent:** A verbose programmer writes more LOC for the same feature.
3.  **Late Availability:** Can only be measured *after* coding is done.

**Does FP Overcome this?**
**Yes.** Function Points measure "Functionality delivered to the user" (e.g., Inputs, Outputs). This is independent of the language used and can be estimated **early** (from requirements).

***

## 2. Function Points (FP)

### 2.1 Explain the concept of Function Point. Why is it becoming acceptable?
**Concept:** Break the system into 5 Functional Units:
1.  **External Inputs (EI)**
2.  **External Outputs (EO)**
3.  **External Inquiries (EQ)**
4.  **Internal Logical Files (ILF)**
5.  **External Interface Files (EIF)**
**Formula:** $FP = \text{Count} \times \text{Weight} \times \text{Complexity Adjustment Factor (CAF)}$.

**Why Acceptable?**
*   **Language Independent:** Works for Java, C++, or SQL equally.
*   **Early Estimation:** Can be calculated from the SRS document before a single line of code is written.

## Function Point Weight Table

| Component | Simple | Average | Complex |
|-----------|--------|---------|---------|
| **External Inputs (EI)** | 3 | 4 | 6 |
| **External Outputs (EO)** | 4 | 5 | 7 |
| **External Inquiries (EQ)** | 3 | 4 | 6 |
| **Internal Logical Files (ILF)** | 7 | 10 | 15 |
| **External Interface Files (EIF)** | 5 | 7 | 10 |

**Example Calculation:**
- Inputs: 24 (Simple) → 24 × 3 = 72
- Outputs: 65 (Average) → 65 × 5 = 325
- Files: 12 (Complex) → 12 × 15 = 180
- UFP = 72 + 325 + 180 = 577
- If VAF = 1.05, then FP = 577 × 1.05 = 606


### 2.2 Practical Application of FP Method.
It is used primarily for **Project Planning**:
1.  **Estimating Size:** Before coding starts.
2.  **Estimating Cost/Effort:** Using historical data (e.g., "It costs $100 per FP").
3.  **Measuring Productivity:** "FPs per Month" is a better metric than "Lines of Code per Month."

***

## 3. COCOMO Theory

### 3.1 Explain all levels of the COCOMO Model.
**COCOMO (Constructive Cost Model)** estimates Effort and Time.

1.  **Basic COCOMO:** Quick, rough estimate. Uses only **KLOC** (Size).
    *   *Formula:* $E = a(KLOC)^b$
    *   *Modes:* Organic (Simple), Semi-detached (Medium), Embedded (Complex).
2.  **Intermediate COCOMO:** More accurate. Uses KLOC + **15 Cost Drivers** (e.g., Reliability, Team Capability).
    *   *Formula:* $E = E_{nominal} \times \text{EAF (Effort Adjustment Factor)}$.
3.  **Detailed COCOMO:** Break system into modules and apply Intermediate COCOMO to each module separately.

### 3.2 How does Intermediate COCOMO provide more accurate estimates?
**Basic COCOMO** assumes all 10,000-line projects take the same effort.
**Intermediate COCOMO** realizes that a 10,000-line project requiring **High Reliability** (e.g., flight software) takes more effort than a 10,000-line **Student Project**.
*   It calculates the **EAF** (Product of 15 multipliers).
*   *Example:* If "Reliability" is Very High, multiplier might be 1.40. This increases the effort estimate by 40%, making it more realistic.

### 3.3 Why is the sum of $\mu_p$ and $\tau_p$ not equal to 1?
*   **$\mu_p$ (Effort):** The breakdown of **Man-hours** across phases. This **must sum to 1** (100% of work).
*   **$\tau_p$ (Time):** The breakdown of **Schedule** (Calendar months).
    *   *Why it might not sum to 1:* Phases often **overlap**. "Coding" might start before "Design" is 100% finished. Therefore, the sum of calendar fractions can exceed 1.0 depending on how parallelism is modeled.

### 3.4 When does Project Planning start? How is Size estimated?
*   **Start:** Planning starts immediately after the **SRS (Requirements)** is finalized.
*   **Why Estimate Size?** You cannot estimate Cost ("How much money?") or Schedule ("When will it be done?") without knowing Size ("How big is it?").
*   **How:** Using **LOC** (Analogy based) or **Function Points** (Count based).

***

## 4. Risk Management

### 4.1 What is Risk? Activities?
**Risk:** A potential problem that *might* happen and *would* hurt the project.
**Activities:**
1.  **Risk Assessment:** Identifying and Analyzing risks.
2.  **Risk Control:** Mitigating and Monitoring risks.

### 4.2 How do we Assess and Control Risk?
*   **Assess:** Calculate **Risk Exposure (RE)**.
    *   $RE = \text{Probability} \times \text{Impact}$.
    *   *Example:* 10% chance of Server Crash $\times$ $50,000 cost = $5,000 RE.
*   **Control (RMMM Plan):**
    1.  **Mitigation:** Reduce probability (e.g., Backup server).
    2.  **Monitoring:** Watch for symptoms.
    3.  **Management:** Plan for if it actually happens (Contingency).

### 4.3 Is it possible to prioritize risk?
**Yes.** You prioritize based on **Risk Exposure (RE)**.
*   High Probability + High Impact = **Top Priority**.
*   Low Probability + Low Impact = **Ignore/Low Priority**.