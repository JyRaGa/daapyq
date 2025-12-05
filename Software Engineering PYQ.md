
# **Software Engineering Question Bank**
## **(Compiled from 25+ Papers)**

***
## Table of Contents

1.  [**Fundamentals & Introduction**](#1-fundamentals--introduction)
    *   Software Concepts
    *   Process & Management
2.  [**Software Process Models**](#2-software-process-models)
    *   Spiral Model
    *   Prototyping & Evolutionary
    *   Lifecycle Selection & Other Models
3.  [**Requirements Engineering**](#3-requirements-engineering)
    *   Requirements Concepts
    *   SRS Document
    *   Elicitation Techniques
    *   Validation
4.  [**Software Design**](#4-software-design)
    *   Coupling & Cohesion
    *   Design Approaches
    *   Data Modeling & Rules
5.  [**UML & Modeling (Text-Based Questions)**](#5-uml--modeling-text-based-questions)
    *   Diagram Concepts
6.  [**Drawing, Design & Diagramming Tasks**](#6-drawing-design--diagramming-tasks)
    *   System-Specific Design Tasks (Airline, Hotel, Metro, etc.)
7.  [**Verification, Validation & Testing**](#7-verification-validation--testing)
    *   V&V
    *   Testing Concepts & Methodologies
8.  [**Software Maintenance**](#8-software-maintenance)
    *   Concepts
    *   Reverse Engineering
9.  [**Software Quality & Standards**](#9-software-quality--standards)
    *   CMM & ISO
    *   Quality Attributes & Models
    *   Configuration Management
10. [**Metrics & Estimation**](#10-metrics--estimation)
    *   Metrics Concepts
    *   Function Points
    *   COCOMO Theory
    *   Risk Management
11. [**Calculation & Practice Problems**](#11-calculation--practice-problems)
    *   Function Point Calculations
    *   COCOMO Calculations
    *   Halstead Metrics
    *   Maintenance Calculations
    *   Test Case Design
    *   Scenario Writing
12. [**Selected Optional Problems**](#12-selected-optional-problems)

***

## **1. Fundamentals & Introduction**
- **Software Concepts:**
  - Differentiate between **Program** and **Software**.
  - Differentiate between **Process** and **Product**.
  - What is Software? Explain its components.
  - What do you mean by the statement "Software doesn't wear out"? Compare it with the failure intensity rate curve of the hardware.
  - Discuss briefly the major areas of applications of a software.
  - What is the purpose of problem partitioning?
  - Why is documentation given importance in software development?
  - What are **Software Myths**? Discuss how they affect the software process. Explain widely held myths among:
      *   Management
      *   Customers
      *   Practitioners

- **Process & Management:**
  - Explain the four P's of software management.
  - State the four factors of management of software development.
  - State the categories that the process framework consists of. Which activities help the software team to manage (not develop) the software? Explain all of them.
  - Discuss the strategy of design.
  - What is the purpose of **CASE** (Computer-Aided Software Engineering)?
  - Contrast between functional and object-oriented approaches of system design.

***

## **2. Software Process Models**
- **Spiral Model:**
  - Explain the Spiral life cycle model and its limitations.
  - What is the most important feature of the spiral model?
  - Discuss the spiral model. What are its advantages and disadvantages?
  - Explain why the spiral model is considered to be a meta model.
  - What are the two characteristics of the spiral model which distinguish it from other process models?
  - Give an example of a software process where the spiral model is suitable and one where it is not. Justify your answer.
  - Explain the Spiral model in software development life cycle. Discuss the conditions based on all parameters where spiral model is best suited.
  - As you move outward along the process flow path of the spiral model, what can you say about the software that is being developed or maintained?
  - How does "project risk" factor affect the spiral model of software development?
  - What are the framework of activities associated with Spiral Model and V Model? Identify their strengths and weaknesses.

- **Prototyping & Evolutionary:**
  - Describe the prototyping model of software development. Under what circumstances is this model suitable over other models?
  - What are the major advantages of first constructing a working prototype before starting to develop actual software? What are the disadvantages?
  - Discuss the Prototyping model. What is the effect of designing a prototype on the overall cost of a project? What are the advantages of developing a prototype?
  - Discuss the advantage and disadvantage of the prototyping model over the evolutionary model for software development.
  - Differentiate between increment and evolutionary process models.

- **Lifecycle Selection & Other Models:**
  - What are the characteristics to be considered for the selection of life cycle model? Discuss in detail.
  - Why do we feel that characteristics of requirements play a very significant role in the selection of a life cycle model? Also, discuss the selection process parameters.
  - Describe the **Rapid Application Development (RAD)** model. Discuss each phase in detail.
  - Explain **Agile** and RAD life cycle models.
  - State the features of waterfall model. Mention the disadvantages and appropriate SDLC model name for each.
  - Explain why incremental development is the most effective approach to developing business software systems. Why is this model less appropriate for real-time systems engineering?
  - Compare the waterfall and the spiral model of software development.

***

## **3. Requirements Engineering**
- **Requirements Concepts:**
  - Explain the importance of requirements.
  - Distinguish between functional, non-functional, and domain requirements with examples.
  - Differentiate between functional and non-functional requirements.
  - Differentiate between functional and non-functional requirements and between user and system requirements.
  - Discuss the difference between Functional and Non-functional requirements.
  - Discuss the difference between User and System requirements.
  - Give two non-functional requirements and briefly explain their implications to system design.
  - How is Functional Requirement different from Non-Functional Requirements?

- **SRS Document:**
  - What is the purpose of an **SRS** (Software Requirement Specification) document?
  - Write the desirable characteristics of an SRS document.
  - Who are the stakeholders of SRS?
  - List the important issues which an SRS must address.
  - What are the issues addressed by SRS writers? What are the characteristics of a good SRS?
  - Discuss the organization of SRS as per IEEE standard.

- **Elicitation Techniques:**
  - What is requirements engineering? Describe the various steps of the requirements engineering process.
  - What is requirement elicitation? Explain any two techniques.
  - Discuss any two requirements elicitation techniques with suitable examples.
  - List out requirement elicitation techniques. Which one is most popular and why?
  - Explain in brief about Requirement Elicitation techniques.
  - Describe **Facilitated Application Specification Technique (FAST)** and compare this with brainstorming sessions.
  - Explain the use case approach of requirements elicitation and also discuss the use-case template.
  - Why are requirements hard to elicit?

- **Validation:**
  - State the differences between Requirement Specification and Validation.
  - What do you think happens when requirement validation reveals an error? Who is involved in correcting the error?

***

## **4. Software Design**
- **Coupling & Cohesion:**
  - What do you understand by coupling and cohesion? Explain their types. What roles do they play in software design?
  - Explain the difference between module cohesion and module coupling. List any two types each for cohesion and coupling. What is the relationship between cohesion and coupling?
  - Discuss module coupling and its types with suitable examples.
  - What is **coupling**? Explain the best and worst types of coupling.
  - What problems are likely to arise if two modules have high coupling?
  - Define **module cohesion** and explain different types of cohesion.
  - What is cohesion? Explain the best and worst types of cohesion.
  - Why is it desirable to have a module having low coupling and high cohesion?
  - Is it true that a good design should have high coupling and low cohesion? Explain your answer.
  - Can a system ever be completely "decoupled"? Can the degree of coupling be reduced so much that there is no coupling between modules? Explain your answer.
  - Also, explain the term cohesion in software (in context of decoupling).

- **Design Approaches:**
  - Explain Top-Down and Bottom-Up approaches in brief.
  - Compare top-down and bottom-up software design approaches with advantages and disadvantages of both approaches.
  - Discuss the difference between object-oriented and function-oriented design.
  - How is function-oriented design different from object-oriented design? Explain with appropriate examples.
  - Contrast between functional and object-oriented approaches of system design.
  - What is design? Describe the difference between conceptual design and technical design.
  - What do you understand by **modularity** in software development? Why is it needed?
  - What is modularity? State the desirable properties of a modular system.

- **Data Modeling & Rules:**
  - What is the use of Data Dictionaries? Explain with example.
  - Describe the contents and model of a data dictionary.
  - What is the role of **Data Dictionary**?
  - What is the purpose of a Data Flow Diagram (DFD)? Distinguish it from a flowchart.
  - What rules should be observed while drawing a **DFD** (Data Flow Diagram)? What constraints must be observed while creating a leveled DFD?
  - What are the logical constraints while drawing an **ERD** (Entity Relationship Diagram)?

***

## **5. UML & Modeling (Text-Based Questions)**
- **Diagram Concepts:**
  - Name the various diagrams used in UML. Also specify the purpose of drawing each diagram.
  - State the properties of class diagram with example.
  - How do you represent a **class** in UML? What information can you show on a class icon?
  - What is a Use case diagram? Explain with example.
  - Explain the difference between association, aggregation, and generalization.
  - What is the difference between a **sequence diagram** and a **collaboration diagram**? Illustrate using a suitable example.
  - In a sequence diagram, how do you represent the flow of control implied by an "if" statement and a "while" statement? Give examples.
  - What is the difference between sequential substates and concurrent substates?
  - How do you represent a node in a **deployment diagram**? What kind of information can appear on a node?

***

## **6. Drawing, Design & Diagramming Tasks**
- **Airline Reservation System:** Design DFD (Upto Level 1) and Use Case Template/Diagram.
- **Hotel Management System:** Draw ER diagram and Level 1 DFD; mention requirements.
- **Hospital Transaction System:** Design Use case diagram and Use cases for a 200-inpatient system.
- **Delhi Metro Automation System (DMAS):** Draw Context, Level-1, and Level-2 DFDs for Token/Smart card functions.
- **Retail Clothing Store:** List data flows/stores/processes; Draw DFD and ER Diagram.
- **University Registration:** Draw Context level, Level-1 DFD, and Level-2 DFD.
- **Transport Notifications:** Draw Context level, Level-1 DFD, and Level-2 DFD.
- **IRCTC (Indian Railway Catering and Tourism Corporation):**
  
   **Complete Requirements:**
  
   i. **Train Search:** Users search trains based on source, destination, date, and class
  
   ii. **Ticket Booking:** Users book tickets for selected train, choose preferred class, make reservations for multiple passengers
  
   iii. **User Account Management:** Registered users can login, view booking history, and cancel reservations
  
   iv. **Admin Functions:** Administrators manage train schedules, update seat availability, generate reports on ticket bookings
  
   v. **Payment Gateway:** System handles online payments securely.
  
   **Draw:** Use Case Diagram, Activity Diagram, Sequence Diagram, Class Diagram, and State Chart Diagram

- **Student Management:** Draw Context and Level-1 DFD.
- **Use Case "Buy Soda":** Draw collaboration diagram for specific scenarios.
- **Data Center:** Draw an ER-diagram for employee/project management.
- **Banking System:** Draw Use Case diagram (dependencies) and DFD for deposit.
- **Library Management System (COMPLETE SPECIFICATIONS):**
   
   **Requirements:**
   
   1) **Issue of Books:**
      
      - Any student can get books issued
      - Book bank books: Only for respective courses
      - General section books: Issued to all
      - Limitation: Max 4 books from book bank + 3 from general section per student
      - Book bank books: Issued for entire semester
      - General section books: Issued for 15 days only
      - System uses current date as issue date and calculates return date automatically
      - Bar code detector saves student and book information
      - Due date stamped on book
   
   3) **Return of Books:**

       - Any person can return books
      - Bar code reader displays student information
      - System shows: Student details, issue date, return date
      - Fine calculation: Rs. 1 per day if returned late
      - Information saved and database updated
   
   5) **Query Processing:**
    
      - Check availability of a particular book
      - Check availability of books by a particular author
      - Number of copies available of desired book
      - Reserve book for 24 hours if currently unavailable
   
   **Draw:** Context diagram, 1-level DFD, and Structured Chart

- **Boehm Quality Model:** Explain with a block diagram.
- Design a system for a metropolitan transport authority that provides **real-time, targeted notifications** to users. Unlike generic broadcasts, this system    must alert users **only** when disruptions occur on their specific route of interest and **only** at the relevant time (e.g., not when they are out of town): Draw Use Case Diagram & Draw a Level-1 DFD."
- **Point of Sales (POS) System:** 
Full Requirements:
   - POS manages sales in retail stores (Restaurants, Gas Stations, Convenience Stores)
   - Components: Printer, barcode scanner, computer, Debit/Credit Card Reader, keyboard, touch screen, weighing machine
   - Process: Cashier scans items → Retrieves price from backend catalog → Interacts with inventory → Shows price to customer including sales tax
   - Payment types: Cash, credit/debit card, coupons, Points/Promotion Card, cheque
   - User login required (Cashiers, Managers, Administrators)
   - Admin-only access for management functions
   - Must be fault tolerant and work offline when remote services unavailable
   - Self-checkout functionality is NOT included
   Draw: (i) Use Case Diagram, (ii) 1-level DFD
- **Order Processing System:**
   - Receives orders through salesman
   - Sends goods by transport
   - Maintains track order including:
     * Order receiving dates
     * Delivery dates
     * Invoice details
   - Use assumptions to add more functionality, Draw: Zero level DFD and One level DFD
- **Student Academic Management System:**
   Specific Features:
   • Register students to subjects
   • Award marks for subjects
   • Query marks
   • Print report cards
   • Compute statistics of student performance, Draw: Context diagram and Level 1 DFD



***

## **7. Verification, Validation & Testing**
- **V&V:**
  - Differentiate between Verification and Validation.
  - Distinguish between software verification and software validation. When are they performed during the software life cycle?
  - Differentiate between verification and validation with examples.

- **Testing Concepts & Methodologies:**
  - What is the difference between **white box** and **black box** testing? Is determining test cases easier in black or white box testing?
  - Explain the significance of **independent paths**. Is it necessary to look for a tool for flow graph generation if program size increases beyond 100 source lines?
  - What is **Boundary Value Analysis** technique for test case generation? How is Robustness testing different from it? Explain.
  - Does fault necessarily lead to failure? Justify your answer with examples.
  - Name four software testing tools that are popularly used these days.
  - Name the stakeholders involved in testing.
  - What are the automation challenges that SQA (Software Quality Assurance) team faces while testing?
  - Differentiate between **Alpha** and **Beta** testing.
  - Define: (i) **Test case**, (ii) **Test suite**.
  - What is the importance of **regression test selection**? Discuss with the help of examples.
   
***

## **8. Software Maintenance**
- **Concepts:**
  - What is Software Maintenance and why do we need it? Also, what are the categories of software maintenance?
  - Why is maintenance mandatory after software delivery? Explain the categories of maintenance.
  - What is software maintenance? Explain its types (Perfective vs. Corrective).
  - Describe the **iterative enhancement model**. Discuss each phase in detail.
  - How is the iterative enhancement model helpful during maintenance? Explain the various stage cycles of this model.
  - Describe the **Taute maintenance model**. What are various phases of this model?

- **Reverse Engineering:**
  - Write a short note on Reverse Engineering.
  - What is reverse engineering? Explain its scope and tasks.
  - Discuss various levels of reverse engineering.

***

## **9. Software Quality & Standards**
- **CMM & ISO:**
  - Discuss the relative merits of **ISO-9001** certification and the **SEI CMM** based evaluation.
  - Point out some of the shortcomings of the ISO-9001 certification process as applied to the software industry.
  - Discuss the difference between CMM and ISO 9001. Why is it suggested that CMM is the better choice than ISO 9001?
  - Discuss the ISO 9000 certification for software industry and also explain the SEI capability maturity model.
  - Explain the **CMM** (Capability Maturity Model) and its levels (Key Process Areas).
  - Name the Maturity Levels of CMM.
  - Write salient requirements for obtaining the ISO 9000 model.
  - Why is a customer only interested in product certification? Discuss any product certification technique with their generic applicability.

- **Quality Attributes & Models:**
  - What do you mean by **software quality**? Explain its attributes.
  - Explain McCall's software quality model.
  - Differentiate between Boehm and McCall software quality models with examples.
  - Write a short note on Boehm Software Quality Model.

- **Configuration Management:**
  - Explain configuration management with the activities involved in it.
  - Write a short note on Configuration Management with suitable examples.

***

## **10. Metrics & Estimation**
- **Metrics Concepts:**
  - Define software metrics and classify them.
  - Define **Halstead software science metrics**.
  - Explain the Halstead theory of software science. Is it significant in today's scenario of component-based software development?
  - Discuss the program length, potential volume, effort & time, and language level as per Token Count metrics.
  - Write a short note on Cyclomatic Complexity.
  - List important shortcomings of **LOC** (Lines of Code) for use as a software size metric. Does the function point metric overcome these?

- **Function Points:**
  - Explain the concept of Function point. Why are function points becoming acceptable in the industry?
  - What is the practical application of function point method?

- **COCOMO Theory:**
  - Explain all levels of the **COCOMO model**.
  - Explain with the help of an example how an **intermediate COCOMO** provides more accurate estimates compared to basic COCOMO.
  - Why is the sum of $\mu_p$ (Effort Multiplier) and $\tau_p$ (Time Multiplier) in the COCOMO model not equal to 1?
  - At which point in the software development life cycle does project planning start? Why does a project manager need to estimate the size of the project? How is the size estimated?

- **Risk Management:**
  - What do you understand by **risk**? What are risk management activities? How do we assess and control the risk?
  - Is it possible to prioritize the risk?
    
- **Project Scheduling Tools:**
   - Explain **Gantt Chart** and **PERT Chart**. Discuss their use in project scheduling.
   - What is the **Critical Path Method (CPM)**? How is it used for project scheduling and resource management?
   - Differentiate between Gantt charts and PERT charts with examples.
   - Write a short note on: (a) Gantt chart and Pert chart, (b) Critical Path Method

***

## **11. Calculation & Practice Problems**
- **Function Point Calculations:**
  - **A:** Inputs=30, Outputs=42, Enquiries=08, Files=07, Interfaces=6. (Complexity: average/moderate).
  - **B:** Inputs=24, Outputs=65, Enquiries=12, Files=12, Interfaces=4. (Complexity: average/moderate).

- **COCOMO Calculations, see the tables:**
 - A software team is working on a project with the following metrics:
    * Total lines of code (LOC): 10,000
    * Average productivity: 200 LOC/person-month
    * Target timeline: 6 months
    * Calculate:  1. Total effort required (in person-months). 2. Estimated number of people required to complete the project on time.
  - **Single Module:** Project size = 32,000 LOC (Organic). Calculate Effort & Time.
  - **Single Module:** Project size = 200 KLOC. Average experience. Calculate Effort, Time, Staff, Productivity.
  - **Single Module:** Project size = 400 KLOC. Calculate Effort & Time for all 3 modes (Organic, Semi, Embedded).
  - **Multi-Module:** System with 5 modules (0.5, 1.5, 2.0, 1.0, 2.0 KLOC). High complexity/reliability, Low experience. Calculate Cost & Schedule.

- **Halstead Metrics: see tables**
  - Program with Unique Operators=20, Unique Operands=40. Compute: Length, Volume, Level, Effort, Language Level.

- **Maintenance Calculations see tables:**
  - **A:** Dev Effort=600 PM, K=0.5, Complexity=7, d=0.7. Calculate Total Effort (M).
  - **B:** Dev Effort=500 PM, K=0.3, Complexity=8. Calculate Effort for d=0.9 and d=0.1.
  - **C (Annual Change):** ACT=25%, Dev Effort=500 PM, Lifetime=5 yrs. Compute Annual Maintenance Effort & Total Effort.

- **Test Case Design: see tables**
  - **Quadratic Equation (Roots):** Input triple `<a, b, c>` where `$1 \leq a, b, c \leq 100$`. Design **boundary value** & **equivalence class** test cases.
  - **Previous/Next Date:** Input day, month, year. Day $1 \leq \text{day} \leq 31$; Month $1 \leq \text{month} \leq 12$; Year $1900 \leq \text{year} \leq 2025$. Design **equivalence class** & **robust** test cases.
  - **Student Grades:** Grading rules provided. Design **equivalence class** test cases.
  - **Largest Number:** Largest of three integers (`1 \leq n \leq 200`). Design **equivalence class** test cases.
  - Consider a program that accepts three positive integers (x, y, z) representing the sides of a triangle, where inputs are in the range. The output determines if the triangle is **Scalene, Isosceles, Equilateral, or Not a Triangle**. Design **Boundary Value Analysis (BVA)** test cases for this program.
**🆕 1. Quadratic Equation (Roots) - Range  Variant:**
- Consider a program for the determination of the nature of roots of a quadratic equation. Its input is a triple of positive integers (say `a`, `b`, `c`) and values may be from interval `[0, 50]`. The program output may have one of the following words:
  - Not a quadratic equation
  - Real roots
  - Imaginary roots
  - Equal roots
  
  Design **equivalence class** test cases.


**🆕 2. Next Date Program (Robust Testing):**
- Consider a program for determining the **next date** in a calendar. Its input is a triple of day, month, and year with the following range:
  - `1 ≤ month ≤ 12`
  - `1 ≤ day ≤ 31`
  - `1900 ≤ year ≤ 2025`
  
  The possible output would be **next date** or **invalid input date**. Design **robust** and **worst** test cases for this program.


**🆕 3. Largest Number - Extended (With Code, Decision Table & Cyclomatic Complexity):**
- Consider the following program for the selection of the largest of three numbers:

```c
void main()
{
    float a, b, c;
    printf("Enter three values\n");
    scanf("%f%f%f", &a, &b, &c);
    printf("\n Largest value is");
    if(a > b) {
        if(a > c)
            printf("%f\n", a);
        else
            printf("%f\n", c);
    }
    else {
        if(c > b)
            printf("%f\n", c);
        else
            printf("%f\n", b);
    }
}
```

**Tasks:**
1. Design test cases using **Equivalence class testing** technique
2. Design test cases using **Decision table testing** technique
3. Calculate McCabe's **cyclomatic complexity** for the above program


***

## **SECTION A: TABLE-BASED QUESTIONS FROM FIRST 12 PDFs**

### **1. COCOMO Calculation with Full Reference Tables**
**(Source: CO301-SE-2023-Mid-Sept.pdf)**

**Question:** Suppose a system for office automation is to be designed. It is clear from requirements that there will be five modules of size 0.5 KLOC, 1.5 KLOC, 2.0 KLOC, 1.0 KLOC, and 2.0 KLOC respectively. Complexity and reliability requirements are high. Programmer's capability and experience is low. All other factors are of nominal rating. Use COCOMO model to determine the overall cost and schedule estimated. Also calculate and schedule estimates for different phases.

**Table 1: Coefficients for Intermediate COCOMO**

| Project | $a_i$ | $b_i$ | $c_i$ | $d_i$ |
|---------|-------|-------|-------|-------|
| Organic | 3.2 | 1.05 | 2.5 | 0.38 |
| Semidetached | 3.0 | 1.12 | 2.5 | 0.35 |
| Embedded | 2.8 | 1.20 | 2.5 | 0.32 |

**Table 2: Multipliers of Different Cost Drivers**

| Cost Driver | Very Low | Low | Nominal | High | Very High | Extra High |
|---|---|---|---|---|---|---|
| **Product Attributes** | | | | | | |
| Software Reliability | 0.75 | 0.88 | 1.00 | 1.15 | 1.40 | -- |
| Database Size | -- | 0.94 | 1.00 | 1.08 | 1.16 | -- |
| Product Complexity | 0.70 | 0.85 | 1.00 | 1.15 | 1.30 | 1.65 |
| **Computer Attributes** | | | | | | |
| Execution Time Constraint | -- | -- | 1.00 | 1.11 | 1.30 | 1.66 |
| Main Storage Constraint | -- | -- | 1.00 | 1.06 | 1.21 | 1.56 |
| Virtual Machine Volatility | -- | 0.87 | 1.00 | 1.15 | 1.30 | -- |
| Turnaround Time | -- | 0.87 | 1.00 | 1.07 | 1.15 | -- |
| **Personnel Attributes** | | | | | | |
| Analyst Capability | 1.46 | 1.19 | 1.00 | 0.86 | 0.71 | -- |
| Application Experience | 1.29 | 1.13 | 1.00 | 0.91 | 0.82 | -- |
| Programmer Capability | 1.42 | 1.17 | 1.00 | 0.86 | 0.70 | -- |
| Virtual Machine Experience | 1.21 | 1.10 | 1.00 | 0.90 | -- | -- |
| Language Experience | 1.14 | 1.07 | 1.00 | 0.95 | -- | -- |
| **Project Attributes** | | | | | | |
| Modern Programming Practices | 1.24 | 1.10 | 1.00 | 0.91 | 0.82 | -- |
| Use of Software Tools | 1.24 | 1.10 | 1.00 | 0.91 | 0.83 | -- |
| Development Schedule | 1.23 | 1.08 | 1.00 | 1.04 | 1.10 | -- |

**Table 3: Lifecycle Phase Values of $\mu_p$ (Effort Distribution)**

| Plan & Requirements | System Design | Detailed Design | Module Code & Test | Integration & Test |
|---|---|---|---|---|
| 0.06 | 0.16 | 0.26 | 0.42 | 0.16 |

**Table 4: Lifecycle Phase Values of $\tau_p$ (Time Distribution)**

| Plan & Requirements | System Design | Detailed Design | Module Code & Test | Integration & Test |
|---|---|---|---|---|
| 0.10 | 0.19 | 0.24 | 0.39 | 0.18 |

***

### **2. Student Grading System (Test Case Design)**
**(Sources: CO301-SE-2022-End-Nov.pdf)**

**Question:** Let us consider an example of grading the students in an academic institution. The grading is done according to the following rules: Generate test cases using equivalence class testing technique.

| Marks Obtained | Grade |
|---|---|
| 80-100 | Distinction |
| 60-79 | First Division |
| 50-59 | Second Division |
| 40-49 | Third Division |
| 0-39 | Fail |

***

### **3. Function Point Calculation (Data Characteristics)**
**(Sources: CO301-SE-2022-End-Nov.pdf, IT304-SE-2019-Mid-March.pdf)**

**Question:** Compute the function point value for a project with the following information domain characteristics:

| Parameter | Project A | Project B |
|---|---|---|
| Number of user inputs | 30 | -- |
| Number of user outputs | 42 | -- |
| Number of user enquiries | 08 | -- |
| Number of files | 07 | -- |
| Number of external interfaces | 06 | -- |

Assume all complexity adjustment values are moderate.

***

### **4. COCOMO Coefficients (Project to develop Full Screen Editor)**
**(Source: CO301-SE-2018-End-Nov.pdf)**

**Question:** Consider a project to develop a full screen editor. The major components identified are: (i) Screen edit (ii) Command Language Interpreter (iii) File Input & Output (iv) Cursor Movement (v) Screen Movement. The size of these are estimated to be 4k, 2k, 1k, 2k and 3k delivered source code lines. Use COCOMO to determine the overall cost and schedule estimates.

**COCOMO Coefficients Table:**

| Project | $a$ | $b$ | $c$ | $d$ |
|---|---|---|---|---|
| Organic | 3.2 | 1.05 | 2.5 | 0.38 |
| Semidetached | 3.0 | 1.12 | 2.5 | 0.35 |
| Embedded | 2.8 | 1.20 | 2.5 | 0.32 |

*(Cost drivers provided: 1.15, 1.15, 0.86, 1.07 with rest nominal)*

***

### **5. Employee Data Center (ER Diagram Requirements)**
**(Source: CO412-SE-2005-Mid-MArch.pdf)**

**Question:** A data center involved in the design of software products has two types of employees; Technical and Administrative. The company maintains the following information:

| Attribute |
|---|
| Employee ID |
| Name |
| Address |
| Date-of-Birth |
| Date-of-Joining |
| Monthly-Salary |

*(Additional specifics: Technical staff → Data-entry operator, Programmer, System Analyst; Administrative staff categories provided)*

***

## **SECTION B: TABLE-BASED QUESTIONS FROM NEXT 12 PDFs**

### **6. COCOMO Calculation (200 KLOC Project)**
**(Source: SE301-SE-2019-End-Nov.pdf)**

**Question:** A program size of 200 KLOC is to be developed. Software development team has average experience on similar type of projects. The project schedule is not very tight. Calculate the effort, development time, average staff size and productivity.

**COCOMO Coefficients Table:**

| Project | $a_i$ | $b_i$ | $c_i$ | $d_i$ |
|---|---|---|---|---|
| Organic | 3.2 | 1.05 | 2.5 | 0.38 |
| Semidetached | 3.0 | 1.12 | 2.5 | 0.35 |
| Embedded | 2.8 | 1.20 | 2.5 | 0.32 |

***

### **7. COCOMO Calculation (400 KLOC Project)**
**(Source: CO301-SE-2020-End-Feb.pdf)**

**Question:** Suppose a project was estimated to be 400 KLOC. Calculate the effort and development time for each of the three models i.e., organic, semi-detached & embedded.

**COCOMO Coefficients Table:**

| Project | $a$ | $b$ | $c$ | $d$ |
|---|---|---|---|---|
| Organic | 3.2 | 1.05 | 2.5 | 0.38 |
| Semidetached | 3.0 | 1.12 | 2.5 | 0.35 |
| Embedded | 2.8 | 1.20 | 2.5 | 0.32 |

***

### **8. Function Point Calculation (Different Project)**
**(Source: IT304-SE-2019-Mid-March.pdf)**

**Question:** Compute the function point value for a project with the following information domain characteristics:

| Parameter | Value |
|---|---|
| Number of user inputs | 30 |
| Number of user outputs | 42 |
| Number of user enquiries | 08 |
| Number of files | 07 |
| Number of external interfaces | 6 |

Assume all complexity adjustment values are moderate.

***

### **9. Function Point Calculation (SE202-SE-2020-Mid-March.pdf)**

**Question:** Compute the function point value for a project with the following information domain characteristics:

| Parameter | Value |
|---|---|
| Number of user inputs | 24 |
| Number of user outputs | 65 |
| Number of user enquiries | 12 |
| Number of files | 12 |
| Number of external interfaces | 4 |

Assume all complexity adjustment values are moderate.

***

### **10. Quadratic Equation Test Case Design (Equivalence Class)**
**(Source: CO301-SE-2020-End-Feb.pdf)**

**Question:** Consider a program for the determination of the nature of roots of a quadratic equation. Its input is a triple of positive integer (say `a`, `b`, `c`) in the range `[1, 100]`. The program output may have one of the following:

| Output Type |
|---|
| Not a quadratic equation |
| Real roots |
| Imaginary roots |
| Equal roots |

Design equivalence class test cases.

***

### **11. Quadratic Equation Test Case Design (Boundary Value)**
**(Source: SE301-SE-2019-End-Nov.pdf)**

**Question:** Consider a program for the determination of the nature of roots of a quadratic equation. Its input is a triple of positive integers (say `a`, `b`, `c`) in the range `[1, 100]`. The program output may have one of the following:

| Output Type |
|---|
| Not a quadratic equation |
| Real roots |
| Imaginary roots |
| Equal roots |

Design boundary value test cases.

***

### **12. Previous Date Program (Equivalence Class)**
**(Source: CO301-SE-2018-End-Nov.pdf)**

**Question:** Consider a program for determining the previous date. Its input is a triple of `day`, `month`, `year` with the values in the range: Day `[1, 31]`, Month `[1, 12]`, Year `[1900, 2025]`.

The possible outputs would be previous date or invalid input date. Design the Equivalence class test cases.

***

### **13. Previous Date Program (Equivalence Class - Range Variant)**
**(Source: IT304-SE-2019-End-May.pdf)**

**Question:** Consider a program for determining the previous date. Its input is `<Day, Month, Year>` with ranges: Day `[1, 31]`, Month `[1, 12]`, Year `[1900, 2025]`.

The possible outcomes would be previous date or invalid date. Identify equivalence test cases for input and output domain.

***

### **14. Delhi Metro Automation System (DMAS) - Specifications Table**
**(Source: SE202-SE-2019-Mid-March.pdf)**

**Question:** The aim is to develop a Delhi Metro Automation System (DMAS). The DMAS has the following functions and constraints:

| Constraint Type | Details |
|---|---|
| Token/Smart Card Duration | 10 minutes from entry |
| Late Fine | Rs.50 (if exit after 120 minutes) |
| Smart Card Discount | 10% on all transactions |
| Refill Max Limit | Rs. 800 |
| Refill Min Limit | Rs. 50 |
| Refill Denomination | Multiples of Rs. 50 |
| Door Opening Time | 30 seconds (ideal conditions) |
| Door Obstruction Attempts | 3 times before full open |

Draw Context, Level-1 DFD, and Level-2 DFD (for purchase smart card process).

***

### **15. Control Flow Graph (Cyclomatic Complexity)**
**(Source: CO301-SE-2020-End-Feb.pdf)**

**Question:** Draw the control flow graph of the following code and also find the cyclomatic complexity:

```

Int A;
IF (A%2==0)
PRINT("No is Even");
ELSE
PRINT("No is Odd");
ENDIF

```

**Expected Output Table:**

| Metric | Value |
|---|---|
| Cyclomatic Complexity | ? |
| Number of Independent Paths | ? |

***

### **16. Triangle Validity (Halstead Metrics)**
**(Source: SE301-SE-2019-End-Nov.pdf)**

**Question:** Explain the Halstead theory of software metrics with the given function:

```

/*the function to check the validity of a triangle*/
int triangle (int a, int b, int c)
{
int valid;
if(((a+b)>c)\&\&((c+a)>b)\&\&((b+c)>a))
{
valid=1;
}
else
{
valid=0;
}
return valid;
}

```

**Expected Calculations:**

| Halstead Metric | Formula | Value |
|---|---|---|
| Unique Operators ($n_1$) | Count | ? |
| Unique Operands ($n_2$) | Count | ? |
| Total Operators ($N_1$) | Count | ? |
| Total Operands ($N_2$) | Count | ? |
| Program Length (N) | $N_1 + N_2$ | ? |
| Program Vocabulary (n) | $n_1 + n_2$ | ? |
| Volume (V) | $N \times \log_2(n)$ | ? |
| Difficulty (D) | $(n_1 / 2) \times (N_2 / n_2)$ | ? |
| Effort (E) | $D \times V$ | ? |
| Time (T) | $E / 18$ seconds | ? |

***

## **SUMMARY STATISTICS - TABLE-BASED QUESTIONS**

| Category | Count |
|---|---|
| COCOMO Coefficient Tables | 4 |
| Function Point Calculations (with data tables) | 4 |
| Test Case Design (with range/grade tables) | 5 |
| Halstead/Complexity Tables | 2 |
| System Specifications (DMAS, Editor, etc.) | 2 |
| **TOTAL TABLE-BASED QUESTIONS** | **17** |

***

## **12. Selected Optional Questions (Mapped to Syllabus)**
*These are high-value questions derived from previous years' papers and syllabus gaps. They are strictly aligned with Units 1, 4, 5, and 6.*

- **Agile & Project Management (Unit 1 & 4):**
  - Describe the **Extreme Programming (XP)** methodology. Explain key practices (Pair programming, TDD, CI), and how it differs from traditional waterfall.
  - Explain the **Scrum framework**. Describe the three roles (Owner, Master, Team), three artifacts (Backlogs, Increment), and ceremonies (Sprints, Standups).

- **Quality, Standards & Estimation (Unit 4):**
  - Explain the 5 Levels of the **SEI Capability Maturity Model (CMM)** in detail (Initial, Managed, Defined, Managed, Optimizing).
  - Differentiate between **ISO 9001** certification and **SEI CMM**. Why is CMM often considered better for software specifically?
  - Explain the **Risk Management** process (Risk Matrix: Probability × Impact; Strategies: Avoid, Mitigate, Accept, Transfer).
  - Explain **Three-Point Estimation (PERT)**. How do you calculate the Expected Value $E = \frac{(Optimistic + 4 \times MostLikely + Pessimistic)}{6}$?

- **Maintenance & Configuration Management (Unit 6):**
  - Explain **Configuration Management**. Discuss Configuration Items (CIs), CM Plan (CMP), and Activities (Identification, Control, Status Accounting, Audits).
  - Explain **Reverse Engineering** in the context of legacy systems. What are the techniques (Wrapping, Componentization) and Scope (Code → Design → Specification)?
  - Differentiate between **Adaptive** (environment changes) and **Perfective** (new requirements/enhancements) maintenance.

- **Calculation Practice Problems (Must Practice):**
  - **LOC-Based Estimation:** A project has 50,000 LOC and productivity of 300 LOC/pm. Calculate Effort ($50,000 / 300$), Staff needed for 12 months ($Effort / 12$), and Total Cost ($Staff \times Duration \times Salary$).
  - **Risk-Adjusted COCOMO:** Calculate effort for a 100 KLOC project given specific effort multipliers (e.g., Complexity 1.30) by multiplying standard COCOMO effort by the product of cost drivers.
  - **Test Case Design (Password):** Design **Equivalence Classes** (Valid vs. Invalid) for a password that must be 6-20 chars with 1 upper, 1 lower, and 1 digit.
  - **Test Case Design (Age Category):** Design **Boundary Value Analysis** cases for age categories: Child (0-12), Teen (13-19), Adult (20-60).

- **Low Priority / Check Syllabus (Unit 1 & 3 Gaps):**
  - *(Verify if taught in class)* Explain the **V-Model** and how testing phases map to development phases.
  - *(Verify if taught in class)* Explain the **Singleton** and **Factory** design patterns with examples.
  - *(Verify if taught in class)* Compare **Monolithic** vs. **Microservices** architecture.

---
The most frequently asked topics, categorized by their weight and recurrence :-

### **🔥 High Priority (Most Repeated Topics)**
*These topics appear in almost every section or have multiple distinct questions dedicated to them. You must master these for the exam.*

1.  **COCOMO Model (Cost Estimation):**
    *   **Why:** It appears in theory (levels, cost drivers) and heavy calculation problems (Organic/Semi-detached/Embedded modes, effort multipliers).
    *   **Key types:** Calculating Effort/Time, explaining the 3 modes, and Intermediate COCOMO coefficients.
2.  **Software Process Models (Spiral & Prototyping):**
    *   **Why:** The **Spiral Model** is the single most asked process model (meta-model, risk handling, advantages). **Prototyping** is a close second, often compared with Evolutionary models.
3.  **Testing Strategies (Black Box vs. White Box):**
    *   **Why:** There are theoretical questions (differences, definitions) and practical design questions (Equivalence Class Partitioning, Boundary Value Analysis, Cyclomatic Complexity).
4.  **Requirements Engineering (SRS & Elicitation):**
    *   **Why:** Heavy focus on what makes a "good" SRS, Functional vs. Non-Functional requirements, and elicitation techniques like FAST and Use Cases.
5.  **Coupling and Cohesion:**
    *   **Why:** Multiple questions ask for definitions, types (best/worst), and the relationship between them (High Cohesion/Low Coupling).

***

### **⚠️ Medium Priority (Frequent Topics)**
*These topics are very likely to appear as 5 or 10-marker questions.*

1.  **Data Flow Diagrams (DFD) & ER Diagrams:**
    *   **Why:** There is a dedicated "Drawing Tasks" section where you are asked to draw DFDs (Level 0, 1, 2) for specific systems like Metro, Hotel, or Library management.
2.  **Function Point Analysis:**
    *   **Why:** Appears in both theory (what is it, why use it) and calculation tables (computing FP based on inputs/outputs).
3.  **Software Maintenance:**
    *   **Why:** Specific focus on the types of maintenance (Corrective, Perfective, etc.) and Reverse Engineering.
4.  **CMM vs. ISO 9001:**
    *   **Why:** Repeated comparison questions. You need to know the CMM levels (KPAs) and how they differ from ISO certification.
5.  **UML Diagrams:**
    *   **Why:** Focus on Class, Sequence, and Use Case diagrams.

***

### **Topic Frequency Breakdown**

| Topic Category | Frequency | Key Focus Areas |
| :--- | :--- | :--- |
| **Estimation & Metrics** | **Very High** | COCOMO calculations, Function Points, Halstead Metrics. |
| **Process Models** | **High** | Spiral Model (Risk), Prototyping, Waterfall limitations. |
| **Testing** | **High** | Boundary Value, Equivalence Class, Cyclomatic Complexity paths. |
| **Design Concepts** | **Medium** | Coupling vs. Cohesion, Modularity. |
| **Diagramming** | **Medium** | DFD Level 0-2, ER Diagrams, Use Cases. |
| **Quality** | **Low-Medium** | CMM Levels, ISO 9000/9001 comparisons. |

### **Study Strategy Recommendation**
1.  **Start with Calculations:** Master the **COCOMO** and **Function Point** formulas. These are "free marks" if you know the formula, as the tables are often provided.
2.  **Diagram Practice:** Practice drawing a **DFD Level 1** and a **Use Case Diagram** for a generic system (like a Library or ATM), as this pattern repeats.

3.  **Theory Memorization:** Memorize the **Spiral Model** phases and the **Types of Cohesion/Coupling** (from worst to best).


