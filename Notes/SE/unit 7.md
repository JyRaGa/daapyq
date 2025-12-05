Here is the **Final Hybrid Document for Unit 7**. It combines the clear, table-based explanations from your text (V&V, White/Black Box) with the **complete content** from the file (Alpha/Beta, Tools, Definitions) that your text missed.

***

# Unit 7: Verification, Validation & Testing

## 1. Verification and Validation (V&V)

### 1.1 Differentiate between Verification and Validation. When are they performed?

| Feature | Verification (Checking the Process) | Validation (Checking the Product) |
| :--- | :--- | :--- |
| **Primary Question** | "Are we building the product **right**?" | "Are we building the **right** product?" |
| **Focus** | Checks if software conforms to **specifications**. | Checks if software conforms to **user needs**. |
| **Methodology** | Reviews, Walkthroughs, Inspections. (Static) | System Testing, User Acceptance Testing. (Dynamic) |
| **Timing** | Performed **throughout** the lifecycle. | Performed at the **end** (Testing/Delivery). |

## 2. Testing Concepts & Methodologies

### 2.1 White Box vs. Black Box Testing

| Feature | White Box Testing (Structural) | Black Box Testing (Functional) |
| :--- | :--- | :--- |
| **Definition** | Testing based on internal code structure. | Testing based on external specifications (inputs/outputs). |
| **Visibility** | Tester **knows** the internal code/logic. | Tester treats system as a **Black Box** (unknown logic). |
| **Techniques** | Path Testing, Cyclomatic Complexity. | Equivalence Class Partitioning, Boundary Value Analysis. |
| **Test Cases** | Harder to design (needs flow graph). | **Easier** to design (based on requirements). |

### 2.2 Significance of Independent Paths
*   **Definition:** An independent path is any path through the program that introduces at least one new set of processing statements or a new condition.
*   **Significance:** In **Basis Path Testing** (White Box), executing all independent paths guarantees that every statement in the program has been executed at least once. The number of independent paths is given by **Cyclomatic Complexity** $V(G) = E - N + 2$.
*   **Necessity of Tools:** Yes. As program size increases (e.g., >100 lines), the number of paths grows exponentially ($10^{14}$ in complex loops). Manual calculation is impossible; automated tools are required.

### 2.3 Boundary Value Analysis (BVA) vs. Robustness Testing
*   **Boundary Value Analysis:** A Black Box technique that focuses on the **edges** of the input domain (Min, Max, Min+1, Max-1).
    *   *Test Cases:* $4n + 1$ (where $n$ = number of variables).
*   **Robustness Testing:** An extension of BVA that tests **invalid** values just *outside* the boundary (Min-1, Max+1).
    *   *Goal:* To check if the system crashes or handles errors gracefully.
    *   *Test Cases:* $6n + 1$.

### 2.4 Does a Fault necessarily lead to Failure?
**No.**
*   **Fault (Bug):** A defect in the code (e.g., `if (x > 100)` should be `if (x >= 100)`).
*   **Failure:** The visible error produced during execution.
*   **Reasoning:** A fault only causes a failure if the code is executed **and** the specific input triggers the bug. If `x` is never exactly 100 during testing, the fault lies dormant and no failure occurs.

## 3. Testing Tools & Stakeholders

### 3.1 Popular Software Testing Tools
1.  **Coverage Analyzers:** Measure how much code is exercised (e.g., Statement/Branch coverage).
2.  **Test Data Generators:** Automatically create input data for testing.
3.  **Output Comparators:** Automatically compare actual output vs. expected output.
4.  **Test Harnesses:** Drivers/Stubs used to test modules in isolation (Unit Testing).

### 3.2 Stakeholders in Testing
1.  **Developers:** Perform Unit Testing.
2.  **Independent Test Group (SQA):** Perform Integration/System Testing.
3.  **Customers/Users:** Perform Acceptance/Beta Testing.
4.  **Project Managers:** Track testing progress and quality metrics.

### 3.3 Automation Challenges for SQA
1.  **Complexity:** Huge number of device/platform combinations (especially mobile).
2.  **Reproducibility:** Hard to reproduce intermittent errors (timing/network issues).
3.  **Semantic Errors:** Tools can check syntax/crashes but can't check if content is "offensive" or "misleading."
4.  **High Variability:** Network speeds and server loads vary unpredictably.

## 4. Alpha vs. Beta Testing

| Feature | Alpha Testing | Beta Testing |
| :--- | :--- | :--- |
| **Location** | **Developer's Site** (Internal). | **User's Site** (External/Real World). |
| **Testers** | Internal Employees/QA Team. | Real Customers/End Users. |
| **Environment**| Controlled/Simulated. | Uncontrolled/Live. |
| **Purpose** | Find bugs before releasing to Beta. | Final validation/feedback before public launch. |

## 5. Definitions

### 5.1 Test Case vs. Test Suite
*   **Test Case:** A single set of **Inputs**, **Execution Conditions**, and **Expected Results** developed for a specific objective (e.g., "Verify Login with valid password").
*   **Test Suite:** A **collection of test cases** grouped together for execution (e.g., "Regression Test Suite").

### 5.2 Importance of Regression Test Selection
*   **Definition:** Re-running tests to ensure recent code changes didn't break existing features.
*   **Selection:** Instead of re-running *all* 10,000 tests (too slow), we select only:
    1.  Tests for the **modified module**.
    2.  Tests for modules that **depend on** the modified module.
*   **Example:** If you change the "Interest Calculation" module, you must re-test "Interest" and "Monthly Statement" (which uses Interest), but you can skip "Address Change" (unrelated).

## Data Flow Testing (NEW 2024)

**Concepts:**
- **DEF:** Variable is defined/assigned (x = 10)
- **USE:** Variable is used
  - **C-use:** In computation (z = x + y)
  - **P-use:** In condition (if x > 0)
- **DU-pair:** Definition at line i, Use at line j

**Coverage Criteria:**
1. **All-defs:** Every definition reaches at least ONE use
2. **All-uses:** Every definition reaches ALL uses
3. **All-du-paths:** Test ALL paths from DEF to USE

## Decision Table Testing (NEW 2024)

**Steps:**
1. List all conditions (rows)
2. List all actions (bottom rows)
3. Create rules (columns) for each combination
4. Mark actions with X for each rule
5. Generate test cases from rules

**Example:** Login System
- Conditions: Valid username? Valid password?
- Actions: Grant access, Deny access, Log attempt
