Here is the **final hybrid Unit 3 document**. It combines the **precise definitions and process steps** from the file (which are technically superior) with the **tables and examples** from your new text (which are better for learning and exams).

***

# Unit 3: Requirements Engineering

## Requirements Concepts

### 1. Explain the importance of requirements.
Requirements describe **what** the system will do, not **how** it will do it. The process that creates the requirements is crucial, as they are related to the quality of the product.
The importance of requirements is evident in the negative outcomes when they are poorly defined:
*   **Developers** do not know precisely what to build.
*   **Customers** do not know what to expect.
*   **Validation** criteria are unclear, making it impossible to test if the software works correctly.

### 2. Distinguish between Functional, Non-Functional, and Domain Requirements with examples.

| Requirement Type | Description | Examples / Implications |
| :--- | :--- | :--- |
| **Functional Requirements** | Specify the functions or features the system must perform. They define **product features**. | *Examples:* Login, Calculate GPA, Generate Report. <br> *Focus:* "What" the system does. |
| **Non-Functional Requirements** | Stipulate **how well** the software performs its functions. These are quality attributes. | *Examples:* Reliability, Availability, Usability, Efficiency. <br> *Focus:* Constraints on the system. |
| **Domain Requirements** | Related to the specific **business environment** or domain constraints. | *Example:* Banking rules, tax laws, or medical regulations that the software must obey. |

### 3. Differentiate between Functional and Non-Functional Requirements.

| Feature | Functional Requirements | Non-Functional Requirements |
| :--- | :--- | :--- |
| **Scope** | Defines capabilities and services (Functions). | Defines quality criteria and constraints (Attributes). |
| **Question** | Addresses **"WHAT"** the system does. | Addresses **"HOW WELL"** it does it. |
| **Examples** | User input, data processing, report generation. | Speed, Security, Reliability, Maintainability. |

### 4. Differentiate between User and System Requirements.
*   **User Requirements:** Written for the **customer/end-user**. They describe what the user needs in natural language and diagrams.
*   **System Requirements:** A detailed **technical breakdown** derived from user requirements. They are written for developers and form the basis of the system design.

### 5. Give two non-functional requirements and explain their implications to system design.
1.  **Reliability:** The probability that software will work without failure for a specified time.
    *   *Implication:* Requires design decisions like **error tolerance**, redundancy, and rigorous exception handling.
2.  **Efficiency:** The relationship between performance and resource usage.
    *   *Implication:* Constrains design choices regarding **data structures, algorithms**, and hardware (e.g., using a Hash Map instead of a List for speed).

***

## SRS Document

### 6. What is the purpose of an SRS (Software Requirement Specification) document?
The SRS is the final outcome of the requirements phase. It defines the "What" of the system.
**Purposes:**
1.  **Contract:** Serves as a formal agreement between customer and developer.
2.  **Black Box Specification:** Describes system behavior without revealing internal design.
3.  **Communication:** Ensures developers know what to build and customers know what to expect.

### 7. Write the desirable characteristics of an SRS document.
A good SRS must be:
1.  **Correct:** Accurately reflects the user's needs.
2.  **Complete:** Contains all necessary requirements; nothing is missing.
3.  **Consistent:** No two requirements contradict each other.
4.  **Unambiguous:** Each requirement has only one interpretation.
5.  **Traceable:** Each requirement can be linked to code and test cases.
6.  **Modifiable:** Easy to change without breaking structure.
7.  **Design-Independent:** Describes "what", not "how".

### 8. Who are the stakeholders of SRS?
*   **Users:** The people who will actually use the software.
*   **Customers:** The people paying for the software.
*   **Developers:** The people building the software.
*   **Testers:** The people verifying the software.

### 9. List the important issues which an SRS must address.
An SRS must comprehensively address:
1.  **Functionality:** What the system does.
2.  **External Interfaces:** Interaction with hardware, users, and other systems.
3.  **Performance:** Speed, response time, throughput.
4.  **Attributes:** Reliability, Security, Maintainability.
5.  **Design Constraints:** limitations on implementation (e.g., specific OS, language).

***

## Elicitation Techniques

### 10. What is Requirements Engineering? Describe the steps.
Requirements Engineering (RE) is the process of analyzing, documenting, and validating requirements.
**Crucial Steps:**
1.  **Elicitation:** Gathering requirements from stakeholders (Interviews, etc.).
2.  **Analysis:** Refining and modeling requirements to resolve conflicts.
3.  **Documentation:** Writing the SRS document.
4.  **Review/Validation:** Checking the SRS for errors and quality.

### 11. What is Requirement Elicitation? Explain two techniques.
Elicitation is the process of gathering requirements. It is the most communication-intensive step.
**Techniques:**
1.  **Interviews:** Direct conversation with stakeholders. Can be **Structured** (pre-set questions) or **Open-ended** (flexible discussion).
2.  **Use Case Approach:** Describes system behavior from a user's point of view. Focuses on **Actors** (users) and their **Goals**.

### 12. Describe FAST (Facilitated Application Specification Technique).
*   **Definition:** A team-oriented approach where customers and developers work together to identify the problem and propose elements of the solution.
*   **Process:** Participants list system objects, functions, and constraints.
*   **Key Rule:** **No criticism or debate** is allowed during the generation phase to encourage free ideas.
*   **Comparison to Brainstorming:** Similar to brainstorming but more structured, with a specific focus on generating software specifications (objects, functions).

### 13. Explain the Use Case Approach and the Use Case Template.
*   **Use Case:** A description of a system's behavior as it responds to a request from a user (Actor).
*   **Actor:** An external entity (person or system) interacting with the software.
*   **Template Example (Login):**
    *   **Actor:** User / Admin.
    *   **Pre-condition:** User is on the login page.
    *   **Basic Flow:**
        1.  User enters username and password.
        2.  System validates credentials.
        3.  System redirects to dashboard.
    *   **Alternative Flow:**
        1.  User enters invalid credentials.
        2.  System shows error message.
    *   **Post-condition:** User is authenticated.

### 14. Why are requirements hard to elicit?
1.  **Ambiguity:** Users don't know exactly what they want.
2.  **Volatility:** Requirements change during the project.
3.  **Communication Gap:** Developers and users speak different "languages" (technical vs. business).
4.  **Conflicting Requirements:** Different stakeholders have different needs.

***

## Validation

### 15. Differentiate between Requirement Specification and Validation.

| Aspect | Requirement Specification | Requirement Validation |
| :--- | :--- | :--- |
| **Process** | Documentation of requirements. | Verification of requirements quality. |
| **Output** | **SRS Document**. | **List of Problems** / Error Report. |
| **Goal** | To define "What" to build. | To ensure the definition is **Correct, Complete, and Consistent**. |

### 16. What happens when validation reveals an error?
*   **Action:** The error is documented in a "List of Problems."
*   **Correction:** The **Requirements Engineer** modifies the SRS.
*   **Involvement:** The **Stakeholders** (Customer/User) must review the change to ensure the correction actually meets their needs.