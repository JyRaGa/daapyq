
# **Software Engineering Question Bank**
## **(Compiled from 30 Papers)**

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
        
- **Software Engineering Definition:**
  - Define the term Software Engineering.
  - What is Software Engineering? Discuss its objectives and scope.

- **CASE Tools (Extended):**
  - Draw a general architecture of a CASE environment. Explain its important characteristics.
  - What is the difference between **upper CASE** and **lower CASE** tools?
  - List at least 2 commercial CASE tools supporting different stages of the software life cycle.

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

- **Problems in Requirements:**
  - Explain the problems in the formulation of requirements for any software project.
  - Discuss the challenges in requirements gathering and specification.
  - Why is requirements formulation considered one of the most challenging phases?

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
    
- **Design Approaches (Comparison):**
  - List the similarities and dissimilarities between structured analysis and object-oriented requirements analysis techniques.
  - Compare structured design vs object-oriented design approaches.


- **Data Modeling & Rules:**
  - What is the use of Data Dictionaries? Explain with example.
  - Describe the contents and model of a data dictionary.
  - What is the role of **Data Dictionary**?
  - What is the purpose of a Data Flow Diagram (DFD)? Distinguish it from a flowchart.
  - What rules should be observed while drawing a **DFD** (Data Flow Diagram)? What constraints must be observed while creating a leveled DFD?
  - What are the logical constraints while drawing an **ERD** (Entity Relationship Diagram)?
    
- **ER Diagrams (Extended):**
  - What is the **degree of a relationship**? Give an example of each relationship degree (Unary, Binary, Ternary).

- **Design Reuse:**
  - Why are **design patterns** an effective form of design reuse? What are the disadvantages to this approach?

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
    
 - **Purpose of Modeling:**
   
  - What are some of the reasons for creating models during system development?
  - Why is modeling considered essential in software engineering?
  - Discuss the benefits of visual modeling in requirements and design phases.


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
- **Text Book Inventory System:**
  
  **Requirements:**
     The purpose of Text Book Inventory system at a campus bookstore is to supply textbooks to students for classes at a local university. The university's academic department supplies initial data about courses, instructors, textbooks and projected enrollment to the bookstore on a Text Book Master List. The bookstore generates a Form No. 11 purchase order, which is sent to publishing companies supplying textbooks. Book orders arrive at the bookstore accompanied by a packing slip which is checked and verified by the receiving department. Students fill out a Books Request form that includes course information when they pay for their books. The students are given a cash register Sale Receipt.
  
  **Draw:** 
  - (i) ER diagram
  - (ii) Context diagram
  - (iii) Level-1 DFD

- **WEB EDIT System (Web Page Maker):**
  
  **Requirements:**
  WEB EDIT is a web page maker that allows any user who has a connection to the Internet and a web browser to use it to create a nice and simple web page. Users design and create a page by filling in some information. Newly created pages can be saved on a server. This allows a user to preview a designed page after creating it and before saving it on the web. In case they are dissatisfied with its design, the user can delete the web page at a later stage. The user can also upload the page at any time.
  
  **Draw:**
  - (i) Use case diagram
  - (ii) Class diagram

- **Shipping Department Purchase Order System:**
  
  **Requirements:**
  The shipping department receives all shipments on outstanding purchase orders. When the clerk in the shipping department receives a shipment, they find the outstanding purchase order for those items. The clerk then sends multiple copies of the shipment packing slip: One copy goes to purchasing (updates records to indicate purchase order fulfilled), another copy goes to accounting (so payment can be made), and a third copy goes to the requesting in-house customer (so they can receive the shipment). Once payment is made, the accounting department sends a notification to purchasing. Once the customer receives and accepts the goods, they send notification to purchasing. When purchasing receives these verifications, it closes the purchase order as filled and paid.
  
  **Draw:**
  - (i) Use case diagram
  - (ii) Activity diagram

- **Hospital Room Scheduling System (IHS):**
  
  **Requirements:**
  The International Hospital Service (IHS) is building a new scheduling system to help track occupancy of beds and rooms in a hospital. A hospital room is either occupied or vacant. However, scheduling a room is more complicated. A room can be scheduled or unscheduled independently of whether it is occupied or not. When a room is vacant, it becomes occupied when a patient is assigned to the room. If the patient is admitted as an emergency (unscheduled), then nothing else needs to happen. However, if admittance is a scheduled arrival, the room scheduling system must note that fact and update the schedule to show it as being fulfilled. Immediately after a room is vacated, it goes into a temporary state of "dirty." That simply means it should be cleaned before another patient can be moved in, so even though it is in reality vacant, it is not considered vacant until it has been cleaned.
  
  **Draw:** State chart diagram showing all states and transitions

- **University Registration System (URS) - Detailed:**
  
  **Requirements:**
  A university is organized in different teaching schools and each school conducts a variety of programmes. Students are registered in various schools manually based on admission slips. Students are assigned courses depending upon the scheme of the selected programme. Every school is responsible for its registration process. The system maintains:
  - List of students registered in a programme
  - List of students registered for a particular course
  - List of courses offered in a particular semester
  - List of faculty in a school
  - Personal details of the students
  - Registration card for every registered student
  
  **The proposed URS system should:**
  - Maintain the personal details of the students
  - Maintain the details of the faculty
  - Maintain the detail of various courses as per the scheme of the programme
  - Issue of registration card to the student in every semester
  - Generate list of programmes offered by university
  - Generate list of courses offered in a particular semester for a particular programme
  
  **Draw:**
  - (i) Context level diagram
  - (ii) Level-1 DFD for URS
  - (iii) Level-2 DFD for "maintain students details" process

- **Automated Book Management System (ABMS):**
  
  **Requirements:**
  DTU engineers team has launched an "Automated Book Management System" (ABMS) which aims to provide any course or extra books on demand by students on rental basis. Students are provided with their account ID to login and can search for the respected book they need. Books are managed in the warehouse by a manager and are collected in the store by vendor. Every student on renting a book will be provided an invoice which will act as a token for submitting the book further. New students or users are mandatory to login with 6 month subscription. Student accounts are linked with the ERP of college (to maintain integrity). If any user doesn't return the book on time, an alert on ERP will be notified and late charges will be applied on return. Money collected will be used by the team members for college fest preparations and charity in future. The purpose is to provide large collection of respectable course books and not to challenge library management.
  
  **Draw:**
  - (i) ER diagram
  - (ii) DFD-0 level

- **Open-Ended DFD Exercise:**
  - Choose a transaction that you are likely to encounter (perhaps ordering a suit for graduation), and develop a high-level DFD. Decompose this to a level-0 diagram.

- **Library System (Books, Videos, CDs):**
  
  **Requirements:**
  Consider the world of libraries. A library has books, videos, and CDs that it loans to its users. All library material has an id# and a title. In addition:
  - **Books** have one or more authors
  - **Videos** have one producer and one or more actors
  - **CDs** have one or more entertainers
  
  The library maintains one or more copies of each library item (book, video or CD). Copies of all library material can be loaned to users:
  - **Reference-only material:** Loaned for 2 hours and can't be removed from the library
  - **Other material:** Can be loaned for 2 weeks
  
  For every loan, the library records:
  - User information
  - Loan date and time
  - Return date and time
  
  For users, the library maintains:
  - Name
  - Address
  - Phone number
  
  **Draw:**
  - Class diagram with attributes, multiplicities, and aggregations/compositions
  - DFD (Level 0 and Level 1)

- **Online Food Delivery System (Zomato/Swiggy-style):**

  **System Description:**
  An online food delivery system connects customers with restaurants. The system involves the following entities and processes:
  
  **Entities:**
  1. **Customer** - Places orders, makes payments
  2. **Restaurant** - Receives orders, prepares food
  3. **Delivery Person** - Picks up and delivers orders
  4. **Payment Gateway** - Processes payments
  5. **Admin** - Manages system, monitors operations
  6. **System** - Coordinates all activities
  
  **Key Processes:**
  - Customer browses menu, selects items, places order
  - System forwards order to restaurant
  - Restaurant confirms and prepares order
  - System assigns delivery person
  - Delivery person picks up from restaurant
  - Delivery person delivers to customer
  - Customer makes payment (online/cash)
  - System updates order status throughout
  
  **Requirements:**
  - Customer can track order in real-time
  - Multiple payment options (card, wallet, cash)
  - Restaurant can accept/reject orders
  - Delivery person can update location
  - Admin can monitor all transactions
  
  **Draw:**
  1. **Activity Diagram** - Complete order flow from browsing to delivery
  2. **Sequence Diagram** - Interaction between Customer, System, Restaurant, Delivery Person
  3. **Collaboration Diagram** - Same interactions with numbered messages
  4. **Class Diagram** - All 6 entities with attributes, methods, relationships
  5. **State Chart Diagram** - Order states (Placed → Confirmed → Preparing → Ready → Picked Up → Delivered → Completed)
  
  **[10 Marks - CS209 Nov 2024]**
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
  - 
- **Testing Philosophy:**
  - What are the objectives of testing? Explain why testing can only detect the presence of errors, not their absence.
  - Discuss the fundamental principle: "Testing shows the presence of defects, not their absence."

- **Level of Testing:**
  - Write a short note on **Level of Testing** including:
    * Unit Testing
    * Integration Testing
    * System Testing
    * Acceptance Testing
  - Explain each level with its objectives and who performs it.
   
- **What is Data Flow Testing? Explain the different techniques of data flow testing.**

  **Data Flow Testing** is a white-box testing technique that focuses on the **flow of data** through a program. It examines the definition and use of variables throughout the program execution.
  
  **Key Concepts:**
  
  1. **DEF (Definition):** A statement where a variable is defined or assigned a value
     - Example: `x = 10;` or `read(y);`
  
  2. **USE:** A statement where a variable's value is used
     - **C-use (Computational use):** Variable used in computation
       - Example: `z = x + y;`
     - **P-use (Predicate use):** Variable used in condition/decision
       - Example: `if (x > 0)`
  
  3. **DU-pair (Definition-Use pair):** A pair consisting of:
     - A definition of variable at location i
     - A use of same variable at location j
     - A path from i to j with no other definition
  
  **Data Flow Testing Techniques:**
  
  1. **All-defs Coverage:**
     - For each variable definition, test at least ONE path to at least ONE use
     - Ensures every definition reaches some use
     - **Weakest** data flow criterion
  
  2. **All-uses Coverage:**
     - For each variable definition, test paths to ALL uses (both C-uses and P-uses)
     - Ensures every definition reaches every possible use
     - **Moderate** coverage
  
  3. **All-du-paths Coverage:**
     - Test ALL possible paths from each definition to each use
     - Includes all loop variations and branches
     - **Strongest** data flow criterion
     - Most thorough but most expensive
  
  **Example:**
  ```
  1. read(x);          // DEF of x
  2. y = x + 10;       // USE of x (C-use), DEF of y
  3. if (y > 20)       // USE of y (P-use)
  4.    z = y * 2;     // USE of y (C-use), DEF of z
  5. else
  6.    z = y / 2;     // USE of y (C-use), DEF of z
  7. print(z);         // USE of z (C-use)
  ```
  
  **DU-pairs:**
  - (x, 1, 2) - definition at line 1, use at line 2
  - (y, 2, 3) - definition at line 2, use at line 3
  - (y, 2, 4) - definition at line 2, use at line 4
  - (y, 2, 6) - definition at line 2, use at line 6
  - (z, 4, 7) - definition at line 4, use at line 7
  - (z, 6, 7) - definition at line 6, use at line 7
  
  **Advantages:**
  - Detects unused variables
  - Finds uninitialized variable uses
  - Identifies unreachable code
  - More thorough than statement/branch coverage
  
  **[5 Marks - CS209 Nov 2024]**
  
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
    
- **COTS and System Integration:**
  - What are **COTS** (Commercial Off-The-Shelf) products?
  - Explain why **adaptors** are usually needed when systems are constructed using COTS products.
  - Discuss the advantages and challenges of using COTS in software development.

- **Legacy Systems (Extended):**
  - What are legacy systems? What is the need of software reengineering?
  - Explain the challenges in maintaining legacy systems and strategies to handle them.

- **Professional Course Admission - Decision Table Testing:**

  **Problem Statement:**
  A student can get admission into a professional course based on the following criteria:
  
  **Admission Criteria:**
  - Student must have Physics AND Chemistry as subjects
  - Student must have Mathematics OR Computer Science
  - Student marks must be greater than 60% to get admission in Honours course
  - Student marks must be greater than 50% to get admission in Pass course
  
  **Tasks:**
  1. Draw the complete decision table for this admission system
  2. Design test cases based on the decision table
  3. Identify all possible outcomes (Honours admission, Pass admission, Rejection)
  
  **Decision Table Structure:**
  
  | Condition | R1 | R2 | R3 | R4 | R5 | R6 | R7 | R8 |
  |-----------|----|----|----|----|----|----|----|----|
  | Has Physics? | Y | Y | Y | Y | Y | Y | N | N |
  | Has Chemistry? | Y | Y | Y | Y | N | N | - | - |
  | Has Math OR CS? | Y | Y | N | N | - | - | - | - |
  | Marks > 60%? | Y | N | - | - | - | - | - | - |
  | Marks > 50%? | - | Y | - | - | - | - | - | - |
  | **Action** | | | | | | | | |
  | Admit to Honours | X | | | | | | | |
  | Admit to Pass | | X | | | | | | |
  | Reject | | | X | X | X | X | X | X |
  
  **Test Cases:**
  
  | TC# | Physics | Chemistry | Math/CS | Marks | Expected Result |
  |-----|---------|-----------|---------|-------|-----------------|
  | TC1 | Yes | Yes | Math | 65% | Honours Admission |
  | TC2 | Yes | Yes | CS | 55% | Pass Admission |
  | TC3 | Yes | Yes | Math | 45% | Rejected |
  | TC4 | Yes | Yes | None | 70% | Rejected |
  | TC5 | Yes | No | Math | 65% | Rejected |
  | TC6 | No | Yes | Math | 65% | Rejected |
  | TC7 | No | No | None | 40% | Rejected |
  | TC8 | Yes | Yes | Both | 62% | Honours Admission |
  
  **Key Points:**
  - Physics AND Chemistry are **mandatory**
  - Math OR CS means **at least one** must be present
  - Marks threshold determines Honours vs Pass
  - If basic subjects missing, marks don't matter
  
  **[5 Marks - CS209 Nov 2024]**
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

- **ISO 9126 Quality Model:**
  - What is **SQA** (Software Quality Assurance)? Discuss the **ISO 9126 quality model**.
  - Explain the six quality characteristics of ISO 9126:
    * **Functionality** (Suitability, Accuracy, Interoperability, Security)
    * **Reliability** (Maturity, Fault tolerance, Recoverability)
    * **Usability** (Understandability, Learnability, Operability)
    * **Efficiency** (Time behavior, Resource utilization)
    * **Maintainability** (Analyzability, Changeability, Stability, Testability)
    * **Portability** (Adaptability, Installability, Conformance, Replaceability)
  - Differentiate between ISO 9001 (process quality) and ISO 9126 (product quality).

- **Quality Views:**
  - How is **Gravin's view** of quality different from **Alan's view**?
  - What do you understand by software quality? Discuss different perspectives of viewing quality.

- **Design Quality:**
  - What are the characteristics of a good design?
  - Discuss design quality attributes and their importance in software development.


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

- **Measurement Types:**
  - Differentiate between **direct measurement** and **indirect measurement** in software metrics.
  - Give examples of each type of measurement.

- **Software Reliability:**
  - What is **software reliability**? How is it measured?
  - Describe the **Jelinski-Moranda model** of software reliability.
  - Explain the concept of failure intensity and failure intensity decay parameter.
  - What is the **Logarithmic Poisson execution time model** of software reliability?

- **Project Planning:**
  - Explain the steps involved in project planning.
  - Discuss the various factors that affect a project plan.
  - How does project planning differ from project scheduling?

- **Metrics Application:**
  - Why do we need metrics in software?
  - Discuss the areas of applications of software metrics.
  - State the advantages and disadvantages of using LOC as a metric. (Give 2 reasons for each)


- **CMM-ISO 9001 Correlation Table:**

  **Mapping between CMM Key Process Areas (KPAs) and ISO 9000/9001 Clauses:**
  
  | CMM Level | CMM Key Process Area (KPA) | ISO 9001 Clause | ISO 9001 Requirement |
  |-----------|----------------------------|-----------------|----------------------|
  | **Level 2** | Requirements Management | 4.3 | Contract Review |
  | | Software Project Planning | 4.9 | Process Control |
  | | Software Project Tracking | 4.9, 4.1.3 | Process Control, Management Review |
  | | Software Quality Assurance | 4.1, 4.16, 4.17 | Quality System, Quality Records, Internal Audits |
  | | Software Configuration Management | 4.5, 4.8, 4.12 | Document Control, Product ID, Inspection Status |
  | | Software Subcontract Management | 4.6 | Purchasing |
  | **Level 3** | Organization Process Focus | 4.1.1, 4.1.2 | Management Responsibility |
  | | Organization Process Definition | 4.2, 4.9 | Quality System, Process Control |
  | | Training Program | 4.18 | Training |
  | | Integrated Software Management | 4.1, 4.2 | Management Responsibility, Quality System |
  | | Software Product Engineering | 4.4, 4.9 | Design Control, Process Control |
  | | Intergroup Coordination | 4.1.2.3 | Management Representative |
  | | Peer Reviews | 4.13 | Inspection and Testing |
  | **Level 4** | Quantitative Process Management | 4.9, 4.20 | Process Control, Statistical Techniques |
  | | Software Quality Management | 4.1, 4.14 | Quality System, Corrective Action |
  | **Level 5** | Defect Prevention | 4.14 | Corrective and Preventive Action |
  | | Technology Change Management | 4.2.3 | Quality Planning |
  | | Process Change Management | 4.1.3 | Management Review |
  
  **Key Correlations:**
  
  1. **Both focus on process:**
     - CMM: Process maturity levels
     - ISO 9001: Process-based quality system
  
  2. **Documentation emphasis:**
     - CMM: Documented procedures at Level 2+
     - ISO 9001: Clause 4.2 (Quality System documentation)
  
  3. **Continuous improvement:**
     - CMM: Level 5 (Optimizing)
     - ISO 9001: Clause 4.1 (Management commitment to improvement)
  
  4. **Management responsibility:**
     - CMM: Senior management commitment throughout
     - ISO 9001: Clause 4.1 (Management Responsibility)
  
  5. **Training requirements:**
     - CMM: Training Program (Level 3 KPA)
     - ISO 9001: Clause 4.18 (Training)
  
  **Differences:**
  - CMM: Software-specific, staged maturity
  - ISO 9001: Generic quality, certification-based
  - CMM: 5 levels of progression
  - ISO 9001: Pass/fail certification
  
  **[3 Marks - CS209 Nov 2024]**


    

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


- **Function Point Calculation (New Variant):**
  - Compute the function point value for a project with the following information domain characteristics:
    * Number of user inputs = 30
    * Number of user outputs = 25
    * Number of user enquiries = 10
    * Number of files = 06
    * Number of external interfaces = 4
    
    Assume that all complexity adjustment factors are average.

- **Software Reliability Calculations:**
  - Assume that the initial failure intensity is 20 failures/CPU hr. The failure intensity decay parameter is 0.02/failure. We have experienced 100 failures up to this time.
    
    Calculate:
    * (i) Determine the current failure intensity
    * (ii) Find the decrement of failure intensity per failure
    * (iii) Calculate the failures experienced and failure intensity after 20 and 100 CPU hrs. of execution
    * (iv) Compute additional failures and additional execution time required to reach the failure intensity objective of 2 failures/CPU hr.
    
    Use **Logarithmic Poisson execution time model** of software reliability for the calculations.

- **Halstead Metrics (New Code Variants):**

**Code 1: Euclid GCD Algorithm**
```
euclid (int m, int n) {
    int r;
    if (n > m) {
        r = m % n;
        while(r != 0) {
            m = n;
            n = r;
            r = m % n;
        }
    }
    return n;
}
```
Find Halstead's software science metrics and cyclomatic complexity.

**Code 2: Student Marks Averaging Program**
```
main() {
    int num_students, marks, subjects, total;
    float average;
    num_student = 1;
    while (num_student <= 25) {
        total = 0;
        subject = 1;
        while (subject <= 5) {
            scanf("%d", &marks);
            total = total + marks;
            subject++;
        }
        average = total / 5;
        if (average < 50)
            printf("Fail");
        else
            printf("\n pass..Average marks are %f\n", average);
        num_student++;
    }
    printf("End of program");
}
```
Tasks:
- (i) Draw flow graph for above code
- (ii) Compute cyclomatic complexity
- (iii) Identify all independent paths

**Code 3: GCD Program (Alternate Variant)**
```
/* program to calculate GCD of 2 numbers */
int compute_gcd (x, y)
int x, y;
{
    while (x != y)
        if (x > y) then x = x - y;
        else y = y - x;
    return x;
}
```
Estimate the Halstead's length and volume measures and compare them with LOC measures.

- **Critical Path Method (Network Diagram):**
  - Identify the critical activities and critical path for the problem given below:
  
  *(Include network diagram with activities a, b, c, d, e, f, g, h, k with durations: Start→a(8)→b(8)→g(8)→e(15)→Finish; a→d(12)→h(10)→Finish; d→f(10)→k(12)→Finish; etc.)*
  
  Calculate:
  - Earliest start time (EST) and Latest start time (LST) for each activity
  - Critical path
  - Total project duration

- **Control Flow Graph (Simple Code Variant):**

Draw the control flow graph of the following code and find the cyclomatic complexity:

```
1. A=10
2. IF B>C THEN
3.    A=B
4. ELSE
5.    A=C
6. ENDIF
7. PRINT A
8. PRINT B
9. PRINT C
```

Tasks:
- Draw control flow graph
- Calculate cyclomatic complexity
- Identify independent paths

- **Halstead Metrics - Array Sorting Function:**

  Calculate all Halstead metrics for the following array sorting code, given Stroud number = 18:
  
  ```
  void sort(int arr[], int n) {
      int i, j, temp;
      for (i = 0; i < n-1; i++) {
          for (j = 0; j < n-i-1; j++) {
              if (arr[j] > arr[j+1]) {
                  temp = arr[j];
                  arr[j] = arr[j+1];
                  arr[j+1] = temp;
              }
          }
      }
  }
  ```
  
  **Step 1: Identify Operators and Operands**
  
  **Unique Operators (n1):**
  1. `void` (return type)
  2. `()` (function call/parameter)
  3. `[]` (array subscript)
  4. `,` (comma separator)
  5. `int` (type declaration)
  6. `=` (assignment)
  7. `for` (loop)
  8. `<` (less than)
  9. `-` (subtraction)
  10. `++` (increment)
  11. `if` (conditional)
  12. `>` (greater than)
  13. `+` (addition)
  14. `;` (statement terminator)
  15. `{}` (block delimiters)
  
  **n1 = 15**
  
  **Unique Operands (n2):**
  1. `sort` (function name)
  2. `arr` (array parameter)
  3. `n` (size parameter)
  4. `i` (loop variable)
  5. `j` (loop variable)
  6. `temp` (temporary variable)
  7. `0` (constant)
  8. `1` (constant)
  
  **n2 = 8**
  
  **Total Operator Occurrences (N1):**
  - Count all operator appearances: **N1 = 52**
  
  **Total Operand Occurrences (N2):**
  - Count all operand appearances: **N2 = 36**
  
  **Step 2: Calculate Halstead Metrics**
  
  1. **Program Vocabulary:** n = n1 + n2 = 15 + 8 = **23**
  
  2. **Program Length:** N = N1 + N2 = 52 + 36 = **88**
  
  3. **Calculated Length:** N̂ = n1 × log₂(n1) + n2 × log₂(n2)
     - N̂ = 15 × log₂(15) + 8 × log₂(8)
     - N̂ = 15 × 3.907 + 8 × 3.0
     - N̂ = 58.605 + 24.0 = **82.605**
  
  4. **Volume:** V = N × log₂(n)
     - V = 88 × log₂(23)
     - V = 88 × 4.524 = **398.11 bits**
  
  5. **Difficulty:** D = (n1/2) × (N2/n2)
     - D = (15/2) × (36/8)
     - D = 7.5 × 4.5 = **33.75**
  
  6. **Effort:** E = D × V
     - E = 33.75 × 398.11 = **13,436.21 elementary mental discriminations**
  
  7. **Time to Program:** T = E / S (where S = Stroud number = 18)
     - T = 13,436.21 / 18 = **746.46 seconds**
     - T = **12.44 minutes**
  
  8. **Delivered Bugs:** B = V / 3000
     - B = 398.11 / 3000 = **0.133 bugs**
  
  **Summary:**
  - Volume: 398.11 bits
  - Difficulty: 33.75
  - Effort: 13,436.21
  - Time: 12.44 minutes
  - Expected Bugs: 0.133
  
  **[5 Marks - CS209 Nov 2024]**

---

- **Quadratic Equation [0, 100] - Worst Case Testing:**

  **Problem:** For a program that takes three integers (a, b, c) in the range [0, 100] and solves the quadratic equation ax² + bx + c = 0, design test cases using **Worst Case Testing** technique.
  
  **Worst Case Testing:**
  - Tests **all combinations** of extreme values
  - More exhaustive than Boundary Value Analysis
  - For n variables with 5 values each: 5ⁿ test cases
  
  **Test Values for each variable:**
  - **Minimum:** 0
  - **Just above minimum:** 1
  - **Nominal:** 50
  - **Just below maximum:** 99
  - **Maximum:** 100
  
  **Worst Case Test Cases (5³ = 125 test cases total):**
  
  Sample of key test cases:
  
  | TC# | a | b | c | Expected Result |
  |-----|---|---|---|-----------------|
  | TC1 | 0 | 0 | 0 | Not a quadratic equation |
  | TC2 | 0 | 0 | 1 | No solution |
  | TC3 | 0 | 0 | 50 | No solution |
  | TC4 | 0 | 0 | 99 | No solution |
  | TC5 | 0 | 0 | 100 | No solution |
  | TC6 | 0 | 1 | 0 | Linear: x = 0 |
  | TC7 | 0 | 1 | 1 | Linear: x = -1 |
  | ... | ... | ... | ... | ... |
  | TC21 | 1 | 0 | 0 | x = 0 (repeated) |
  | TC22 | 1 | 0 | 1 | Complex roots |
  | TC23 | 1 | 0 | 50 | Complex roots |
  | ... | ... | ... | ... | ... |
  | TC61 | 50 | 50 | 50 | Real/complex roots |
  | ... | ... | ... | ... | ... |
  | TC121 | 100 | 99 | 99 | Real roots |
  | TC122 | 100 | 99 | 100 | Real roots |
  | TC123 | 100 | 100 | 0 | Real roots |
  | TC124 | 100 | 100 | 99 | Real roots |
  | TC125 | 100 | 100 | 100 | Real roots |
  
  **Complete Combination Matrix:**
  - **First variable (a):** 0, 1, 50, 99, 100 (5 values)
  - **Second variable (b):** 0, 1, 50, 99, 100 (5 values)
  - **Third variable (c):** 0, 1, 50, 99, 100 (5 values)
  - **Total:** 5 × 5 × 5 = **125 test cases**
  
  **Categories to Cover:**
  1. a = 0 (not quadratic) → 25 test cases
  2. a ≠ 0, discriminant > 0 (real distinct roots) → test cases
  3. a ≠ 0, discriminant = 0 (real equal roots) → test cases
  4. a ≠ 0, discriminant < 0 (complex roots) → test cases
  
  **Note:** Worst case testing is exhaustive and may be impractical for large domains, but ensures maximum coverage.
  
  **[3 Marks - CS209 Nov 2024]**

---

- **Software Maintenance Calculation (Belady-Lehman Model):**

  **Problem:** An application developed for an insurance company has been in production for several years. During this period, many changes have been made, and 800 person-months (PM) of effort have been invested in maintenance. Using the Belady-Lehman maintenance model with K = 0.4 and initial complexity = 8, calculate:
  
  1. Current complexity of the system
  2. Total change in complexity
  3. Average complexity increase per maintenance cycle
  
  **Belady-Lehman Maintenance Model:**
  
  The model states that software complexity increases over time due to maintenance:
  
  **Formula:**
  \[ C(t) = C_0 + K \times E \]
  
  Where:
  - \( C(t) \) = Complexity after maintenance
  - \( C_0 \) = Initial complexity
  - \( K \) = Complexity growth constant
  - \( E \) = Maintenance effort (in person-months)
  
  **Given:**
  - Initial complexity \( C_0 = 8 \)
  - Maintenance effort \( E = 800 \) PM
  - Complexity constant \( K = 0.4 \)
  
  **Solution:**
  
  **1. Current Complexity:**
  \[ C(t) = C_0 + K \times E \]
  \[ C(t) = 8 + (0.4 \times 800) \]
  \[ C(t) = 8 + 320 \]
  \[ C(t) = 328 \]
  
  **Answer:** Current complexity = **328**
  
  **2. Total Change in Complexity:**
  \[ \Delta C = C(t) - C_0 \]
  \[ \Delta C = 328 - 8 \]
  \[ \Delta C = 320 \]
  
  **Answer:** Total complexity increase = **320**
  
  **3. Average Complexity Increase per PM:**
  \[ \text{Average increase} = \frac{\Delta C}{E} \]
  \[ \text{Average increase} = \frac{320}{800} \]
  \[ \text{Average increase} = 0.4 \]
  
  **Answer:** Average complexity increase = **0.4 per person-month**
  
  **Interpretation:**
  - System complexity has grown from 8 to 328 (41× increase!)
  - For every person-month spent on maintenance, complexity increased by 0.4 units
  - High K value (0.4) indicates rapid complexity growth
  - This suggests need for re-engineering or refactoring
  
  **Belady-Lehman Laws of Evolution:**
  1. **Continuing Change:** System must adapt or become less useful
  2. **Increasing Complexity:** Complexity increases unless work is done to reduce it
  3. **Self-Regulation:** Evolution process is self-regulating
  4. **Conservation of Organizational Stability:** Average activity rate remains constant
  5. **Conservation of Familiarity:** Incremental growth remains constant
  
  **[5 Marks - CS209 Nov 2024]**

***

---

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

- **Future Challenges:**
  - Identify three major challenges that software engineering is likely to face in the next 10 years.
  - Explain how the universal use of the Web has changed software systems.
  - Discuss emerging trends like AI/ML integration, cloud-native development, etc.

- **Boehm's Maintenance Model:**

  **Boehm's Maintenance Model** categorizes software maintenance activities and provides a framework for understanding maintenance effort distribution.
  
  **Maintenance Categories (Boehm's Classification):**
  
  1. **Adaptive Maintenance (18-25%)**
     - Changes to adapt software to new environments
     - Examples:
       - Migrating to new OS
       - Database version upgrades
       - Hardware platform changes
       - Compliance with new regulations
  
  2. **Perfective Maintenance (50-60%)**
     - Enhancements to improve performance or maintainability
     - Examples:
       - Adding new features per user requests
       - Improving efficiency/performance
       - Enhancing user interface
       - Code restructuring for better maintainability
     - **Largest category** of maintenance effort
  
  3. **Corrective Maintenance (17-21%)**
     - Fixing defects discovered after release
     - Examples:
       - Bug fixes
       - Logic errors
       - Design flaws
       - Coding mistakes
  
  4. **Preventive Maintenance (2-4%)**
     - Changes to prevent future problems
     - Examples:
       - Code refactoring
       - Documentation updates
       - Optimization to prevent performance degradation
       - Security patches before exploitation
     - **Smallest category** but important
  
  **Boehm's Maintenance Effort Distribution:**
  
  | Maintenance Type | Percentage | Description |
  |------------------|------------|-------------|
  | Perfective | 50-60% | New features, enhancements |
  | Adaptive | 18-25% | Environmental changes |
  | Corrective | 17-21% | Defect fixing |
  | Preventive | 2-4% | Future problem prevention |
  
  **Key Insights from Boehm's Model:**
  
  1. **Majority is enhancement:** 50-60% goes to new features
  2. **Small portion for bugs:** Only ~20% for fixing defects
  3. **Adaptation required:** ~20% for environment changes
  4. **Prevention often neglected:** Only 2-4% despite importance
  
  **Boehm's Maintenance Cost Factors:**
  
  According to Boehm, maintenance cost depends on:
  
  1. **Program Structure Quality**
     - Well-structured: Lower maintenance cost
     - Poor structure: Exponentially higher cost
  
  2. **Programming Language**
     - High-level languages: Easier maintenance
     - Low-level languages: More effort required
  
  3. **Documentation Quality**
     - Good documentation: 30-40% effort reduction
     - Poor/missing documentation: Significantly higher effort
  
  4. **Personnel Capability**
     - Experienced staff: Higher productivity
     - Inexperienced staff: More errors, longer time
  
  5. **Application Domain Complexity**
     - Simple domains: Lower maintenance
     - Complex domains (aerospace, medical): Higher maintenance
  
  **Maintenance Cost Formula (Boehm):**
  
  \[ ACT = (AM) \times (1 + 0.02 \times SDT) \]
  
  Where:
  - ACT = Annual Change Traffic (% of code changed annually)
  - AM = Annual Maintenance effort
  - SDT = Software Development Time
  
  **Comparison with Other Models:**
  
  | Aspect | Boehm | Belady-Lehman | IEEE |
  |--------|-------|---------------|------|
  | Categories | 4 types | Complexity focus | 3 types |
  | Focus | Effort distribution | Evolution laws | Activity types |
  | Percentages | Quantified | Not specified | Quantified |
  
  **Practical Application:**
  
  Use Boehm's model to:
  - Allocate maintenance budget across categories
  - Justify resources for preventive maintenance
  - Predict maintenance effort distribution
  - Plan maintenance team size and composition
  
  **[5 Marks - CS209 Nov 2024]**



---
## **📈 Most Frequently Asked Topics (Based on 30 PDFs, 2005-2024)**

*Analysis of 173+ questions across 19 years reveals clear patterns and priorities.*

---

### **🔥 HIGH PRIORITY (Appears 10+ times across papers)**
*Master these topics - they appear in nearly every exam with multiple question variants.*

1. **COCOMO Model (Estimation & Calculation)** ⭐⭐⭐⭐⭐
   - **Frequency:** Appears in 25+ papers (83%)
   - **Types:** Basic COCOMO (3 modes), Intermediate COCOMO (15 cost drivers), Detailed COCOMO
   - **Key Focus:**
     - Calculating Effort (E), Time (T), Team Size (N)
     - Organic/Semi-detached/Embedded coefficient tables (a, b, c, d)
     - Effort multipliers (RELY, DATA, CPLX, TIME, etc.)
     - μp and τp distribution percentages
   - **Why Critical:** Worth 5-10 marks per paper, formulaic (easy scoring if you know tables)

2. **Spiral Model (Process Model)** ⭐⭐⭐⭐⭐
   - **Frequency:** Appears in 20+ papers (67%)
   - **Key Focus:**
     - 4 Quadrants (Planning, Risk Analysis, Engineering, Customer Evaluation)
     - Risk-driven approach vs. document-driven
     - When to use (large, complex, risky projects)
     - Advantages over Waterfall
     - Meta-model concept
   - **Why Critical:** Single most asked process model, often 5-10 marks

3. **Testing Techniques (Black Box + White Box)** ⭐⭐⭐⭐⭐
   - **Frequency:** Appears in 28+ papers (93%)
   - **Key Focus:**
     - **Black Box:** Equivalence Class Partitioning, Boundary Value Analysis (BVA), Robustness Testing, Worst Case Testing, Decision Tables
     - **White Box:** Cyclomatic Complexity, Basis Path Testing, Data Flow Testing (NEW in 2024)
     - Test case design for specific systems (Quadratic, Triangle, NextDate)
   - **Why Critical:** Both theory and practical questions, worth 10-15 marks per paper

4. **Requirements Engineering (SRS + Elicitation)** ⭐⭐⭐⭐
   - **Frequency:** Appears in 22+ papers (73%)
   - **Key Focus:**
     - Characteristics of good SRS (Correct, Unambiguous, Complete, Consistent, Ranked, Verifiable, Modifiable, Traceable)
     - Functional vs. Non-Functional requirements
     - Elicitation techniques (FAST, JAD, Brainstorming, Interviews, Questionnaires)
     - IEEE SRS format (Section 3 structure)
   - **Why Critical:** Foundation topic, often combined with case studies

5. **Coupling & Cohesion (Design Principles)** ⭐⭐⭐⭐
   - **Frequency:** Appears in 18+ papers (60%)
   - **Key Focus:**
     - **Coupling types (Worst to Best):** Content > Common > External > Control > Stamp > Data
     - **Cohesion types (Worst to Best):** Coincidental > Logical > Temporal > Procedural > Communicational > Sequential > Functional
     - High Cohesion + Low Coupling = Good design
   - **Why Critical:** Short answer staple (3-5 marks), easy to score

---

### **⚠️ MEDIUM PRIORITY (Appears 5-9 times)**
*Likely to appear as 5-10 marker questions, focus after mastering high priority.*

6. **Data Flow Diagrams (DFD) - Level 0, 1, 2** ⭐⭐⭐
   - **Frequency:** Appears in 15+ papers (50%)
   - **Key Focus:**
     - Context Diagram (Level 0)
     - Level 1 decomposition (major processes)
     - Level 2 detailed processes
     - DFD rules (balancing, no cycles in data stores)
   - **Systems:** Metro, Library, Hospital, ATM, E-commerce
   - **Why Important:** 10-mark drawing questions, pattern-based

7. **Function Point Analysis** ⭐⭐⭐
   - **Frequency:** Appears in 12+ papers (40%)
   - **Key Focus:**
     - UFP = (# of Inputs × weight) + (# of Outputs × weight) + ...
     - VAF calculation (14 GSCs)
     - FP = UFP × VAF
   - **Why Important:** Calculation-based, 5 marks per occurrence

8. **UML Diagrams (Multiple Types)** ⭐⭐⭐
   - **Frequency:** Appears in 14+ papers (47%)
   - **2024 TREND:** Now asking for **5 diagrams for ONE system!** (Activity, Sequence, Collaboration, Class, State Chart)
   - **Key Focus:**
     - Use Case (actors, relationships)
     - Class Diagram (attributes, methods, associations)
     - Sequence/Collaboration (interactions)
     - State Chart (state transitions)
   - **Why Important:** Nov 2024 showed 10-mark question requiring 5 UML diagrams

9. **Software Maintenance Models** ⭐⭐⭐
   - **Frequency:** Appears in 10+ papers (33%)
   - **Key Focus:**
     - Types: Corrective (17-21%), Adaptive (18-25%), Perfective (50-60%), Preventive (2-4%)
     - **Boehm's Model:** Effort distribution percentages
     - **Belady-Lehman Model:** C(t) = C₀ + K × E (complexity growth)
     - Reverse Engineering vs. Re-engineering
   - **Why Important:** Theory + calculation questions (5 marks)

10. **CMM vs. ISO 9001** ⭐⭐⭐
    - **Frequency:** Appears in 11+ papers (37%)
    - **Key Focus:**
      - CMM 5 Levels (Initial → Repeatable → Defined → Managed → Optimizing)
      - Key Process Areas (KPAs) at each level
      - ISO 9001 clauses correlation
      - Continuous improvement vs. certification
    - **Why Important:** Comparison questions (5-7 marks)

11. **Decision Table Testing** ⭐⭐ (NEW EMPHASIS 2024)
    - **Frequency:** Appears in 5+ papers, increasing trend
    - **Key Focus:**
      - Rules, conditions, actions
      - Complex OR/AND logic
      - Complete coverage of combinations
    - **Why Important:** Nov 2024 dedicated 5 marks, likely to repeat

12. **Data Flow Testing** ⭐⭐ (NEW CONCEPT 2024)
    - **Frequency:** NEW in Nov 2024, likely future trend
    - **Key Focus:**
      - DEF (definition) and USE (C-use, P-use)
      - DU-pairs identification
      - All-defs, All-uses, All-du-paths coverage
    - **Why Important:** Advanced testing technique (5 marks)

---

### **📊 Topic Frequency Analysis (30 PDFs)**

| Topic Category | Frequency | Question Types | Avg Marks |
|----------------|-----------|----------------|-----------|
| **COCOMO & Estimation** | 25/30 (83%) | Theory + Calculation | 7-10 marks |
| **Testing (All types)** | 28/30 (93%) | Theory + Design + Code | 10-15 marks |
| **Spiral Model** | 20/30 (67%) | Theory + Diagram | 5-10 marks |
| **Requirements/SRS** | 22/30 (73%) | Theory + Case Study | 5-8 marks |
| **Coupling/Cohesion** | 18/30 (60%) | Theory + Examples | 3-5 marks |
| **DFD Drawing** | 15/30 (50%) | Drawing Task | 10 marks |
| **Function Points** | 12/30 (40%) | Calculation | 5 marks |
| **UML Diagrams** | 14/30 (47%) | Drawing (now 5 types!) | 10 marks |
| **Maintenance** | 10/30 (33%) | Theory + Calculation | 5 marks |
| **CMM/ISO** | 11/30 (37%) | Comparison Table | 5-7 marks |
| **Halstead Metrics** | 8/30 (27%) | Code + Calculation | 5 marks |
| **Quality Models** | 9/30 (30%) | Theory (McCall/Boehm/ISO 9126) | 3-5 marks |

---

### **🎯 Optimized Study Strategy (For 173+ Question Bank)**

#### **PHASE 1: Master Calculations (Week 1-2)**
*These are "formula-based free marks" - highest ROI for study time*

✅ **Day 1-3: COCOMO Mastery**
- Memorize ALL coefficient tables (a, b, c, d for 3 modes)
- Practice 7 COCOMO problems in your bank
- Focus on: Effort (E), Time (T), Team Size (N), μp, τp

✅ **Day 4-5: Function Points**
- Memorize complexity weights (Simple/Average/Complex)
- Practice 4 FP problems
- Master VAF calculation (14 GSCs)

✅ **Day 6-7: Halstead Metrics**
- Operators vs. Operands identification
- Practice 6 code examples in your bank
- Memorize formulas: n, N, N̂, V, D, E, T, B

✅ **Day 8-10: Test Case Design**
- BVA (4n+1 test cases)
- Robustness (6n+1 test cases)
- Worst Case (5ⁿ test cases)
- Practice: Quadratic, Triangle, NextDate

✅ **Day 11-14: Complexity & Maintenance**
- Cyclomatic Complexity: V(G) = E - N + 2P
- Independent paths identification
- Belady-Lehman: C(t) = C₀ + K × E
- Practice 5 code CFG problems

**Goal:** Complete 31 calculation problems, achieve 95%+ accuracy

---

#### **PHASE 2: Drawing Practice (Week 3-4)**
*Pattern-based questions - once you learn the template, all variants become easy*

✅ **Week 3: DFD Mastery**
- Learn Level 0 (Context) template
- Practice Level 1 decomposition (5-7 major processes)
- Master Level 2 detailed breakdown
- **Practice systems:** DMAS Metro, Library, IRCTC, Hospital (all in your bank)
- Target: 1 complete DFD (L0+L1+L2) per day

✅ **Week 4: UML Diagrams (NEW 2024 FOCUS)**
- **Critical:** Nov 2024 asked for 5 UML diagrams for ONE system!
- Practice sequence:
  1. Use Case (actors, relationships)
  2. Class Diagram (6+ entities with attributes/methods)
  3. Activity Diagram (swimlanes, decisions)
  4. Sequence Diagram (object interactions, lifelines)
  5. State Chart (states, transitions, events)
- **Practice system:** Food Delivery (Zomato) from Nov 2024
- Target: Complete all 5 diagrams for 2-3 systems

**Goal:** Comfortable drawing any diagram in 15-20 minutes

---

#### **PHASE 3: Theory Mastery (Week 5)**
*High-frequency short answer questions*

✅ **Day 1-2: Process Models**
- **Spiral Model (MUST KNOW!):** 4 quadrants, risk-driven, meta-model concept
- Prototyping types (Throwaway vs. Evolutionary)
- Waterfall limitations (5-6 points)
- Iterative Enhancement, RAD Model

✅ **Day 3-4: Requirements Engineering**
- 8 Characteristics of good SRS (acronym: CUCRRVMT)
- Functional vs. Non-Functional (with 3 examples each)
- 5 Elicitation techniques (FAST, JAD, Brainstorming, Interviews, Questionnaires)
- IEEE SRS Section 3 structure

✅ **Day 5: Design Principles**
- **Coupling types (6 types, worst to best)** - Content, Common, External, Control, Stamp, Data
- **Cohesion types (7 types, worst to best)** - Coincidental, Logical, Temporal, Procedural, Communicational, Sequential, Functional
- Modularity advantages (4-5 points)

✅ **Day 6-7: Testing Theory**
- Black Box vs. White Box (5 differences table)
- V&V differences
- Testing levels (Unit, Integration, System, Acceptance)
- **NEW:** Data Flow Testing (DEF, USE, DU-pairs, All-defs/uses/paths)
- **NEW:** Decision Table Testing (conditions, rules, actions)

**Goal:** Memorize all high-frequency definitions and lists

---

#### **PHASE 4: Quality & Advanced Topics (Week 5 continued)**

✅ **CMM Levels**
- Level 1-5 names and descriptions
- Key Process Areas (KPAs) for Levels 2-5
- CMM-ISO 9001 correlation table (from Nov 2024)

✅ **Quality Models**
- **McCall:** 11 factors in 3 categories (Product Operation, Revision, Transition)
- **Boehm:** Same 11 + 7 primitives
- **ISO 9126:** 6 characteristics (Functionality, Reliability, Usability, Efficiency, Maintainability, Portability)

✅ **Maintenance**
- **Boehm's percentages:** Perfective (50-60%), Adaptive (18-25%), Corrective (17-21%), Preventive (2-4%)
- Reverse Engineering, Re-engineering, Refactoring
- Legacy system challenges

**Goal:** Complete all theory topics with examples

---

#### **PHASE 5: Case Studies & Integration (Week 6)**

✅ **Days 1-3: Complete System Specifications**
Your bank has **22 complete case studies**. Practice these:
- **High Priority:** DMAS (Delhi Metro), Food Delivery (Zomato), IRCTC, Library Management
- Read full specifications
- Practice drawing 2-3 diagrams per system
- Write 10 functional + 5 non-functional requirements

✅ **Days 4-5: Mixed Problem Sets**
- 3 calculations (COCOMO, FP, Halstead)
- 2 drawing tasks (DFD + UML)
- 5 short theory answers
- Simulate exam conditions (time yourself)

✅ **Days 6-7: Final Revision**
- Review ALL high-priority topics (top 5)
- Redo problems you got wrong
- Memorize formulas, tables, lists
- Focus on Nov 2024 new topics (Data Flow Testing, Decision Tables, Multiple UML)

**Goal:** Exam-ready confidence, <3 hours to complete any paper

---

### **📌 2024 EXAM TRENDS TO WATCH**

Based on Nov 2024 paper analysis:

🆕 **1. Real-World Systems:** Zomato/Swiggy (food delivery), modern CRM
🆕 **2. Multiple Diagrams:** 5 UML diagrams for ONE system (Activity, Sequence, Collaboration, Class, State Chart)
🆕 **3. Advanced Testing:** Data Flow Testing (NEW concept), Decision Table emphasis
🆕 **4. Complete Specifications:** 10-mark questions require detailed system understanding
🆕 **5. Latest Parameters:** Stroud number = 18 (Halstead), K = 0.4 (Belady-Lehman)

---

### **⚡ Quick Win Topics (If Time is Limited)**

If you have <2 weeks, focus ONLY on:

| Priority | Topic | Study Time | Expected Marks |
|----------|-------|------------|----------------|
| 🔴 #1 | COCOMO Calculation | 8 hours | 10 marks |
| 🔴 #2 | Spiral Model Theory | 3 hours | 5-7 marks |
| 🔴 #3 | Coupling/Cohesion | 2 hours | 5 marks |
| 🔴 #4 | Test Case Design (BVA) | 4 hours | 8 marks |
| 🔴 #5 | DFD Level 0-1 | 5 hours | 10 marks |
| **TOTAL** | **5 Topics** | **22 hours** | **38-40 marks** |

---

### **✅ Daily Practice Checklist**

- [ ] 2 COCOMO/FP/Halstead calculations (20 min)
- [ ] 1 Drawing task (DFD or UML) (30 min)
- [ ] 3 Short theory answers (15 min)
- [ ] 5 Test cases for any system (15 min)
- [ ] Review previous day's mistakes (10 min)

**Total: 90 minutes/day = Exam ready in 6 weeks**

---

### **🎓 Final Confidence Checklist**

Before the exam, ensure you can:

✅ Calculate COCOMO (Effort, Time, Team Size) in <10 minutes
✅ Draw DFD Level 0-1 for any system in <20 minutes
✅ List Coupling types (worst to best) in correct order
✅ List Cohesion types (worst to best) in correct order
✅ Explain Spiral Model with diagram in <10 minutes
✅ Design 10+ test cases using BVA/Robustness in <15 minutes
✅ Calculate Cyclomatic Complexity and find independent paths in <10 minutes
✅ Draw 5 UML diagrams for a given system in <30 minutes (NEW 2024 requirement)
✅ Explain Data Flow Testing (DEF, USE, DU-pairs) with example (NEW 2024)
✅ Create Decision Table with complete rules/actions (NEW 2024)

**If you can do all 10 ✅ = You are EXAM READY!**

---





