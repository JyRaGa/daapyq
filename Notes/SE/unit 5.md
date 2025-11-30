
# Unit 5: UML & Modeling

### 1. Name the various diagrams used in UML. Also specify the purpose of drawing each diagram.
UML provides 13 different diagrams, categorized into **Structural** (static) and **Behavioral** (dynamic).

| Diagram Name | Category | Purpose (Specification) |
| :--- | :--- | :--- |
| **Class Diagram** | Structural | Defines the **static structure** of the system: classes, attributes, methods, and relationships (inheritance, association). It acts as a blueprint for objects. |
| **Use Case Diagram** | Behavioral | Visualizes **functional requirements** from a user's perspective. Shows **Actors** (users) and their interactions with system features (Use Cases). |
| **Sequence Diagram** | Behavioral | Depicts object interactions **over time**. Shows the order of messages passed between objects to complete a specific task. |
| **Communication Diagram** | Behavioral | Focuses on **object relationships** and organization. Unlike Sequence diagrams, it emphasizes *who* talks to *whom* rather than *when*. |
| **Activity Diagram** | Behavioral | Models the **flow of control** (workflow) of a system. Similar to a flowchart, it shows actions, decisions, and parallel processing. |
| **State Diagram** | Behavioral | Models the **lifecycle of a single object**. Shows the different states an object goes through (e.g., Order Placed -> Shipped -> Delivered) in response to events. |
| **Deployment Diagram** | Structural | Maps software artifacts (code, DB) to **physical hardware** (servers, devices). Shows the physical architecture. |

### 2. State the properties of a Class Diagram with an example.
A Class Diagram acts as a template for creating objects.
**Properties/Components:**
1.  **Class Name:** The unique identifier (e.g., `Student`).
2.  **Attributes:** Data variables held by the class.
    *   *Visibility:* `+` (Public), `-` (Private), `#` (Protected).
    *   *Example:* `- studentID: int`.
3.  **Operations:** Methods or functions the class can perform.
    *   *Example:* `+ calculateGPA(): float`.
4.  **Relationships:** Lines connecting classes (Association, Inheritance, etc.).

### 3. How do you represent a class in UML?
A class is represented as a **rectangle divided into three compartments**:
1.  **Top:** Class Name (Centered, Bold).
2.  **Middle:** Attributes (List of variables).
3.  **Bottom:** Operations (List of methods).

**Example Notation:**
```
+-----------------------+
|       Student         |  <-- Name
+-----------------------+
| - name: String        |  <-- Attributes
| - rollNo: int         |
+-----------------------+
| + register(): void    |  <-- Operations
| + getResults(): void  |
+-----------------------+
```

### 4. What is a Use Case Diagram? Explain with an example.
A **Use Case Diagram** captures the **functional requirements** of a system. It shows "Who" (Actors) does "What" (Use Cases).
**Components:**
*   **Actor:** An external entity (User, Admin, System) represented by a stick figure.
*   **Use Case:** A specific function or goal represented by an oval (e.g., "Login").
*   **System Boundary:** A box defining the scope of the system.

**Example (Result Management System):**
*   **Actors:** Data Entry Operator, Student.
*   **Use Cases:** `Login`, `Enter Marks`, `Generate Report`, `Check Result`.
*   *Scenario:* The "Data Entry Operator" (Actor) connects to the "Enter Marks" (Use Case) via a line.

### 5. Explain the difference between Association, Aggregation, and Generalization.

| Relationship | Symbol | Description |
| :--- | :--- | :--- |
| **Generalization** | Solid line with **hollow triangle** arrow pointing to parent. | **"Is-A" Relationship** (Inheritance). <br> *Example:* `Car` is a `Vehicle`. Subclass inherits from Superclass. |
| **Association** | Solid line (can have arrow). | **"Uses" Relationship**. Two classes interact but are independent. <br> *Example:* `Teacher` teaches `Student`. |
| **Aggregation** | Solid line with **hollow diamond** at the container end. | **"Has-A" Relationship** (Weak ownership). Child can exist without Parent. <br> *Example:* `Classroom` has `Students`. If Classroom is deleted, Students still exist. |
| **Composition** | Solid line with **filled diamond**. | **Strong "Has-A"**. Child dies if Parent dies. <br> *Example:* `House` has `Room`. If House is destroyed, Room is gone. |

### 6. Difference between Sequence Diagram and Communication (Collaboration) Diagram.

| Feature | Sequence Diagram | Communication Diagram |
| :--- | :--- | :--- |
| **Focus** | **Time Ordering** of messages. | **Structural Relationships** between objects. |
| **Axis** | Vertical axis represents **Time**. | No time axis; uses numbered labels (1, 1.1, 2) for order. |
| **Usage** | Best for seeing the flow of logic step-by-step. | Best for seeing which objects talk to each other. |
| **Visual** | Lifelines (vertical dashed lines) drop down. | Network of objects connected by links. |

### 7. How do you represent "if" and "while" in a Sequence Diagram?
We use **Interaction Frames** (rectangular boxes):
*   **If / Else:** Use an **`alt`** (Alternative) frame. The box is split into two sections (e.g., `[valid login]` top half, `[invalid]` bottom half).
*   **If (Single):** Use an **`opt`** (Optional) frame. Messages inside run only if the condition is true.
*   **While Loop:** Use a **`loop`** frame. The condition (e.g., `[for each item]`) is written at the top.

### 8. What is the difference between Sequential Substates and Concurrent Substates?

| Feature | Sequential Substates | Concurrent Substates |
| :--- | :--- | :--- |
| **Definition** | Substates occur **one at a time** in a sequence. | Substates occur **in parallel** (simultaneously). |
| **Active State** | Only **one** substate is active. | **Multiple** substates (one per region) are active. |
| **Transition** | Triggered by events moving from A to B. | Usually enter/exit a composite state together. |
| **Visual** | Connected by arrows in a single region. | Separated by **dashed lines** (swimlanes) inside the state. |
| **Example** | ATM: Reading Card -> Verifying PIN. | Car: Engine Running || Radio Playing. |

### 9. How do you represent a node in a Deployment Diagram?
*   **Representation:** A **3D Box** (Cube).
*   **Information on Node:**
    *   **Node Name:** (e.g., `Database Server`).
    *   **Stereotype:** (e.g., `<<device>>`).

    *   **Artifacts:** The actual files deployed inside (e.g., `student_db.sql`, `app.exe`).
