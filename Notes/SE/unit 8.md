I have successfully found the missing information! The "Taute Maintenance Model" is a real (though older) model with **8 distinct phases**, and the "Levels of Reverse Engineering" refer to **Implementation, Design, and Specification/Analysis Abstraction**.

Here is your **100% complete Unit 8**, replacing all the "Skipped" sections with the correct answers.

***

# Unit 8: Software Maintenance

## 1. Concepts

### 1.1 What is Software Maintenance and why is it needed?
**Definition:** Software Maintenance is the set of activities required to keep a software system operational and useful after it has been delivered to the customer.
**Need for Maintenance:**
1.  **To correct errors** (bugs) that were not discovered during testing.
2.  **To adapt** the software to changes in its environment (new OS, hardware, or regulations).
3.  **To enhance** the software by adding new features requested by stakeholders.
4.  **To prevent** future problems by restructuring code (Preventive maintenance).
*   *Note:* Software does not "wear out," but it deteriorates due to change. Maintenance arrests this deterioration.

### 1.2 Categories of Software Maintenance (The 4 Types)

| Type | Purpose | Trigger |
| :--- | :--- | :--- |
| **Corrective** | To fix bugs/defects. | User reports a crash or error. |
| **Adaptive** | To move software to a new environment. | OS upgrade, new hardware, new database. |
| **Perfective** | To improve performance or add features. | User requests a new report format or faster speed. |
| **Preventive** | To improve maintainability/future-proof. | Code refactoring, updating documentation. |

### 1.3 Describe the Iterative Enhancement Model.
**Definition:** A maintenance model that treats changes as **iterative cycles**. It assumes the software has good documentation.
**The 3 Stages:**
1.  **Analysis:** Analyze the existing system and the requested change to understand the impact.
2.  **Classification:** Classify the change (Corrective, Adaptive, etc.) and classify the affected modules.
3.  **Implementation:** Implement the change in a cycle: **Design -> Coding -> Testing**.
**Benefit:** It controls complexity by handling maintenance in manageable "chunks" (iterations) rather than one chaotic fix.

### 1.4 Describe the Taute Maintenance Model. What are its phases?
The **Taute Model** is a classic cyclical maintenance model with **8 Phases**:
1.  **Change Request:** Customer submits a formal request for modification.
2.  **Estimate:** Maintenance team estimates time/effort and does **Impact Analysis**.
3.  **Schedule:** Change is assigned to a specific release schedule.
4.  **Programming:** Source code is modified to implement the change.
5.  **Test:** Regression testing is performed to ensure no new bugs were introduced.
6.  **Documentation:** System and user manuals are updated to reflect the change.
7.  **Release:** The updated software is delivered to the customer.
8.  **Operation:** Software enters normal use until the next Change Request arrives.

***

## 2. Reverse Engineering (RE)

### 2.1 What is Reverse Engineering? Scope and Tasks.
**Definition:** The process of analyzing a subject system to identify its components and their relationships, and to create representations of the system at a **higher level of abstraction** (e.g., creating Design from Code).
**Scope & Tasks:**
1.  **Understanding:** Gaining knowledge about the legacy system's logic.
2.  **Documentation:** Generating missing or outdated documents (specs, diagrams).
3.  **Recovery:** Recovering design and requirements from source code.
4.  **Redocumentation:** Creating new, readable documentation.

### 2.2 Levels of Reverse Engineering (Abstraction Levels)
Reverse engineering can extract information at three different levels of abstraction:

| Level | Name | Description |
| :--- | :--- | :--- |
| **Level 1** | **Implementation Abstraction** | (Lowest Level) Extracting details about the **source code**, syntax, and local data structures. Recovering *how* it was coded. |
| **Level 2** | **Design Abstraction** | (Middle Level) Recovering the **structure** of the system: modules, interfaces, and data flow (DFDs, Structure Charts). Recovering *how* it was designed. |
| **Level 3** | **Specification/Analysis Abstraction**| (Highest Level) Recovering the **business rules** and domain requirements. Recovering *what* the system actually does conceptually. |