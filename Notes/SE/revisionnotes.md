# **📚 REVISED Q1 & Q2 - CONCISE FORMAT**

***

## **Q1. What is Software? Explain its components.**

### **ANSWER (6-8 marks):**

**Definition:**
Software is a collection of programs, documentation, and operating procedures that provide desired features, functions, and performance when executed.

**According to Pressman:**
> "Software is: (1) instructions that provide features/function; (2) data structures that enable information manipulation; (3) documentation describing operation and use."

***

### **Three Primary Components:**

#### **1. Computer Programs (Instructions)**
- Executable code (compiled/interpreted)
- Contains algorithms and logic
- Directs computer to perform operations
- **Example:** Sorting algorithm in C++, web app in JavaScript

#### **2. Data Structures**
- Organized formats for storing/managing data
- Enable efficient data manipulation
- **Types:** Arrays, trees, hash tables, databases
- **Example:** Student database schema with tables for courses, grades

#### **3. Documentation**
- Describes software operation and usage
- **Types:**
  - **User Documentation:** Manuals, tutorials, help files
  - **System Documentation:** Design docs, architecture diagrams
  - **Code Documentation:** Comments, API references
- **Forms:** Hard copy (printed manuals) + Virtual (online help)

***

### **Key Characteristics:**

| Software | Hardware |
|----------|----------|
| Logical (intangible) | Physical |
| Developed/Engineered | Manufactured |
| Doesn't wear out | Wears out over time |
| Highly flexible | Less flexible |
| Complex (millions LOC) | Predictable failure |

***

### **Software Categories (Pressman):**

1. **System Software:** OS, compilers, drivers
2. **Application Software:** Business apps, MS Office
3. **Engineering/Scientific:** CAD, simulations
4. **Embedded:** IoT devices, automotive systems
5. **Web/Mobile:** Cloud apps, mobile apps
6. **AI Software:** Machine learning, expert systems

**Complete Equation:** 
**Software = Programs + Data Structures + Documentation**

***

## **Q2. Explain the Spiral Model in detail.**

### **ANSWER (8-10 marks):**

**Spiral Model** (Barry Boehm, 1988) is a **risk-driven** evolutionary process model that combines iterative prototyping with Waterfall's systematic control.

***

### **Key Concept:**

Represented as a **spiral** with multiple loops:
- Each loop = one phase/iteration
- **Radial dimension:** Cumulative cost (increases outward)
- **Angular dimension:** Progress through cycle

***

### **Four Quadrants (Per Loop):**

#### **Quadrant 1: Objective Setting (Planning)**
**Activities:**
- Determine objectives for this iteration
- Identify constraints (budget, schedule, technology)
- Explore alternative approaches
- Stakeholder communication

**Output:** Objectives document, alternatives list

***

#### **Quadrant 2: Risk Assessment and Reduction**
**Activities:**
- **Identify risks:** Technical, schedule, cost
- **Analyze:** Probability × Impact
- **Mitigate:** Prototyping, simulation, benchmarking
- **Decision:** Go/No-Go for next phase

**Output:** Risk analysis, prototypes, feasibility studies

**K.K. Aggarwal:** *"Risk analysis is the backbone of Spiral Model. If risks can't be mitigated, project may terminate before wasting resources."*

***

#### **Quadrant 3: Engineering (Development)**
**Activities:**
- Design (architectural + detailed)
- Coding
- Unit Testing
- Integration
- System Testing

**Output:** Code modules, integrated system increment, test results

***

#### **Quadrant 4: Customer Evaluation (Planning Next)**
**Activities:**
- Customer reviews deliverables
- Evaluate against objectives (Q1)
- Collect feedback
- Plan next iteration (what to build next, risks to address)

**Output:** Customer feedback, revised requirements, next loop plan

***

### **Diagram:**

```
           Cumulative Cost →
              (Outward)
                 
      ┌─────────────────┐
      │  1. Planning    │
      │  Set Objectives │
      └────────┬────────┘
               │
    ┌──────────▼──────────┐
    │ 2. Risk Assessment  │
    │   Prototyping       │
    └──────────┬──────────┘
               │
      ┌────────▼────────┐
      │ 3. Engineering  │
      │  Development    │
      └────────┬────────┘
               │
    ┌──────────▼──────────┐
    │ 4. Customer Review  │
    │  Plan Next Loop     │
    └─────────────────────┘
           ↓
      (Next Spiral Loop)
```

**Each loop produces increasingly complete system version**

***

### **Advantages:**

1. **Risk Management:**
   - Explicit, continuous risk analysis
   - Early risk identification/mitigation
   - Can terminate early if risks unmanageable (cost-effective)

2. **Flexibility:**
   - Accommodates changing requirements
   - Evolutionary refinement based on feedback

3. **Customer Involvement:**
   - Regular feedback (every iteration)
   - Customers see working increments early

4. **Suitable for Large Projects:**
   - Handles high complexity through iterations
   - Used by NASA, defense (mission-critical systems)

5. **Incremental Delivery:**
   - Early operational capability
   - Phased funding possible

***

### **Disadvantages:**

1. **High Complexity:**
   - Requires experienced management
   - Documentation overhead (risk reports, plans)

2. **Cost/Time Uncertainty:**
   - Hard to predict total duration upfront
   - Budget uncertainty with each loop

3. **Risk Assessment Expertise Required:**
   - Not all organizations have skilled risk analysts
   - Ineffective risk analysis undermines the model

4. **Not for Small Projects:**
   - Overhead too high for simple applications
   - Cost of risk analysis > project value

5. **Potential for Infinite Spirals:**
   - Without strict exit criteria, may loop indefinitely
   - Scope creep if customer keeps adding requirements

***

### **When to Use:**

**✓ Ideal for:**
- Large-scale, high-risk projects (air traffic control, military)
- Evolving requirements (research software)
- New technology/unfamiliar domain (autonomous vehicles)
- Long-duration projects (multi-year ERP implementations)
- Continuous stakeholder engagement needed

**✗ Unsuitable for:**
- Small, simple projects (web forms)
- Well-defined, stable requirements
- Low-risk, routine projects (CRUD apps)
- Tight budget/schedule constraints (fixed-price contracts)

***

### **Spiral as Meta-Model:**

**Pressman:** *"Spiral is a meta-model—each loop can internally use different process models."*

**Example:**
- Loop 1: **Waterfall** for infrastructure
- Loop 2: **Prototyping** for unclear UI
- Loop 3: **Incremental** for feature rollout

***

### **Real-World Example:**

**NASA Space Shuttle Software:**
- Loop 1: Prove digital fly-by-wire feasibility
- Loop 2: Core navigation algorithms
- Loop 3: Integrate redundant systems
- Loop 4: Full system with failover

**Each loop addressed specific high-risk challenges with extensive review before proceeding.**

**Outcome:** Zero in-flight failures over decades.

***

## **Q3. Explain COCOMO Model (Basic & Intermediate levels).**

### **ANSWER (8-10 marks):**

**COCOMO (Constructive Cost Model)** by Barry Boehm (1981) is an empirical software cost estimation model.

***

### **Basic COCOMO:**

**Three Development Modes:**

1. **Organic:** Small teams, familiar domain (≤50 KLOC)
2. **Semi-Detached:** Medium complexity (50-300 KLOC)  
3. **Embedded:** Complex, real-time, tight constraints (>300 KLOC)

**Formulas:**
- **Effort:** \( E = a \times (KLOC)^b \) (Person-Months)
- **Time:** \( T = c \times (E)^d \) (Months)
- **Team Size:** \( N = E/T \)

**Constants Table:**
| Mode | a | b | c | d |
|------|---|---|---|---|
| Organic | 2.4 | 1.05 | 2.5 | 0.38 |
| Semi-Detached | 3.0 | 1.12 | 2.5 | 0.35 |
| Embedded | 3.6 | 1.20 | 2.5 | 0.32 |

**Example:** 32 KLOC Organic project
- \( E = 2.4 \times (32)^{1.05} = 81.5 \text{ PM} \)
- \( T = 2.5 \times (81.5)^{0.38} = 13.8 \text{ months} \)
- \( N = 81.5/13.8 = 6 \text{ people} \)

***

### **Intermediate COCOMO:**

Adds **15 cost drivers** (EAF - Effort Adjustment Factor):

**Formula:** \( E = E_{nominal} \times EAF \)

**Categories:**
1. **Product:** Reliability (RELY), Complexity (CPLX), Database size (DATA)
2. **Hardware:** Execution time (TIME), Storage (STOR)
3. **Personnel:** Analyst capability (ACAP), Programmer capability (PCAP), Experience (AEXP, LEXP)
4. **Project:** Tools (TOOL), Modern practices (MODP), Schedule (SCED)

**Example:** If RELY=1.15, CPLX=1.15, others=1.0
- \( EAF = 1.15 \times 1.15 = 1.32 \)
- \( E_{adjusted} = 81.5 \times 1.32 = 108 \text{ PM} \)

**Advantage:** 20% more accurate than Basic COCOMO.

***

## **Q4. Explain Coupling and Cohesion types (Best to Worst).**

### **ANSWER (8-10 marks):**

***

### **COUPLING (Interdependence between modules):**

**Goal: LOW Coupling**

**Types (Best → Worst):**

1. **Data Coupling** ✓ Best
   - Pass simple parameters only
   - Example: `int add(int a, int b)`

2. **Stamp Coupling**
   - Pass data structures
   - Example: Pass `Employee` struct, use only `salary` field

3. **Control Coupling**
   - Pass control flags
   - Example: `file_op(filename, operation_code)`

4. **Common Coupling** ✗ Avoid
   - Share global variables
   - Example: Multiple modules access `global_user_id`

5. **Content Coupling** ✗ Never
   - Directly modify another module's internals
   - Example: Break encapsulation via reflection

***

### **COHESION (Relatedness within module):**

**Goal: HIGH Cohesion**

**Types (Best → Worst):**

1. **Functional Cohesion** ✓ Best
   - One well-defined task
   - Example: `calculate_circle_area(radius)`

2. **Sequential Cohesion**
   - Output of A → Input of B (pipeline)
   - Example: `parse() → validate() → transform()`

3. **Communicational Cohesion**
   - Operate on same data
   - Example: `generate_report(student)` - prints name, GPA, courses

4. **Procedural Cohesion**
   - Follow procedural sequence
   - Example: `initialize_system()` - setup hardware, load config, start services

5. **Temporal Cohesion**
   - Execute at same time
   - Example: Startup initialization module

6. **Logical Cohesion** ✗ Avoid
   - Category grouping with control flag
   - Example: `io_operation(type)` - type selects read/write/network

7. **Coincidental Cohesion** ✗ Never
   - Random grouping
   - Example: "Utility" class with unrelated functions

**Design Rule:** **Low Coupling + High Cohesion = Good Design**

***

## **Q5. What is SRS? Explain its characteristics.**

### **ANSWER (6-8 marks):**

**SRS (Software Requirements Specification)** is a complete description of the behavior of the system to be developed. It serves as a contract between customer and developer.

***

### **Characteristics (IEEE 830):**

1. **Correct:** Every requirement accurately reflects stakeholder needs
   - Example: Customer wants SMS, not email

2. **Unambiguous:** Only ONE interpretation possible
   - ❌ "System shall be fast"
   - ✓ "Response time ≤ 2 seconds"

3. **Complete:** All significant requirements included (functional, non-functional, interfaces)
   - No "TBD" items remaining

4. **Consistent:** No contradictions
   - Requirements don't conflict with each other

5. **Ranked:** Prioritized (Essential/Conditional/Optional)
   - MoSCoW: Must/Should/Could/Won't have

6. **Verifiable:** Every requirement is testable
   - ❌ "User-friendly"
   - ✓ "95% users complete task in ≤3 clicks"

7. **Modifiable:** Easy to change without breaking structure
   - Use unique IDs, avoid redundancy

8. **Traceable:** Forward (to design/code/test) and backward (to source)
   - Requirement → Test case mapping

***

### **Key Stakeholders:**
- **Customers:** Validate needs
- **Developers:** Implementation blueprint
- **Testers:** Test case derivation
- **Project Managers:** Scope/cost estimation
- **Maintenance:** System documentation

***

## **Q6. Explain Black Box vs White Box Testing.**

### **ANSWER (6-8 marks):**

***

### **Black Box Testing:**

**Definition:** Testing based on **functional specifications** without knowledge of internal code structure.

**Focus:** **What** the system does (inputs → outputs)

**Techniques:**
1. **Equivalence Partitioning:** Divide inputs into valid/invalid classes
2. **Boundary Value Analysis:** Test at boundaries (min, max, just above/below)
3. **Decision Tables:** Test all input combinations
4. **State Transition:** Test state changes

**Example:** Testing login with valid/invalid passwords

**Advantages:**
- Tester independent of implementation
- Tests user perspective
- Applicable to all levels (unit, integration, system)

**Disadvantages:**
- Can't test internal paths
- Limited code coverage

***

### **White Box Testing:**

**Definition:** Testing based on **internal code structure** (logic, paths, branches).

**Focus:** **How** the system works (code coverage)

**Techniques:**
1. **Statement Coverage:** Execute every statement
2. **Branch Coverage:** Test all if/else branches
3. **Path Coverage:** Test all execution paths
4. **Condition Coverage:** Test all boolean conditions

**Cyclomatic Complexity:** \( V(G) = E - N + 2 \)
- E = edges, N = nodes in control flow graph

**Example:** Testing all paths through nested if-else

**Advantages:**
- Thorough code coverage
- Finds hidden errors
- Optimizes code

**Disadvantages:**
- Requires programming knowledge
- Expensive (all paths testing impractical)
- Misses missing functionality

***

### **Comparison:**

| Aspect | Black Box | White Box |
|--------|-----------|-----------|
| **Basis** | Specifications | Code structure |
| **Tester** | End users/QA | Developers |
| **Level** | All levels | Mainly unit testing |
| **Coverage** | Functional | Structural |
| **Example** | BVA, Decision tables | Statement/branch coverage |

**Best Practice:** Use **BOTH** for comprehensive testing.

***

## **Q7. Explain the Spiral Model with diagram.**

### **ANSWER (8-10 marks):**

**Spiral Model** (Barry Boehm, 1988) is a **risk-driven** evolutionary process model combining iterative development with Waterfall's systematic approach.

***

### **Structure:**

**Spiral Loops:** Each loop = one iteration through 4 quadrants

**Axes:**
- **Radial:** Cumulative cost
- **Angular:** Progress through cycle

***

### **Four Quadrants (Each Loop):**

1. **Objective Setting (Planning)**
   - Define objectives for iteration
   - Identify constraints
   - Explore alternatives

2. **Risk Assessment**
   - Identify risks (technical, schedule, cost)
   - Analyze risk exposure
   - Mitigate via prototyping/simulation
   - **Go/No-Go decision**

3. **Engineering (Development)**
   - Design → Code → Test
   - Integrate components
   - Produce working increment

4. **Customer Evaluation**
   - Customer reviews deliverables
   - Feedback collection
   - Plan next iteration

***

### **Diagram:**
```
        Objective Setting
              ↓
    Risk ← → Engineering
    Analysis    ↓
              Customer
             Evaluation
              ↓
        (Next Loop...)
```

**Each loop moves outward** (increasing commitment/cost)

***

### **Advantages:**
1. **Risk management:** Explicit focus on risks
2. **Flexibility:** Accommodates changing requirements
3. **Early customer feedback**
4. **Suitable for large, complex projects**

### **Disadvantages:**
1. **Requires risk expertise**
2. **Expensive** (high management overhead)
3. **Difficult cost/time estimation**
4. **Not suitable for small projects**

### **When to Use:**
- Large, high-risk projects (NASA, defense)
- Evolving requirements
- New technology/unfamiliar domain

***

# **📚 HIGH-PRIORITY QUESTIONS - Q8 ONWARDS**

***

## **Q8. Explain Function Point Analysis (FPA) with example.**

### **ANSWER (8-10 marks):**

**Function Point Analysis** (Allan Albrecht, IBM 1979) measures software size based on **functionality delivered** to users, independent of programming language.

***

### **Five Components:**

| Component | Description | Weight (Simple/Avg/Complex) |
|-----------|-------------|----------------------------|
| **External Inputs (EI)** | User inputs, forms | 3 / 4 / 6 |
| **External Outputs (EO)** | Reports, screens | 4 / 5 / 7 |
| **External Inquiries (EQ)** | Queries (input+output) | 3 / 4 / 6 |
| **Internal Logical Files (ILF)** | Data maintained by system | 7 / 10 / 15 |
| **External Interface Files (EIF)** | Data referenced from other systems | 5 / 7 / 10 |

***

### **FPA Calculation Steps:**

**Step 1: Count Unadjusted Function Points (UFP)**

\[ UFP = \sum (\text{Count} \times \text{Weight}) \]

**Step 2: Calculate Value Adjustment Factor (VAF)**

14 General System Characteristics (GSC) rated 0-5 each:
- Data communications
- Distributed processing
- Performance requirements
- Heavily used configuration
- Transaction rate
- Online data entry
- End-user efficiency
- Online update
- Complex processing
- Reusability
- Installation ease
- Operational ease
- Multiple sites
- Facilitate change

\[ VAF = 0.65 + (0.01 \times \sum GSC) \]

**Step 3: Calculate Adjusted Function Points**

\[ FP = UFP \times VAF \]

***

### **Example:**

**Library Management System:**

**Counts:**
- External Inputs: 5 (Add book, Issue book, Return book, Add member, Update member) - Average = 5 × 4 = **20**
- External Outputs: 4 (Overdue report, Member list, Book catalog, Fine report) - Average = 4 × 5 = **20**
- External Inquiries: 3 (Search book, Check availability, Member status) - Simple = 3 × 3 = **9**
- Internal Files: 2 (Books database, Members database) - Average = 2 × 10 = **20**
- External Interface Files: 1 (University student database) - Simple = 1 × 5 = **5**

**UFP = 20 + 20 + 9 + 20 + 5 = 74**

**GSC Total = 35** (example)

**VAF = 0.65 + (0.01 × 35) = 1.0**

**FP = 74 × 1.0 = 74 Function Points**

***

### **Advantages:**
1. **Language independent:** 1 FP ≈ 50 LOC (Java), 25 LOC (C++)
2. **Early estimation:** Can estimate before coding
3. **User perspective:** Based on functionality, not technical implementation
4. **Standardized:** ISO recognized

### **Disadvantages:**
1. **Subjective:** Complexity rating depends on analyst
2. **Not suitable for:** Real-time, embedded systems
3. **Learning curve:** Requires training

***

## **Q9. Explain Requirements Elicitation Techniques.**

### **ANSWER (6-8 marks):**

**Requirements Elicitation** is the process of gathering requirements from stakeholders through communication and discovery.

***

### **Major Techniques:**

#### **1. Interviews**
**Types:**
- **Structured:** Predefined questions (closed-ended)
- **Unstructured:** Open-ended discussion

**Advantages:** Direct communication, clarifications possible  
**Disadvantages:** Time-consuming, biased responses

**Example:** Interview hospital staff for medical system requirements

***

#### **2. Questionnaires/Surveys**
- Written questions distributed to large audience
- Statistical analysis of responses

**Advantages:** Reach many stakeholders quickly, quantitative data  
**Disadvantages:** No clarifications, low response rate

***

#### **3. Observation/Ethnography**
- Analyst observes users in their work environment
- Understand actual workflow (not just stated workflow)

**Advantages:** Discover implicit requirements, see real problems  
**Disadvantages:** Time-intensive, Hawthorne effect (people behave differently when watched)

**Example:** Watch nurses use current system to identify pain points

***

#### **4. Document Analysis**
- Study existing documentation:
  - Current system manuals
  - Business process documents
  - Regulatory requirements
  - Competitor analysis

**Advantages:** Baseline understanding, identify gaps  
**Disadvantages:** May be outdated or incomplete

***

#### **5. Prototyping**
- Build throwaway/evolutionary prototype
- Users interact and provide feedback

**Advantages:** Clarifies vague requirements, visual feedback  
**Disadvantages:** Users may expect prototype = final system

***

#### **6. Brainstorming**
- Group creativity session
- No criticism, encourage wild ideas
- Combine/refine ideas later

**Advantages:** Generate many ideas quickly, team alignment  
**Disadvantages:** Can be chaotic, requires skilled facilitator

***

#### **7. FAST (Facilitated Application Specification Technique)**
- Structured workshop with customers and developers
- Pre-meeting preparation → Workshop → Follow-up

**Participants:** Facilitator, customers, developers

**Advantages:** Rapid requirements gathering, team consensus  
**Disadvantages:** Requires commitment from all stakeholders

***

#### **8. Use Cases**
- Describe system behavior from user perspective
- Actors + Goals + Steps

**Advantages:** User-centric, testable scenarios  
**Disadvantages:** May miss non-functional requirements

***

### **Best Practice:**
**Use multiple techniques** - triangulate requirements from different sources for validation.

***

## **Q10. Explain the Waterfall Model with advantages and disadvantages.**

### **ANSWER (6-8 marks):**

**Waterfall Model** (Winston Royce, 1970) is the **oldest, simplest** software process model following a **linear sequential** approach.

***

### **Phases (Sequential):**

```
1. Requirements Analysis
   ↓ (Requirements Document)
2. System Design
   ↓ (Design Document)
3. Implementation (Coding)
   ↓ (Code)
4. Testing
   ↓ (Test Reports)
5. Deployment
   ↓ (Operational System)
6. Maintenance
```

**Each phase must complete before next begins**  
**Output of one phase = Input to next phase**

***

### **Phase Details:**

1. **Requirements:** Gather and document all requirements (SRS)
2. **Design:** 
   - High-level design (architecture)
   - Detailed design (modules, algorithms)
3. **Implementation:** Write code according to design
4. **Testing:** Verify system meets requirements
5. **Deployment:** Install and handover to customer
6. **Maintenance:** Fix bugs, enhancements

***

### **Advantages:**

1. **Simple to Understand:** Clear phases, easy to explain to customers
2. **Well-Documented:** Each phase produces documentation
3. **Easy to Manage:** Rigid structure, clear milestones
4. **Works for Small Projects:** Requirements clear and stable
5. **Easy Progress Tracking:** % completion per phase

***

### **Disadvantages:**

1. **Inflexible:** Cannot accommodate changing requirements
2. **Late Testing:** Bugs discovered only at end (expensive to fix)
3. **No Working Software Until Late:** Customer sees product only at end
4. **Risk and Uncertainty:** High risk if requirements misunderstood
5. **Not Suitable for:**
   - Long, complex projects
   - Object-oriented development
   - Projects with unclear requirements

**Pressman:** *"Real projects rarely follow sequential flow. Waterfall is idealized, rarely practical."*

***

### **When to Use:**

✓ **Use when:**
- Requirements are well-understood and stable
- Technology is well-known
- Short duration project
- Resources with required expertise available

✗ **Avoid when:**
- Requirements are vague or evolving
- High-risk project
- Complex, long-duration project

***

### **Royce's Original Proposal:**
Royce actually recommended **iteration backward** to previous phases, not pure sequential! Industry misunderstood his paper.

***

## **Q11. Explain Agile Methodology and its principles.**

### **ANSWER (6-8 marks):**

**Agile** is an **iterative, incremental** software development approach emphasizing flexibility, customer collaboration, and rapid delivery.

**Origin:** Agile Manifesto (2001) by 17 software practitioners

***

### **Four Core Values (Agile Manifesto):**

1. **Individuals and interactions** > Processes and tools
2. **Working software** > Comprehensive documentation
3. **Customer collaboration** > Contract negotiation
4. **Responding to change** > Following a plan

***

### **12 Agile Principles:**

1. **Highest priority:** Satisfy customer through early/continuous delivery
2. **Welcome changing requirements** even late in development
3. **Deliver working software frequently** (weeks, not months)
4. **Business people and developers work together** daily
5. **Build projects around motivated individuals**
6. **Face-to-face conversation** most effective communication
7. **Working software** is primary measure of progress
8. **Sustainable development** (constant pace indefinitely)
9. **Continuous attention** to technical excellence and good design
10. **Simplicity** (maximize work not done)
11. **Self-organizing teams** produce best architectures
12. **Regular reflection** on how to become more effective

***

### **Agile Practices:**

#### **1. Iterative Development**
- Short cycles (sprints) of 1-4 weeks
- Each iteration delivers working increment

#### **2. User Stories**
- Requirements as: *"As a [user], I want [goal] so that [benefit]"*
- **Example:** "As a customer, I want to filter products by price so that I can find affordable items"

#### **3. Daily Stand-ups**
- 15-minute meetings
- What I did yesterday? What I'll do today? Any blockers?

#### **4. Continuous Integration**
- Code integrated multiple times daily
- Automated testing

#### **5. Pair Programming**
- Two developers, one workstation
- Driver (types) + Navigator (reviews)

#### **6. Test-Driven Development (TDD)**
- Write test before code
- Red → Green → Refactor

***

### **Popular Agile Frameworks:**

**1. Scrum**
- Roles: Product Owner, Scrum Master, Development Team
- Artifacts: Product Backlog, Sprint Backlog, Increment
- Events: Sprint Planning, Daily Scrum, Sprint Review, Retrospective

**2. Kanban**
- Visualize workflow (Kanban board)
- Limit work-in-progress (WIP)
- Continuous flow

**3. Extreme Programming (XP)**
- Emphasis on technical practices
- Pair programming, TDD, continuous integration

***

### **Advantages:**

1. **Customer Satisfaction:** Regular delivery of working software
2. **Adaptable:** Responds to changing requirements
3. **Early ROI:** Functional software delivered quickly
4. **Risk Reduction:** Issues identified early
5. **Team Morale:** Self-organizing, empowered teams

***

### **Disadvantages:**

1. **Minimal Documentation:** Can be problematic for maintenance
2. **Requires Experienced Team:** Self-organization needs maturity
3. **Customer Availability:** Requires active customer participation
4. **Not Suitable for:**
   - Large, distributed teams
   - Safety-critical systems (need extensive documentation)
   - Fixed-price contracts

***

### **When to Use:**

✓ Small to medium projects  
✓ Evolving requirements  
✓ Experienced, co-located teams  
✓ Customer can participate actively

***

## **Q12. Explain Data Flow Diagrams (DFD) with example.**

### **ANSWER (6-8 marks):**

**Data Flow Diagram (DFD)** is a graphical representation showing **flow of data** through a system and the **processes** that transform data.

**Purpose:** Model system functionality from user perspective (logical model, not physical)

***

### **DFD Symbols (Gane-Sarson Notation):**

| Symbol | Name | Description |
|--------|------|-------------|
| **Rectangle** | External Entity | Source/sink of data (users, systems) |
| **Rounded Rectangle/Circle** | Process | Transforms data (verb phrase) |
| **Open Rectangle** | Data Store | Repository (files, databases) |
| **Arrow** | Data Flow | Movement of data |

***

### **DFD Levels:**

#### **1. Context Diagram (Level 0)**
- Highest level, single process
- Shows system as black box
- External entities and data flows

**Example: Library System Context Diagram**
```
[Member] ---(Borrow Request)---> (Library System) ---(Book Details)---> [Member]
[Librarian] ---(Add Book)---> (Library System)
```

***

#### **2. Level 1 DFD**
- Decompose context into major processes
- Shows data stores

**Example:**
```
[Member] ---(Book Request)---> (1. Search Books) ---> D1[Book Catalog]
                                       ↓
                              (2. Issue Book) ---> D2[Loan Records]
                                       ↓
                              ---(Issue Receipt)---> [Member]
```

***

#### **3. Level 2 DFD**
- Further decompose Level 1 processes
- More detailed view

***

### **DFD Rules:**

1. **Process Naming:** Use verb + noun (e.g., "Validate User", "Calculate Total")
2. **Data Flow Naming:** Use noun (e.g., "Customer Data", "Invoice")
3. **Balancing:** Child DFD inputs/outputs = Parent process inputs/outputs
4. **No Process-to-Process Direct Flow:** Data must flow through data store or external entity
5. **Data Store Naming:** Use plural noun (e.g., "Orders", "Customers")

***

### **Complete Example: Online Shopping**

**Level 0 (Context):**
```
[Customer] ---(Order)---> (Online Shopping System) ---(Confirmation)---> [Customer]
[Admin] ---(Product Info)---> (Online Shopping System)
(Online Shopping System) ---(Payment Request)---> [Payment Gateway]
```

**Level 1:**
```
[Customer] ---(Login)---> (1. Authenticate User) ---> D1[User Database]
[Customer] ---(Browse)---> (2. Display Products) <---> D2[Product Catalog]
[Customer] ---(Add to Cart)---> (3. Manage Cart) ---> D3[Shopping Cart]
(3. Manage Cart) ---(Order Details)---> (4. Process Payment) ---> [Payment Gateway]
(4. Process Payment) ---(Confirmation)---> [Customer]
```

***

### **Advantages:**
1. **Simple notation:** Easy to understand
2. **Focuses on data flow:** Not control flow
3. **Communication tool:** Bridge between users and developers
4. **Basis for design:** Guides system architecture

### **Limitations:**
1. **No control flow:** Doesn't show decisions, loops
2. **No timing:** Can't show sequence or concurrency
3. **Large systems complex:** Too many DFDs for big projects

***

## **Q13. Explain Testing Levels: Unit, Integration, System, Acceptance.**

### **ANSWER (6-8 marks):**

Testing occurs at **four major levels** during software development, each with different objectives and scope.

***

### **1. UNIT TESTING**

**Definition:** Testing **individual components/modules** in isolation.

**Who:** Developers  
**When:** During coding phase  
**Focus:** Internal logic, boundary conditions

**Techniques:**
- White box testing
- Statement/branch coverage
- Stubs/drivers for dependencies

**Example:** Test `calculateTax(income)` function with various income values

**Tools:** JUnit, NUnit, PyTest

**Advantages:** Early bug detection, easier debugging  
**Disadvantages:** Can't detect integration issues

***

### **2. INTEGRATION TESTING**

**Definition:** Testing **interfaces between modules** when combined.

**Who:** Developers/Testers  
**When:** After unit testing  
**Focus:** Module interactions, data flow between modules

**Approaches:**

**a) Big Bang:**
- Integrate all modules at once
- Test the complete system
- ✗ Hard to isolate defects

**b) Top-Down:**
- Start from main module
- Integrate downward (breadth/depth first)
- Use **stubs** (dummy lower modules)
- ✓ Major decisions tested early

**c) Bottom-Up:**
- Start from lowest modules
- Integrate upward
- Use **drivers** (dummy calling programs)
- ✓ Testing can start early

**d) Sandwich (Hybrid):**
- Top-down + Bottom-up simultaneously
- Meet in middle layer

**Example:** Test if `PaymentModule` correctly calls `DatabaseModule.saveTransaction()`

**Advantages:** Detects interface errors  
**Disadvantages:** Requires integration environment

***

### **3. SYSTEM TESTING**

**Definition:** Testing the **complete integrated system** as a whole against requirements.

**Who:** Independent testing team  
**When:** After integration testing  
**Focus:** End-to-end functionality, non-functional requirements

**Types:**

**a) Functional Testing:**
- Verify features against SRS
- Black box testing

**b) Performance Testing:**
- Load testing (expected load)
- Stress testing (beyond limits)
- Scalability testing

**c) Security Testing:**
- Penetration testing
- Vulnerability scanning

**d) Usability Testing:**
- User interface evaluation
- User experience assessment

**e) Compatibility Testing:**
- Different browsers, OS, devices

**f) Recovery Testing:**
- System behavior after failures

**Example:** Test entire e-commerce system: Browse → Add to Cart → Checkout → Payment → Order Confirmation

**Advantages:** Validates complete system  
**Disadvantages:** Expensive, requires full environment

***

### **4. ACCEPTANCE TESTING**

**Definition:** Testing by **customer/end-users** to verify system meets business requirements.

**Who:** Customers, end-users, business analysts  
**When:** After system testing (before deployment)  
**Focus:** Business requirements, user workflows

**Types:**

**a) Alpha Testing:**
- Performed at **developer's site**
- Controlled environment
- Developer observes users
- Identify bugs before release

**b) Beta Testing:**
- Performed at **customer's site**
- Real-world environment
- Large user group (public beta)
- Feedback for improvements

**Example:** Hospital staff test patient management system in pilot ward before hospital-wide deployment

**Acceptance Criteria:** Defined in contract/SRS
- ✓ All critical features working
- ✓ Performance meets targets
- ✓ User satisfaction survey > 80%

**Outcome:** Go/No-Go decision for production deployment

**Advantages:** Real user validation, reduces deployment risk  
**Disadvantages:** Difficult to coordinate, users may lack testing expertise

***

### **Testing Hierarchy (V-Model):**

```
Requirements  ←→  Acceptance Testing
     ↓                    ↑
Design        ←→  System Testing
     ↓                    ↑
Module Design ←→  Integration Testing
     ↓                    ↑
Coding        ←→  Unit Testing
```

**Each development phase has corresponding test phase**

***

## **Q14. Explain Software Maintenance Types.**

### **ANSWER (6-8 marks):**

**Software Maintenance** is modification of software after delivery to:
- Correct faults
- Improve performance
- Adapt to environment changes
- Add new features

**IEEE defines:** Activities to keep software operational and responsive to user needs

***

### **Four Types of Maintenance:**

#### **1. CORRECTIVE MAINTENANCE**

**Definition:** Fixing **defects/bugs** discovered after deployment.

**Triggers:**
- User-reported bugs
- System crashes
- Incorrect outputs

**Examples:**
- Fix login authentication failure
- Correct salary calculation error
- Fix memory leak causing crashes

**Characteristics:**
- **Reactive** (responds to problems)
- **Urgent** (often critical fixes)
- **Most visible** to users

**Percentage:** ~20% of total maintenance effort

***

#### **2. ADAPTIVE MAINTENANCE**

**Definition:** Modifying software to work in **changed environment** (platform, OS, hardware, regulations).

**Triggers:**
- New OS version (Windows 10 → 11)
- Database upgrade (MySQL 5 → 8)
- New regulations (GDPR compliance)
- Hardware changes (cloud migration)

**Examples:**
- Port application from Windows to Linux
- Update tax calculation for new tax laws
- Migrate from on-premise to AWS
- Support new payment gateway API

**Characteristics:**
- **Proactive** (anticipate changes)
- **Planned** (scheduled updates)
- **No functional changes** (same features)

**Percentage:** ~25% of maintenance effort

***

#### **3. PERFECTIVE MAINTENANCE**

**Definition:** Enhancing software with **new features** or **improving existing functionality** based on user requests.

**Triggers:**
- User enhancement requests
- Competitive pressure
- Improved user experience needs

**Examples:**
- Add dark mode to app
- Improve search algorithm speed
- Add export to Excel feature
- Enhance UI/UX design

**Activities:**
- Add new reports
- Optimize database queries
- Improve algorithm efficiency
- Add user-requested features

**Characteristics:**
- **Proactive** (improve system)
- **User-driven** (requests from users)
- **Adds value** (new capabilities)

**Percentage:** ~50% of maintenance effort (largest category!)

***

#### **4. PREVENTIVE MAINTENANCE**

**Definition:** Modifying software to **prevent future problems** and improve **maintainability**.

**Objectives:**
- Improve reliability
- Reduce complexity
- Prevent future failures
- Enhance maintainability

**Examples:**
- Code refactoring (improve structure without changing behavior)
- Update documentation
- Add logging for troubleshooting
- Optimize code to prevent performance degradation
- Replace obsolete libraries

**Activities:**
- **Refactoring:** Restructure code for clarity
- **Reverse engineering:** Understand legacy code
- **Re-engineering:** Modernize architecture
- **Code optimization**

**Characteristics:**
- **Proactive** (prevent problems)
- **Long-term focus**
- **Invisible to users** (no feature changes)

**Percentage:** ~5% of maintenance effort

***

### **Maintenance Effort Distribution:**

```
Perfective:  ████████████████████████ 50%
Adaptive:    ████████████ 25%
Corrective:  ████████ 20%
Preventive:  ██ 5%
```

**Key Insight:** Most maintenance is **enhancements** (perfective), not bug fixes!

***

### **Maintenance Cost Factors:**

1. **Application Domain:** Business apps easier than embedded systems
2. **Staff Skills:** Experienced staff faster
3. **Program Age:** Older systems harder to maintain
4. **Program Structure:** Well-designed code easier
5. **Documentation Quality:** Good docs reduce effort

**K.K. Aggarwal:** *"Maintenance costs typically exceed 60% of total software lifecycle costs."*

***

### **Maintenance Challenges:**

1. **Staff Turnover:** Original developers leave
2. **Poor Documentation:** Hard to understand code
3. **Legacy Technology:** Obsolete tools/languages
4. **Ripple Effects:** Changes cause unintended side effects
5. **Testing Overhead:** Regression testing after changes

***

### **Best Practices:**

✓ Maintain good documentation  
✓ Use version control (Git)  
✓ Write modular, loosely-coupled code  
✓ Comprehensive test suites  
✓ Configuration management

***
# **📚 HIGH-PRIORITY QUESTIONS - Q15 ONWARDS**

***

## **Q15. Explain RAD (Rapid Application Development) Model.**

### **ANSWER (6-8 marks):**

**RAD Model** (James Martin, 1991) is a **high-speed** development approach using **prototyping** and **iterative delivery** with **tight time constraints**.

**Core Concept:** Sacrifice optimization for rapid delivery using CASE tools, reusable components, and small teams.

***

### **Four Phases:**

#### **1. Business Modeling**
- Identify information flow between business functions
- Answer: What info drives business? What info is generated? Who generates/processes it?

**Output:** Business requirements document

***

#### **2. Data Modeling**
- Define data objects and relationships
- Create ER diagrams, data dictionaries

**Activities:**
- Identify data attributes
- Define relationships (one-to-many, many-to-many)
- Normalize databases

**Output:** Data model (ER diagram)

***

#### **3. Process Modeling**
- Transform data objects into information flow
- Create DFDs showing data transformations

**Activities:**
- Define processing logic
- Design algorithms
- Create process descriptions

**Output:** DFDs, process specifications

***

#### **4. Application Generation**
- Build actual system using:
  - 4GL (Fourth Generation Languages)
  - Automatic code generators
  - Reusable components
  - CASE tools

**Focus:** Reuse existing components rather than build from scratch

**Output:** Working application

***

#### **5. Testing & Turnover**
- Test components (already tested as reused)
- Test interfaces
- Rapid deployment

**Emphasis:** Reduced testing time (components pre-tested)

***

### **RAD Team Structure:**

**Multiple Small Teams (2-6 people) work in parallel:**
- Each team develops one component
- **Timeboxing:** Strict deadlines (60-90 days typically)
- Teams coordinate via "construction coordinator"

***

### **Advantages:**

1. **Fast Development:** 60-90 days typical cycle
2. **Reduced Cost:** Reuse components
3. **Quick Feedback:** Frequent prototypes
4. **Flexibility:** Easy to accommodate changes
5. **Measurable Progress:** Visible deliverables

***

### **Disadvantages:**

1. **Requires Skilled Team:** Must be proficient with tools
2. **Customer Commitment:** Continuous availability needed
3. **Not for Large Projects:** Coordination overhead
4. **Technology Dependent:** Requires CASE tools, component libraries
5. **Not Suitable For:**
   - High-performance systems (optimization needed)
   - High-risk projects (rapid = less rigor)
   - Systems with no modular architecture

***

### **When to Use:**

✓ Project can be modularized  
✓ Tight deadlines (2-3 months)  
✓ Budget available for tools  
✓ Skilled, experienced team  
✓ Customer can participate actively  

✗ **Avoid when:**
- System cannot be componentized
- High performance critical
- High technical risks
- Technology unfamiliar to team

***

### **RAD vs. Waterfall:**

| Aspect | RAD | Waterfall |
|--------|-----|-----------|
| **Speed** | 60-90 days | 6-12 months |
| **Approach** | Iterative | Sequential |
| **Prototyping** | Heavy use | Minimal |
| **Reuse** | Extensive | Limited |
| **Requirements** | Evolving | Fixed |
| **Customer Role** | Active | Passive |

***

## **Q16. Explain Prototyping Model with types.**

### **ANSWER (6-8 marks):**

**Prototyping** is building a **working model** of software to understand requirements and validate design before full development.

**Purpose:** Clarify vague requirements, visualize system early, gather feedback

***

### **Prototyping Process:**

```
1. Requirements Gathering (Quick design)
   ↓
2. Build Prototype (Quick, incomplete version)
   ↓
3. Customer Evaluation (Use and provide feedback)
   ↓
4. Refine Prototype (Incorporate changes)
   ↓ (Iterate steps 2-4)
5. Final Product (Build actual system)
```

***

### **Types of Prototypes:**

#### **1. Throwaway/Rapid Prototype**

**Characteristics:**
- Built **quickly** with shortcuts
- Used **only for requirements validation**
- **Discarded** after requirements clear
- Not part of final system

**Purpose:** Understand requirements, not implementation

**Example:**
- Paper mockups for UI
- Quick HTML/CSS screens (no backend)
- PowerPoint demos

**Advantages:**
- Fast feedback
- Low cost
- No maintenance burden

**Disadvantages:**
- Wasted effort (thrown away)
- Customer may not understand it's temporary

***

#### **2. Evolutionary Prototype**

**Characteristics:**
- Starts as basic version
- **Continuously refined**
- **Becomes final product**
- Incremental additions

**Process:**
1. Build core features (prototype)
2. Deploy and gather feedback
3. Add features incrementally
4. Eventually becomes production system

**Example:**
- Release MVP (Minimum Viable Product)
- Add features based on usage
- Gmail started as prototype, evolved continuously

**Advantages:**
- No wasted effort
- Early deployment
- Continuous improvement

**Disadvantages:**
- May have architectural issues (not designed for long-term)
- Technical debt accumulation

***

#### **3. Incremental Prototype**

**Characteristics:**
- System divided into **independent modules**
- Each module prototyped separately
- Modules integrated progressively

**Example:**
- Prototype UI → Get feedback
- Prototype backend → Get feedback
- Integrate both → Get feedback

***

#### **4. Extreme Prototype**

**Used for:** Web applications

**Three Layers:**
1. **Prototype 1:** HTML pages (static)
2. **Prototype 2:** Add functionality (simulated services)
3. **Prototype 3:** Implement actual services

***

### **Advantages of Prototyping:**

1. **Clarifies Requirements:** Visual model easier to understand
2. **Early Feedback:** Catch issues before expensive development
3. **User Involvement:** Active participation increases satisfaction
4. **Reduces Risk:** Validate feasibility early
5. **Better Design:** Explore alternatives cheaply

***

### **Disadvantages:**

1. **Customer Expectations:** May expect prototype = final system
2. **Incomplete Specifications:** May skip documentation
3. **Over-reliance:** May continue iterating indefinitely
4. **Quality Issues:** Rapid prototypes often have poor code quality
5. **Management Difficulty:** Hard to plan/estimate

**Pressman warns:** *"Quick and dirty prototypes must be thrown away, not polished into production systems."*

***

### **When to Use:**

✓ **Use when:**
- Requirements unclear
- User interface critical
- High user interaction
- New technology (feasibility test)

✗ **Avoid when:**
- Requirements well-defined
- Real-time, embedded systems (difficult to prototype)
- Large-scale systems (prototyping overhead)

***

## **Q17. Explain Risk Management in Software Projects.**

### **ANSWER (8-10 marks):**

**Risk** is any adverse event that can negatively impact project success (schedule, budget, quality).

**Risk Management:** Systematic process to identify, analyze, and control risks.

***

### **Categories of Risks:**

#### **1. Project Risks**
- Affect schedule/resources
- **Examples:** Staff turnover, budget cuts, customer delays

#### **2. Technical Risks**
- Threaten quality/performance
- **Examples:** Technology complexity, integration issues, performance bottlenecks

#### **3. Business Risks**
- Threaten project viability
- **Examples:** Competitor releases similar product, market changes, management changes

***

### **Risk Management Process:**

#### **Step 1: Risk Identification**

**Techniques:**
- Brainstorming sessions
- Checklists (common risks)
- Expert interviews
- Historical data analysis

**Example Risks:**
- "Senior developer may leave project"
- "Third-party API may be unreliable"
- "Requirements may change frequently"

***

#### **Step 2: Risk Analysis**

**Assess two dimensions:**

**a) Probability (Likelihood):**
- High (>70%)
- Medium (30-70%)
- Low (<30%)

**b) Impact (Consequence):**
- Catastrophic (project failure)
- Critical (major delays)
- Marginal (minor delays)
- Negligible (minimal effect)

**Risk Exposure = Probability × Impact**

**Example:**
```
Risk: "Senior developer leaves"
Probability: 30% (Medium)
Impact: High ($50K cost, 2 months delay)
Risk Exposure: 0.30 × $50K = $15K

Risk: "Requirements change"
Probability: 80% (High)
Impact: Medium ($20K cost)
Risk Exposure: 0.80 × $20K = $16K
```

***

#### **Step 3: Risk Prioritization**

**Risk Matrix:**
```
         Impact →
    │ Low  │ Med  │ High │
────┼──────┼──────┼──────┤
High│ Med  │ High │ CRIT │ P
  ↓ │      │      │      │ r
Med │ Low  │ Med  │ High │ o
    │      │      │      │ b
Low │ Ign  │ Low  │ Med  │
```

**Priority:** CRIT > High > Med > Low > Ignore

***

#### **Step 4: Risk Planning (Mitigation Strategies)**

**Four Strategies:**

**a) Avoidance:**
- Eliminate risk by changing plan
- **Example:** Use proven technology instead of experimental

**b) Mitigation (Reduction):**
- Reduce probability or impact
- **Example:** Cross-train team members (if one leaves, others can continue)

**c) Acceptance:**
- Acknowledge risk, prepare contingency
- **Example:** Budget reserve for cost overruns

**d) Transfer:**
- Shift risk to third party
- **Example:** Insurance, outsourcing, fixed-price contracts

***

#### **Step 5: Risk Monitoring**

**Activities:**
- Track identified risks
- Identify new risks
- Execute mitigation plans
- Review effectiveness

**Indicators:** Risk triggers that signal risk becoming reality

**Example:**
- Trigger: "Team member starts job hunting" → Execute retention plan

***

### **Risk Management Plan Document:**

**Contents:**
1. Risk ID
2. Description
3. Probability
4. Impact
5. Risk Exposure
6. Mitigation Strategy
7. Contingency Plan
8. Owner (responsible person)
9. Status

***

### **Example Risk Table:**

| ID | Risk | Prob | Impact | Exposure | Mitigation | Owner |
|----|------|------|--------|----------|------------|-------|
| R1 | Staff turnover | 30% | High | $15K | Cross-training, retention bonus | HR Mgr |
| R2 | Req. changes | 80% | Med | $16K | Agile approach, change control | PM |
| R3 | API failure | 20% | Crit | $30K | Build fallback, vendor SLA | Tech Lead |

***

### **Boehm's Top 10 Software Risks:**

1. Personnel shortfalls
2. Unrealistic schedules/budgets
3. Wrong software functions
4. Wrong user interface
5. Gold-plating (unnecessary features)
6. Requirements changes
7. Shortfalls in external components
8. Shortfalls in external tasks
9. Real-time performance issues
10. Straining computer science capabilities

***

### **Benefits of Risk Management:**

✓ Proactive problem prevention  
✓ Better decision-making  
✓ Cost savings (early mitigation cheaper)  
✓ Improved project success rate  
✓ Stakeholder confidence

***

## **Q18. Explain CMM (Capability Maturity Model).**

### **ANSWER (8-10 marks):**

**CMM** (Capability Maturity Model) developed by **SEI (Software Engineering Institute), Carnegie Mellon University** is a framework for **improving software process maturity**.

**Purpose:** Assess organization's software development capability and provide roadmap for improvement.

***

### **Five Maturity Levels:**

***

#### **Level 1: INITIAL (Chaotic)**

**Characteristics:**
- **Ad-hoc, chaotic** process
- Success depends on **individual heroics**
- No defined processes
- **Unpredictable** outcomes
- **Fire-fighting** mode

**Process:** Undefined, reactive

**Capability:** Unpredictable results, often delayed/over-budget

**Example:** Small startup, no formal procedures

**Percentage of Organizations:** ~25%

***

#### **Level 2: REPEATABLE (Managed)**

**Characteristics:**
- Basic **project management** processes
- Success can be **repeated** for similar projects
- **Tracking:** Cost, schedule, functionality
- **Discipline** to repeat earlier successes

**Key Process Areas (KPAs):**
1. **Requirements Management:** Track and control changes
2. **Project Planning:** Estimate effort, schedule
3. **Project Tracking:** Monitor progress
4. **Subcontract Management:** Manage vendors
5. **Quality Assurance:** Review processes
6. **Configuration Management:** Version control

**Focus:** Project-level processes

**Example:** Team follows basic PM practices, uses version control

**Percentage:** ~50%

***

#### **Level 3: DEFINED (Standardized)**

**Characteristics:**
- **Organization-wide** standard process
- Projects **tailor** standard process
- **Documented** procedures
- Training programs
- **Proactive** process improvement

**Key Process Areas:**
1. **Organization Process Focus:** Improve processes
2. **Organization Process Definition:** Standard process library
3. **Training Program:** Skill development
4. **Integrated Software Management:** Tailor standard process
5. **Peer Reviews:** Code/design reviews
6. **Intergroup Coordination:** Team collaboration

**Focus:** Organization-level processes

**Example:** Company has "Development Handbook", all teams follow it

**Percentage:** ~15%

***

#### **Level 4: MANAGED (Quantitatively Controlled)**

**Characteristics:**
- **Quantitative goals** for quality/performance
- **Metrics collected:** Defect rates, productivity
- **Statistical process control**
- **Predictable** processes

**Key Process Areas:**
1. **Quantitative Process Management:** Measure and control
2. **Software Quality Management:** Quality targets with data

**Metrics Examples:**
- Defects per KLOC
- Productivity (FP per person-month)
- Review efficiency

**Focus:** Quantitative management

**Example:** "Target: <5 defects per KLOC, measure weekly"

**Percentage:** ~5%

***

#### **Level 5: OPTIMIZING (Continuous Improvement)**

**Characteristics:**
- **Continuous process improvement**
- Feedback from process/technology
- **Prevent defects** proactively
- **Innovation** encouraged

**Key Process Areas:**
1. **Defect Prevention:** Root cause analysis
2. **Technology Change Management:** Adopt new tools/methods
3. **Process Change Management:** Continuous optimization

**Focus:** Innovation and optimization

**Example:** Google, Microsoft (selected teams)

**Percentage:** <1%

***

### **CMM Level Progression:**

```
Level 5: OPTIMIZING      🏆 Focus: Innovation
         ↑ (Continuous improvement)

Level 4: MANAGED         📊 Focus: Quantification
         ↑ (Measure and control)

Level 3: DEFINED         📖 Focus: Standardization
         ↑ (Organization-wide process)

Level 2: REPEATABLE      ✅ Focus: Project Management
         ↑ (Discipline and tracking)

Level 1: INITIAL         ❌ Focus: Individual heroics
         (Chaotic)
```

***

### **Maturity Level Characteristics Table:**

| Level | Name | Process | Predictability | Focus |
|-------|------|---------|----------------|-------|
| **1** | Initial | Chaotic | Unpredictable | Individuals |
| **2** | Repeatable | Disciplined | Some | Project Mgmt |
| **3** | Defined | Standard | Good | Organization |
| **4** | Managed | Measured | High | Quantification |
| **5** | Optimizing | Improving | Very High | Innovation |

***

### **Benefits of CMM:**

1. **Quality Improvement:** Higher levels → fewer defects
2. **Predictability:** Better schedule/cost estimates
3. **Productivity:** Higher maturity → higher productivity
4. **Customer Satisfaction:** Reliable delivery
5. **Competitive Advantage:** CMM certification (contract requirement)

**Research (SEI):**
- Level 1→3: **2× productivity**, **50% reduction** in defects
- Level 3→5: **80% reduction** in post-release defects

***

### **CMM Assessment:**

**SCE (Software Capability Evaluation):** Assess organization's CMM level

**Process:**
1. Review documentation
2. Interview staff
3. Check KPAs compliance
4. Assign maturity level

**Result:** "XYZ Corp is CMM Level 3"

***

### **CMM vs. CMMI:**

**CMMI (CMM Integration)** released 2000, replaces CMM:
- Integrates software, systems engineering, supplier sourcing
- 5 maturity levels (same structure)
- 22 process areas (expanded KPAs)

***

### **Limitations:**

1. **Time-consuming:** Takes years to move levels
2. **Expensive:** Consulting, training, audits
3. **Bureaucracy:** Can add overhead
4. **Not suitable for:** Small organizations, agile environments (debated)

***

## **Q19. Explain ISO 9000 Standards for Software.**

### **ANSWER (6-8 marks):**

**ISO 9000** is a family of **quality management standards** developed by **International Organization for Standardization (ISO)**.

**Purpose:** Ensure organizations consistently deliver products/services meeting customer and regulatory requirements.

***

### **ISO 9000 Family Components:**

#### **1. ISO 9000**
- **Quality Management Fundamentals**
- Terminology and concepts
- Foundation for other standards

#### **2. ISO 9001** (Most Important)
- **Quality Management Systems - Requirements**
- Specifies requirements for QMS
- **Certifiable standard** (organizations get "ISO 9001 certified")

#### **3. ISO 9004**
- Guidelines for performance improvement
- Not for certification (guidance only)

***

### **ISO 9001 Principles (8 Quality Management Principles):**

1. **Customer Focus:** Understand and meet customer needs
2. **Leadership:** Establish unity of purpose
3. **Engagement of People:** Involve all staff
4. **Process Approach:** Manage activities as processes
5. **Improvement:** Continuous improvement culture
6. **Evidence-based Decision Making:** Data-driven decisions
7. **Relationship Management:** Manage supplier relationships
8. **System Approach:** Interrelated processes as a system

***

### **ISO 9001 Requirements (Clauses):**

#### **Clause 4: Context of Organization**
- Understand organization and context
- Interested parties and requirements
- Define QMS scope

#### **Clause 5: Leadership**
- Management commitment
- Quality policy
- Roles, responsibilities, authorities

#### **Clause 6: Planning**
- Risk/opportunity planning
- Quality objectives
- Planning changes

#### **Clause 7: Support**
- Resources (people, infrastructure, environment)
- Competence and awareness
- Communication
- **Documented information** (key for software: maintain docs)

#### **Clause 8: Operation**
- Operational planning and control
- Requirements for products/services
- Design and development (critical for software)
- Control of external providers
- Production and service provision
- Release of products/services
- Control of nonconforming outputs

#### **Clause 9: Performance Evaluation**
- Monitoring, measurement, analysis
- Internal audits
- Management review

#### **Clause 10: Improvement**
- Nonconformity and corrective action
- Continual improvement

***

### **ISO 9001 for Software Development:**

**Key Requirements:**

**1. Documentation:**
- **Quality Manual:** QMS overview
- **Procedures:** How processes work
- **Work Instructions:** Detailed task steps
- **Records:** Evidence of conformance

**Software Example:**
- Requirements document (SRS)
- Design documents
- Test plans/reports
- Change logs

**2. Design & Development Control:**
- **Planning:** Define design stages
- **Inputs:** Requirements clearly specified
- **Outputs:** Design documents, code
- **Review:** Design reviews at stages
- **Verification:** Design meets requirements
- **Validation:** Product meets user needs
- **Changes:** Controlled change management

**3. Process Control:**
- Defined software development process
- **Reviews:** Code reviews, design reviews
- **Testing:** Unit, integration, system testing
- **Version Control:** Git, SVN

**4. Corrective/Preventive Action:**
- **Bug tracking:** Defect management system
- **Root cause analysis:** Why did defect occur?
- **Prevention:** Process improvements

***

### **ISO 9001 Certification Process:**

**Steps:**
1. **Gap Analysis:** Compare current practices vs. ISO requirements
2. **Implementation:** Establish QMS, document processes
3. **Internal Audit:** Self-assessment
4. **Management Review:** Senior leadership review
5. **Certification Audit:** External auditor assessment
   - Stage 1: Documentation review
   - Stage 2: Implementation verification
6. **Certification:** Issued if compliant (valid 3 years)
7. **Surveillance Audits:** Annual checks

***

### **Benefits:**

1. **Quality Assurance:** Consistent processes → fewer defects
2. **Customer Confidence:** "ISO certified" = quality commitment
3. **Market Access:** Some contracts require ISO certification
4. **Process Improvement:** Documented processes easier to improve
5. **Efficiency:** Standardized procedures reduce waste

***

### **Limitations:**

1. **Bureaucracy:** Heavy documentation burden
2. **Cost:** Certification expensive ($10K-$50K+)
3. **Time:** 6-18 months to implement
4. **Maintenance:** Ongoing audits and updates
5. **Not Specific:** Generic standard, not software-specific

***

### **ISO 9001 vs. CMM:**

| Aspect | ISO 9001 | CMM |
|--------|----------|-----|
| **Focus** | Quality Management System | Process maturity |
| **Scope** | All industries | Software-specific |
| **Levels** | Pass/Fail (certified or not) | 5 maturity levels |
| **Origin** | ISO (international) | SEI (US) |
| **Emphasis** | Documentation | Capability improvement |
| **Assessment** | External audit | Self/external assessment |

**Both can coexist:** Organization can be ISO 9001 certified AND CMM Level 3

***

## **Q20. Explain Configuration Management.**

### **ANSWER (6-8 marks):**

**Configuration Management (CM)** is a set of activities designed to **control change** by identifying work products, managing versions, and ensuring consistency throughout the software lifecycle.

**IEEE Definition:** *"Identifying configuration items, controlling changes, recording/reporting status, verifying completeness/correctness."*

***

### **Why Configuration Management?**

**Problems Without CM:**
- Multiple developers overwrite each other's code
- Can't recreate older versions (customer finds bug in v2.1, can't reproduce)
- Don't know which version is in production
- Changes made without documentation
- Integration conflicts

**Example Chaos:**
```
Developer A: "I fixed that bug"
Developer B: "What bug? I don't see your fix"
Manager: "Customer wants v2.3, what's in it?"
Team: "Uh... we don't remember"
```

***

### **Configuration Items (CIs):**

**Definition:** Any artifact controlled by CM.

**Examples:**
- Source code files
- Design documents (UML diagrams, architecture docs)
- Requirements documents (SRS)
- Test plans and test cases
- Build scripts, makefiles
- Database schemas
- User manuals
- Project plans

**Baseline:** Approved version of CI that serves as reference for future changes

***

### **Configuration Management Activities:**

#### **1. Identification**

**Purpose:** Define what to control

**Activities:**
- Identify all CIs
- Assign unique identifiers (naming scheme)
- Define baseline versions

**Example Naming:**
```
ProjectX_SRS_v1.2.doc
ProjectX_Design_Module_Authentication_v2.0.pdf
ProjectX_src_login.cpp_v3.5
```

**Baseline Types:**
- **Functional Baseline:** Approved requirements
- **Allocated Baseline:** Approved design
- **Product Baseline:** Approved delivered system

***

#### **2. Version Control**

**Purpose:** Track changes to CIs over time

**Tools:** Git, SVN, Mercurial, Perforce

**Concepts:**

**Repository:** Central storage for all versions

**Check-out/Check-in:**
- Check-out: Get copy to work on
- Check-in: Submit changes (new version created)

**Versioning Scheme:**
```
Major.Minor.Patch
Example: v2.3.5
- Major (2): Incompatible changes
- Minor (3): New features, backward compatible
- Patch (5): Bug fixes
```

**Branching:**
```
main (production)
  ├─ develop (integration)
  │   ├─ feature-login (developer A)
  │   └─ feature-payment (developer B)
  └─ hotfix-security (urgent fix)
```

***

#### **3. Change Control**

**Purpose:** Manage changes systematically

**Change Control Board (CCB):**
- Committee that approves/rejects changes
- Members: Project manager, architects, customer rep, QA lead

**Change Request Process:**
```
1. Submit Change Request (CR)
   ↓
2. Impact Analysis (cost, schedule, risk)
   ↓
3. CCB Review
   ↓ (Approved / Rejected)
4. Implement Change
   ↓
5. Verify Change (testing)
   ↓
6. Update Baseline
```

**Change Request Form:**
- CR ID
- Requestor
- Description
- Rationale (why needed)
- Priority (critical, high, medium, low)
- Impact analysis
- CCB decision
- Implementation status

**Example:**
```
CR-234: Add "Forgot Password" feature
Priority: High
Impact: 40 hours, $5K, 1-week delay
CCB Decision: Approved
Status: Implemented in v2.4
```

***

#### **4. Status Accounting**

**Purpose:** Track status of CIs and changes

**Reports:**
- **CI Status:** What's the current version?
- **Change Status:** Which CRs approved/pending/rejected?
- **Baseline Status:** What's in each baseline?

**Example Report:**
```
CI: login.cpp
Current Version: v3.7
Last Modified: 2024-12-01
Modified By: Developer A
Changes: Fixed null pointer bug (CR-245)
```

***

#### **5. Auditing**

**Purpose:** Verify CI integrity and completeness

**Types:**

**Physical Audit:**
- Verify actual CIs match records
- Check completeness (all required docs present)

**Functional Audit:**
- Verify CIs meet requirements
- Test that baseline works as documented

**Example:**
- Audit before release: "Does v3.0 contain all features in SRS?"

***

### **Configuration Management Plan:**

**Document specifying:**
1. Which items under CM
2. Naming conventions
3. Version control procedures
4. CCB composition and procedures
5. Baseline schedule
6. Tools used (Git, JIRA)
7. Roles and responsibilities

***

### **Benefits:**

1. **Control:** Prevent unauthorized changes
2. **Traceability:** Know what changed, when, why, by whom
3. **Reproducibility:** Recreate any version
4. **Parallel Development:** Multiple developers work simultaneously
5. **Quality:** Consistent, controlled process
6. **Compliance:** Audit trail for regulations

***

### **Tools:**

**Version Control:**
- Git (distributed)
- SVN (centralized)
- Mercurial

**Build Management:**
- Maven, Gradle (Java)
- Make, CMake (C/C++)

**Issue Tracking:**
- JIRA, Bugzilla
- GitHub Issues

**CI/CD:**
- Jenkins, GitLab CI
- Automated build/test/deploy

***

### **Best Practices:**

✓ Commit frequently with meaningful messages  
✓ Tag releases (v1.0, v2.0)  
✓ Use branches for features  
✓ Never commit directly to main/production  
✓ Document all changes  
✓ Automate builds

***
# **📚 HIGH-PRIORITY QUESTIONS - Q21 ONWARDS**

***

## **Q21. Explain Project Scheduling: Gantt Charts and CPM/PERT.**

### **ANSWER (8-10 marks):**

**Project Scheduling** determines the **timeline, sequence, and dependencies** of project activities.

***

### **GANTT CHARTS**

**Definition:** **Bar chart** showing project schedule with tasks on Y-axis and time on X-axis.

**Developed by:** Henry Gantt (1910s)

***

#### **Components:**

1. **Tasks/Activities:** Listed vertically
2. **Time Scale:** Horizontal axis (days/weeks/months)
3. **Bars:** Horizontal bars showing duration
4. **Milestones:** Diamond symbols for key events
5. **Dependencies:** Arrows showing task relationships (optional)

***

#### **Example Gantt Chart:**

```
Tasks              Week 1  Week 2  Week 3  Week 4  Week 5
──────────────────┼───────┼───────┼───────┼───────┼───────
1. Requirements   ████████
                           ↓
2. Design                  ████████████
                                    ↓
3. Coding                          ████████████████
                                            ↓
4. Testing                                 ████████████
                                                    ↓
5. Deployment                                      ◆ (Milestone)
```

***

#### **Advantages:**

1. **Visual Clarity:** Easy to understand at a glance
2. **Progress Tracking:** Shade bars to show completion %
3. **Simple:** No complex calculations
4. **Communication:** Good for stakeholders

***

#### **Disadvantages:**

1. **No Critical Path:** Can't identify which tasks are critical
2. **Complex Dependencies:** Hard to show intricate relationships
3. **No Resource Management:** Doesn't show resource allocation
4. **Inflexible:** Updates require redrawing

***

### **CPM (Critical Path Method)**

**Definition:** **Network analysis** technique to identify the **longest path** (critical path) through project activities.

**Developed by:** DuPont Corporation (1957)

***

#### **Key Concepts:**

**Activity:** Task to be performed  
**Event/Node:** Start/end point of activity  
**Critical Path:** Longest sequence of dependent activities (determines minimum project duration)  
**Slack/Float:** Time an activity can be delayed without delaying project

***

#### **CPM Network Diagram:**

**Notation:** **Activity on Arrow (AOA)**

```
        5 days        3 days
   ┌────[A]────┐  ┌───[C]───┐
Start              E1         End
   └────[B]────┘  └───[D]───┘
        4 days        6 days
```

**Paths:**
- Start → A → C → End = 5 + 3 = **8 days**
- Start → B → D → End = 4 + 6 = **10 days** ← **Critical Path** (longest)

**Project Duration = 10 days** (critical path length)

***

#### **CPM Calculations:**

**For Each Activity:**

**1. Earliest Start (ES):** Earliest time activity can start
**2. Earliest Finish (EF):** ES + Duration
**3. Latest Start (LS):** Latest time activity can start without delaying project
**4. Latest Finish (LF):** LS + Duration
**5. Slack (Float):** LS - ES (or LF - EF)

**Critical Activities:** Slack = 0 (no delay possible)

***

#### **Example:**

**Project Activities:**

| Activity | Duration | Predecessor |
|----------|----------|-------------|
| A | 3 | - |
| B | 4 | A |
| C | 2 | A |
| D | 5 | B, C |

**Network:**
```
      B(4)
    ↗      ↘
A(3)         D(5)
    ↘      ↗
      C(2)
```

**Forward Pass (Calculate ES, EF):**
- A: ES=0, EF=0+3=3
- B: ES=3 (after A), EF=3+4=7
- C: ES=3 (after A), EF=3+2=5
- D: ES=7 (max of B,C), EF=7+5=12

**Project Duration = 12 days**

**Backward Pass (Calculate LS, LF):**
- D: LF=12, LS=12-5=7
- B: LF=7, LS=7-4=3
- C: LF=7, LS=7-2=5
- A: LF=3, LS=3-3=0

**Slack:**
- A: 0-0 = **0** (Critical)
- B: 3-3 = **0** (Critical)
- C: 5-3 = **2 days** (non-critical)
- D: 7-7 = **0** (Critical)

**Critical Path: A → B → D** (all have slack = 0)

***

#### **Advantages of CPM:**

1. **Identifies Critical Path:** Focus on activities that determine project duration
2. **Shows Dependencies:** Complex relationships clear
3. **What-if Analysis:** "If B delays 2 days, what happens?"
4. **Resource Optimization:** Focus resources on critical activities

***

#### **Disadvantages:**

1. **Complexity:** Requires training to create/interpret
2. **Assumes Deterministic:** Activity durations fixed (unrealistic)
3. **Difficult for Large Projects:** Network becomes complex

***

### **PERT (Program Evaluation and Review Technique)**

**Extension of CPM** that handles **uncertainty** in activity durations.

**Developed by:** US Navy (1958) for Polaris missile project

***

#### **Key Difference from CPM:**

**CPM:** Activity duration = fixed value  
**PERT:** Activity duration = **three estimates**

***

#### **PERT Three Estimates:**

1. **Optimistic (a):** Best-case duration (if everything goes perfectly)
2. **Most Likely (m):** Realistic duration (most probable)
3. **Pessimistic (b):** Worst-case duration (if everything goes wrong)

**Expected Duration (te):**
\[ t_e = \frac{a + 4m + b}{6} \]

**Standard Deviation (σ):**
\[ \sigma = \frac{b - a}{6} \]

**Variance (σ²):**
\[ \sigma^2 = \left(\frac{b - a}{6}\right)^2 \]

***

#### **Example:**

**Activity A:**
- Optimistic (a) = 2 days
- Most Likely (m) = 5 days
- Pessimistic (b) = 8 days

**Expected Duration:**
\[ t_e = \frac{2 + 4(5) + 8}{6} = \frac{30}{6} = 5 \text{ days} \]

**Standard Deviation:**
\[ \sigma = \frac{8 - 2}{6} = 1 \text{ day} \]

**Interpretation:** Activity A will likely take 5 days, but could vary ±1 day.

***

#### **PERT for Project Duration:**

**Sum expected durations along critical path:**
\[ T_e = \sum t_e \text{ (critical path activities)} \]

**Project Standard Deviation:**
\[ \sigma_{project} = \sqrt{\sum \sigma^2 \text{ (critical path activities)}} \]

**Probability Calculations:**

Using **normal distribution**:
\[ Z = \frac{T_{target} - T_e}{\sigma_{project}} \]

**Example:** What's probability of finishing in 20 days if Te=18, σ=2?
\[ Z = \frac{20 - 18}{2} = 1.0 \]
From Z-table: P(Z≤1.0) = 84% chance

***

#### **Advantages of PERT:**

1. **Handles Uncertainty:** Realistic for complex projects
2. **Probability Analysis:** "90% chance of finishing by X date"
3. **Risk Assessment:** High σ = high risk activity

***

#### **Disadvantages:**

1. **Subjective Estimates:** Three estimates may be guesses
2. **Assumes Beta Distribution:** May not fit all situations
3. **More Complex:** Calculations tedious

***

### **CPM vs. PERT Comparison:**

| Aspect | CPM | PERT |
|--------|-----|------|
| **Duration** | Deterministic (fixed) | Probabilistic (3 estimates) |
| **Use Case** | Construction, manufacturing | R&D, new technology |
| **Focus** | Time and cost | Time only |
| **Certainty** | High certainty | High uncertainty |
| **Calculation** | Simple | Complex (statistics) |

***

## **Q22. Explain ER (Entity-Relationship) Diagrams.**

### **ANSWER (6-8 marks):**

**ER Diagram** is a **visual representation** of data and relationships between data in a database.

**Developed by:** Peter Chen (1976)

**Purpose:** Design database schema logically before physical implementation

***

### **Basic Components:**

#### **1. Entity**

**Definition:** Object or thing with independent existence (real or abstract)

**Notation:** Rectangle

**Types:**
- **Strong Entity:** Exists independently (e.g., Student, Book)
- **Weak Entity:** Depends on another entity (e.g., Dependents of Employee)
  - Notation: **Double rectangle**

**Example:** `Student`, `Course`, `Instructor`

***

#### **2. Attribute**

**Definition:** Property or characteristic of entity

**Notation:** Oval/Ellipse

**Types:**

**a) Simple vs. Composite:**
- **Simple:** Cannot be divided (e.g., Age)
- **Composite:** Can be divided (e.g., Name = First + Middle + Last)

**b) Single-valued vs. Multi-valued:**
- **Single-valued:** One value (e.g., Student ID)
- **Multi-valued:** Multiple values (e.g., Phone Numbers)
  - Notation: **Double oval**

**c) Stored vs. Derived:**
- **Stored:** Stored in database (e.g., Date of Birth)
- **Derived:** Calculated from other attributes (e.g., Age from DOB)
  - Notation: **Dashed oval**

**d) Key Attribute:**
- **Primary Key:** Uniquely identifies entity (e.g., Student_ID)
  - Notation: **Underlined**

**Example:** For Student entity: `Student_ID` (key), `Name`, `DOB`, `Age` (derived)

***

#### **3. Relationship**

**Definition:** Association between entities

**Notation:** Diamond

**Example:** Student **enrolls in** Course

***

### **Cardinality (Relationship Types):**

**Defines how many instances of one entity relate to instances of another**

***

#### **1. One-to-One (1:1)**

One entity instance relates to **exactly one** instance of another

**Example:** `Employee` ↔ `Passport`
- Each employee has one passport
- Each passport belongs to one employee

**Notation:**
```
[Employee] ──1────< manages >────1──[Department]
```

***

#### **2. One-to-Many (1:N)**

One entity instance relates to **many** instances of another

**Example:** `Professor` ↔ `Students`
- One professor advises many students
- Each student has one advisor

**Notation:**
```
[Professor] ──1────< advises >────N──[Student]
```

***

#### **3. Many-to-One (N:1)**

**Many** instances relate to **one** instance

**Example:** `Students` ↔ `University`
- Many students belong to one university

***

#### **4. Many-to-Many (M:N)**

**Many** instances relate to **many** instances

**Example:** `Students` ↔ `Courses`
- One student enrolls in many courses
- One course has many students

**Notation:**
```
[Student] ──M────< enrolls >────N──[Course]
```

**Implementation:** Requires **junction table** in database
```
Student_Course (Student_ID, Course_ID, Grade)
```

***

### **Participation Constraints:**

**Total Participation (Mandatory):**
- Every entity **must** participate in relationship
- Notation: **Double line**
- Example: Every employee **must** work in some department

**Partial Participation (Optional):**
- Entity **may or may not** participate
- Notation: **Single line**
- Example: Employee may or may not manage a project

***

### **Complete ER Diagram Example: University System**

```
┌────────────┐               ┌────────────┐
│  STUDENT   │               │   COURSE   │
├────────────┤               ├────────────┤
│ Student_ID │(PK)           │ Course_ID  │(PK)
│ Name       │               │ Title      │
│ DOB        │               │ Credits    │
│ (Age)      │(derived)      │ Department │
└─────┬──────┘               └─────┬──────┘
      │                            │
      │M                          N│
      │        ┌─────────┐         │
      └────────│ ENROLLS │─────────┘
               ├─────────┤
               │ Grade   │(attribute of relationship)
               │ Semester│
               └─────────┘

┌────────────┐               ┌────────────┐
│ PROFESSOR  │               │ DEPARTMENT │
├────────────┤               ├────────────┤
│Professor_ID│(PK)           │  Dept_ID   │(PK)
│ Name       │               │  Name      │
│ Office     │               │  Building  │
└─────┬──────┘               └─────┬──────┘
      │1                          1│
      │        ┌─────────┐         │
      └────────│  HEADS  │─────────┘
               └─────────┘
```

**Cardinalities:**
- Student **enrolls** Course: **M:N** (junction table needed)
- Professor **heads** Department: **1:1** (one professor heads one dept)

***

### **Steps to Create ER Diagram:**

1. **Identify Entities:** Nouns in requirements (Student, Course, Professor)
2. **Identify Attributes:** Properties (Student has ID, Name, DOB)
3. **Identify Relationships:** Verbs (Student enrolls Course, Professor teaches Course)
4. **Determine Cardinality:** How many? (1:1, 1:N, M:N)
5. **Identify Keys:** What uniquely identifies each entity?
6. **Add Constraints:** Total/partial participation

***

### **ER to Relational Schema Conversion:**

**Entities → Tables:**
```sql
Student (Student_ID, Name, DOB)
Course (Course_ID, Title, Credits, Department)
```

**Relationships:**
- **1:1:** Add foreign key to either table
- **1:N:** Add foreign key to "many" side
- **M:N:** Create junction table
```sql
Enrollment (Student_ID, Course_ID, Grade, Semester)
  -- Foreign keys: Student_ID → Student, Course_ID → Course
```

***

### **Advantages:**

✓ **Visual clarity:** Easy to understand database structure  
✓ **Communication tool:** Bridge between users and developers  
✓ **Design phase:** Catch errors before implementation  
✓ **Documentation:** Serves as database blueprint

***

### **Limitations:**

✗ No procedural logic (queries, transactions)  
✗ Can become complex for large systems  
✗ Different notations exist (Chen, Crow's Foot, UML)

***

## **Q23. Explain Use Case Diagrams with example.**

### **ANSWER (6-8 marks):**

**Use Case Diagram** is a **behavioral UML diagram** showing **interactions** between **actors** and **system** to achieve goals.

**Purpose:** Capture functional requirements from user perspective

***

### **Components:**

#### **1. Actor**

**Definition:** External entity interacting with system (user, external system, hardware)

**Notation:** Stick figure

**Types:**
- **Primary Actor:** Initiates use case (e.g., Customer)
- **Secondary Actor:** Provides services (e.g., Payment Gateway)

**Example:** `Customer`, `Admin`, `Bank System`

***

#### **2. Use Case**

**Definition:** Specific functionality/service system provides

**Notation:** Oval/Ellipse with name inside

**Naming:** Verb phrase from actor's perspective (e.g., "Place Order", "Generate Report")

**Example:** `Login`, `Search Products`, `Checkout`

***

#### **3. System Boundary**

**Definition:** Rectangle representing system scope

**Shows:** What's **inside** system vs. **outside** (actors)

**Notation:** Rectangle with system name

***

#### **4. Relationships**

**a) Association:**
- **Solid line** connecting actor to use case
- Shows actor participates in use case

**b) Include (<<include>>):**
- **Dashed arrow** with stereotype <<include>>
- Base use case **always** invokes included use case
- **Example:** "Place Order" **includes** "Validate Payment"

**c) Extend (<<extend>>):**
- **Dashed arrow** with stereotype <<extend>>
- Optional behavior (may or may not occur)
- **Example:** "Purchase Product" **extends** to "Apply Coupon Code" (optional)

**d) Generalization:**
- **Solid line with hollow triangle** (inheritance)
- Specialized use case inherits from general use case
- **Example:** "Credit Card Payment" and "PayPal Payment" generalize "Make Payment"

***

### **Complete Example: Online Shopping System**

```
           ┌──────────────────────────────────────┐
           │    Online Shopping System            │
           │                                      │
           │   ┌───────────────┐                 │
  Customer ────│ Browse Products│                 │
    (👤)   │   └───────────────┘                 │
           │           │                          │
           │           │ <<include>>              │
           │           ↓                          │
           │   ┌───────────────┐                 │
           ────│  Search        │                 │
           │   └───────────────┘                 │
           │                                      │
           │   ┌───────────────┐                 │
           ────│  Place Order   │                 │
           │   └───────┬───────┘                 │
           │           │ <<include>>              │
           │           ↓                          │
           │   ┌───────────────┐                 │
           │   │Validate Payment│←──────────────────Payment
           │   └───────────────┘                 │  Gateway
           │           ↑                          │   (👤)
           │           │ <<extend>>               │
           │   ┌───────────────┐                 │
           │   │ Apply Coupon  │                 │
           │   └───────────────┘                 │
           │                                      │
           │   ┌───────────────┐                 │
   Admin  ────│ Manage Inventory│                 │
    (👤)  │   └───────────────┘                 │
           │                                      │
           │   ┌───────────────┐                 │
           ────│Generate Reports│                 │
           │   └───────────────┘                 │
           │                                      │
           └──────────────────────────────────────┘
```

**Relationships:**
1. Customer → Browse Products (**association**)
2. Browse Products **<<include>>** Search (always searches when browsing)
3. Place Order **<<include>>** Validate Payment (always validates payment)
4. Apply Coupon **<<extend>>** Place Order (optional: only if customer has coupon)
5. Payment Gateway → Validate Payment (secondary actor provides service)

***

### **Use Case Description (Textual):**

**Use Case:** Place Order

**Actors:** Customer (primary), Payment Gateway (secondary)

**Preconditions:** Customer logged in, items in cart

**Main Flow:**
1. Customer clicks "Checkout"
2. System displays order summary
3. Customer enters shipping address
4. Customer selects payment method
5. System validates payment (include Validate Payment)
6. System confirms order
7. System sends confirmation email

**Alternate Flow:**
- 5a. Payment fails → Display error, return to step 4
- 4a. Customer applies coupon → Extend to Apply Coupon

**Postconditions:** Order placed, inventory updated, email sent

***

### **Include vs. Extend:**

| Aspect | <<include>> | <<extend>> |
|--------|-------------|------------|
| **When** | Always executes | Conditionally executes |
| **Direction** | Base → Included | Extended ← Base |
| **Example** | Login includes Validate Credentials | Purchase extends Apply Discount |
| **Purpose** | Factor out common behavior | Optional behavior |

**Memory Aid:**
- **Include:** "Every time I do A, I **must** do B" (mandatory)
- **Extend:** "Sometimes when I do A, I **might** do B" (optional)

***

### **Advantages:**

1. **User-centric:** Focuses on what user wants to achieve
2. **Simple notation:** Easy for non-technical stakeholders
3. **Requirements capture:** Identifies functional requirements
4. **Scope definition:** System boundary shows what's in/out
5. **Communication:** Bridge between users and developers

***

### **Limitations:**

1. **No sequence:** Doesn't show order of operations (use sequence diagram for that)
2. **No data flow:** Doesn't show data details (use activity diagram)
3. **High-level:** Lacks implementation details

***

## **Q24. Explain Cyclomatic Complexity with example.**

### **ANSWER (6-8 marks):**

**Cyclomatic Complexity** is a **software metric** measuring the **complexity** of a program by counting the number of **linearly independent paths** through the code.

**Developed by:** Thomas McCabe (1976)

**Purpose:** 
- Measure code complexity
- Determine number of test cases needed (structural testing)
- Predict maintenance difficulty

***

### **Formula:**

**Three equivalent formulas:**

**1. Cyclomatic Complexity from Control Flow Graph:**
\[ V(G) = E - N + 2P \]

Where:
- **E** = Number of edges (arrows)
- **N** = Number of nodes (circles)
- **P** = Number of connected components (usually P=1 for single program)

**Simplified (for single program):**
\[ V(G) = E - N + 2 \]

***

**2. Cyclomatic Complexity from Decision Points:**
\[ V(G) = \pi + 1 \]

Where **π** = Number of decision points (if, while, for, case, &&, ||)

***

**3. Cyclomatic Complexity from Regions:**
\[ V(G) = R \]

Where **R** = Number of enclosed regions (including outer region)

***

### **Control Flow Graph (CFG):**

**Nodes:** Represent statements or groups of sequential statements  
**Edges:** Represent control flow (arrows)

***

### **Example 1: Simple If Statement**

**Code:**
```c
void check_number(int x) {
    if (x > 0) {           // Decision point 1
        printf("Positive");
    } else {
        printf("Non-positive");
    }
}
```

**Control Flow Graph:**
```
    [1] Start
      ↓
    [2] if (x > 0)
      ↙   ↘
   [3]     [4]
 Positive  Non-positive
      ↘   ↙
    [5] End
```

**Calculation:**

**Method 1 (E - N + 2):**
- Nodes (N) = 5
- Edges (E) = 6 (1→2, 2→3, 2→4, 3→5, 4→5, implicit start)
- V(G) = 6 - 5 + 2 = **3**

**Method 2 (π + 1):**
- Decision points (π) = 1 (one if statement)
- V(G) = 1 + 1 = **2**

**Wait, discrepancy!** 

**Correction:** When counting edges, count carefully:
- E = 5 (1→2, 2→3, 2→4, 3→5, 4→5)
- V(G) = 5 - 5 + 2 = **2** ✓

**Method 3 (Regions):**
- Region 1: Outside
- Region 2: Path through [2→3→5]
- R = **2** ✓

**Independent Paths:**
1. 1 → 2 → 3 → 5 (x > 0, TRUE path)
2. 1 → 2 → 4 → 5 (x > 0, FALSE path)

**Test Cases Needed:** **2** (to cover all paths)

***

### **Example 2: Nested If-Else**

**Code:**
```c
void classify(int x) {
    if (x > 0) {              // Decision 1
        if (x > 10) {         // Decision 2
            printf("Large positive");
        } else {
            printf("Small positive");
        }
    } else {
        printf("Non-positive");
    }
}
```

**Decision Points (π):**
- if (x > 0) → 1
- if (x > 10) → 1
- Total π = 2

**Cyclomatic Complexity:**
\[ V(G) = \pi + 1 = 2 + 1 = 3 \]

**Independent Paths:**
1. x > 0 (FALSE) → Non-positive
2. x > 0 (TRUE) && x > 10 (TRUE) → Large positive
3. x > 0 (TRUE) && x > 10 (FALSE) → Small positive

**Test Cases:** **3**

***

### **Example 3: Loop (While)**

**Code:**
```c
void print_numbers(int n) {
    int i = 0;
    while (i < n) {          // Decision point
        printf("%d", i);
        i++;
    }
}
```

**Decision Points:** 1 (while condition)

**Cyclomatic Complexity:**
\[ V(G) = 1 + 1 = 2 \]

**Paths:**
1. n ≤ 0 (loop never executes)
2. n > 0 (loop executes at least once)

***

### **Example 4: Switch Statement**

**Code:**
```c
void process_grade(char grade) {
    switch(grade) {          // Decision point
        case 'A':
            printf("Excellent");
            break;
        case 'B':
            printf("Good");
            break;
        case 'C':
            printf("Average");
            break;
        default:
            printf("Invalid");
    }
}
```

**Decision Points:** 
- **switch** with **N cases** = **N-1 decision points** (N branches - 1 default)
- Here: 3 cases + 1 default = **3 decisions**

**Cyclomatic Complexity:**
\[ V(G) = 3 + 1 = 4 \]

**Paths:** 4 (A, B, C, default)

***

### **Example 5: Complex Code**

**Code:**
```c
void complex_logic(int a, int b, int c) {
    if (a > 0) {                  // Decision 1
        if (b > 0) {              // Decision 2
            printf("Both positive");
        }
    }
    
    while (c > 0) {               // Decision 3
        printf("%d", c);
        c--;
    }
    
    if (a > b || b > c) {         // Decision 4 (||), Decision 5
        printf("Condition met");
    }
}
```

**Decision Points:**
- if (a > 0): 1
- if (b > 0): 1
- while (c > 0): 1
- if (a > b || b > c): **2** (|| creates two decision points: a>b AND b>c)

**Total π = 5**

**Cyclomatic Complexity:**
\[ V(G) = 5 + 1 = 6 \]

**Test Cases Needed:** **6**

***

### **McCabe's Complexity Guidelines:**

| Complexity | Risk | Interpretation |
|------------|------|----------------|
| **1-10** | **Low** | Simple, easy to test/maintain |
| **11-20** | **Moderate** | Moderately complex |
| **21-50** | **High** | Complex, hard to test |
| **>50** | **Very High** | Unmaintainable, **refactor!** |

**McCabe's Recommendation:** V(G) should not exceed **10** for any module.

***

### **Uses:**

1. **Testing:** Minimum test cases = V(G) (for path coverage)
2. **Code Quality:** High V(G) = hard to maintain
3. **Refactoring Trigger:** V(G) > 10 → split function
4. **Code Review:** Flag complex methods for review
5. **Risk Assessment:** High complexity = high defect risk

***

### **Advantages:**

✓ **Objective metric:** Quantifiable, not subjective  
✓ **Testing guide:** Indicates minimum test cases  
✓ **Maintenance predictor:** High complexity = high maintenance cost  
✓ **Language independent:** Applies to any procedural language

***

### **Limitations:**

✗ **Doesn't measure all complexity:** Nested loops same as sequential conditions  
✗ **No data complexity:** Only control flow  
✗ **False sense of quality:** Low V(G) ≠ good design  
✗ **OOP challenges:** Method level only, not class/system level

***

## **Q25. Explain Software Reliability Models.**

### **ANSWER (6-8 marks):**

**Software Reliability** is the probability that software will operate **without failure** for a specified period under specified conditions.

**Reliability Models** predict failure behavior, estimate remaining defects, and determine release readiness.

***

### **Key Reliability Metrics:**

**1. MTBF (Mean Time Between Failures):**
\[ MTBF = \frac{\text{Total Operating Time}}{\text{Number of Failures}} \]

**Example:** System runs 1000 hours, fails 5 times → MTBF = 1000/5 = **200 hours**

***

**2. MTTF (Mean Time To Failure):**
- For **non-repairable** systems
- Average time until first failure

***

**3. MTTR (Mean Time To Repair):**
\[ MTTR = \frac{\text{Total Repair Time}}{\text{Number of Repairs}} \]

***

**4. Availability:**
\[ Availability = \frac{MTBF}{MTBF + MTTR} \]

**Example:** MTBF=200hr, MTTR=10hr → Availability = 200/(200+10) = **95.2%**

***

**5. Failure Rate (λ):**
\[ \lambda = \frac{1}{MTBF} \]

**Example:** MTBF=200hr → λ = 1/200 = **0.005 failures/hour**

***

**6. Reliability Function:**
\[ R(t) = e^{-\lambda t} \]

Probability system survives until time **t**

**Example:** λ=0.005, t=100hr → R(100) = e^(-0.005×100) = e^(-0.5) = **60.7%**

***

### **Major Reliability Models:**

#### **1. Jelinski-Moranda Model**

**Assumptions:**
- Software contains **N** unknown defects initially
- Failures occur randomly
- Each failure equally likely
- Fix removes one defect (no new defects introduced)

**Failure Rate (after i defects fixed):**
\[ \lambda_i = \phi(N - i) \]

Where **φ** = proportionality constant

**Characteristics:**
- **Decreasing failure rate** (improves over time)
- Simple, early model (1972)

***

#### **2. Musa Basic Execution Time Model**

**Failure Intensity (λ):**
\[ \lambda(t) = \lambda_0 \left(1 - \frac{\mu(t)}{\mu_{\infty}}\right) \]

Where:
- **λ₀** = Initial failure intensity
- **μ(t)** = Defects found by time t
- **μ∞** = Total defects

**As testing progresses:**
- μ(t) increases → λ(t) decreases (fewer remaining defects)

**Example:**
- λ₀ = 10 failures/day
- Total defects = 100
- After fixing 50 defects:
  \[ \lambda = 10 \left(1 - \frac{50}{100}\right) = 10 \times 0.5 = 5 \text{ failures/day} \]

***

#### **3. Goel-Okumoto Model (NHPP)**

**Non-Homogeneous Poisson Process**

**Mean Value Function:**
\[ m(t) = a(1 - e^{-bt}) \]

Where:
- **a** = Expected total defects
- **b** = Defect detection rate
- **t** = Testing time

**Failure Intensity:**
\[ \lambda(t) = ab \cdot e^{-bt} \]

**Characteristics:**
- **Exponential decay** in failure rate
- Widely used in practice

***

#### **4. Shooman's Model**

**Residual Defects:**
\[ N(t) = N_0 - K \cdot ET \]

Where:
- **N₀** = Initial defects
- **K** = Defect detection rate
- **ET** = Execution time

**Example:**
- N₀ = 100 defects
- K = 0.5 defects/hour
- After 50 hours: N(50) = 100 - 0.5×50 = **75 defects remaining**

***

### **Reliability Growth Curve:**

**Typical Pattern:**

```
Failure
Rate
  ↑
  │ ╲
  │  ╲
  │   ╲___
  │       ‾‾‾---___
  │                ‾‾‾‾----____
  └──────────────────────────→ Time
     Testing Progress
```

**Phases:**
1. **Early:** High failure rate (finding easy bugs)
2. **Middle:** Decreasing rate (fixing defects)
3. **Late:** Low, stable rate (approaching release)

***

### **Model Selection Criteria:**

**Choose based on:**
1. **Development phase:** Early vs. late testing
2. **Data available:** How much historical data?
3. **Assumptions:** Do they match your process?
4. **Accuracy needed:** Rough estimate vs. precise prediction

***

### **Challenges:**

1. **Assumption violations:** Real defects aren't always independent
2. **Imperfect fixes:** Bug fixes introduce new bugs
3. **Changing code:** New features added during testing
4. **Environment differences:** Test ≠ production environment

***

### **Practical Use:**

**Release Decision:**
```
IF (Current failure rate < Acceptable threshold)
   AND (Predicted reliability > Customer requirement)
   AND (Test coverage > 90%)
THEN Release
ELSE Continue testing
```

**Example:**
- Current λ = 0.01 failures/hour
- Target λ = 0.02 failures/hour
- **Decision:** Ready to release ✓

***

## **Q26. Explain Reverse Engineering and Re-engineering.**

### **ANSWER (6-8 marks):**

**Reverse Engineering** and **Re-engineering** are techniques for understanding and improving **legacy systems**.

***

### **REVERSE ENGINEERING**

**Definition:** Process of analyzing existing software to identify components and relationships, creating representations at **higher levels of abstraction**.

**Direction:** Implementation → Design → Requirements (backward)

**Purpose:** **Understand** existing system (no code changes)

***

#### **Reverse Engineering Levels:**

**1. Redocumentation:**
- Generate documentation from code
- **Tools:** JavaDoc, Doxygen
- **Output:** API docs, call graphs, data dictionaries

**2. Design Recovery:**
- Extract design from code
- **Output:** Class diagrams, architecture diagrams, DFDs

**3. Specification Recovery:**
- Infer requirements from implementation
- **Output:** Functional specifications

***

#### **Reverse Engineering Process:**

```
Source Code
    ↓ (Parse)
Abstract Syntax Tree
    ↓ (Analyze)
Control/Data Flow Graphs
    ↓ (Pattern Recognition)
Design Models (UML)
    ↓ (Abstraction)
Requirements Specifications
```

***

#### **Techniques:**

**1. Static Analysis:**
- Examine code without execution
- **Tools:** Code analyzers, decompilers
- **Output:** Call graphs, dependencies

**2. Dynamic Analysis:**
- Execute code, observe behavior
- **Tools:** Debuggers, profilers
- **Output:** Execution traces, performance data

**3. Pattern Matching:**
- Recognize design patterns in code
- **Example:** Identify Singleton, Factory patterns

***

#### **Applications:**

1. **Legacy System Understanding:** Decades-old code, no documentation
2. **Security Analysis:** Malware reverse engineering
3. **Competitive Analysis:** Study competitor products (legal gray area)
4. **Migration:** Port to new platform (understand old system first)
5. **Maintenance:** Fix bugs without original documentation

***

#### **Example:**

**Code:**
```c
void process() {
    if (validate()) {
        transform();
        save();
    }
}
```

**Reverse Engineered Design:**
- **Class:** DataProcessor
- **Methods:** validate(), transform(), save()
- **Pattern:** Template Method (process defines skeleton)

***

### **RE-ENGINEERING (Software Re-engineering)**

**Definition:** Examination and alteration of existing software to **reconstitute it in a new form**, followed by implementation of the new form.

**Direction:** Old System → Understanding → **New System** (includes code changes)

**Purpose:** **Improve** system (modernize, enhance)

***

#### **Re-engineering Activities:**

**1. Inventory Analysis:**
- Catalog all system components
- Identify candidates for re-engineering

**2. Document Restructuring:**
- Update outdated documentation
- Create missing documentation

**3. Reverse Engineering:**
- Understand existing system

**4. Code Restructuring:**
- Improve code structure (refactor)
- **Examples:**
  - Remove GOTOs
  - Extract functions
  - Improve naming

**5. Data Restructuring:**
- Normalize databases
- Modernize data models

**6. Forward Engineering:**
- Implement improved system
- Apply modern design patterns

***

#### **Re-engineering Process:**

```
┌──────────────────────────────────────┐
│         Existing System              │
└────────────┬─────────────────────────┘
             ↓
      ┌──────────────┐
      │   Reverse    │
      │ Engineering  │ (Understand)
      └──────┬───────┘
             ↓
      ┌──────────────┐
      │  Analyze &   │
      │  Redesign    │ (Improve)
      └──────┬───────┘
             ↓
      ┌──────────────┐
      │   Forward    │
      │ Engineering  │ (Rebuild)
      └──────┬───────┘
             ↓
┌──────────────────────────────────────┐
│         New System                   │
└──────────────────────────────────────┘
```

***

#### **Types of Re-engineering:**

**1. Preventive Re-engineering:**
- Improve maintainability before problems occur
- **Example:** Refactor complex functions (V(G)>10)

**2. Corrective Re-engineering:**
- Fix architectural flaws
- **Example:** Eliminate tight coupling

**3. Adaptive Re-engineering:**
- Migrate to new platform
- **Example:** Mainframe → Cloud

**4. Perfective Re-engineering:**
- Add new features during restructuring

***

#### **Example: Legacy COBOL to Java**

**Before (COBOL):**
```cobol
01 CUSTOMER-RECORD.
   05 CUST-ID PIC 9(5).
   05 CUST-NAME PIC X(20).

PROCEDURE DIVISION.
   READ CUSTOMER-FILE INTO CUSTOMER-RECORD.
   DISPLAY CUST-NAME.
```

**Reverse Engineer:**
- Understand: CUSTOMER-RECORD is entity
- Operations: Read, Display

**Re-engineer (Java):**
```java
class Customer {
    private int id;
    private String name;
    
    public void display() {
        System.out.println(name);
    }
}
```

**Improvements:**
- Object-oriented design
- Encapsulation
- Modern language

***

### **Reverse Engineering vs. Re-engineering:**

| Aspect | Reverse Engineering | Re-engineering |
|--------|---------------------|----------------|
| **Goal** | **Understand** | **Improve** |
| **Code Changes** | **NO** | **YES** |
| **Output** | Documentation, models | New/improved system |
| **Scope** | Analysis only | Analysis + reconstruction |
| **Purpose** | Knowledge recovery | Modernization |
| **Example** | Generate UML from code | Migrate mainframe to web |

***

### **When to Re-engineer:**

✓ **Re-engineer if:**
- System critical but unmaintainable
- Technology obsolete
- Performance inadequate
- Cost of maintenance > re-engineering

✗ **Replace if:**
- System beyond repair
- COTS (Commercial Off-The-Shelf) available
- Business requirements changed completely

***

### **Economics:**

**Cost Comparison:**
- **Maintenance:** 60-80% of lifecycle cost
- **Re-engineering:** Typically 30-50% cost of new development
- **New Development:** 100% cost

**ROI:** If re-engineering reduces maintenance costs significantly, it pays off in 2-3 years

***

### **Challenges:**

1. **Risk:** May break working system
2. **Testing:** Extensive regression testing needed
3. **Time:** Can take months/years for large systems
4. **Skills:** Need both legacy and modern technology expertise
5. **Business continuity:** System must keep running during re-engineering

***
# **📚 HIGH-PRIORITY QUESTIONS - Q27 ONWARDS**

***

## **Q27. Explain the V-Model (Verification and Validation Model).**

### **ANSWER (6-8 marks):**

**V-Model** is an extension of the **Waterfall Model** where development and testing phases are **paired** in a "V" shape, emphasizing **verification** (are we building it right?) and **validation** (are we building the right thing?).

**Also called:** Verification and Validation Model

***

### **V-Model Structure:**

```
Requirements ←──────────────→ Acceptance Testing
      ↓                              ↑
System Design ←──────────→ System Testing
      ↓                              ↑
Architecture Design ←──→ Integration Testing
      ↓                              ↑
Module Design ←────────→ Unit Testing
      ↓                              ↑
      └──→ CODING ───→
```

**Left Side (Verification):** Development phases  
**Right Side (Validation):** Testing phases  
**Bottom:** Implementation (coding)

***

### **Phase Mapping:**

#### **1. Requirements ↔ Acceptance Testing**
- **Requirements Analysis:** Define what customer wants (SRS)
- **Acceptance Test Plan:** How to validate requirements met?
- **Question:** Does the system meet user needs?

#### **2. System Design ↔ System Testing**
- **System Design:** Overall architecture, technology stack
- **System Test Plan:** Test integrated system
- **Question:** Does complete system work as designed?

#### **3. High-Level Design ↔ Integration Testing**
- **HLD:** Modules, interfaces between modules
- **Integration Test Plan:** Test module interactions
- **Question:** Do modules work together correctly?

#### **4. Low-Level Design ↔ Unit Testing**
- **LLD:** Detailed algorithms, data structures
- **Unit Test Plan:** Test individual functions/methods
- **Question:** Does each unit work correctly?

***

### **Key Principles:**

**1. Early Test Planning:**
- Test cases designed **during** corresponding development phase
- **Example:** Write acceptance tests while gathering requirements

**2. Verification Activities (Static):**
- Reviews, inspections, walkthroughs
- **No execution** of code
- **Left side** of V

**3. Validation Activities (Dynamic):**
- Actual testing with code execution
- **Right side** of V

**4. Traceability:**
- Each requirement traced to test case
- Ensures complete testing coverage

***

### **V-Model Process Flow:**

**Downward (Left Side):**
```
1. Business Requirements
   ↓ (What customer wants)
2. System Requirements (SRS)
   ↓ (What system will do)
3. High-Level Design (Architecture)
   ↓ (How system structured)
4. Low-Level Design (Module details)
   ↓ (How modules implemented)
5. Coding
```

**Upward (Right Side):**
```
6. Unit Testing
   ↑ (Verify modules)
7. Integration Testing
   ↑ (Verify interfaces)
8. System Testing
   ↑ (Verify complete system)
9. Acceptance Testing
   ↑ (Validate user requirements)
```

***

### **Advantages:**

1. **Early Defect Detection:** Test planning during design catches issues early
2. **Clear Milestones:** Each phase has entry/exit criteria
3. **Structured Testing:** Systematic test approach at each level
4. **High Discipline:** Rigorous verification at each stage
5. **Suitable for Critical Systems:** Medical, aerospace (where defects catastrophic)
6. **Traceability:** Requirements directly linked to tests

**Pressman notes:** *"V-Model ensures that validation is considered from the very beginning, not as an afterthought."*

***

### **Disadvantages:**

1. **Inflexible:** Like Waterfall, hard to accommodate changes
2. **No Early Prototypes:** Customer sees product only at end
3. **Sequential:** Cannot overlap phases easily
4. **Not for Evolving Requirements:** Requirements must be clear upfront
5. **Expensive for Small Projects:** Overhead of test planning
6. **Late Risk Discovery:** Integration issues found late

***

### **When to Use:**

✓ **Use when:**
- Requirements well-defined and stable
- Safety-critical systems (medical devices, avionics)
- Project scope clear from start
- Sufficient resources for test planning
- High reliability needed

✗ **Avoid when:**
- Requirements unclear or changing
- Quick prototypes needed
- Agile/flexible approach required
- Small, low-risk projects

***

### **V-Model vs. Waterfall:**

| Aspect | Waterfall | V-Model |
|--------|-----------|---------|
| **Testing** | After coding | Planned early, executed after |
| **Emphasis** | Development | **Verification & Validation** |
| **Test Plan** | Created late | Created during design |
| **Defect Cost** | High | Lower (early detection) |
| **Structure** | Linear | V-shaped (paired phases) |

***

## **Q28. Explain the Incremental Model.**

### **ANSWER (6-8 marks):**

**Incremental Model** is a process where software is developed and delivered in **increments** (small portions). Each increment adds functionality to previous increments.

**Core Idea:** "Build a little, deliver a little" repeatedly until complete system delivered.

***

### **Incremental Model Structure:**

```
Increment 1:  Requirements → Design → Code → Test → Deploy (Core features)
                                                        ↓
Increment 2:  Requirements → Design → Code → Test → Deploy (+Feature Set 1)
                                                        ↓
Increment 3:  Requirements → Design → Code → Test → Deploy (+Feature Set 2)
                                                        ↓
                                                    Final Product
```

**Each increment:**
- Goes through complete development cycle
- Delivers working software
- Builds on previous increments

***

### **Process Flow:**

#### **Phase 1: Planning**
- Identify **all requirements**
- Divide requirements into **increments** (builds)
- Prioritize: Core functionality first

**Example (E-commerce):**
- **Increment 1:** User registration, login (core)
- **Increment 2:** Product catalog, search
- **Increment 3:** Shopping cart
- **Increment 4:** Payment, checkout
- **Increment 5:** Order tracking, reviews

***

#### **Phase 2: Increment Development**

**For Each Increment:**

**Step 1: Requirements Analysis**
- Analyze requirements for this increment only

**Step 2: Design**
- Design features for this increment
- Ensure integration with previous increments

**Step 3: Implementation**
- Code new features
- Integrate with existing system

**Step 4: Testing**
- **Unit test:** New features
- **Integration test:** New + existing
- **Regression test:** Ensure old features still work

**Step 5: Deployment**
- Deploy to production
- Gather user feedback

***

#### **Phase 3: Integration**
- Each increment **integrates** with previous ones
- System grows incrementally

***

### **Incremental vs. Iterative:**

**Incremental:** Add new functionality each cycle  
**Iterative:** Refine existing functionality each cycle

| Model | Focus | Result |
|-------|-------|--------|
| **Incremental** | **Add features** | Each release has **MORE** features |
| **Iterative** | **Refine features** | Each release **IMPROVES** features |

**Many projects use both:** Add features (incremental) + refine them (iterative)

***

### **Types of Incremental Models:**

#### **1. Staged Delivery**
- First increment: Most critical features
- Later increments: Less critical features
- **Priority-driven**

#### **2. Parallel Development**
- Multiple teams develop different increments simultaneously
- Integrate at end

***

### **Advantages:**

1. **Early Delivery:** First increment delivered quickly (partial functionality)
2. **Customer Feedback:** Users provide feedback after each increment
3. **Reduced Risk:** Core features tested early
4. **Flexibility:** Later increments can be adjusted based on feedback
5. **Revenue Early:** Can start earning from first increment (SaaS model)
6. **Lower Initial Cost:** Pay-as-you-go development
7. **Easier Testing:** Smaller portions easier to test than whole system
8. **Parallel Development:** Multiple teams can work on different increments

**K.K. Aggarwal:** *"Incremental model provides operational capability earlier while retaining flexibility for future enhancements."*

***

### **Disadvantages:**

1. **Requires Good Planning:** Must identify increments correctly
2. **Architectural Challenges:** Must design for future increments (scalability)
3. **Integration Complexity:** Each increment must integrate smoothly
4. **Regression Testing Overhead:** Test old + new each time
5. **Not Suitable If:** System cannot be modularized
6. **Customer Availability:** Needs customer feedback after each increment

***

### **When to Use:**

✓ **Use when:**
- Major requirements identified, details can evolve
- Need to deliver working system quickly
- High-risk project (validate core early)
- Resources can be added incrementally
- Market pressure (release basic version fast)

✗ **Avoid when:**
- Requirements unclear
- System cannot be decomposed into increments
- Tight deadlines for complete system (not partial)

***

### **Example: Microsoft Word Development (Hypothetical)**

**Increment 1 (Month 1-3):**
- Basic text editing (type, delete)
- Save/open files
- **Deploy:** Basic text editor

**Increment 2 (Month 4-6):**
- Formatting (bold, italic, fonts)
- Copy/paste
- **Deploy:** Formatted text editor

**Increment 3 (Month 7-9):**
- Spell check
- Find/replace
- **Deploy:** Enhanced editor

**Increment 4 (Month 10-12):**
- Tables, images
- Print functionality
- **Deploy:** Full word processor

**Each increment adds value, system usable from Increment 1**

***

### **Incremental vs. Other Models:**

| Aspect | Waterfall | Incremental | Spiral |
|--------|-----------|-------------|--------|
| **Delivery** | At end | Multiple releases | Multiple spirals |
| **Feedback** | Late | After each increment | After each loop |
| **Risk** | High | Medium | Low (explicit risk analysis) |
| **Flexibility** | Low | High | Very High |
| **User Involvement** | Low | Medium | High |

***

## **Q29. Explain Software Metrics: LOC and Halstead Metrics.**

### **ANSWER (8-10 marks):**

**Software Metrics** are quantitative measures of software attributes (size, complexity, quality).

**Purpose:** Estimation, quality assessment, productivity measurement

***

### **LOC (Lines of Code) Metric**

**Definition:** Count of **source code lines** (excluding comments, blank lines).

***

#### **Variants:**

**1. Physical LOC:**
- Count all non-blank, non-comment lines
- **Language-dependent**

**Example (C):**
```c
int add(int a, int b) {    // 1 LOC
    return a + b;          // 2 LOC
}
```
**Physical LOC = 2**

***

**2. Logical LOC:**
- Count **statements/instructions**
- Multiple statements on one line = multiple LOC

**Example:**
```c
int x = 5; int y = 10;    // 2 logical LOC (one physical line)
```

***

**3. KLOC (Kilo LOC):**
- Thousands of Lines of Code
- Used in COCOMO: 1 KLOC = 1000 LOC

***

#### **Counting Rules:**

**Include:**
- Executable statements
- Data declarations

**Exclude:**
- Blank lines
- Comments
- Braces (some standards exclude)

**Example:**
```c
/* This is a comment */     ← Exclude
                            ← Exclude (blank)
int factorial(int n) {      ← Include (declaration)
    if (n == 0)             ← Include
        return 1;           ← Include
    else                    ← Exclude (keyword only)
        return n * factorial(n-1);  ← Include
}
```
**LOC = 4**

***

#### **Language Productivity:**

**Average LOC per Function Point:**

| Language | LOC/FP |
|----------|--------|
| Assembly | 320 |
| C | 128 |
| C++ | 64 |
| Java | 53 |
| Python | 25 |
| SQL | 12 |

**Interpretation:** 1 FP of functionality = 128 LOC in C, but only 25 LOC in Python

***

#### **Advantages of LOC:**

1. **Simple:** Easy to count (automated tools available)
2. **Intuitive:** "Bigger program = more LOC"
3. **Historical Data:** Decades of LOC data for estimation
4. **Language-Specific Productivity:** LOC/person-month per language

***

#### **Disadvantages:**

1. **Language Dependent:** Can't compare Java vs. Python LOC
2. **Rewards Verbosity:** More LOC ≠ better code
3. **Penalizes Reuse:** Reusing library reduces LOC (looks less productive!)
4. **Ignores Complexity:** 100 LOC sorting ≠ 100 LOC UI
5. **Late Metric:** Only available after coding

**Example of Bad Metric:**
```c
// Verbose (5 LOC)
int x = 5;
int y = 10;
int sum = x + y;
int result = sum;
return result;

// Concise (1 LOC)
return 5 + 10;
```
**First looks "more productive" but is worse code!**

***

### **HALSTEAD METRICS (Software Science)**

**Developed by:** Maurice Halstead (1977)

**Definition:** Measures software complexity by analyzing **operators** and **operands** in code.

***

#### **Basic Concepts:**

**Operators (η₁):**
- Keywords: `if`, `while`, `return`
- Symbols: `+`, `-`, `*`, `=`, `==`, `()`, `[]`, `;`

**Operands (η₂):**
- Variables: `x`, `count`, `total`
- Constants: `0`, `100`, `"Hello"`

***

#### **Halstead Metrics:**

**1. Program Vocabulary (η):**
\[ \eta = \eta_1 + \eta_2 \]
- η₁ = number of **unique operators**
- η₂ = number of **unique operands**

**2. Program Length (N):**
\[ N = N_1 + N_2 \]
- N₁ = **total** operator occurrences
- N₂ = **total** operand occurrences

**3. Calculated Length (N̂):**
\[ \hat{N} = \eta_1 \log_2(\eta_1) + \eta_2 \log_2(\eta_2) \]
(Theoretical minimum length)

**4. Volume (V):**
\[ V = N \times \log_2(\eta) \]
**Units:** Bits  
**Interpretation:** Information content of program

**5. Difficulty (D):**
\[ D = \frac{\eta_1}{2} \times \frac{N_2}{\eta_2} \]
**Interpretation:** How hard to write/understand

**6. Effort (E):**
\[ E = D \times V \]
**Units:** Elementary mental discriminations  
**Interpretation:** Mental effort to develop

**7. Time (T):**
\[ T = \frac{E}{S} \]
- S = Stroud number ≈ 18 (mental discriminations per second)
**Units:** Seconds

**8. Bugs (B):**
\[ B = \frac{V}{3000} \]
**Interpretation:** Expected number of errors

***

#### **Example:**

**Code:**
```c
int sum(int a, int b) {
    return a + b;
}
```

**Operators:**
- Unique (η₁): `int`, `()`, `{}`, `return`, `+`, `;` = **6**
- Total (N₁): Count each occurrence = **8**

**Operands:**
- Unique (η₂): `sum`, `a`, `b` = **3**
- Total (N₂): `sum`, `a`(×2), `b`(×2) = **5**

**Calculations:**

**Vocabulary:**
\[ \eta = 6 + 3 = 9 \]

**Length:**
\[ N = 8 + 5 = 13 \]

**Volume:**
\[ V = 13 \times \log_2(9) = 13 \times 3.17 = 41.2 \text{ bits} \]

**Difficulty:**
\[ D = \frac{6}{2} \times \frac{5}{3} = 3 \times 1.67 = 5.0 \]

**Effort:**
\[ E = 5.0 \times 41.2 = 206 \]

**Time:**
\[ T = \frac{206}{18} = 11.4 \text{ seconds} \]

**Bugs:**
\[ B = \frac{41.2}{3000} = 0.014 \text{ (very low, simple function)} \]

***

#### **Advantages of Halstead:**

1. **Language Independent:** Works for any language
2. **Early Estimation:** Can estimate from pseudocode
3. **Objective:** Automated calculation
4. **Comprehensive:** Multiple dimensions (volume, effort, bugs)

***

#### **Disadvantages:**

1. **Tedious Counting:** Must identify every operator/operand
2. **Subjective Boundaries:** Is `++` one operator or two (`+` twice)?
3. **No Control Flow:** Ignores logic complexity (nested loops)
4. **Empirical Constants:** 3000 for bugs, 18 for Stroud (may not fit all)

***

### **LOC vs. Halstead:**

| Aspect | LOC | Halstead |
|--------|-----|----------|
| **What Measured** | Physical size | Vocabulary & logic |
| **Language Dep.** | Yes | No |
| **Complexity** | No | Yes (Difficulty, Volume) |
| **When Available** | After coding | After coding (can be earlier) |
| **Use Case** | Size estimation | Effort/complexity estimation |

***

## **Q30. Explain Software Quality Assurance (SQA).**

### **ANSWER (6-8 marks):**

**Software Quality Assurance (SQA)** is a **systematic, planned set of activities** ensuring that software processes and products conform to requirements, standards, and procedures.

**IEEE Definition:** *"A planned and systematic pattern of actions to provide confidence that software conforms to established technical requirements."*

***

### **Quality vs. QA vs. QC:**

| Term | Focus | When | Activities |
|------|-------|------|------------|
| **Quality** | Conformance to requirements | Throughout | Meet customer needs |
| **QA (Assurance)** | **Process** | Throughout | Audits, reviews, standards |
| **QC (Control)** | **Product** | Testing phase | Testing, inspections |

**Key Distinction:**
- **QA:** Proactive, **prevent** defects (process-focused)
- **QC:** Reactive, **detect** defects (product-focused)

***

### **SQA Activities:**

#### **1. Process Definition and Improvement**

**Activities:**
- Define standard development process
- Document procedures (coding standards, design guidelines)
- Continuous process improvement

**Example:** "All code must follow Google Java Style Guide"

***

#### **2. Project Reviews and Audits**

**Reviews:**
- **Peer Reviews:** Developers review each other's work
- **Management Reviews:** Assess project status
- **Technical Reviews:** Evaluate technical decisions

**Audits:**
- **Process Audits:** Is team following defined process?
- **Product Audits:** Does product meet standards?

**Example:** Quarterly audit checks if all design docs follow template

***

#### **3. Standards Compliance**

**Types of Standards:**
- **Coding Standards:** Naming conventions, formatting
- **Documentation Standards:** SRS template, design doc structure
- **Testing Standards:** Test case format, coverage criteria
- **External Standards:** ISO 9001, IEEE standards

**Example:** IEEE 830 for SRS format

***

#### **4. Verification and Validation**

**Verification (Are we building it right?):**
- Reviews, inspections, walkthroughs
- **Static analysis** (no code execution)

**Validation (Are we building the right thing?):**
- Testing (unit, integration, system)
- **Dynamic analysis** (execute code)

***

#### **5. Problem Reporting and Corrective Action**

**Activities:**
- **Defect Tracking:** JIRA, Bugzilla
- **Root Cause Analysis:** Why did defect occur?
- **Corrective Actions:** Prevent recurrence
- **Metrics:** Defect density, fix time

***

#### **6. Tools and Technology**

**SQA Tools:**
- **Static Analysis:** SonarQube, ESLint, Checkstyle
- **Test Automation:** Selenium, JUnit
- **Configuration Management:** Git, SVN
- **CI/CD:** Jenkins, GitLab CI

***

#### **7. Risk Management**

**Activities:**
- Identify quality risks (e.g., untested code)
- Mitigate risks (e.g., increase test coverage)
- Monitor risk indicators

***

#### **8. Training and Awareness**

**Activities:**
- Train developers on quality practices
- Awareness programs on standards
- Share best practices

***

### **SQA Plan Document:**

**IEEE 730 Standard for SQA Plans:**

**Contents:**
1. **Purpose & Scope:** What this SQA plan covers
2. **Reference Documents:** Standards, procedures
3. **Management:** SQA team roles, responsibilities
4. **Documentation:** What docs required (SRS, design, test plans)
5. **Standards, Practices, Conventions:** Coding standards, etc.
6. **Reviews and Audits:** Schedule, participants
7. **Testing:** Test strategies, acceptance criteria
8. **Problem Reporting:** Defect tracking process
9. **Tools:** SQA tools used
10. **Code Control:** Version control procedures
11. **Media Control:** Backup, archival
12. **Supplier Control:** Third-party component quality
13. **Records:** QA records maintenance
14. **Training:** QA training plans

***

### **SQA Organization:**

**SQA Group:**
- **Independent** from development team (avoid conflict of interest)
- **Reports to:** Senior management (not project manager)
- **Responsibilities:**
  - Monitor process compliance
  - Conduct audits
  - Report quality status

**Typical Structure:**
```
VP Engineering
    ├─ Development Manager
    │    └─ Developers
    └─ SQA Manager (independent reporting)
         └─ SQA Engineers
```

***

### **SQA Metrics:**

**Process Metrics:**
- % projects following standards
- Average review effectiveness
- Audit findings trend

**Product Metrics:**
- Defect density (defects/KLOC)
- Test coverage (% code tested)
- Mean Time Between Failures (MTBF)

**Example:**
```
Metric: Defect Density
Target: <5 defects per KLOC
Actual: 3.2 defects per KLOC
Status: ✓ Meeting quality goals
```

***

### **Software Quality Factors (McCall's Model):**

**Three Perspectives:**

**1. Product Operation (Using the software):**
- **Correctness:** Does it meet requirements?
- **Reliability:** Failure-free operation
- **Efficiency:** Resource usage (CPU, memory)
- **Integrity:** Security (access control)
- **Usability:** Ease of use

**2. Product Revision (Changing the software):**
- **Maintainability:** Ease of fixing bugs
- **Flexibility:** Ease of modifications
- **Testability:** Ease of testing

**3. Product Transition (Moving to new environment):**
- **Portability:** Move to different platform
- **Reusability:** Use in other applications
- **Interoperability:** Interface with other systems

***

### **Benefits of SQA:**

1. **Reduced Defects:** Early detection prevents expensive late fixes
2. **Predictable Quality:** Consistent process → consistent quality
3. **Customer Satisfaction:** Meets requirements reliably
4. **Cost Savings:** Prevention cheaper than correction
5. **Regulatory Compliance:** Meets ISO, FDA, etc.
6. **Competitive Advantage:** Higher quality = market differentiation

**IBM Study:** 
- Cost to fix defect in requirements: **$1**
- Cost to fix in design: **$5**
- Cost to fix in coding: **$10**
- Cost to fix in testing: **$50**
- Cost to fix in production: **$500+**

**SQA focuses on preventing defects in requirements/design phase!**

***

### **Challenges:**

1. **Overhead:** SQA activities take time/resources
2. **Resistance:** Developers may view QA as bureaucracy
3. **Subjectivity:** Some quality attributes hard to measure (usability)
4. **Keeping Pace:** Fast development (Agile) challenges traditional SQA

***

### **SQA in Agile:**

**Modern Adaptations:**
- **Continuous Integration:** Automated quality checks
- **Test-Driven Development (TDD):** Quality built-in
- **Pair Programming:** Real-time peer review
- **Definition of Done:** Quality criteria for each story
- **Sprint Reviews:** Regular quality validation

***

## **Q31. Explain Software Project Management: Estimation and Staffing.**

### **ANSWER (8-10 marks):**

**Software Project Management** involves planning, organizing, and controlling software projects to deliver on time, within budget, and meeting quality requirements.

***

### **PART 1: SOFTWARE ESTIMATION**

**Purpose:** Predict effort, time, cost, and resources **before** development begins.

***

#### **What to Estimate:**

**1. Size:**
- LOC (Lines of Code)
- Function Points
- Number of modules

**2. Effort:**
- Person-Months (PM)
- Person-Hours

**3. Duration:**
- Months or weeks

**4. Cost:**
- Budget (salary × person-months + overhead)

**5. Resources:**
- Team size
- Skills needed

***

#### **Estimation Techniques:**

***

##### **1. Expert Judgment (Delphi Technique)**

**Process:**
1. **Round 1:** Experts independently estimate
2. **Coordinator:** Summarizes estimates (anonymous)
3. **Round 2:** Experts revise based on summary
4. **Repeat** until consensus

**Advantages:**
- Leverages experience
- Multiple perspectives
- Anonymous (no dominant personality)

**Disadvantages:**
- Time-consuming
- Subjective
- Quality depends on expert accuracy

**Example:**
```
Expert A: 500 hours
Expert B: 600 hours
Expert C: 550 hours
Average: 550 hours (consensus)
```

***

##### **2. Analogy-Based Estimation**

**Process:**
1. Find **similar past project**
2. Adjust for differences (complexity, team, technology)
3. Estimate current project

**Formula:**
\[ \text{Estimate} = \text{Past Effort} \times \text{Adjustment Factor} \]

**Example:**
```
Past Project: E-commerce site = 1000 hours
Current: Similar, but adding mobile app (30% more complex)
Estimate: 1000 × 1.30 = 1300 hours
```

**Advantages:**
- Uses real data
- Intuitive

**Disadvantages:**
- Requires historical data
- Finding truly similar project hard

***

##### **3. Decomposition (Bottom-Up)**

**Process:**
1. **Break down** project into tasks/modules
2. **Estimate each** component separately
3. **Sum** all estimates

**Example (Library System):**
```
Module               Estimate (hours)
─────────────────────────────────
User Management      120
Book Catalog         150
Borrowing System     200
Reporting            80
Integration/Testing  100
─────────────────────────────────
Total:               650 hours
```

**Advantages:**
- Detailed, accurate (if breakdown good)
- Identifies all tasks

**Disadvantages:**
- Time-consuming
- May miss integration complexity

***

##### **4. Algorithmic Models**

**Use mathematical formulas (COCOMO, Function Points)**

**Already covered in Q3 (COCOMO) and Q8 (Function Points)**

***

##### **5. Three-Point Estimation (PERT)**

**Formula:**
\[ \text{Expected} = \frac{\text{Optimistic} + 4 \times \text{Most Likely} + \text{Pessimistic}}{6} \]

**Example:**
```
Task: Database Design
Optimistic (best case): 20 hours
Most Likely: 30 hours
Pessimistic (worst case): 50 hours

Expected = (20 + 4×30 + 50) / 6 = 31.7 hours
```

***

#### **Estimation Challenges:**

1. **Uncertain Requirements:** Changes during development
2. **Technology Risk:** New tools/platforms
3. **Team Variability:** Productivity differs by person
4. **Optimism Bias:** Underestimate difficulties
5. **Pressure:** Management wants low estimates

**Brooks' Law:** *"Adding people to a late project makes it later"*
- New people need training (reduces productivity temporarily)
- Communication overhead increases

***

### **PART 2: STAFFING (Team Structure)**

**Key Question:** How many people? What skills? How organized?

***

#### **Staffing Calculation:**

**From COCOMO:**
\[ \text{Team Size (N)} = \frac{\text{Effort (E)}}{\text{Duration (T)}} \]

**Example:**
```
Effort: 360 Person-Months
Duration: 18 Months
Team Size: 360 / 18 = 20 people (average)
```

**Note:** Team size varies over project lifecycle (Rayleigh curve)

***

#### **Team Organization Models:**

***

##### **1. Democratic Team (Egoless)**

**Structure:**
- **No leader**
- **Peer collaboration**
- Decisions by consensus

**Characteristics:**
- Everyone equal
- Shared responsibility
- Open communication

**Advantages:**
- High morale
- Creative solutions
- Knowledge sharing

**Disadvantages:**
- Slow decisions
- No clear accountability
- May lack direction

**Best For:** Research projects, small teams (3-5 people)

***

##### **2. Chief Programmer Team**

**Structure:**
```
Chief Programmer (Lead)
    ├─ Backup Programmer (Deputy)
    ├─ Programmers (2-3)
    ├─ Librarian (Documentation/CM)
    └─ Toolsmith (Tools support)
```

**Chief Programmer:**
- Best technical person
- Makes all major decisions
- Reviews all code
- Critical path tasks

**Advantages:**
- Clear leadership
- Fast decisions
- High quality (expert oversight)

**Disadvantages:**
- Single point of failure (if chief leaves)
- Bottleneck (chief overloaded)
- Team morale (others feel subordinate)

**Best For:** Complex projects needing strong technical leadership

***

##### **3. Hierarchical Team (Traditional)**

**Structure:**
```
Project Manager
    ├─ Module Lead 1
    │    ├─ Developer A
    │    └─ Developer B
    ├─ Module Lead 2
    │    ├─ Developer C
    │    └─ Developer D
    └─ QA Lead
         └─ Testers
```

**Advantages:**
- Scalable (works for large teams)
- Clear reporting structure
- Specialization by module

**Disadvantages:**
- Communication overhead (hierarchical layers)
- Slower information flow
- May create silos

**Best For:** Large projects (50+ people)

***

##### **4. Agile Team (Self-Organizing)**

**Structure:**
- **Product Owner:** Defines requirements
- **Scrum Master:** Facilitates process
- **Development Team:** Cross-functional (5-9 people)

**Characteristics:**
- Self-organizing (team decides how to work)
- Cross-functional (developers + testers + designers)
- Flat structure

**Advantages:**
- Flexible, adaptive
- High ownership
- Fast delivery

**Disadvantages:**
- Requires mature team
- Can be chaotic if undisciplined

**Best For:** Evolving requirements, customer collaboration

***

#### **Staffing Over Time (Rayleigh Curve):**

**Team size varies by phase:**

```
Team
Size
  ↑
20│         ╱‾‾╲
  │        ╱    ╲
15│       ╱      ╲
  │      ╱        ╲___
10│     ╱              ‾‾╲
  │    ╱                   ╲
 5│___╱                     ╲___
  └─────────────────────────────→ Time
    Req  Design  Code  Test  Deploy

Phase      Team Size
────────   ──────────
Req        5 (analysts)
Design     10 (architects + developers)
Coding     20 (peak: many developers)
Testing    15 (testers + developers)
Deploy     5 (ops team)
```

**Ramp-Up:** Gradual increase (training, onboarding)  
**Peak:** During coding phase  
**Ramp-Down:** Gradual decrease after testing

***

#### **Skill Mix:**

**Typical Roles:**
1. **Project Manager** (1): Planning, tracking, stakeholder management
2. **Architects** (2-3): High-level design, technology decisions
3. **Senior Developers** (20%): Complex modules, mentoring
4. **Developers** (50%): Implementation
5. **Testers** (20%): QA, test automation
6. **DevOps** (1-2): Deployment, infrastructure
7. **UI/UX Designer** (1): User interface
8. **Technical Writer** (1): Documentation

***

#### **Staffing Best Practices:**

1. **Right Skills:** Match skills to tasks (don't put junior dev on critical module)
2. **Balanced Team:** Mix of senior/junior (mentoring)
3. **Continuity:** Avoid high turnover (knowledge loss)
4. **Communication:** Small teams communicate better (keep teams 5-9 people)
5. **Motivation:** Recognize contributions, avoid burnout

***

### **Project Tracking:**

**Milestones:**
- **Milestone:** Measurable checkpoint (e.g., "Design Complete")
- **Deliverable:** Tangible output (e.g., Design Document)

**Earned Value Management (EVM):**
- **Planned Value (PV):** Budgeted cost for scheduled work
- **Earned Value (EV):** Budgeted cost for completed work
- **Actual Cost (AC):** Actual cost spent

**Metrics:**
\[ \text{Schedule Variance (SV)} = EV - PV \]
\[ \text{Cost Variance (CV)} = EV - AC \]

**Example:**
```
PV (planned): $100K by Week 10
EV (completed): $80K worth of work
AC (spent): $90K

SV = 80K - 100K = -20K (behind schedule)
CV = 80K - 90K = -10K (over budget)
```

***
# **📚 HIGH-PRIORITY QUESTIONS - Q32 ONWARDS**

***

## **Q32. Explain McCall's Quality Model.**

### **ANSWER (6-8 marks):**

**McCall's Quality Model** (1977) is a framework for assessing software quality through **11 quality factors** organized into **3 perspectives** of software use.

**Purpose:** Provide objective criteria for measuring software quality

***

### **Three Perspectives:**

***

#### **1. PRODUCT OPERATION (Using the software)**

**"How well does the software work during execution?"**

***

##### **a) Correctness**

**Definition:** Extent to which program satisfies specifications and meets user objectives

**Measures:**
- Completeness (% requirements implemented)
- Consistency (no contradictions)
- Traceability (requirements → features)

**Example:** Banking software correctly calculates interest per specifications

***

##### **b) Reliability**

**Definition:** Extent to which software performs without failures

**Measures:**
- MTBF (Mean Time Between Failures)
- Failure rate
- Availability (uptime %)

**Example:** System runs 99.9% of time without crashes

***

##### **c) Efficiency**

**Definition:** Computing resources required for software execution

**Measures:**
- **Execution Efficiency:** CPU time, response time
- **Storage Efficiency:** Memory usage, disk space

**Example:** Search completes in <1 second using <50MB RAM

***

##### **d) Integrity**

**Definition:** Extent to which software prevents unauthorized access

**Measures:**
- Access control mechanisms
- Encryption strength
- Audit trails

**Example:** User authentication, role-based permissions

***

##### **e) Usability**

**Definition:** Effort required to learn, operate, and prepare inputs

**Measures:**
- Learning time (hours to proficiency)
- Task completion rate
- Error rate
- User satisfaction score

**Example:** New user completes checkout in <3 clicks without help

***

#### **2. PRODUCT REVISION (Changing the software)**

**"How easy is it to modify the software?"**

***

##### **f) Maintainability**

**Definition:** Effort required to locate and fix defects

**Measures:**
- Code complexity (Cyclomatic Complexity)
- Modularity (coupling/cohesion)
- Documentation quality
- Mean Time To Repair (MTTR)

**Example:** Bug fix takes <2 hours on average

***

##### **g) Flexibility**

**Definition:** Effort required to modify operational software

**Measures:**
- Modifiability (ease of changes)
- Extensibility (adding features)
- Configuration options

**Example:** Add new payment method in 1 day (not 1 month)

***

##### **h) Testability**

**Definition:** Effort required to test software to ensure it performs intended function

**Measures:**
- Code coverage achievable
- Test case design ease
- Fault isolation ability

**Example:** 90% code coverage achieved with automated tests

***

#### **3. PRODUCT TRANSITION (Moving software)**

**"How easily can software adapt to new environments?"**

***

##### **i) Portability**

**Definition:** Effort required to transfer software from one platform to another

**Measures:**
- Platform independence
- Hardware dependencies
- OS dependencies

**Example:** Software runs on Windows, Mac, Linux without changes

***

##### **j) Reusability**

**Definition:** Extent to which software (or parts) can be reused in other applications

**Measures:**
- Modularity
- Generality (not application-specific)
- Documentation for reuse

**Example:** Payment module reused in 5 different projects

***

##### **k) Interoperability**

**Definition:** Effort required to couple software with other systems

**Measures:**
- Standard protocols (REST, SOAP)
- API documentation
- Data format compatibility (JSON, XML)

**Example:** System integrates with SAP, Salesforce via APIs

***

### **McCall's Quality Model Structure:**

```
                   SOFTWARE QUALITY
                          │
        ┌─────────────────┼─────────────────┐
        │                 │                 │
  PRODUCT           PRODUCT            PRODUCT
  OPERATION         REVISION          TRANSITION
        │                 │                 │
    ┌───┴────┬───────┬────┴─┬────┬───┬─────┴──┬─────────┐
    │        │       │      │    │   │        │         │
Correct  Reliable Efficient Integ Usable Main Flex Test Port Reuse Inter
```

***

### **Measuring Quality Factors:**

**Each factor measured through multiple criteria:**

**Example: Reliability**
- **Criteria:**
  1. Completeness (all functions work)
  2. Consistency (no contradictory outputs)
  3. Accuracy (results correct)
  4. Error tolerance (handles invalid inputs)

**Metrics:**
- Defect density: 2 defects/KLOC
- MTBF: 500 hours
- Availability: 99.5%

**Scoring:**
\[ \text{Reliability Score} = \text{Weighted Average of Criteria} \]

***

### **Advantages:**

1. **Comprehensive:** Covers multiple quality dimensions
2. **Structured:** Organized by user perspective
3. **Measurable:** Each factor has metrics
4. **User-Centric:** Addresses what users care about

***

### **Limitations:**

1. **Overlapping Factors:** Some factors related (maintainability ↔ testability)
2. **Measurement Difficulty:** Subjective metrics (usability)
3. **Trade-offs:** High efficiency may reduce maintainability
4. **Outdated:** 1977 model, doesn't address modern concerns (security emphasis)

***

## **Q33. Explain Boehm's Quality Model.**

### **ANSWER (6-8 marks):**

**Boehm's Quality Model** (1978) is a hierarchical model organizing software quality into **high-level characteristics**, **intermediate characteristics**, and **primitive characteristics**.

**Structure:** Tree-like hierarchy (top-down decomposition)

***

### **Top Level: Three Primary Uses**

***

#### **1. AS-IS UTILITY**

**"How well does the software perform NOW?"**

**Sub-characteristics:**

##### **a) Portability**
- **Device Independence:** Runs on different hardware
- **Self-Containedness:** Minimal external dependencies
- **Accuracy:** Correct computational results

##### **b) Reliability**
- **Completeness:** All features implemented
- **Robustness:** Handles errors gracefully
- **Consistency:** No contradictory behavior

##### **c) Efficiency**
- **Accountability:** Resource usage tracked
- **Accessibility:** Easy to use
- **Communicativeness:** Clear user feedback

***

#### **2. MAINTAINABILITY**

**"How easy is it to understand and modify?"**

**Sub-characteristics:**

##### **a) Testability**
- **Structuredness:** Well-organized code
- **Self-Descriptiveness:** Clear documentation
- **Augmentability:** Easy to add features

##### **b) Understandability**
- **Consistency:** Uniform coding style
- **Structuredness:** Logical organization
- **Conciseness:** Minimal complexity

##### **c) Modifiability**
- **Structuredness:** Modular design
- **Augmentability:** Easy to extend

***

#### **3. GENERAL UTILITY (Portability)**

**"How easily can it be transferred to new environments?"**

**Includes:** Device independence, self-containedness

***

### **Boehm's Hierarchy Example:**

```
SOFTWARE QUALITY
    │
    ├─ AS-IS UTILITY
    │   ├─ Portability
    │   │   ├─ Device Independence
    │   │   ├─ Self-Containedness
    │   │   └─ Accuracy
    │   │
    │   ├─ Reliability
    │   │   ├─ Completeness
    │   │   ├─ Robustness
    │   │   └─ Consistency
    │   │
    │   └─ Efficiency
    │       └─ (Resource optimization)
    │
    ├─ MAINTAINABILITY
    │   ├─ Testability
    │   ├─ Understandability
    │   └─ Modifiability
    │
    └─ PORTABILITY (General Utility)
```

***

### **Primitive Characteristics (Lowest Level):**

**Measurable attributes:**

1. **Structuredness:** Modularity, low complexity
2. **Self-Descriptiveness:** Comments, documentation
3. **Conciseness:** LOC, complexity metrics
4. **Augmentability:** Ease of adding features
5. **Device Independence:** Platform-neutral code
6. **Completeness:** % requirements met
7. **Consistency:** Naming conventions, style
8. **Robustness:** Error handling coverage
9. **Accuracy:** Test pass rate

***

### **Key Concepts:**

#### **1. Hierarchical Decomposition**

**Each quality characteristic broken down** into sub-characteristics until measurable primitives reached.

**Example:**
```
Maintainability
    → Understandability
        → Consistency
            → Naming convention adherence (95%)
            → Comment density (20% of code)
```

***

#### **2. Trade-offs**

**Boehm emphasized quality trade-offs:**

**Examples:**
- **Efficiency ↔ Maintainability:** Optimized code often harder to read
- **Portability ↔ Efficiency:** Platform-neutral code may be slower
- **Robustness ↔ Efficiency:** Error checking adds overhead

**Decision:** Prioritize based on project needs

***

### **Boehm vs. McCall:**

| Aspect | McCall | Boehm |
|--------|--------|-------|
| **Structure** | 3 perspectives, 11 factors | Hierarchical tree |
| **Focus** | User perspective | Developer + user perspective |
| **Depth** | Flat (factors → metrics) | Deep (multiple levels) |
| **Emphasis** | Operational quality | Maintenance + operation |
| **Trade-offs** | Not explicit | **Explicitly addressed** |

***

### **Advantages:**

1. **Hierarchical:** Clear decomposition to measurable attributes
2. **Trade-off Aware:** Recognizes conflicting goals
3. **Developer-Friendly:** Emphasizes maintainability
4. **Systematic:** Structured assessment approach

***

### **Limitations:**

1. **Complexity:** Many levels, hard to navigate
2. **Overlapping:** Some characteristics appear in multiple branches
3. **Measurement:** Still subjective at primitive level
4. **Incomplete:** Doesn't cover all modern concerns (security)

***

## **Q34. Explain ISO 9126 Quality Model.**

### **ANSWER (6-8 marks):**

**ISO 9126** (International Standard) defines a **comprehensive quality model** for evaluating software products, now replaced by **ISO/IEC 25010** (2011) but still widely referenced.

***

### **Six Quality Characteristics:**

***

#### **1. FUNCTIONALITY**

**Definition:** Capability of software to provide functions meeting stated/implied needs

**Sub-characteristics:**

##### **a) Suitability**
- Appropriateness for specified tasks
- **Example:** Word processor has spell-check (suitable for document editing)

##### **b) Accuracy**
- Correctness of results
- **Example:** Calculator computes 2+2=4 (not 5)

##### **c) Interoperability**
- Ability to interact with specified systems
- **Example:** Import/export Excel files

##### **d) Security**
- Protect information/data
- **Example:** Encryption, access control

##### **e) Compliance**
- Adherence to standards, regulations
- **Example:** GDPR compliance for EU users

***

#### **2. RELIABILITY**

**Definition:** Capability to maintain performance level under stated conditions

**Sub-characteristics:**

##### **a) Maturity**
- Low frequency of failure
- **Example:** Version 3.0 crashes less than version 1.0

##### **b) Fault Tolerance**
- Maintain performance despite faults
- **Example:** Continue operating if one server fails (redundancy)

##### **c) Recoverability**
- Re-establish performance after failure
- **Example:** Auto-save recovers document after crash

***

#### **3. USABILITY**

**Definition:** Effort needed to use software and user satisfaction

**Sub-characteristics:**

##### **a) Understandability**
- User can recognize what software does
- **Example:** Clear menu labels ("File", "Edit", "Help")

##### **b) Learnability**
- Effort to learn how to use
- **Example:** Tutorial completes in 10 minutes

##### **c) Operability**
- Ease of operation and control
- **Example:** Keyboard shortcuts for common tasks

##### **d) Attractiveness**
- Appealing to user
- **Example:** Modern UI design, pleasant colors

***

#### **4. EFFICIENCY**

**Definition:** Performance relative to resources used

**Sub-characteristics:**

##### **a) Time Behavior**
- Response time, throughput
- **Example:** Page loads in <2 seconds

##### **b) Resource Utilization**
- Amount/duration of resources used
- **Example:** Uses <100MB RAM, <10% CPU

***

#### **5. MAINTAINABILITY**

**Definition:** Effort needed to make modifications

**Sub-characteristics:**

##### **a) Analyzability**
- Ease of diagnosing deficiencies
- **Example:** Logs help identify error cause

##### **b) Changeability**
- Ease of modification
- **Example:** Change tax rate in config file (not hardcoded)

##### **c) Stability**
- Avoid unexpected effects from changes
- **Example:** Fixing login doesn't break checkout

##### **d) Testability**
- Ease of validating modified software
- **Example:** Unit tests verify changes

***

#### **6. PORTABILITY**

**Definition:** Ease of transferring to different environments

**Sub-characteristics:**

##### **a) Adaptability**
- Adapt to different environments
- **Example:** Runs on Windows 10 and 11

##### **b) Installability**
- Ease of installation
- **Example:** One-click installer

##### **c) Co-existence**
- Co-exist with other software
- **Example:** Two antivirus programs don't conflict

##### **d) Replaceability**
- Replace other software
- **Example:** Import settings from competitor product

***

### **ISO 9126 Structure:**

```
            SOFTWARE QUALITY
                  │
    ┌─────┬───────┼────┬──────┬──────────┐
    │     │       │    │      │          │
Functional Reliable Usable Efficient Maintain Portable
    │     │       │    │      │          │
(5 sub) (3 sub) (4 sub) (2 sub) (4 sub) (4 sub)
```

**Total: 6 characteristics, 27 sub-characteristics**

***

### **Quality Metrics (Examples):**

**Functionality:**
- Security: # of security vulnerabilities found
- Compliance: % of regulatory requirements met

**Reliability:**
- Maturity: Defects per KLOC
- Recoverability: Mean Time To Recover (MTTR)

**Usability:**
- Learnability: Time for novice to complete task
- Operability: # of clicks to complete task

**Efficiency:**
- Time Behavior: Average response time
- Resource: Peak memory usage

**Maintainability:**
- Analyzability: Time to locate defect
- Changeability: Effort to implement change

**Portability:**
- Adaptability: # platforms supported
- Installability: Installation time

***

### **ISO/IEC 25010 (Successor to 9126):**

**Added Characteristics:**
1. **Compatibility:** (Replaces co-existence, interoperability)
   - Co-existence
   - Interoperability

2. **Security:** (Elevated from sub-characteristic)
   - Confidentiality
   - Integrity
   - Non-repudiation
   - Accountability
   - Authenticity

**Reflects modern concerns:** Cybersecurity, cloud computing, mobile apps

***

### **Advantages:**

1. **International Standard:** Widely accepted
2. **Comprehensive:** Covers all quality aspects
3. **Structured:** Clear hierarchy
4. **Measurable:** Each sub-characteristic has metrics
5. **Certification Basis:** Used in quality audits

***

### **Limitations:**

1. **Abstract:** High-level, needs interpretation
2. **Overlapping:** Some sub-characteristics related
3. **Context-Dependent:** Priorities vary by project
4. **Measurement Subjectivity:** Some metrics hard to quantify (attractiveness)

***

## **Q35. Explain Software Documentation Types and Importance.**

### **ANSWER (6-8 marks):**

**Software Documentation** consists of written text/illustrations accompanying software, explaining **how it works**, **how to use it**, and **how it was developed**.

**IEEE Definition:** *"Written material conveying information about software systems."*

***

### **Types of Documentation:**

***

#### **1. USER DOCUMENTATION**

**Audience:** End-users, customers

**Purpose:** Help users **operate** the software

***

##### **a) User Manual**

**Content:**
- Installation instructions
- Feature descriptions
- Step-by-step procedures
- Screenshots, tutorials

**Example:** "How to create invoice in accounting software"

***

##### **b) Quick Start Guide**

**Content:**
- Basic setup (5 pages max)
- Common tasks
- Minimal detail for quick start

**Example:** "Install → Create Account → First Project (10 minutes)"

***

##### **c) Online Help**

**Content:**
- Context-sensitive help (F1 key)
- Search functionality
- FAQs

**Example:** Click "?" icon on form → explains each field

***

##### **d) Tutorial/Training Materials**

**Content:**
- Hands-on exercises
- Video tutorials
- Sample datasets

**Example:** "Create your first dashboard: Step 1..."

***

##### **e) Release Notes**

**Content:**
- New features in version
- Bug fixes
- Known issues
- Upgrade instructions

**Example:** "Version 3.5: Added dark mode, fixed login bug"

***

#### **2. SYSTEM DOCUMENTATION**

**Audience:** Developers, maintainers, architects

**Purpose:** Explain **how system works** internally

***

##### **a) Requirements Document (SRS)**

**Content:**
- Functional requirements
- Non-functional requirements
- Constraints, assumptions

**Example:** "System shall process 10,000 transactions/second"

***

##### **b) Design Documents**

**Content:**

**High-Level Design (HLD):**
- Architecture diagrams
- Technology stack
- Module structure

**Low-Level Design (LLD):**
- Class diagrams
- Algorithm pseudocode
- Database schema

**Example:** ER diagram, UML class diagram

***

##### **c) Source Code Documentation**

**Content:**
- **Inline Comments:** Explain complex logic
- **Function Headers:** Parameters, return values, purpose
- **API Documentation:** JavaDoc, Doxygen

**Example:**
```java
/**
 * Calculates compound interest.
 * @param principal Initial amount
 * @param rate Annual interest rate (0.05 for 5%)
 * @param years Number of years
 * @return Total amount after interest
 */
public double calculateInterest(double principal, double rate, int years) {
    return principal * Math.pow(1 + rate, years);
}
```

***

##### **d) Test Documentation**

**Content:**
- Test plans
- Test cases (inputs, expected outputs)
- Test reports (results, defects)

**Example:** "Test Case TC-101: Login with invalid password → Expect error message"

***

##### **e) Configuration Management Documents**

**Content:**
- Version control procedures
- Build instructions
- Deployment procedures

**Example:** "To deploy: git pull → mvn clean install → docker build"

***

#### **3. PROCESS DOCUMENTATION**

**Audience:** Project managers, auditors, new team members

**Purpose:** Explain **how development process** works

***

##### **a) Project Plan**

**Content:**
- Schedule (Gantt chart)
- Resource allocation
- Risk management plan

***

##### **b) Quality Assurance Plan**

**Content:**
- Quality standards
- Review procedures
- Metrics collection

***

##### **c) Process Manuals**

**Content:**
- Coding standards
- Review checklists
- Change control process

**Example:** "All code must pass SonarQube analysis before merge"

***

### **Importance of Documentation:**

***

#### **1. Knowledge Transfer**

**Without Documentation:**
- Knowledge locked in developers' heads
- Team member leaves → knowledge lost
- New hires take months to understand system

**With Documentation:**
- New developers productive faster
- Continuity despite turnover
- Distributed teams aligned

**Example:** Developer gets hit by bus (Bus Factor) → documentation ensures project continues

***

#### **2. Maintenance & Troubleshooting**

**Scenario:** Bug reported in production

**Without Documentation:**
- Must reverse-engineer code to understand behavior
- Hours/days to locate root cause
- Risk of breaking unrelated features

**With Documentation:**
- Design doc explains module interactions
- Comments explain complex logic
- Logs help trace execution

**Example:** "Payment failing → Check design doc → See PaymentService calls ExternalAPI → Check API docs → API changed format"

***

#### **3. User Adoption**

**Without Documentation:**
- Users don't know how to use features
- Support calls overwhelm team
- Users abandon product

**With Documentation:**
- Users self-serve (tutorials, FAQs)
- Reduced support costs
- Higher user satisfaction

**Example:** Google products have extensive help centers → users find answers without contacting support

***

#### **4. Quality Assurance**

**Documentation enables:**
- **Reviews:** Design reviews catch flaws before coding
- **Testing:** Requirements doc → test cases
- **Audits:** Prove compliance (ISO, FDA)

**Example:** Medical software requires FDA approval → extensive documentation mandatory

***

#### **5. Legal/Contractual**

**Documentation as:**
- **Contract:** SRS defines what's delivered
- **Proof:** Timestamped docs prove IP ownership
- **Compliance:** GDPR requires data handling documentation

**Example:** Customer disputes feature → SRS shows feature out of scope → contract upheld

***

#### **6. Team Coordination**

**Large teams need:**
- **Interface specs:** Module A developers know how to call Module B
- **Coding standards:** Consistent code across team
- **Architecture docs:** Align on overall structure

**Example:** 50-person team → without docs, chaos; with docs, coordinated development

***

### **Documentation Best Practices:**

**1. Keep Updated:**
- ❌ Outdated docs worse than no docs (misleading)
- ✓ Update docs with code changes

**2. Appropriate Level:**
- ❌ Too detailed: Takes forever to read
- ❌ Too vague: Useless
- ✓ Right detail for audience

**3. Use Diagrams:**
- One diagram > 1000 words
- UML, flowcharts, screenshots

**4. Searchable:**
- Online docs with search
- Indexed PDFs

**5. Version Controlled:**
- Docs in Git (like code)
- Track changes over time

***

### **Common Problems:**

**1. Outdated Documentation:**
- Code changed, docs didn't → misleading

**2. Missing Documentation:**
- "The code is self-documenting" (it's not)

**3. Over-Documentation:**
- 500-page manual nobody reads

**4. Poor Quality:**
- Typos, unclear writing, bad translations

***

### **Tools:**

**User Docs:**
- Confluence, Notion
- MkDocs, Sphinx
- Adobe FrameMaker

**Code Docs:**
- JavaDoc, Doxygen
- Swagger (API docs)

**Diagrams:**
- Visio, Lucidchart
- PlantUML, Draw.io

***

## **Q36. Explain CASE (Computer-Aided Software Engineering) Tools.**

### **ANSWER (6-8 marks):**

**CASE Tools** are software applications that **automate** or **support** software engineering activities throughout the SDLC.

**Purpose:** Increase productivity, improve quality, reduce manual effort

***

### **Categories of CASE Tools:**

***

#### **1. UPPER CASE (Front-End Tools)**

**Focus:** Early phases (requirements, design)

**Tools:**

##### **a) Requirements Tools**
- Capture, organize, track requirements
- **Examples:** IBM DOORS, Jama Connect, Caliber

**Features:**
- Requirements traceability matrix
- Impact analysis (which design elements affected by requirement change)
- Version control for requirements

***

##### **b) Analysis & Design Tools**
- Create diagrams (DFD, ER, UML)
- **Examples:** 
  - **Rational Rose:** UML modeling
  - **Enterprise Architect:** Complete modeling suite
  - **Visio:** General-purpose diagramming

**Features:**
- Drag-and-drop diagram creation
- Consistency checking (e.g., all classes in sequence diagram exist in class diagram)
- Code generation from diagrams

***

##### **c) Prototyping Tools**
- Rapid UI mockups
- **Examples:** Figma, Adobe XD, Balsamiq

**Features:**
- Wireframing
- Interactive prototypes (clickable)
- User feedback collection

***

#### **2. LOWER CASE (Back-End Tools)**

**Focus:** Implementation, testing, maintenance

**Tools:**

##### **a) Code Generators**
- Generate code from designs
- **Examples:** 
  - Hibernate (Java persistence from DB schema)
  - WSDL2Java (web service stubs from WSDL)

**Features:**
- Boilerplate code generation (getters/setters, constructors)
- Database mapping
- Template-based generation

***

##### **b) Compilers & Debuggers**
- Translate code, find errors
- **Examples:** GCC, Visual Studio, IntelliJ IDEA

**Features:**
- Syntax checking
- Step-through debugging
- Breakpoints, watch variables

***

##### **c) Testing Tools**

**Unit Testing:**
- JUnit (Java), NUnit (C#), PyTest (Python)

**Integration Testing:**
- Selenium (web UI automation)
- Postman (API testing)

**Performance Testing:**
- JMeter, LoadRunner

**Features:**
- Test case execution
- Coverage analysis
- Regression testing

***

##### **d) Static Analysis Tools**
- Analyze code without executing
- **Examples:** SonarQube, ESLint, Checkstyle

**Features:**
- Code smell detection (long methods, high complexity)
- Security vulnerability scanning
- Coding standard enforcement

***

#### **3. INTEGRATED CASE (I-CASE)**

**Definition:** Tools covering **entire lifecycle** (requirements → maintenance)

**Examples:**
- **IBM Rational Suite:** Requirements, design, coding, testing
- **Microsoft Visual Studio Team System:** Complete ALM

**Features:**
- Single repository (all artifacts)
- Seamless tool integration
- End-to-end traceability

***

#### **4. CONFIGURATION MANAGEMENT TOOLS**

**Version Control:**
- **Git:** Distributed version control
- **SVN:** Centralized version control

**Build Tools:**
- **Maven/Gradle:** Java build automation
- **Make/CMake:** C/C++ build

**CI/CD:**
- **Jenkins:** Continuous integration
- **GitLab CI:** Integrated CI/CD

**Features:**
- Automated builds
- Merge conflict resolution
- Deployment pipelines

***

#### **5. PROJECT MANAGEMENT TOOLS**

**Examples:** JIRA, Trello, MS Project, Asana

**Features:**
- Task tracking (Kanban, Scrum boards)
- Gantt charts
- Resource allocation
- Time tracking

***

### **Workbench Concept:**

**CASE Workbench:** Integrated environment with multiple tools

**Example: Eclipse IDE**
```
┌─────────────────────────────────┐
│         Eclipse IDE              │
├─────────────────────────────────┤
│ Editor (syntax highlighting)    │
│ Compiler (javac)                │
│ Debugger                        │
│ JUnit (testing)                 │
│ Git (version control)           │
│ Maven (build)                   │
│ SonarLint (code quality)        │
└─────────────────────────────────┘
```

**Single interface, multiple tools integrated**

***

### **Repository:**

**Central database storing all project artifacts:**

**Contents:**
- Requirements
- Design models
- Source code
- Test cases
- Documentation

**Benefits:**
- **Consistency:** Single source of truth
- **Traceability:** Link requirements → code → tests
- **Reuse:** Find and reuse components
- **Impact Analysis:** See what's affected by changes

***

### **Advantages of CASE Tools:**

**1. Increased Productivity:**
- Code generation saves time
- Automation reduces manual work
- **Example:** Generating 1000 lines of boilerplate in 1 second vs. 2 hours manual

**2. Improved Quality:**
- Static analysis catches defects early
- Consistency checking (diagrams match code)
- **Example:** SonarQube finds security vulnerabilities before production

**3. Better Documentation:**
- Auto-generate docs from code (JavaDoc)
- Keep diagrams synchronized with code
- **Example:** UML diagrams updated automatically when code changes

**4. Enhanced Collaboration:**
- Shared repository
- Conflict resolution (version control)
- **Example:** 10 developers work on same project without overwriting each other

**5. Cost Reduction:**
- Early defect detection (cheaper to fix)
- Reduced testing time (automation)
- **Example:** Automated tests run in 10 minutes vs. 2 days manual testing

**6. Standardization:**
- Enforce coding standards automatically
- Consistent process across teams
- **Example:** All code follows Google Style Guide (checked by tool)

***

### **Disadvantages:**

**1. High Initial Cost:**
- Enterprise tools expensive (IBM Rational: $10K+ per license)
- Training costs

**2. Learning Curve:**
- Complex tools take weeks/months to master
- Productivity dip initially

**3. Over-Reliance:**
- Developers may not understand generated code
- Tools can't replace human judgment

**4. Vendor Lock-In:**
- Switching tools difficult (repository migration)
- Proprietary formats

**5. Maintenance:**
- Tools require updates
- May not support latest technologies

**6. Not Universal:**
- Different tools for different languages/platforms
- Integration challenges

***

### **Examples by Category:**

| Category | Tool | Purpose |
|----------|------|---------|
| **Requirements** | DOORS | Manage requirements |
| **Modeling** | Rational Rose | UML diagrams |
| **IDE** | IntelliJ IDEA | Java development |
| **Version Control** | Git | Source control |
| **Testing** | Selenium | Web automation |
| **CI/CD** | Jenkins | Automated build/deploy |
| **Static Analysis** | SonarQube | Code quality |
| **Project Mgmt** | JIRA | Issue tracking |
| **Documentation** | Doxygen | API docs from code |

***

### **Trends:**

**1. Cloud-Based CASE:**
- GitHub, GitLab (cloud repositories)
- No installation, accessible anywhere

**2. AI-Assisted Tools:**
- GitHub Copilot (AI code completion)
- DeepCode (AI bug detection)

**3. DevOps Integration:**
- CASE tools integrate with CI/CD pipelines
- Automated testing in production

***

## **Q37. Explain Software Reuse Concept.**

### **ANSWER (6-8 marks):**

**Software Reuse** is the process of using **existing software artifacts** (code, designs, documentation) in new applications rather than building from scratch.

**Principle:** "Don't reinvent the wheel"

***

### **What Can Be Reused?**

**1. Code:**
- Functions, classes, modules
- **Example:** Reuse `StringUtils.reverse()` in 10 projects

**2. Design:**
- Design patterns (Singleton, Factory)
- Architecture patterns (MVC, microservices)

**3. Requirements:**
- Common features (user login, payment processing)
- Domain knowledge (banking regulations)

**4. Test Cases:**
- Test scripts for common scenarios
- **Example:** Login test reused across applications

**5. Documentation:**
- User manual templates
- API documentation patterns

***

### **Levels of Reuse:**

***

#### **1. Ad-Hoc Reuse (Opportunistic)**

**Approach:** Copy-paste code as needed

**Example:**
```java
// Project A: validation.java
public boolean isValidEmail(String email) {
    return email.matches("^[A-Z]+@[A-Z]+\\.[A-Z]+$");
}

// Project B: Copy-paste same function
public boolean isValidEmail(String email) { ... }
```

**Problems:**
- **No centralization:** Bug fix in A doesn't propagate to B
- **Version divergence:** B modifies code, now two versions
- **Hard to track:** Where else did we copy this?

***

#### **2. Planned Reuse (Systematic)**

**Approach:** Design components **intentionally for reuse**

**Example:**
```java
// commons-validator library (designed for reuse)
<dependency>
    <groupId>commons-validator</groupId>
    <artifactId>commons-validator</artifactId>
</dependency>

// All projects use same library
EmailValidator.getInstance().isValid(email);
```

**Benefits:**
- **Centralized:** One bug fix → all projects benefit
- **Tested:** Library thoroughly tested
- **Documented:** Clear API documentation

***

### **Reuse Approaches:**

***

#### **1. Component-Based Reuse**

**Definition:** Build software from **pre-built components** (like LEGO blocks)

**Examples:**
- **UI Components:** React components, Angular modules
- **Business Logic:** Payment processing SDK
- **Data Access:** Hibernate ORM

**Example:**
```javascript
// Reusable React component
import { Button } from 'react-bootstrap';

<Button variant="primary">Submit</Button>
```

**Used in 100 pages → consistent look, minimal code**

***

#### **2. Application Frameworks**

**Definition:** Reusable architecture + common features

**Examples:**
- **Spring Framework (Java):** Dependency injection, MVC
- **Django (Python):** ORM, admin panel, authentication
- **.NET Framework:** Base class libraries

**Benefit:** 80% of application structure provided, focus on business logic

***

#### **3. Design Pattern Reuse**

**Definition:** Reuse proven **solutions to common problems**

**Examples:**
- **Singleton:** Ensure only one instance (database connection)
- **Factory:** Create objects without specifying class
- **Observer:** Notify objects of state changes (event handling)

**Example:**
```java
// Singleton pattern (reused concept, not code)
public class Database {
    private static Database instance;
    
    private Database() {}
    
    public static Database getInstance() {
        if (instance == null)
            instance = new Database();
        return instance;
    }
}
```

**Pattern reused in thousands of projects**

***

#### **4. Service Reuse (SOA)**

**Definition:** Reuse functionality via **web services**

**Examples:**
- Payment Gateway (Stripe API)
- Maps (Google Maps API)
- Authentication (Auth0, OAuth)

**Example:**
```javascript
// Reuse Stripe payment service
stripe.charges.create({
    amount: 2000,
    currency: 'usd',
    source: 'tok_visa',
});
```

**No need to build payment processing from scratch**

***

#### **5. Product Line Reuse**

**Definition:** Family of products sharing **common core** with **variable features**

**Example: Automotive Software Product Line**
- **Core:** Engine control, braking system
- **Variants:** Sedan, SUV, Truck (different configurations)

**Benefit:** 70% code reused across product variants

***

### **Benefits of Reuse:**

**1. Reduced Development Time:**
- Don't rewrite existing components
- **Example:** Using React library saves 50% UI development time

**2. Lower Cost:**
- Amortize development cost across projects
- **Example:** $100K library used in 10 projects → $10K per project

**3. Improved Quality:**
- Reused components **battle-tested** (bugs already fixed)
- **Example:** Apache Commons library used by millions → highly reliable

**4. Faster Time-to-Market:**
- Ship products faster
- **Example:** Bootstrap accelerates web development → launch in weeks, not months

**5. Standardization:**
- Consistent look and feel
- **Example:** All Google products use Material Design components

**6. Reduced Maintenance:**
- Fix bug once → all projects benefit
- **Example:** Security patch in library → update dependency, all apps secured

***

### **Challenges:**

**1. Finding Reusable Components:**
- **Problem:** Don't know what exists
- **Solution:** Component repository, search tools

**2. Understanding Components:**
- **Problem:** Unclear API, poor documentation
- **Solution:** Comprehensive docs, examples

**3. Not Invented Here (NIH) Syndrome:**
- **Problem:** Developers prefer writing own code
- **Solution:** Management policy, incentives for reuse

**4. Modification Difficulty:**
- **Problem:** Component almost fits, but needs tweaks
- **Solution:** Design for extensibility (interfaces, inheritance)

**5. Integration Issues:**
- **Problem:** Component conflicts with existing code
- **Solution:** Loose coupling, dependency management

**6. Licensing:**
- **Problem:** Open-source licenses (GPL, MIT) have restrictions
- **Solution:** Carefully review licenses

***

### **Reuse Metrics:**

**1. Reuse Ratio:**
\[ \text{Reuse Ratio} = \frac{\text{Reused LOC}}{\text{Total LOC}} \]

**Example:** 5000 LOC reused / 10000 total = **50% reuse**

**2. Cost Avoidance:**
\[ \text{Cost Saved} = \text{Cost to Build} - \text{Cost to Reuse} \]

**Example:** Build from scratch: $50K, Reuse library: $5K → **$45K saved**

**3. Defect Reduction:**
\[ \text{Defect Reduction} = \frac{\text{Defects}_{\text{new}} - \text{Defects}_{\text{reused}}}{\text{Defects}_{\text{new}}} \]

***

### **Best Practices:**

✓ **Design for Reuse:** Modular, well-documented, general-purpose  
✓ **Component Repository:** Centralized catalog (Maven Central, npm)  
✓ **Version Control:** Semantic versioning (v1.2.3)  
✓ **Clear Licensing:** Specify usage terms  
✓ **Support:** Provide help, bug fixes  
✓ **Evangelism:** Promote reuse culture

***

# **📚 HIGH-PRIORITY QUESTIONS - Q38 ONWARDS**

***

## **Q38. Explain Cleanroom Software Engineering.**

### **ANSWER (6-8 marks):**

**Cleanroom Software Engineering** is a rigorous engineering process emphasizing **defect prevention** rather than defect removal through testing.

**Origin:** Developed by IBM (Harlan Mills, 1980s), inspired by hardware "cleanrooms" (dust-free manufacturing)

**Core Philosophy:** "Build it right the first time" — prevent defects rather than find and fix them.

***

### **Key Principles:**

#### **1. Mathematical Verification (not testing)**

**Approach:**
- Use **formal methods** to prove correctness mathematically
- **Box structure specification** (black box, state box, clear box)
- Verify logic before coding

**Example:**
```
Specification: Function returns sum of array elements
Proof: By induction, sum accumulator correct at each iteration
∴ Final result mathematically proven correct
```

**vs. Traditional:** Write code → test → find bugs → fix

***

#### **2. Statistical Quality Control**

**Usage-Based Testing:**
- Generate test cases based on **expected usage patterns**
- Not exhaustive testing (impossible), but statistically representative

**Operational Profile:**
- Probability distribution of user operations
- **Example:** 70% users search, 20% browse, 10% purchase

**Certification:**
- Measure reliability (MTTF) statistically
- **Example:** "99.9% probability of 1000-hour MTTF"

***

#### **3. Incremental Development**

**Process:**
- Develop in **small increments** (~500 LOC)
- Each increment formally verified
- Integrate and certify incrementally

**Benefit:** Catch errors in small chunks (easier to locate/fix)

***

### **Cleanroom Process:**

```
1. SPECIFICATION
   ↓ (Formal specification using box structures)
   
2. DEVELOPMENT
   ↓ (Design → Code WITHOUT executing it)
   
3. CORRECTNESS VERIFICATION
   ↓ (Mathematical proof, peer reviews - NO debugging!)
   
4. STATISTICAL TESTING
   ↓ (Usage-based test cases)
   
5. CERTIFICATION
   (Measure reliability statistically)
```

***

### **Box Structure Specification:**

#### **Three Views:**

**1. Black Box:**
- **External view** (what system does)
- Inputs → Outputs (no implementation details)

**Example:**
```
Black Box: Calculator Add Function
Input: (a, b) where a, b are integers
Output: sum = a + b
```

***

**2. State Box:**
- **State view** (system state + behavior)
- Includes internal state variables

**Example:**
```
State Box: Counter
State: count (integer)
Operations:
  - increment(): count = count + 1
  - reset(): count = 0
  - getValue(): return count
```

***

**3. Clear Box:**
- **Implementation view** (how it works)
- Procedural details, algorithms

**Example:**
```
Clear Box: Counter Increment
Algorithm:
1. Read current count
2. Add 1 to count
3. Write new count
4. Return
```

**Progression:** Black → State → Clear (increasing detail)

***

### **Correctness Verification (Not Testing!):**

**Techniques:**

**1. Structured Programming:**
- Only use sequence, selection (if-else), iteration (loops)
- No GOTOs (unpredictable control flow)

**2. Stepwise Refinement:**
- Start with high-level design
- Refine progressively to implementation
- Verify correctness at each step

**3. Formal Inspections:**
- **Team reviews** code for correctness
- Use checklists (boundary conditions, loop invariants)
- **No execution** (mental/paper verification only)

**4. Mathematical Proofs:**
- Prove preconditions → postconditions
- Loop invariants (property true before/after each iteration)

**Example:**
```c
// Prove: Returns sum of array[0..n-1]
int sum(int array[], int n) {
    int total = 0;
    // Invariant: total = sum of array[0..i-1]
    for (int i = 0; i < n; i++) {
        total += array[i];
    }
    // Post: total = sum of array[0..n-1] ✓ Proven
    return total;
}
```

***

### **Statistical Testing:**

**Process:**

**1. Define Operational Profile:**
- Identify user operations (login, search, checkout)
- Estimate frequency (search: 60%, checkout: 10%)

**2. Generate Test Cases:**
- Randomly generate tests matching profile
- **Example:** 60% of tests are searches

**3. Execute Tests:**
- Run until failure or target reliability achieved

**4. Measure Reliability:**
- MTTF (Mean Time To Failure)
- Defect rate per operation

**5. Certification Decision:**
```
IF (measured MTTF ≥ target MTTF)
   THEN Certify for release
   ELSE Continue development
```

***

### **Advantages:**

**1. High Reliability:**
- Defects prevented, not just detected
- **NASA study:** Cleanroom projects had **5-10× fewer defects** than traditional

**2. Reduced Testing Time:**
- Statistical testing more efficient than exhaustive
- Focus on common scenarios

**3. Mathematical Rigor:**
- Correctness provable (not just probable)
- Suitable for safety-critical systems

**4. Clear Specifications:**
- Box structures force precise requirements
- Reduces ambiguity

**5. Predictable Quality:**
- Statistical measures provide confidence levels
- **Example:** "95% confidence of 1000-hour MTTF"

***

### **Disadvantages:**

**1. Requires Expertise:**
- Formal methods, statistics not widely known
- Steep learning curve

**2. High Initial Cost:**
- Verification time-intensive
- Training investment

**3. Resistance to Change:**
- Developers accustomed to "code and debug"
- **"No debugging?"** cultural shift

**4. Not Suitable for All:**
- Small projects: overhead too high
- Rapid prototyping: too rigid

**5. Scalability:**
- Formal proofs hard for large, complex systems
- Manual verification doesn't scale

***

### **When to Use:**

✓ **Use when:**
- Safety-critical (medical, avionics)
- High reliability required (99.999% uptime)
- Formal certification needed (FDA, FAA)
- Long-lived systems (nuclear power plant control)

✗ **Avoid when:**
- Prototype/experimental projects
- Rapidly changing requirements
- Time-to-market critical
- Team lacks formal methods expertise

***

### **Real-World Success:**

**IBM Project (1990s):**
- Developed satellite software using Cleanroom
- **Result:** Zero defects in 80 KLOC over 3 years operational use
- **Comparison:** Traditional methods: 5-10 defects/KLOC

***

## **Q39. Explain Belady-Lehman's Laws of Software Evolution.**

### **ANSWER (6-8 marks):**

**Belady-Lehman Laws** (1970s-80s) describe how software systems **evolve** over time, based on study of large IBM systems.

**Purpose:** Understand long-term maintenance challenges

***

### **The Eight Laws:**

***

#### **Law 1: CONTINUING CHANGE**

**Statement:** *"A system must be continually adapted or it becomes progressively less satisfactory."*

**Explanation:**
- Real-world changes (business, regulations, technology)
- Software must evolve to remain useful
- **Static software = obsolete software**

**Example:**
- Tax software must update annually for new tax laws
- E-commerce must support new payment methods (cryptocurrencies)

**Implication:** Maintenance inevitable, budget for it

***

#### **Law 2: INCREASING COMPLEXITY**

**Statement:** *"As a system evolves, its complexity increases unless work is done to maintain or reduce it."*

**Explanation:**
- Each change adds **interdependencies**
- **Entropy increases** (disorder grows)
- Without refactoring, system becomes unmaintainable

**Example:**
```
Initial: 10 modules, 20 dependencies
After 5 years of patches: 50 modules, 300 dependencies
→ Any change risks breaking multiple modules
```

**Implication:** **Refactoring essential** to control complexity

**Metrics:**
- Coupling increases
- Cyclomatic complexity increases
- Code becomes "spaghetti"

***

#### **Law 3: SELF-REGULATION**

**Statement:** *"The evolution process is self-regulating with close to normal distribution of measures."*

**Explanation:**
- Evolution metrics (defects, changes, growth) follow **statistical patterns**
- Predictable trends emerge over time

**Example:**
- Large system typically gets ~5% code changes per year
- Deviation from norm signals problems (massive rewrite? Staff turnover?)

**Implication:** Use historical data to predict future evolution

***

#### **Law 4: CONSERVATION OF ORGANIZATIONAL STABILITY**

**Statement:** *"The average effective global activity rate on an evolving system is invariant over the product's lifetime."*

**Explanation:**
- **Work rate stays roughly constant** over time
- Organization's capacity doesn't scale with system size
- As system grows, productivity per module decreases

**Example:**
```
Year 1: 100 KLOC, 10 developers, 100 changes/year
Year 5: 500 KLOC, 10 developers, still ~100 changes/year
(Same effort spread across larger system)
```

**Implication:** Can't accelerate evolution by throwing more people at it

***

#### **Law 5: CONSERVATION OF FAMILIARITY**

**Statement:** *"Average incremental growth remains invariant as the system evolves."*

**Explanation:**
- Each release adds similar **percentage growth**
- ~5% growth per release (typical)
- Too much change → unfamiliar system → user resistance

**Example:**
```
Release 1.0: 100 KLOC
Release 2.0: 105 KLOC (+5 KLOC, 5%)
Release 3.0: 110.25 KLOC (+5.25 KLOC, 5%)
```

**Implication:** Gradual evolution preferred over radical rewrites

***

#### **Law 6: CONTINUING GROWTH**

**Statement:** *"Functional content must be continually increased to maintain user satisfaction."*

**Explanation:**
- Users always want **more features**
- Competitive pressure drives feature growth
- Stagnant software loses market share

**Example:**
- Microsoft Word: Started as text editor, now has charts, mail merge, macros, cloud sync...
- User expectations ratchet upward (can't go backward)

**Implication:** Plan for perpetual growth (architecture scalability)

***

#### **Law 7: DECLINING QUALITY**

**Statement:** *"Evolving systems will appear to be declining in quality unless rigorously maintained and adapted to environmental changes."*

**Explanation:**
- Continuous changes introduce defects
- **Technical debt** accumulates
- Without proactive maintenance, quality deteriorates

**Example:**
```
Version 1.0: 2 bugs per KLOC (clean)
Version 5.0: 15 bugs per KLOC (after many patches)
```

**Causes:**
- Hasty bug fixes
- Workarounds instead of proper solutions
- No refactoring

**Implication:** **Preventive maintenance** (refactoring, regression testing) essential

***

#### **Law 8: FEEDBACK SYSTEM**

**Statement:** *"Evolution processes constitute multi-level, multi-loop, multi-agent feedback systems."*

**Explanation:**
- Multiple feedback loops:
  - **User feedback** → feature requests
  - **Defect reports** → bug fixes
  - **Technology changes** → upgrades
  - **Management** → budget, deadlines

**Complexity:** Interactions between loops create unpredictable dynamics

**Example:**
- User complaints → quick patch → introduces bug → more complaints → rushed fix → technical debt increases → declining quality (Law 7) → larger refactoring needed

**Implication:** Manage feedback systematically (change control, prioritization)

***

### **Graphical Representation:**

```
System
Complexity
    ↑                  Law 2 (Increasing Complexity)
    │              ╱‾‾‾‾
    │          ╱‾‾‾
    │      ╱‾‾‾               Law 7 (Declining Quality)
    │  ╱‾‾‾                   if no refactoring
    │╱‾
    └────────────────────────────→ Time
    
System
Size
    ↑                  Law 6 (Continuing Growth)
    │              ╱‾‾‾‾
    │          ╱‾‾‾
    │      ╱‾‾‾
    │  ╱‾‾‾
    │╱‾
    └────────────────────────────→ Time
```

***

### **Practical Implications:**

**1. Budget for Evolution:**
- 60-80% of lifecycle cost is **post-deployment**
- Plan maintenance budget from day 1

**2. Design for Change:**
- Modular architecture (low coupling)
- Well-documented
- Automated tests (regression prevention)

**3. Refactor Regularly:**
- Combat Law 2 (increasing complexity)
- Technical debt must be paid

**4. Manage Growth:**
- Don't add features indiscriminately (feature bloat)
- Prioritize: essential vs. nice-to-have

**5. Measure Evolution:**
- Track metrics (LOC growth, defect density, complexity)
- Detect deviations from expected patterns (Law 3)

***

### **Validation:**

**Studies confirmed Belady-Lehman laws in:**
- OS systems (IBM OS/360)
- Commercial software (banking systems)
- Open-source (Linux kernel follows Law 6 - continuing growth)

**Modern Relevance:** Still applicable despite agile/DevOps (fundamental evolution patterns persist)

***

## **Q40. Explain Requirements Validation Techniques.**

### **ANSWER (6-8 marks):**

**Requirements Validation** ensures that requirements are **correct, complete, consistent, and testable** before design begins.

**Goal:** Catch requirement defects early (cheapest to fix)

**IEEE Definition:** *"Process of ensuring requirements define the system the customer really wants."*

***

### **Validation vs. Verification:**

| Aspect | Validation | Verification |
|--------|------------|--------------|
| **Question** | "Are we building the **right** product?" | "Are we building the product **right**?" |
| **Focus** | **Requirements** correctness | **Implementation** correctness |
| **When** | Requirements phase | Design/coding/testing |
| **Example** | Customer confirms SRS | Test that code matches design |

***

### **Requirements Validation Techniques:**

***

#### **1. REQUIREMENTS REVIEWS (Inspections)**

**Process:**
- **Formal meeting** with stakeholders
- Systematically examine SRS document
- Identify defects (ambiguity, incompleteness, inconsistency)

**Participants:**
- **Moderator:** Leads review
- **Author:** Presents requirements
- **Reviewers:** Customers, developers, testers, domain experts

**Steps:**
1. **Planning:** Schedule, distribute SRS
2. **Preparation:** Reviewers study SRS independently
3. **Meeting:** Line-by-line review (2-4 hours max)
4. **Defect Logging:** Record issues (don't fix in meeting)
5. **Follow-up:** Author fixes, re-review

**Checklist Items:**
- ✓ All requirements numbered/traceable?
- ✓ No ambiguous terms ("fast", "reliable")?
- ✓ Conflicting requirements?
- ✓ Testable requirements?

**Effectiveness:** **Finds 60-70% of defects** (IBM study)

***

#### **2. PROTOTYPING**

**Approach:**
- Build **throwaway/evolutionary prototype**
- Users interact, provide feedback
- **Visual validation** (easier than reading specs)

**Types:**

**a) UI Prototype:**
- **Mockups** (Figma, Balsamiq)
- Validate interface requirements

**Example:**
```
Requirement: "User shall filter products by price range"
Prototype: Show slider widget (min/max price)
Feedback: "We need dropdown for categories too"
→ Add requirement for category filter
```

**b) Functional Prototype:**
- Working subset of features
- Validate behavior

**Example:**
- Build checkout flow (no payment integration)
- Test workflow: Cart → Shipping → Order Confirm
- Discover: "Back button doesn't preserve cart" → Add requirement

**Advantages:**
- Clarifies vague requirements
- Reveals missing requirements
- Users see what they'll get

**Disadvantages:**
- Time/cost to build
- Customer expects prototype = final product

***

#### **3. TEST CASE GENERATION (Early Testing)**

**Approach:**
- Write **test cases** from requirements (before coding!)
- If can't write test → requirement **not testable**

**Process:**
1. For each requirement, design test cases
2. Identify expected results
3. If ambiguous → requirement needs clarification

**Example:**
```
Requirement: "System shall validate email format"

Test Cases:
- TC1: Input "user@example.com" → Expect: Accept ✓
- TC2: Input "invalid.email" → Expect: Reject ✓
- TC3: Input "user@" → Expect: ??? (unclear!)

→ Requirement ambiguous, needs refinement:
"Email must contain @ symbol followed by domain with TLD"
```

**Benefit:** Forces **precision** in requirements

***

#### **4. AUTOMATED CONSISTENCY CHECKING**

**Approach:**
- Use **tools** to detect inconsistencies

**Tools:**
- **DOORS (IBM):** Requirements management
- **Jama Connect:** Traceability analysis
- **ReqIF:** Interchange format for tool integration

**Checks:**

**a) Syntactic:**
- Spelling, grammar
- Undefined terms (references)

**b) Semantic:**
```
Inconsistency Example:
REQ-1: "Password length: 8-16 characters"
REQ-25: "Password minimum: 12 characters"
→ Tool flags contradiction
```

**c) Traceability:**
```
Orphan Requirements:
REQ-50: No trace to business need
→ Why is this requirement here? (Maybe unnecessary)

Missing Requirements:
Business Need BN-10: No corresponding requirement
→ Gap in SRS
```

***

#### **5. USER ACCEPTANCE CRITERIA DEFINITION**

**Approach:**
- For each requirement, define **acceptance criteria** (how to verify)
- **Quantitative** (not subjective)

**Example:**
```
Requirement: "System shall be fast"
Acceptance Criteria:
✓ Search results in <2 seconds (95th percentile)
✓ Page load <1 second on 10 Mbps connection
✓ Support 1000 concurrent users
```

**Benefits:**
- Removes ambiguity
- Creates testable requirements
- Agreement on "done"

***

#### **6. MODEL VALIDATION (Formal Methods)**

**Approach:**
- Create **formal models** (state machines, Petri nets)
- Analyze for completeness, consistency

**Example: Vending Machine**
```
States: {Idle, CoinInserted, Dispensing}
Events: {InsertCoin, SelectProduct, Dispense}

State Transition:
Idle --InsertCoin--> CoinInserted
CoinInserted --SelectProduct--> Dispensing
Dispensing --Dispense--> Idle

Validation: Can we reach all states? Yes ✓
Deadlock? No ✓
```

**Tools:** 
- **SPIN:** Model checker
- **Alloy:** Formal specification

**Advantages:**
- Mathematical rigor
- Automated verification

**Disadvantages:**
- Requires expertise
- Time-intensive

***

#### **7. WALKTHROUGH**

**Informal Version of Review:**
- **Author presents** requirements to team
- Participants ask questions, spot issues
- Less formal than inspection (no defect metrics)

**When Used:** Early drafts, quick feedback

***

#### **8. PERSPECTIVE-BASED READING**

**Approach:**
- Reviewers assigned **different perspectives**:
  - **Customer:** "Does this meet my needs?"
  - **Designer:** "Can I design this?"
  - **Tester:** "Can I test this?"
  - **Maintainer:** "Can I modify this later?"

**Benefit:** Catches different types of defects (each perspective finds unique issues)

***

#### **9. CHECKLISTS**

**Standard Questions:**
- ✓ Requirements prioritized?
- ✓ All stakeholders identified?
- ✓ Security requirements included?
- ✓ Performance targets specified?
- ✓ Error handling defined?
- ✓ Backward compatibility addressed?

**Example Checklist Item:**
```
☐ Does requirement avoid implementation details?
   BAD: "System shall use MySQL database"
   GOOD: "System shall store data persistently"
```

***

### **Validation Metrics:**

**1. Defects Found:**
- Count issues discovered per technique
- Track: Ambiguous, incomplete, inconsistent, incorrect

**2. Review Effectiveness:**
\[ \text{Effectiveness} = \frac{\text{Defects Found in Validation}}{\text{Total Defects}} \times 100\% \]

**Example:** Found 50 defects in review, 10 more later → 50/(50+10) = **83% effective**

**3. Rework Cost:**
- Cost to fix requirement defect:
  - In validation: **$1**
  - In design: **$5**
  - In testing: **$50**
  - In production: **$500+**

**ROI of Validation:** Prevent expensive late fixes

***

### **Challenges:**

**1. Stakeholder Availability:**
- Busy customers can't attend reviews
- **Solution:** Schedule early, emphasize importance

**2. Incomplete Participation:**
- Domain experts don't attend
- **Solution:** Make attendance mandatory

**3. Time Pressure:**
- "Skip validation, start coding!"
- **Solution:** Show cost of late defect discovery

**4. Changing Requirements:**
- Requirements evolve during validation
- **Solution:** Version control, change management

***

### **Best Practices:**

✓ **Multiple Techniques:** Use 2-3 methods (reviews + prototyping)  
✓ **Early and Continuous:** Validate throughout requirements phase  
✓ **Independent Reviewers:** Not just authors  
✓ **Customer Involvement:** Essential for correctness  
✓ **Tool Support:** Automated checks supplement manual  
✓ **Documented Results:** Track defects, resolution

***

## **Q41. Explain Design Principles: Abstraction, Modularity, and Information Hiding.**

### **ANSWER (8-10 marks):**

**Design Principles** are fundamental concepts guiding software architecture to achieve **maintainability, reusability, and understandability**.

***

### **1. ABSTRACTION**

**Definition:** Emphasize **essential characteristics** while suppressing **irrelevant details**.

**Purpose:** Manage complexity by focusing on "what" (not "how")

***

#### **Levels of Abstraction:**

**a) Procedural Abstraction:**
- Function hides implementation details
- User knows **what it does**, not **how**

**Example:**
```java
// High abstraction
double sqrt(double x);

// User knows: Computes square root
// User doesn't know: Newton's method, bit manipulation, etc.
```

**b) Data Abstraction:**
- ADT (Abstract Data Type) hides representation
- User interacts via **interface**, not internal structure

**Example:**
```java
// Stack ADT
Stack<Integer> stack = new Stack<>();
stack.push(10);  // User doesn't know: array? linked list?
int top = stack.pop();
```

**Internal:** Could be array, linked list, dynamic array (user doesn't care)

***

#### **Abstraction Hierarchy:**

```
High Abstraction (User View)
    ↑
    │ "Save document"
    │
Mid Abstraction (System View)
    │
    │ saveDocument(filename) {
    │   validate(filename);
    │   serialize(document);
    │   writeToFile(filename);
    │ }
    │
Low Abstraction (Implementation)
    ↓
    write bytes to disk sector 0x4A3F...
```

**Each level hides details from the level above**

***

#### **Benefits:**

**1. Complexity Management:**
- Don't need to understand entire system at once
- Focus on relevant abstraction level

**2. Flexibility:**
- Change implementation without affecting users
- **Example:** Switch from array to linked list (Stack interface unchanged)

**3. Reusability:**
- Abstract components more general (reusable in multiple contexts)

***

#### **Example: Database Abstraction**

```java
// High abstraction
interface Database {
    void save(Object obj);
    Object load(int id);
}

// Low abstraction (hidden from users)
class MySQLDatabase implements Database {
    public void save(Object obj) {
        // SQL INSERT statements
        // Connection pooling
        // Transaction management
        // All hidden!
    }
}

// User code (doesn't know it's MySQL)
Database db = new MySQLDatabase();
db.save(customer);  // Simple interface, complex implementation hidden
```

**User can switch to `MongoDatabase` without changing code** (same interface)

***

### **2. MODULARITY**

**Definition:** Decompose software into **separate components (modules)** with well-defined interfaces.

**Module:** Cohesive unit performing specific function

***

#### **Why Modularity?**

**Without Modularity (Monolithic):**
```
┌──────────────────────────────┐
│     One Giant Program        │
│  50,000 lines of code        │
│  Everything interconnected   │
└──────────────────────────────┘

Problems:
- Hard to understand
- Change anywhere affects everywhere
- Can't reuse parts
- Can't test independently
```

**With Modularity:**
```
┌──────┐   ┌──────┐   ┌──────┐
│Module│   │Module│   │Module│
│  A   │──│  B   │──│  C   │
└──────┘   └──────┘   └──────┘

Benefits:
- Understand one module at a time
- Changes localized
- Reuse modules
- Test independently
```

***

#### **Module Characteristics:**

**1. Well-Defined Interface:**
- Public methods/functions (contract)
- **Example:** `CustomerModule.addCustomer(name, email)`

**2. Information Hiding:** (See next section)
- Internal details private

**3. Independence:**
- Low coupling (minimal dependencies)
- High cohesion (focused purpose)

***

#### **Modular Decomposition Example:**

**E-commerce System:**
```
┌────────────────────────────────┐
│    E-Commerce Application      │
└────────────────┬───────────────┘
                 │
      ┌──────────┼──────────┐
      │          │          │
┌─────▼────┐ ┌──▼──────┐ ┌─▼────────┐
│ User Mgmt│ │ Catalog │ │ Payment  │
│  Module  │ │ Module  │ │  Module  │
└──────────┘ └─────────┘ └──────────┘
│register() │ │search() │ │process() │
│login()    │ │browse() │ │refund()  │
└──────────┘ └─────────┘ └──────────┘

Each module: 500-1000 LOC (manageable)
```

***

#### **Optimal Module Size:**

**Too Large:**
- Hard to understand
- High complexity

**Too Small:**
- Too many interfaces
- Integration overhead

**Sweet Spot:** 
- **100-1000 LOC per module**
- **5-9 modules per subsystem** (Miller's Law: humans manage 7±2 items)

***

#### **Benefits:**

**1. Parallel Development:**
- Team A: User module
- Team B: Payment module
- Work independently, integrate later

**2. Incremental Testing:**
- Test each module separately (unit testing)
- Then integration testing

**3. Maintenance:**
- Fix bug in Payment module → no need to understand User module

**4. Reusability:**
- Payment module reused in multiple projects

***

### **3. INFORMATION HIDING (Encapsulation)**

**Definition:** Hide **internal details** (data structures, algorithms) within module, expose only **necessary interface**.

**Principle (Parnas, 1972):** *"Modules should hide design decisions that are most likely to change."*

***

#### **What to Hide:**

**1. Data Structures:**
```java
// Hidden: How customer list stored (array? hash map?)
public class CustomerManager {
    private List<Customer> customers;  // PRIVATE (hidden)
    
    // Public interface (visible)
    public void addCustomer(Customer c) { ... }
    public Customer findCustomer(int id) { ... }
}
```

**Users call methods, don't access `customers` directly**

**2. Algorithms:**
```java
// Hidden: Sorting algorithm (quicksort? mergesort?)
public List<Product> searchProducts(String query) {
    List<Product> results = database.query(query);
    results.sort(...);  // Internal detail
    return results;
}
```

**Change sorting algorithm → no user code breaks**

**3. Design Decisions:**
```java
// Hidden: Database type (MySQL? MongoDB?)
public class DataAccess {
    private Connection conn;  // HIDDEN
    
    public void save(Object obj) {
        // Could be SQL INSERT or MongoDB insert
        // Users don't know, don't care
    }
}
```

***

#### **Encapsulation in OOP:**

**Access Modifiers:**

```java
public class BankAccount {
    private double balance;  // HIDDEN (can't access from outside)
    
    // Public interface
    public void deposit(double amount) {
        if (amount > 0)
            balance += amount;
    }
    
    public double getBalance() {
        return balance;
    }
}

// User code
BankAccount acc = new BankAccount();
acc.deposit(100);  // OK (public method)
// acc.balance = 1000000;  // ERROR! balance is private
```

**Why Hide?**
- Prevent invalid state (negative balance)
- Can change internal representation (balance as cents? as BigDecimal?)

***

#### **Information Hiding Benefits:**

**1. Reduced Ripple Effect:**
```
Change internal implementation
    → No changes to other modules (interface unchanged)
```

**Example:**
```java
// Version 1: Array
private Customer[] customers = new Customer[100];

// Version 2: HashMap (better performance)
private Map<Integer, Customer> customers = new HashMap<>();

// Interface unchanged! (addCustomer, findCustomer same)
// User code doesn't need modification
```

**2. Independent Development:**
- Module internals can be developed independently
- As long as interface respected

**3. Security:**
- Hide sensitive data (passwords, keys)
- Expose only safe operations

**4. Testability:**
- Test public interface (black-box testing)
- Internals can be unit-tested separately

***

#### **Violation Example (BAD DESIGN):**

```java
// BAD: No information hiding
public class Customer {
    public String name;  // PUBLIC (anyone can modify)
    public String password;  // PUBLIC (security risk!)
}

// Client code
customer.password = "123";  // Direct access (BAD!)
```

**Problems:**
- Can't validate (weak password allowed)
- Can't change representation (password as hash? can't migrate)
- Security vulnerability

**GOOD Design:**
```java
public class Customer {
    private String name;
    private String hashedPassword;  // HIDDEN
    
    public void setPassword(String pwd) {
        if (pwd.length() < 8)
            throw new IllegalArgumentException("Password too short");
        this.hashedPassword = hash(pwd);  // Store hash, not plaintext
    }
    
    public boolean verifyPassword(String pwd) {
        return hash(pwd).equals(hashedPassword);
    }
}
```

**Benefits:**
- Validation enforced
- Can change hashing algorithm internally
- Security preserved

***

### **Relationship Between Principles:**

```
┌────────────────────────────────┐
│        ABSTRACTION             │  (What to show)
│  "Essential characteristics"   │
└───────────┬────────────────────┘
            │
            ↓
┌────────────────────────────────┐
│       MODULARITY               │  (How to organize)
│  "Separate components"         │
└───────────┬────────────────────┘
            │
            ↓
┌────────────────────────────────┐
│   INFORMATION HIDING           │  (What to hide)
│  "Hide implementation"         │
└────────────────────────────────┘
```

**Together:** Create maintainable, understandable, flexible systems

***

### **Design Checklist:**

✓ **Abstraction:** Can user understand module without knowing internals?  
✓ **Modularity:** Is system divided into cohesive, loosely-coupled modules?  
✓ **Information Hiding:** Are implementation details private?  
✓ **Interfaces:** Are module interfaces well-defined and minimal?  
✓ **Encapsulation:** Are data structures protected from direct access?

***
You're absolutely right to ask! 😅

**Where I was getting questions from:**
- Your **unit files** (unit-1.md through unit-10.md) that you uploaded earlier
- **Common Software Engineering syllabus** patterns (based on Pressman, Sommerville, typical university courses)
- **High-priority topics** that frequently appear in exams

I **wasn't specifically looking at your previous year paper** until you just uploaded it! That's why there's a gap. I was covering broadly important topics, but your actual exam pattern focuses more on **UML diagrams** and **specific testing techniques** than I anticipated.

**My bad for not checking the actual paper earlier!** 🙈

***

# **🎯 NOW LET'S COVER THE MISSING TOPICS!**

***

## **Q42. Explain UML Diagrams: Activity, Sequence, Collaboration, Class, and State Chart Diagrams.**

### **ANSWER (10-12 marks - Since Q2 is worth 10 marks):**

**UML (Unified Modeling Language)** provides standardized diagrams to visualize software systems from different perspectives.

***

### **1. ACTIVITY DIAGRAM**

**Definition:** Shows **workflow** or **sequence of activities** in a process (like flowchart).

**Purpose:** Model business processes, algorithm logic, workflows

**Key Components:**

#### **Elements:**

**1. Start Node (Initial State):**
- Filled circle: ●
- Entry point of activity

**2. Activity/Action:**
- Rounded rectangle
- Represents a task/operation

**3. Decision Node (Diamond):**
- Conditional branching (if-else)
- Multiple outgoing arrows with conditions

**4. Merge Node:**
- Multiple flows join into one

**5. Fork (Parallel Split):**
- Horizontal bar
- Split into parallel activities

**6. Join (Parallel Merge):**
- Horizontal bar
- Wait for all parallel activities to complete

**7. End Node (Final State):**
- Filled circle with border: ◉
- Termination point

**8. Swimlanes:**
- Vertical/horizontal partitions
- Show which actor performs which activity

***

#### **Example: Online Food Delivery System**

```
        ● START
        ↓
   [Customer browses menu]
        ↓
   [Customer adds items to cart]
        ↓
   <Proceed to checkout?>
    /           \
  Yes           No → [Continue browsing] (loop back)
   ↓
[Enter delivery address]
   ↓
[Choose payment method]
   ↓
   ◆ (Fork - Parallel activities)
   ├─→ [Process payment] → [Payment Gateway validates]
   │                            ↓
   │                       <Payment success?>
   │                        /           \
   │                      Yes           No → [Show error] → ◉ END
   │                       ↓
   └─→ [Restaurant receives order]
              ↓
       [Restaurant prepares food]
              ↓
       [Assign delivery driver]
              ↓
   ◆ (Join - Wait for payment + preparation)
              ↓
       [Driver picks up order]
              ↓
       [Driver delivers to customer]
              ↓
       [Customer receives food]
              ↓
        ◉ END
```

**With Swimlanes:**

```
┌──────────────┬────────────────┬──────────────┬─────────────┐
│  Customer    │  Restaurant    │   Driver     │  Payment    │
├──────────────┼────────────────┼──────────────┼─────────────┤
│● Start       │                │              │             │
│↓             │                │              │             │
│[Browse menu] │                │              │             │
│↓             │                │              │             │
│[Add to cart] │                │              │             │
│↓             │                │              │             │
│[Checkout] ───┼──→[Receive]    │              │             │
│              │   [order]      │              │             │
│              │      ↓          │              │             │
│[Pay]─────────┼────────────────┼──────────────→[Process]    │
│              │                │              │ [payment]   │
│              │      ↓          │              │    ↓        │
│              │   [Prepare]    │              │ [Validate]  │
│              │   [food]       │              │             │
│              │      ↓          │              │             │
│              │   [Ready]──────→[Assign]      │             │
│              │                │ [pickup]     │             │
│              │                │    ↓         │             │
│              │                │ [Deliver]    │             │
│              │                │    ↓         │             │
│[Receive]←────┼────────────────┼──┘           │             │
│ [food]       │                │              │             │
│  ↓           │                │              │             │
│ ◉ End        │                │              │             │
└──────────────┴────────────────┴──────────────┴─────────────┘
```

***

### **2. SEQUENCE DIAGRAM**

**Definition:** Shows **interactions between objects** over time (message passing).

**Purpose:** Visualize method calls, API interactions, timing

**Key Components:**

**1. Actor/Object:**
- Rectangle at top
- Lifeline: Dashed vertical line

**2. Activation Bar:**
- Thin rectangle on lifeline
- Shows object is active (processing)

**3. Messages:**
- **Synchronous:** Solid arrow →
- **Asynchronous:** Open arrow ⇢
- **Return:** Dashed arrow ⤺

**4. Time:** Flows **top to bottom**

***

#### **Example: Place Order in Food Delivery System**

```
Customer    :OrderUI    :OrderController    :PaymentService    :Database
   │            │               │                   │              │
   │──place()──→│               │                   │              │
   │            │──create()────→│                   │              │
   │            │               │──validateCart()──→│              │
   │            │               │←─────valid────────│              │
   │            │               │                   │              │
   │            │               │──processPayment()→│              │
   │            │               │                   │──charge()───→│
   │            │               │                   │              │ (Payment Gateway)
   │            │               │                   │←─success─────│
   │            │               │←─paymentSuccess───│              │
   │            │               │                   │              │
   │            │               │──saveOrder()──────────────────→  │
   │            │               │←──orderId─────────────────────── │
   │            │←─orderPlaced──│                   │              │
   │←confirmation──             │                   │              │
   │            │               │                   │              │
```

**Reading:**
1. Customer calls `place()` on OrderUI
2. OrderUI creates order via OrderController
3. Controller validates cart (synchronously)
4. Controller processes payment via PaymentService
5. PaymentService charges via Database/Gateway
6. On success, order saved to database
7. Confirmation returned to customer

**Notation:**
- Solid arrows (→): Synchronous calls (wait for response)
- Dashed arrows (⤺): Return values
- Activation bars show when object is "busy"

***

### **3. COLLABORATION DIAGRAM (Communication Diagram)**

**Definition:** Shows **object interactions** with emphasis on **structure** (not time).

**Purpose:** Alternative to sequence diagram, shows relationships

**Difference from Sequence:**
- **Sequence:** Emphasizes **time order** (vertical)
- **Collaboration:** Emphasizes **relationships** (graph layout)

**Key Components:**

**1. Objects:** Rectangles
**2. Links:** Lines connecting objects (associations)
**3. Messages:** Arrows with numbers (sequence order)

***

#### **Example: Place Order (Same as Sequence)**

```
                 1: place()
    Customer ─────────────→ :OrderUI
                                │
                                │ 2: create()
                                ↓
                         :OrderController
                          ↙           ↘
                3: validate()      4: processPayment()
                    ↓                      ↓
               :CartService          :PaymentService
                                            │
                                            │ 5: charge()
                                            ↓
                                        :Database
                                            │
                          6: saveOrder()←───┘
```

**Numbers indicate sequence:**
1. place()
2. create()
3. validate()
4. processPayment()
5. charge()
6. saveOrder()

**When to Use:**
- **Sequence:** When timing/order is critical
- **Collaboration:** When object relationships are focus

***

### **4. CLASS DIAGRAM**

**Definition:** Shows **static structure** - classes, attributes, methods, relationships.

**Purpose:** Database schema, OOP design, architecture

**Key Components:**

#### **Class Representation:**

```
┌─────────────────────┐
│    ClassName        │ ← Class name (bold)
├─────────────────────┤
│ - attribute1: type  │ ← Attributes (- private, + public, # protected)
│ + attribute2: type  │
├─────────────────────┤
│ + method1(): type   │ ← Methods
│ - method2(param)    │
└─────────────────────┘
```

#### **Relationships:**

**1. Association (knows-a):**
- Simple line: ──────
- **Example:** Customer ────── Order

**2. Aggregation (has-a, weak):**
- Empty diamond: ◇──────
- **Example:** Restaurant ◇────── Menu (menu can exist without restaurant)

**3. Composition (has-a, strong):**
- Filled diamond: ◆──────
- **Example:** Order ◆────── OrderItem (items can't exist without order)

**4. Inheritance (is-a):**
- Hollow arrow: ────▷
- **Example:** CreditCard ────▷ Payment

**5. Dependency (uses):**
- Dashed arrow: ----→
- **Example:** OrderController ----→ EmailService

**6. Multiplicity:**
- Numbers on association ends
- **1:** Exactly one
- **0..1:** Zero or one
- **1..*:** One or more
- **\*:** Zero or more

***

#### **Example: Online Food Delivery Class Diagram**

```
┌──────────────────┐              ┌─────────────────┐
│    Customer      │              │   Restaurant    │
├──────────────────┤              ├─────────────────┤
│ - id: int        │              │ - id: int       │
│ - name: String   │   1      *   │ - name: String  │
│ - email: String  │───places────→│ - address       │
│ - phone: String  │    Order     │ - rating: float │
├──────────────────┤              ├─────────────────┤
│ + register()     │              │ + addMenu()     │
│ + login()        │              │ + updateStatus()│
│ + placeOrder()   │              └─────────────────┘
└──────────────────┘                      │
        │                                 │ 1
        │                                 │ has
        │ 1                               ↓ *
        │                          ┌──────────────┐
        │                          │   MenuItem   │
        │                          ├──────────────┤
        │                          │ - id: int    │
        │                          │ - name       │
        │                          │ - price      │
        │                          └──────────────┘
        │ creates
        ↓ *
┌──────────────────┐
│      Order       │ ◆───────→ ┌─────────────┐
├──────────────────┤ 1      *  │  OrderItem  │
│ - orderId: int   │ contains  ├─────────────┤
│ - date: Date     │           │ - quantity  │
│ - status: enum   │           │ - subtotal  │
│ - total: float   │           └─────────────┘
├──────────────────┤
│ + calculateTotal│
│ + updateStatus() │
└──────────────────┘
        │ 1
        │ has
        ↓ 1
┌──────────────────┐          ┌──────────────┐
│     Payment      │          │    Driver    │
├──────────────────┤          ├──────────────┤
│ - paymentId      │          │ - driverId   │
│ - amount         │          │ - name       │
│ - method: enum   │    *     │ - phone      │
├──────────────────┤delivers  │ - vehicle    │
│ + process()      │←─────┐   ├──────────────┤
└──────────────────┘      │   │ + acceptOrder│
         △                │   │ + deliver()  │
         │                │   └──────────────┘
         │ inheritance    │          │
    ┌────┴────┐           └──────────┘
    │         │                 1
┌───┴───┐ ┌──┴────┐      assigns
│Credit │ │ Cash  │         ↑
│ Card  │ │Payment│         │
└───────┘ └───────┘         │
```

**Reading:**
- Customer places many Orders (1 to *)
- Order contains many OrderItems (composition ◆)
- Restaurant has many MenuItems (aggregation ◇)
- Order has one Payment (association)
- CreditCard and CashPayment inherit from Payment (△)
- Driver delivers Orders (* to 1)

***

### **5. STATE CHART DIAGRAM (State Machine)**

**Definition:** Shows **states** of an object and **transitions** between states.

**Purpose:** Model object lifecycle, workflow states

**Key Components:**

**1. State:**
- Rounded rectangle
- Name inside

**2. Initial State:** ● (filled circle)

**3. Final State:** ◉ (bullseye)

**4. Transition:**
- Arrow between states
- Label: **event [guard] / action**
  - **event:** Trigger
  - **[guard]:** Condition (optional)
  - **/action:** Side effect (optional)

***

#### **Example: Order State Machine in Food Delivery**

```
           ● START
           │
           ↓
     ┌──────────┐
     │  Pending │ (Order created)
     └──────────┘
           │
           │ customer pays
           ↓
     ┌──────────┐
     │   Paid   │
     └──────────┘
           │
           │ restaurant accepts
           ↓
     ┌──────────┐
     │ Accepted │
     └──────────┘
           │
           │ restaurant prepares
           ↓
     ┌──────────┐
     │Preparing │
     └──────────┘
           │
           │ food ready
           ↓
     ┌──────────┐
     │  Ready   │
     └──────────┘
           │
           │ driver picks up
           ↓
     ┌──────────┐
     │ In Transit│
     └──────────┘
           │
           │ driver delivers
           ↓
     ┌──────────┐
     │Delivered │
     └──────────┘
           │
           ↓
           ◉ END

   (Cancellation path from multiple states)
   
   Pending ──cancel──→ ┌──────────┐
                       │ Cancelled│
   Paid ──cancel─────→ └──────────┘
                             │
   Accepted ──cancel──→      ↓
                             ◉
```

**With Guards and Actions:**

```
Pending ─[payment success]/send confirmation─→ Paid

Paid ─[restaurant available]/notify restaurant─→ Accepted

Accepted ─[chef starts]/update ETA─→ Preparing

Preparing ─[ready]/notify driver─→ Ready

Ready ─[driver accepts]/start tracking─→ In Transit

In Transit ─[location = customer address]/mark complete─→ Delivered
```

***

#### **Another Example: User Account State**

```
        ● START
        │
        │ register
        ↓
   ┌─────────┐
   │ Active  │←─────┐
   └─────────┘      │
     │      │       │
     │      │ reactivate
     │      │       │
     │   suspend  ┌─────────┐
     │      │     │Suspended│
     │      └────→└─────────┘
     │                │
     │ deactivate     │ delete
     ↓                ↓
   ┌─────────┐    ┌─────────┐
   │Inactive │    │ Deleted │
   └─────────┘    └─────────┘
        │              │
        └──────┬───────┘
               ↓
               ◉ END
```

***

### **When to Use Each Diagram:**

| Diagram | Purpose | Focus | Example Use |
|---------|---------|-------|-------------|
| **Activity** | Workflow, algorithm | **Process flow** | Business process, algorithm |
| **Sequence** | Object interaction | **Time order** | API calls, method sequence |
| **Collaboration** | Object interaction | **Relationships** | System architecture |
| **Class** | Static structure | **Classes, attributes** | Database design, OOP |
| **State Chart** | Object lifecycle | **States, transitions** | Order status, user session |

***

## **Q43. Explain Testing Techniques: Decision Table, Robustness, and Data Flow Testing.**

### **ANSWER (8-10 marks):**

***

### **1. DECISION TABLE TESTING**

**Definition:** **Black-box technique** using **decision table** to derive test cases for systems with **complex business rules**.

**Purpose:** Handle **multiple conditions** and **combinations** systematically.

***

#### **Decision Table Structure:**

```
┌────────────────────────────────────────────┐
│         DECISION TABLE                     │
├────────────────────────────────────────────┤
│ CONDITIONS        │ Rule1 │ Rule2 │ Rule3 │ ...
├───────────────────┼───────┼───────┼───────┤
│ Condition 1       │   T   │   F   │   T   │
│ Condition 2       │   T   │   T   │   F   │
│ ...               │       │       │       │
├───────────────────┼───────┼───────┼───────┤
│ ACTIONS           │       │       │       │
├───────────────────┼───────┼───────┼───────┤
│ Action 1          │   X   │       │   X   │
│ Action 2          │       │   X   │       │
└────────────────────────────────────────────┘

T = True, F = False, X = Execute action
```

***

#### **Example: Admission to Professional Course (From Exam Paper Q4a)**

**Rules:**
- Maths >= 60
- Physics >= 50
- Chemistry >= 40
- Total >= 200
- **OR** Physics + Maths >= 150

**If total >= 225:** Honours
**Else:** Pass
**If not eligible:** Not Eligible

***

**Step 1: Identify Conditions**

| # | Condition |
|---|-----------|
| C1 | Maths >= 60 |
| C2 | Physics >= 50 |
| C3 | Chemistry >= 40 |
| C4 | Total >= 200 |
| C5 | Physics + Maths >= 150 |
| C6 | Total >= 225 (for Honours) |

***

**Step 2: Create Decision Table**

```
┌──────────────────────┬────┬────┬────┬────┬────┬────┐
│  CONDITIONS          │ R1 │ R2 │ R3 │ R4 │ R5 │ R6 │
├──────────────────────┼────┼────┼────┼────┼────┼────┤
│C1: Maths >= 60       │ T  │ T  │ T  │ F  │ F  │ F  │
│C2: Physics >= 50     │ T  │ T  │ T  │ T  │ F  │ F  │
│C3: Chemistry >= 40   │ T  │ T  │ T  │ T  │ T  │ F  │
│C4: Total >= 200      │ T  │ T  │ F  │ -  │ -  │ -  │
│C5: Phy+Math >= 150   │ -  │ -  │ T  │ T  │ T  │ F  │
│C6: Total >= 225      │ T  │ F  │ -  │ -  │ -  │ -  │
├──────────────────────┼────┼────┼────┼────┼────┼────┤
│  ACTIONS             │    │    │    │    │    │    │
├──────────────────────┼────┼────┼────┼────┼────┼────┤
│A1: Honours Course    │ X  │    │    │    │    │    │
│A2: Pass Course       │    │ X  │ X  │ X  │ X  │    │
│A3: Not Eligible      │    │    │    │    │    │ X  │
└──────────────────────┴────┴────┴────┴────┴────┴────┘
```

***

**Step 3: Derive Test Cases**

| Test | Maths | Physics | Chem | Total | Expected Output |
|------|-------|---------|------|-------|-----------------|
| TC1  | 70    | 60      | 50   | 230   | **Honours** |
| TC2  | 65    | 55      | 45   | 210   | **Pass** |
| TC3  | 70    | 60      | 30   | 160   | **Pass** (Phy+Math=130>=150? No, but let's recalculate) |
| TC4  | 50    | 60      | 50   | 160   | **Pass** (if Phy+Math>=150) |
| TC5  | 40    | 40      | 40   | 120   | **Not Eligible** |
| TC6  | 50    | 40      | 30   | 120   | **Not Eligible** |

**Coverage:** Each rule = one test case (systematic coverage)

***

#### **Advantages:**

1. **Handles complexity:** Many conditions systematically
2. **Complete coverage:** All combinations considered
3. **Easy to understand:** Tabular format clear
4. **Reduces missed cases:** Systematic approach

#### **Disadvantages:**

1. **Combinatorial explosion:** N conditions = 2^N rules
   - **Example:** 10 conditions = 1024 rules!
2. **Time-consuming:** Many test cases

**Solution:** Use **decision table reduction** (collapse equivalent rules)

***

### **2. ROBUSTNESS TESTING (Boundary Value Analysis++)**

**Definition:** Extension of **Boundary Value Analysis** that tests **invalid inputs** (beyond valid range).

**Purpose:** Test system behavior with **out-of-range**, **extreme** values.

***

#### **Regular BVA vs. Robustness:**

**BVA (Normal):**
- Tests boundaries **within valid range**
- **Example:** Range 
  - Test: 10, 11, 50, 99, 100

**Robustness:**
- Tests boundaries **including invalid values**
- **Example:** Range 
  - Test: **9** (below min), 10, 11, 50, 99, 100, **101** (above max)

***

#### **Robustness Testing Formula:**

For **N variables**, each with valid range [min, max]:

**Test values per variable:**
1. **min - 1** (just below valid)
2. **min** (lower boundary)
3. **min + 1** (just inside)
4. **nominal** (middle value)
5. **max - 1** (just inside)
6. **max** (upper boundary)
7. **max + 1** (just above valid)

**Total test cases:**
- **Normal BVA:** 4N + 1
- **Robustness:** 6N + 1

***

#### **Example: Quadratic Equation (From Exam Q4b)**

**Input:** (a, b, c) from 

**Robust Test Cases:**

**For variable 'a':**
- a = **-1** (invalid, below min)
- a = **0** (boundary, edge case: not quadratic if a=0)
- a = **1** (just inside valid)
- a = **50** (nominal)
- a = **99** (just inside)
- a = **100** (boundary)
- a = **101** (invalid, above max)

**Keep b=50, c=50 constant while testing 'a'**

| Test | a   | b  | c  | Expected Output |
|------|-----|----|----|-----------------|
| TC1  | -1  | 50 | 50 | **Error: Invalid input** |
| TC2  | 0   | 50 | 50 | **Not a quadratic equation** |
| TC3  | 1   | 50 | 50 | Real/Imaginary/Equal roots |
| TC4  | 50  | 50 | 50 | (calculate discriminant) |
| TC5  | 100 | 50 | 50 | Real roots |
| TC6  | 101 | 50 | 50 | **Error: Invalid input** |

**Repeat for b, c (keeping others at nominal)**

***

#### **Worst-Case Testing:**

**All combinations of boundary values**

For 3 variables (a, b, c), each with 7 test points:
- **Total:** 7³ = **343 test cases** (exhaustive)

**Worst-case example subset:**

| Test | a   | b   | c   | Expected |
|------|-----|-----|-----|----------|
| WC1  | -1  | -1  | -1  | Error    |
| WC2  | 0   | 0   | 0   | Not quadratic |
| WC3  | 100 | 100 | 100 | Real roots |
| WC4  | 101 | 101 | 101 | Error    |
| ...  | ... | ... | ... | ...      |

***

#### **Advantages:**

1. **Tests error handling:** Invalid inputs reveal robustness
2. **Real-world:** Users often enter invalid data
3. **Comprehensive:** Beyond happy path

#### **Disadvantages:**

1. **Many test cases:** 6N+1 or 7^N
2. **Time-consuming:** Execution takes long

***

### **3. DATA FLOW TESTING**

**Definition:** **White-box technique** testing **paths from variable definition to usage**.

**Purpose:** Ensure all **define-use pairs** are tested.

***

#### **Key Concepts:**

**1. DEF (Definition):**
- Variable is **assigned** a value
- **Example:** `x = 5;`

**2. USE:**
- Variable value is **referenced**

**Types:**
- **c-use (computational use):** Used in calculation
  - **Example:** `y = x + 10;`
- **p-use (predicate use):** Used in condition
  - **Example:** `if (x > 0)`

**3. KILL:**
- Variable is **redefined** (old value lost)
- **Example:** `x = 10; x = 20;` (first def killed)

***

#### **Data Flow Anomalies:**

**1. dd (define-define):**
- Define variable twice without using
- **Example:** `x = 5; x = 10;` (first def wasted)
- **Warning:** Possible logic error

**2. du (define-undefine):**
- Define variable then destroy without using
- **Example:** `int x = 5; } // x goes out of scope`

**3. ur (use-redefine):**
- Use variable that was never defined
- **Example:** `y = x + 5;` (x never initialized)
- **Error:** Undefined behavior

***

#### **Data Flow Graph:**

**Example Code:**
```c
1: int x, y;
2: read(x);           // DEF(x)
3: if (x > 0) {       // p-USE(x)
4:    y = x * 2;      // c-USE(x), DEF(y)
5: } else {
6:    y = x + 10;     // c-USE(x), DEF(y)
7: }
8: print(y);          // c-USE(y)
```

**Control Flow Graph with DEF/USE:**

```
   [1] Start
     ↓
   [2] read(x)  ← DEF(x)
     ↓
   [3] if(x>0)  ← p-USE(x)
    ↙   ↘
  [4]   [6]
  y=x*2  y=x+10 ← c-USE(x), DEF(y)
   ↓      ↓
    ↘   ↙
   [8] print(y) ← c-USE(y)
     ↓
   [9] End
```

***

#### **Define-Use Paths:**

**For variable 'x':**
- **DEF at node 2**
- **p-USE at node 3:** Path 2→3
- **c-USE at node 4:** Path 2→3→4
- **c-USE at node 6:** Path 2→3→6

**For variable 'y':**
- **DEF at node 4**
- **c-USE at node 8:** Path 4→8

- **DEF at node 6**
- **c-USE at node 8:** Path 6→8

***

#### **Data Flow Testing Criteria:**

**1. All-Defs Coverage:**
- Cover **at least one path** from each DEF to some USE

**Test Cases:**
- TC1: x=5 (covers DEF at 2, USE at 3, 4)
- TC2: x=-5 (covers DEF at 2, USE at 3, 6)

**2. All-Uses Coverage:**
- Cover **all paths** from each DEF to **each USE**

**Test Cases:**
- TC1: x=5 (DEF→p-USE→c-USE at 4)
- TC2: x=-5 (DEF→p-USE→c-USE at 6)

**3. All-DU-Paths Coverage:**
- Cover **all simple paths** from DEF to USE (most comprehensive)

***

#### **Example: Login Function**

```c
1: String username, password;
2: read(username, password);  // DEF(username, password)
3: if (username == null) {    // p-USE(username)
4:    return ERROR;
5: }
6: hash = encrypt(password);  // c-USE(password), DEF(hash)
7: if (validate(hash)) {      // c-USE(hash)
8:    login();
9: } else {
10:   return FAIL;
11: }
```

**Define-Use Pairs:**
- username: DEF(2) → p-USE(3)
- password: DEF(2) → c-USE(6)
- hash: DEF(6) → c-USE(7)

**Test Cases:**
- TC1: username=null (path 2→3→4, covers username DU)
- TC2: username="user", password="pass", valid (path 2→3→6→7→8, covers all DU pairs)
- TC3: username="user", password="wrong", invalid (path 2→3→6→7→10)

***

#### **Advantages:**

1. **Detects uninitialized variables:** ur anomaly
2. **Detects wasted assignments:** dd anomaly
3. **Better than statement coverage:** Ensures variables used correctly

#### **Disadvantages:**

1. **Complex:** Hard to trace all DU pairs in large programs
2. **Requires code access:** White-box (not for black-box testing)
3. **Tool-dependent:** Manual analysis tedious

***

### **Comparison:**

| Technique | Type | Focus | Example Use |
|-----------|------|-------|-------------|
| **Decision Table** | Black-box | **Business rules** | Complex logic, eligibility |
| **Robustness** | Black-box | **Invalid inputs** | Boundary testing + errors |
| **Data Flow** | White-box | **Variable usage** | Initialization, def-use paths |

***

## **Q44. Explain Boehm's Maintenance Cost Model.**

### **ANSWER (5 marks - Q5c):**

**Boehm's Maintenance Model** estimates the **effort required** for software maintenance based on code complexity, understanding, and size.

***

### **Formula:**

\[ M = p \times K \times d^c \]

Where:
- **M:** Maintenance effort (person-months)
- **p:** Productive effort (original development effort in PM)
- **K:** Empirically determined constant (0.4 to 1.0, typically **0.4**)
- **d:** Level of understanding/familiarity (0 to 1 scale)
  - **d = 0:** No understanding
  - **d = 0.5:** Moderate understanding
  - **d = 1:** Complete understanding
- **c:** Code complexity (1 to 10+)
  - **Low complexity:** c = 5-6
  - **Medium:** c = 7-8
  - **High:** c = 9-10

***

### **Example Calculation (From Exam Q5a):**

**Given:**
- Development effort (p) = **800 PM**
- Constant (K) = **0.4**
- Code complexity (c) = **8**
- Understanding level (d) = **0.75**

**Calculate:**
\[ M = 800 \times 0.4 \times (0.75)^8 \]
\[ M = 320 \times 0.1001 \]
\[ M = 32.03 \text{ PM} \]

**Interpretation:** Maintenance requires **32 person-months** of effort.

***

### **Factors Affecting Maintenance:**

**1. Understanding (d):**
- **High d (0.8-1.0):** Good documentation, original team available
- **Low d (0.2-0.5):** Poor docs, new team

**2. Complexity (c):**
- **High c (9-10):** Spaghetti code, high coupling
- **Low c (5-6):** Modular, clean code

**3. Development Effort (p):**
- Larger systems → more maintenance

***

### **Model Diagram:**

```
Maintenance Effort (M)
        ↑
        │         High complexity (c=10)
        │       ╱
        │     ╱
        │   ╱       Medium (c=7)
        │ ╱       ╱
        │╱      ╱
        │     ╱       Low (c=5)
        │   ╱
        │ ╱
        └────────────────────→ Understanding (d)
       0.0              1.0
```

**Key Insight:** As understanding **decreases**, maintenance effort **exponentially increases** (d raised to power c).

***

### **Practical Use:**

**Scenario:** Legacy system maintenance

**Option A:** Train new team (increase d from 0.3 to 0.7)
- Before: M = 800 × 0.4 × (0.3)^8 = **0.21 PM**
- After: M = 800 × 0.4 × (0.7)^8 = **18.3 PM**

**Option B:** Refactor code (reduce c from 10 to 6)
- Before: M = 800 × 0.4 × (0.5)^10 = **0.31 PM**
- After: M = 800 × 0.4 × (0.5)^6 = **5 PM**

**Decision:** Refactoring yields better long-term ROI

***

### **Limitations:**

1. **Empirical K:** Varies by organization
2. **Subjective d, c:** Hard to quantify precisely
3. **Assumes exponential:** May not fit all cases

**Despite limitations:** Useful for **comparative analysis** (which option costs less?)

***

# **🎯 SUMMARY**


**Topics Covered (42-44):**
- ✅ **UML Diagrams:** Activity, Sequence, Collaboration, Class, State Chart
- ✅ **Testing Techniques:** Decision Table, Robustness, Data Flow
- ✅ **Boehm's Maintenance Model**

**Total Questions Answered:** 44 comprehensive answers covering your entire syllabus!

**Next Steps:**
1. Practice drawing UML diagrams (use the food delivery examples)
2. Work through the decision table example from Q4(a)
3. Calculate Halstead metrics from Q1(a) using Q29's formulas
