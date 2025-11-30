
# Unit 4: Software Design

## 4.1 Coupling & Cohesion

### 1. What do you understand by coupling and cohesion? Explain their types.
**Coupling:** The degree of interdependence between software modules. High coupling means changes in one module cause ripple effects in others.
*   **Goal:** **Minimize** coupling (Low Coupling).
**Cohesion:** The degree to which elements *inside* a module belong together. High cohesion means a module performs one focused task.
*   **Goal:** **Maximize** cohesion (High Cohesion).

### 2. Types of Coupling (Best to Worst)

| Type | Description | Quality |
| :--- | :--- | :--- |
| **Data Coupling** | Modules pass only necessary data items as parameters. No global data is shared. | **Best** |
| **Stamp Coupling** | Modules pass composite data structures (e.g., records) but may not use all fields. | Good |
| **Control Coupling** | One module controls the logic of another (e.g., passing a "flag" to switch execution paths). | Moderate |
| **Common Coupling** | Multiple modules access the same **global data** area. Hard to track errors. | Bad |
| **Content Coupling** | One module directly modifies or accesses the internal data/code of another. Violates encapsulation. | **Worst** |

### 3. Types of Cohesion (Best to Worst)

| Type | Description | Quality |
| :--- | :--- | :--- |
| **Functional** | The module performs exactly **one well-defined function**. | **Best** |
| **Sequential** | Output of one task becomes the input of the next task in the module. | High |
| **Communicational**| Tasks operate on the same input data or contribute to the same output data. | High |
| **Procedural** | Tasks are grouped because they follow a specific execution order (algorithm). | Moderate |
| **Temporal** | Tasks are grouped because they happen at the **same time** (e.g., initialization). | Moderate |
| **Logical** | Tasks are grouped by category (e.g., "all input routines") and selected by a flag. | Low |
| **Coincidental** | Tasks are grouped arbitrarily with no meaningful relationship. | **Worst** |

### 4. Why is it desirable to have Low Coupling and High Cohesion?
*   **Maintainability:** Changes are localized. You can fix one module without breaking another.
*   **Testability:** Modules can be tested in isolation (Unit Testing).
*   **Reusability:** A highly cohesive module (e.g., "Calculate Tax") can be reused in other programs easily because it doesn't depend on external globals (Low Coupling).

### 5. Can a system ever be completely "decoupled"?
**No.** If modules were completely decoupled (zero coupling), they could not talk to each other, and the system would do nothing. The goal is **loose** coupling (using defined interfaces/parameters), not **no** coupling.

***

## 4.2 Design Approaches

### 6. Top-Down vs. Bottom-Up Approaches

| Feature | Top-Down Approach | Bottom-Up Approach |
| :--- | :--- | :--- |
| **Strategy** | Starts with the main system function and breaks it down into sub-functions (Stepwise Refinement). | Starts with basic components (modules) and combines them to build the system. |
| **Decisions** | Major architectural decisions are made first; details come last. | Low-level details are decided first; architecture emerges later. |
| **Testing** | Main control loop is tested first; stubs are used for missing modules. | Unit testing is done first; drivers are used to call the modules. |
| **Best For** | Clear requirements; clarifying overall structure. | Reusing existing code; testing critical low-level algorithms early. |

### 7. Object-Oriented (OO) vs. Function-Oriented (FO) Design

| Feature | Function-Oriented Design | Object-Oriented Design |
| :--- | :--- | :--- |
| **Focus** | Focuses on **processes** (functions) transforming input to output. | Focuses on **entities** (objects) that hold data and behavior. |
| **Structure** | System is a hierarchy of functions (Top-Down). | System is a collection of interacting objects. |
| **Data Handling** | Data is often global or passed around; separate from functions. | Data is **encapsulated** inside objects (Information Hiding). |
| **Reuse** | Harder to reuse functions due to global dependencies. | Easier to reuse Classes via **Inheritance**. |

### 8. What is Modularity? State its desirable properties.
**Modularity** is the separation of the system into distinct, manageable parts (modules).
**Desirable Properties:**
1.  **Decomposability:** Problem can be broken into smaller sub-problems.
2.  **Composability:** Modules can be assembled into new systems.
3.  **Understandability:** A module can be understood in isolation.
4.  **Continuity:** Small changes affect only a few modules.
5.  **Protection:** Errors in one module don't crash the others.

***

## 4.3 Data Modeling & Rules

### 9. Data Flow Diagram (DFD) vs. Flowchart

| Aspect | Data Flow Diagram (DFD) | Flowchart |
| :--- | :--- | :--- |
| **Focus** | **Flow of Data** (Where does data go?). | **Flow of Control** (What happens next?). |
| **Logic** | **Suppresses** logic (No loops/ifs shown). | **Explicitly shows** logic (Diamond boxes for decisions). |
| **Timing** | No concept of timing or sequence. | strictly sequential. |

### 10. Rules for Drawing a DFD
1.  **Unique Names:** Every process and data store must have a unique name.
2.  **No Logic:** Do not show `if-else` or `loops`. Show only data movement.
3.  **Conservation of Data:** A process cannot create output data that wasn't derived from its input (no "magic" data).
4.  **Balancing:** Inputs/Outputs of a child DFD must match the parent DFD.

### 11. What is a Data Dictionary?
A **Data Dictionary** is a repository that defines all data elements used in the system (in DFDs). It ensures everyone uses the same definitions.
*   **Contents:**
    *   **Name:** (e.g., `Student_ID`)
    *   **Alias:** (e.g., `Roll_No`)
    *   **Type:** (e.g., Integer, 8 digits)
    *   **Description:** (e.g., "Unique identifier for a student")

### 12. Logical Constraints in ER Diagrams
*   **Cardinality:** How many instances relate? (1:1, 1:N, M:N).
*   **Participation:** Is the relationship mandatory or optional? (e.g., A specific employee *must* have a department vs. a department *may* have employees).

*   **Degree:** Unary (recursive), Binary (2 entities), Ternary (3 entities).
