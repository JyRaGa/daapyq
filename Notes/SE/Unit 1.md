## **Unit 1: Fundamentals & Introduction**

### **A. Software Definition and Core Concepts**

**1. What is Software? Explain its components.**
Software is a comprehensive construct that goes beyond just executable code. It is defined as a set of three intertwined elements:
1.  **Instructions (Computer Programs):** The executable code that, when run, provides the desired features, function, and performance.
2.  **Data Structures:** These structures allow the programs to adequately organize and manipulate information.
3.  **Descriptive Information (Documentation):** Information in both hard copy and virtual forms that describes how the programs operate and how they should be used.
*   **Equation:** Software = Program + Documentation + Operating Procedures.

**2. Differentiate between Program and Software.**
| Feature | Program | Software |
| :--- | :--- | :--- |
| **Scope** | Narrow; refers strictly to the set of computer instructions. | Broad; encompasses instructions, data, documentation, and procedures. |
| **Components** | Only the executable instructions. | Instructions + Data Structures + Documentation + Procedures. |
| **Goal** | To perform a specific computational task. | To provide desired features, function, and performance to the user. |

**3. Differentiate between Process and Product.**
*   **Process:** A collection of activities, actions, and tasks performed to create a work product. It provides the framework (the "HOW") for development, regardless of the project's size or complexity. A rigorous process ensures quality and consistency.
*   **Product:** The set of deliverables (the "WHAT") that results from the process. It represents the solution to the user's problem and includes the software, manuals, and data. The process exists to create the product.

**4. What do you mean by "Software doesn't wear out"? Compare it with hardware failure.**
*   **Concept:** Software is logical, not physical. It does not suffer from environmental degradation (dust, vibration, heat) like hardware.
*   **Hardware Failure (Bath Tub Curve):** Hardware follows a "Bath Tub" curve: high failure initially (burn-in), low constant failure (useful life), and rising failure at the end (wear-out phase) due to physical aging.
*   **Software Failure (Idealized vs. Reality):**
    *   **Idealized:** High initial failure (testing), then drops to a steady low rate. It never curves back up because it doesn't "break" physically.
    *   **Reality (Deterioration due to Change):** In practice, software deteriorates because of *change*. As new features or fixes are added, side effects are introduced, causing the failure rate to spike again. This makes the curve jagged and increasing over time, not because of wear, but because of complexity and poorly managed updates.

**5. Major Areas of Software Applications:**
1.  **System Software:** Serves other programs (e.g., OS, compilers).
2.  **Application Software:** Standalone business/consumer programs (e.g., Inventory control).
3.  **Engineering/Scientific:** Number-crunching algorithms (e.g., CAD, Astronomy).
4.  **Embedded Software:** Controls products/systems (e.g., Car breaking systems, microwaves).
5.  **Product Line Software:** Integrated suites for specific markets (e.g., Inventory + Finance).
6.  **Web/Mobile Applications:** Network-centric software widely accessed by browsers/phones.
7.  **Artificial Intelligence (AI):** Uses non-algorithmic heuristics (e.g., Pattern recognition, Robotics).

***

### **B. Software Management and Design**

**6. The 4 P's of Software Management:**
Effective software project management focuses on four Ps, in this specific order of dependency:
1.  **People:** The most important factor. The "human factor" determines success or failure.
2.  **Product:** The software to be built. Objectives and scope must be defined before proceeding.
3.  **Process:** The framework chosen to get the job done (e.g., Agile, Waterfall).
4.  **Project:** The actual planning and tracking of the work to deliver the product.

**7. Strategy of Design:**
Design is the problem-solving activity that focuses on "HOW" the system will work. It follows a four-step strategy:
1.  **Understand the problem:** (Communication & Analysis phase).
2.  **Plan a solution:** (Modeling & Software Design phase). This involves creating the architecture, data structures, and interfaces.
3.  **Carry out the plan:** (Code Generation).
4.  **Examine the result:** (Testing & QA).

**8. Functional vs. Object-Oriented Design Approach:**
| Feature | Functional (Structured) Design | Object-Oriented Design (OOD) |
| :--- | :--- | :--- |
| **Focus** | Focuses on the **function** or process (algorithms). | Focuses on the **data** (objects) and their interactions. |
| **Decomposition**| Decomposes system into functions/modules. | Decomposes system into Objects and Classes. |
| **Viewpoint** | Functions transform input to output. | Objects have state (data) and behavior (methods). |
| **Tools** | DFDs, Structure Charts, Flowcharts. | UML Diagrams (Class, Sequence, Use Case). |

**9. Purpose of Problem Partitioning:**
Partitioning (dividing a large problem into smaller parts) is crucial because:
*   **Reduces Complexity:** Smaller problems are easier to understand and solve.
*   **Separation of Concerns:** Allows focusing on one distinct feature at a time.
*   **Modularity:** Leads to high **Cohesion** (related tasks stay together) and low **Coupling** (dependencies are minimized), which makes maintenance easier.

***

### **C. Process Framework & Myths**

**10. Process Framework Activities (Generic & Umbrella):**
*   **Generic Framework Activities:** The core steps taken to build software: Communication, Planning, Modeling, Construction, Deployment.
*   **Umbrella Activities:** Activities applied *throughout* the process to **manage** and **control** quality (not just write code):
    *   **Software Quality Assurance (SQA):** Ensures standards are followed.
    *   **Software Configuration Management (SCM):** Manages changes (versions, backups).
    *   **Risk Management:** Identifies and mitigates potential problems.
    *   **Measurement:** Collects metrics (size, effort, defects) to improve the process.
    *   **Formal Technical Reviews:** Peer reviews to catch errors early.

**11. Why is Documentation Important?**
Documentation is a core component of software (Software = Program + Documentation).
*   **For Developers:** Without it, they don't know precisely what to build.
*   **For Customers:** Without it, they don't know what to expect or how to verify the product.
*   **For Maintenance:** It is critical for future updates; without it, the system becomes a "black box" that is risky to touch.

**12. Software Myths (Management, Customer, Practitioner):**
*   **Management Myth:** "We have standards, so we are good." -> **Reality:** Standards are often outdated or ignored.
*   **Management Myth:** "Adding people to a late project speeds it up." -> **Reality:** It slows it down (Brooks' Law) due to training and communication overhead.
*   **Customer Myth:** "A general statement of objectives is enough." -> **Reality:** Vague requirements lead to project failure; details are needed upfront.
*   **Customer Myth:** "Requirements can change easily." -> **Reality:** Changes late in the process are exponentially expensive.
*   **Practitioner Myth:** "My job is done when the code runs." -> **Reality:** 60-80% of effort is in maintenance *after* delivery.
*   **Practitioner Myth:** "Working program is the only deliverable." -> **Reality:** Documentation, models, and test plans are equally critical for long-term success.

**13. Purpose of CASE (Computer-Aided Software Engineering):**
CASE tools are automated software systems used to support software engineering activities. They reduce manual effort, ensure consistency, and help manage complexity in tasks like design, coding, testing, and project management.
