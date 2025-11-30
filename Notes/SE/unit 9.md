***

# Unit 9: Software Quality & Standards

## CMM & ISO

### 1. Discuss the relative merits of ISO-9001 vs. SEI CMM. Why is CMM often "better"?
*   **ISO 9001 (Quality Assurance System):**
    *   **Scope:** Generic. Applies to *any* industry (manufacturing, service, software).
    *   **Focus:** Certifies that a company has a **Quality System** in place (procedures, manuals, audits).
    *   **Goal:** Customer satisfaction by meeting specifications.
    *   **Merit:** Widely recognized internationally for business contracts.
*   **SEI CMM (Process Improvement):**
    *   **Scope:** Specific to the **Software Industry**.
    *   **Focus:** Measures the **maturity** of the software process itself.
    *   **Goal:** Continuous process improvement (moving from "Chaos" to "Optimized").
    *   **Why CMM is "Better":** ISO 9001 is a "pass/fail" certification (you have a system or you don't). CMM provides a **roadmap** (Levels 1-5) for *how* to improve. CMM focuses on **quantitative measurement** of the process, which ISO 9001 often lacks.

### 2. Shortcomings of ISO 9001 for the Software Industry
1.  **Generic Nature:** It was originally designed for manufacturing; applying its rigid clauses to flexible software development can be difficult.
2.  **Documentation Heavy:** It often leads to excessive paperwork ("bureaucracy") rather than better software code.
3.  **Focus on Compliance over Quality:** Companies may focus on "passing the audit" rather than actually improving the software product.
4.  **Rigidity:** It can limit improvisation and adaptability, which are crucial for modern Agile software projects.

### 3. Explain the CMM Maturity Levels (Key Process Areas).
The CMM has **5 Maturity Levels**. A company must satisfy all Key Process Areas (KPAs) of a level to move up.

| Level | Name | Characteristics | Key Process Areas (KPAs) |
| :--- | :--- | :--- | :--- |
| **1** | **Initial** | **Ad-hoc / Chaotic.** Success depends on individual heroics. No defined process. | None. |
| **2** | **Repeatable**| **Basic Project Management.** Can repeat success on similar projects. | Requirements Mgmt, Project Planning, Config Mgmt. |
| **3** | **Defined** | **Standardized Process.** Process is documented and standardized across the organization. | Training Program, Peer Reviews, Intergroup Coord. |
| **4** | **Managed** | **Quantitative Measurement.** Process and quality are measured and controlled using data. | Quantitative Process Mgmt, Software Quality Mgmt. |
| **5** | **Optimizing**| **Continuous Improvement.** Focus on defect prevention and innovation. | Defect Prevention, Tech Change Mgmt. |

### 4. Salient Requirements for ISO 9001 (The 20 Clauses)
To get ISO 9001 certified, a company must address 20 clauses, including:
*   **Management Responsibility** (Leadership commitment)
*   **Document Control** (Versioning of manuals)
*   **Design Control** (Planning and verifying design)
*   **Corrective Action** (Fixing problems when they occur)
*   **Internal Quality Audits** (Self-checking)
*   **Training** (Ensuring staff skills)

***

## Quality Attributes & Models

### 5. What is Software Quality? Explain its attributes (ISO 9126).
**Definition:** Software Quality is the degree to which a system meets specified requirements and customer expectations ("Fitness for purpose").
**Attributes (ISO 9126):**
1.  **Functionality:** Does it do what is needed?
2.  **Reliability:** Does it run without crashing?
3.  **Usability:** Is it easy to learn and use?
4.  **Efficiency:** Does it use resources (CPU/RAM) well?
5.  **Maintainability:** Is it easy to modify/fix?
6.  **Portability:** Can it move to another environment easily?

### 6. Explain McCall's Software Quality Model.
McCall organizes 11 quality factors into **3 Viewpoints** (Product Lifecycle):

1.  **Product Operation** (Using it):
    *   *Correctness, Reliability, Efficiency, Integrity, Usability.*
2.  **Product Revision** (Changing it):
    *   *Maintainability, Flexibility, Testability.*
3.  **Product Transition** (Moving it):
    *   *Portability, Reusability, Interoperability.*

### 7. Explain Boehm's Software Quality Model.
Boehm's model is **hierarchical** and focuses on the **User's View** vs. the **Developer's View**.
It has 3 levels:
1.  **High-Level Characteristics (Primary Uses):**
    *   *As-is Utility:* (Reliability, Efficiency, Usability)
    *   *Maintainability:* (Testability, Understandability)
    *   *Portability.*
2.  **Intermediate Constructs:**
    *   7 quality factors (e.g., Reliability, Efficiency) that contribute to the high-level uses.
3.  **Primitive Constructs:**
    *   Low-level, measurable attributes (e.g., **Device Independence**, **Accuracy**, **Completeness**, **Consistency**, **Structuredness**).

**Difference from McCall:** Boehm adds hardware-related factors like **Device Efficiency** and emphasizes the "General Utility" of software more than just its operation.

***

## Configuration Management (SCM)

### 8. Explain Software Configuration Management (SCM) and its activities.
**Definition:** SCM is the discipline of managing **change** in software. It controls the evolution of the product.
**Key Activities:**
1.  **Identification:** Identifying all items (code, docs, data) that need managing (SCIs - Software Configuration Items).
2.  **Version Control:** Managing different versions (V1.0, V1.1) and ensuring developers don't overwrite each other's work.
3.  **Change Control:** A formal process (Change Control Board) to approve/reject requests for changes.
4.  **Configuration Auditing:** Verifying that the released software matches the documentation and requirements.
5.  **Reporting:** Recording and reporting the status of changes ("Who changed what and when?").

### 9. Short Note on SCM (Why we need it)
Software changes constantly (bugs, new features). Without SCM, these changes lead to chaos (e.g., "Which version has the fix?", "Who deleted my code?").
**Example:**
*   **Baseline:** A stable version (e.g., V1.0) is saved.
*   **Check-out:** Developer A checks out a file to edit.
*   **Locking:** SCM prevents Developer B from editing the same file simultaneously to avoid conflicts.
*   **Check-in:** Developer A saves the new version (V1.1). SCM records the change history.