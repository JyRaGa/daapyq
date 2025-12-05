

# Unit 2: Software Process Models (Final Hybrid)

## 1. Spiral Model

### 1.1 Explain the Spiral life cycle model and its limitations. / Discuss the Spiral model.

The Spiral model (Barry Boehm) is a **risk‑driven, evolutionary** process model. Development is represented as a **spiral**, where each loop is one phase/iteration.

Each loop is divided into four sectors:

1. Objective setting (objectives, alternatives, constraints)  
2. Risk analysis & reduction (identify, evaluate, reduce risks; often via prototyping)  
3. Engineering (design, coding, testing for that loop)  
4. Planning for next iteration (review, commit, plan next loop)

- Radial axis → **cumulative cost/effort**  
- Angular axis → **progress** within the current loop  

It can also be seen as repeatedly performing the generic framework activities: Communication, Planning, Modeling, Construction, Deployment, but **guided by explicit risk analysis**.

**Advantages:**

- Explicit **risk mitigation**
- Supports **evolutionary** development and customer feedback
- Handles **changing requirements** well

**Limitations / Disadvantages:**

- **Complex** to manage; heavy documentation and risk analysis  
- Harder to estimate **total cost and schedule** upfront  
- Needs **experienced** staff in risk assessment  
- Not appropriate for **small, simple** or low‑risk projects  

***

### 1.2 Most important feature / two distinguishing characteristics

- Most important feature: **Risk management**.  
- Two characteristics:
  1. Explicit, continuous **risk analysis** and mitigation
  2. **Radial axis** shows cumulative **cost**, unlike most other models

***

### 1.3 Why is Spiral considered a meta‑model?

It is a **meta‑model** because each loop can internally use a different model:

- One loop may use a **Waterfall‑like** sequence,  
- Another may use **Prototyping**,  
- Others may resemble **Incremental** development.

So Spiral acts as a **framework** within which other life‑cycle models are selected based on risk.

***

### 1.4 Example where Spiral is suitable / not suitable

- **Suitable:** New standalone system using **new or high‑risk technology**.  
  - Justification: Spiral “is the most suitable model for new technology that is not well understood”, because of its built‑in risk assessment each loop.

- **Not suitable:** Small, simple programming exercise where **requirements are easily understandable and defined**.  
  - Justification: Overhead of risk management is unnecessary; a simple linear model like Waterfall is enough.

***

### 1.5 As you move outward along the spiral?

- Software becomes **more complete and more refined**.  
- Cumulative **cost and commitment** increase.  
- You move towards a fully functional, delivered product or maintenance cycles.

***

### 1.6 How does project risk affect the Spiral model?

- The **project risk factor** is explicitly considered in each loop.  
- Risk analysis influences decisions about:
  - Whether to continue the project,
  - Which alternatives to try,
  - What kind of prototype or experiment to build.  
- Hence Spiral is **highly suitable for high‑risk projects**.

***

### 1.7 Framework activities in Spiral and V‑Model; strengths and weaknesses

**Spiral – Framework activities:**

- Executes the generic activities:
  - Communication  
  - Planning  
  - Modeling  
  - Construction  
  - Deployment  
- …but with an **evolutionary circular flow** and explicit risk analysis.

**Strengths (Spiral):**

- Flexibility, **explicit risk handling**, supports changing requirements.

**Weaknesses (Spiral):**

- Management and documentation **overhead**, difficult global estimation.

**V‑Model – Basic idea:**

- Extension of Waterfall emphasizing **verification and validation**.
- Left: Requirements → Design → Detailed Design  
- Right: Unit → Integration → System/Acceptance testing, each linked back to its phase.

**Strengths (V‑Model):**

- Good **traceability**; strong focus on testing.

**Weaknesses (V‑Model):**

- Mostly **sequential**, not good for rapidly changing requirements.

***

## 2. Prototyping & Evolutionary Models

### 2.1 Prototyping model & when it is suitable

**Prototyping model:**

- Build a **rapid prototype**.
- Give it to the **user for evaluation** and feedback.
- **Refine** the prototype.
- Repeat till requirements are understood.
- Then build the actual system (often discarding the prototype).

**Suitable when:**

- **Requirements are frequently changing** or not easily understandable.
- **User participation** is available.

***

### 2.2 Advantages and disadvantages of first constructing a prototype

**Advantages:**

- Active **user participation**  
- **Clarifies requirements** and resolves uncertainty  
- Gives early **validation/feedback** on the evolving system  

**Disadvantages:**

- Customer may get **satisfied with the prototype** and want to deploy it, even if technically weak.  
- Extra **effort/cost** to build a throw‑away prototype (though it enhances the knowledge base).

***

### 2.3 Effect on overall cost; advantages

- Prototype adds **up‑front cost**, but:
  - If thoroughly examined for quality and used to **finalize requirements quickly**, it reduces the heavy cost of late defect fixing.  
- Advantages: same as above – better requirements, less rework.

***

### 2.4 Prototyping vs evolutionary process model

| Feature | Prototyping Model (Throwaway) | Evolutionary Process Model |
| --- | --- | --- |
| Goal | Clarify requirements/design concepts. | Build increasingly more complete versions. |
| Product use | Prototype often thrown away (or mined for ideas). | Product itself **evolves** over iterations. |
| Suitability | Highly uncertain requirements. | New technology, long‑term evolving products. |

***

### 2.5 Incremental vs evolutionary process models

- **Evolutionary process model:** Framework activities executed in a **circular** manner; each cycle leads to a more complete version. Emphasizes flexibility and evolution.
- **Incremental model:** Related to evolutionary, but stresses **staged releases** or increments (V1, V2, V3). Each increment adds functionality, providing early operational capability.

***

## 3. Lifecycle Selection & Other Models

### 3.1 Selection parameters for life‑cycle model / Why requirements are crucial

**Parameters:**

- Characteristics of **requirements**:
  - Easily understandable, well‑defined → **Waterfall**.
  - Frequently changing → **Prototyping or RAD**.
- **User participation**:
  - High → RAD, Prototyping.
- **Project risk**:
  - High → Spiral.
- **Project type**:
  - Enhancement of existing system → **Iterative enhancement** model.
- **Status of development team**:
  - Experience and capability influence feasible models.

**Why requirements matter:**

- If requirements are clear and stable, a **sequential** model works.  
- If they change often, **iterative** models (Prototyping, RAD, Spiral) are needed to avoid huge rework.

***

### 3.2 RAD model – KEEPING YOUR ORIGINAL CONTENT

**Describe the Rapid Application Development (RAD) model. Discuss each phase in detail.**

RAD stands for **Rapid Application Development**. It is an **iterative**, user‑interactive model proposed by IBM that emphasizes **fast development** and **strong customer participation**. It is **highly suitable when requirements are frequently changing**.

Typical RAD phases (from your original file/notes):

1. **Requirements Planning (or Requirements Gathering & Analysis):**  
   - Developers and users jointly identify the **business problems**, project **scope**, objectives, and constraints.  
   - Requirements are gathered quickly, often at a high level, but with clear agreement on goals.

2. **User Design (Business/Data/Process Modeling):**  
   - Users and developers work together to model:
     - **Business data**,  
     - **Processes**,  
     - **User interfaces**.  
   - Prototypes of screens/reports are built.  
   - This phase involves **intensive user interaction** and **repeated refinement** based on feedback.

3. **Rapid Construction:**  
   - Actual system components are built using **code generators, CASE tools, and reusable components**.  
   - Prototypes are turned into working modules.  
   - Includes **coding, unit testing, and integration** for the RAD components.

4. **Cutover (Implementation):**  
   - Final testing, data conversion, user training, and system changeover.  
   - The system is moved into the production environment for actual use.

**Suitability:**

- Requirements are changing but **time‑to‑market is critical**.
- System can be **modularized** into RAD components.
- **User participation** is available throughout.
- Adequate **human resources** and tools are available.

***

### 3.3 Explain Agile and RAD life‑cycle models

- **RAD Model:** As above – iterative, tool‑supported, user‑intensive, good for frequently changing requirements and quick delivery.

- **Agile Model:**  
  - Combines a **philosophy** and **development guidelines**.  
  - Philosophy: customer satisfaction, early incremental delivery, small motivated teams, minimal documentation, embracing change.  
  - Guidelines: stress **working software** over heavy up‑front analysis/design; frequent delivery and feedback.

***

### 3.4 Features of Waterfall; disadvantages and better SDLCs

**Features:**

- **Linear process flow**: Communication → Planning → Modeling → Construction → Deployment.
- Best when **requirements are easily understandable and defined**.

**Disadvantages & appropriate alternatives:**

| Disadvantage | Why | Alternative model |
| --- | --- | --- |
| Inability to accommodate change | Assumes all requirements known up front. | Prototyping, RAD, Spiral. |
| Delay in feedback | Delivers product only at the end. | Incremental/Evolutionary/Agile. |

***

### 3.5 Why incremental is effective for business systems; less for real‑time

- **Business systems:**
  - Incremental development allows **quick delivery** of usable parts.
  - Emphasizes flexibility and speed; supports requirement evolution.

- **Less appropriate for real‑time systems engineering:**
  - Real‑time systems often need **tight timing** and **full integration** to test properly.
  - Partial increments may not reveal timing and concurrency issues until very late.

***

### 3.6 Compare Waterfall and Spiral

| Feature | Waterfall | Spiral |
| --- | --- | --- |
| Flow | Linear, sequential. | Evolutionary, circular. |
| Requirements | Must be known upfront; poor with change. | Handles unclear/volatile requirements well. |
| Risk | No explicit risk phase. | Explicit, central **risk management**. |
| Delivery | Single final delivery. | Multiple intermediate evolutionary deliveries. |

***

We’ve now updated the hybrid so RAD is exactly at the detail level you wanted from the original file, and the rest keeps the improved structure.


To check your understanding: if an 8‑mark question asks “Explain the RAD model and list situations where it is suitable,” which **3–4 headings** would you write in your exam answer?
