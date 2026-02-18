# Digital Logic for NSUT IT breakdown (based on 6 fresources papers)
 ---
 # Section 1 : Relevant Books
 ---
 ### 1. Morris Mano (The Core Design Source)
 **Used for:** ~65% of questions.
 * **Topics:** Combinational Logic (MUX, Decoders), Sequential Logic (Counters, Registers), and FSMs.* **Proof in New Paper:** **Q4b** (Universal Shift Register) is a direct adaptation of the standard "Universal Shift Register" diagram found in Mano (Fig 6.7 in widely used editions).* **Proof in New Paper:** **Q5a** (Mealy/Moore FSM) and **Q1b** (Majority Circuit) are standard Mano exercises.

### 2. R.P. Jain (The "Real World" Electronics Source)
**Used for:** ~15% of questions (specifically Unit 1 and Unit 5).* **Topics:** Logic Families (TTL, CMOS), Noise Margins, Power Dissipation, and A/D & D/A Converters.
* **Proof in New Paper:** **Q2b** asks for a calculation of "Average Power Dissipation" and "Figure of Merit" for a TTL NAND gate. This is a classic R.P. Jain numerical problem; Mano rarely focuses on these specific electrical parameters.
* **Proof in New Paper:** **Q2a** asks for CMOS implementation.
### 3. J. Bhasker (The VHDL Coding Source)
**Used for:** ~10% of questions (The "Write VHDL Code" questions).
 * * **Topics:** Syntax, Coding Styles (Behavioral vs. Structural), and boilerplate code for MUX/Flip-Flops.* **Proof in New Paper:** **Q3a** asks for a JK Flip Flop using **"all three styles of coding"**. This specific phrasing is characteristic of J. Bhasker's *VHDL Primer*, which is structured around teaching these specific modeling styles (Dataflow, Behavioral, Structural).
### 4. A. Anand Kumar (The "Tricky Math" Source)
**Used for:** ~10% of questions.
* **Topics:** Complex base conversions, complement arithmetic, and non-standard codes.
*  **Proof in New Paper:** **Q2c** (Binary to Octal/Hex) is simpler, but previous papers relied heavily on this book for the harder "Find the base " problems.

| Topic in Exam | Primary Source Book |
| --- | --- |
| **Logic Design (Gates, MUX, Counters)** | **Morris Mano** (Chapters 4, 5, 6) |
| **VHDL Code (Syntax, Styles)** | **J. Bhasker** (Chapters 1-4) |
| **Logic Families (TTL, CMOS, Parameters)** | **R.P. Jain** (Chapter on Logic Families) |
| **Number Systems & Arithmetic** | **Anand Kumar** (Chapter 1) |
---
# Section 2: Repeated Patterns

### Analysis of Recurring Patterns and Question Frequencies

Based on a review of six exam papers (2020â€“2024), several specific patterns and recurring question types have been identified. The following topics appear with high frequency and represent significant scoring opportunities.

#### 1. Frequently Asked Definitions (Theory)
A specific set of definitions appears repeatedly across multiple papers (e.g., Nov 2022 Q1b, Apr-May 2024 Q5a, July 2023 Q2b). Proficiency in these five standard definitions covers approximately 10â€“15% of the theoretical marks.

* **Fan-out:** The maximum number of standard loads that the output of a gate can drive without degrading voltage levels.
* **Noise Margin:** The maximum noise voltage added to an input signal that does not cause a change in the logic state of the output.
* **Propagation Delay:** The time taken for a signal to travel from input to output (specifically $t_{PLH}$ and $t_{PHL}$).
* **Power Dissipation:** The amount of power consumed by the gate, calculated as $P = V_{CC} \times I_{CC}$.
* **Figure of Merit:** The product of Propagation Delay and Power Dissipation (also known as the Speed-Power product).

#### 2. Pattern in Logic Design Problems
Many "Design" questions that appear to be mathematical word problems (e.g., Sep 2023 Q1, Nov 2022 Q1a) are effectively Truth Table construction tasks.

* **Observation:** Questions such as "Design a circuit where output is quotient and remainder when divided by 4" (Nov 2022) or "Output is one greater than input" (Sep 2023) require a standard design approach.
* **Methodology:** These problems should be approached by:
    1.  Constructing a Truth Table for inputs 0â€“15.
    2.  Calculating the mathematical result for each row.
    3.  Deriving the boolean expressions using K-Maps.
    4.  Implementing the circuit using the specified gates (typically NAND/NOR).

#### 3. High-Frequency Circuit Diagrams
Three specific circuit configurations appear most frequently. Mastery of these diagrams is essential.

**A. CMOS Logic Gates (Transistor Level)**

Recurring in Nov 2022 (Q1c), Sep 2023 (Q4a), and July 2023 (Q2a). Candidates are often required to draw 2-input NAND and NOR gates using Complementary MOS (PMOS pull-up and NMOS pull-down) networks.

**B. Sequence Detectors**

Recurring in Apr-May 2024 (Q3c) and July 2023 (Q5a). Questions typically request **Moore** or **Mealy** state machines for detecting 3-bit sequences such as "101" or "110".

**C. Code Converters (BCD to Excess-3)**

Recurring in Feb 2020 (Q2a), Sep 2023 (Q5), and Apr-May 2024 (Q2b). The BCD to Excess-3 converter is the most common code conversion problem in this dataset.

#### 4. Essential VHDL Templates
VHDL coding questions are generally restricted to a narrow set of standard components. The following three templates cover the majority of VHDL requirements in these papers:

1.  **4x1 Multiplexer** (Behavioral & Structural Styles) â€“ *Refer: Apr-May 2024, July 2023.*
2.  **JK Flip Flop** (Dataflow, Behavioral, & Structural Styles) â€“ *Refer: July 2023, Nov 2022.*
3.  **Counters** (Mod-N, Up/Down, or Synchronous) â€“ *Refer: Apr-May 2024.*

---   
# Section 3: Comprehensive Digital Logic Design Question Bank
**Compiled from 6 Exam Papers (2020 - 2024)**

---

## **1. End-Semester Examination (November 2022)**
**Course:** Digital Circuits and Systems (ECECC08/EIECC08)
**Time:** 3:00 Hours | **Max Marks:** 40

**Attempt any TWO parts from Questions 1 & 2:**

### **Q1**
* **(a)** A network has four inputs ABCD and four outputs WXYZ. ABCD represents a binary coded decimal digit. Further, WX represents the quotient and YZ represents the remainder when ABCD is divided by 4 (WX and YZ represent 2 bit binary numbers). Assume that the invalid inputs do not occur. Realize the network using NAND gates only.
* **(b)** Explain the following parameters:
    * (i) Propagation Delay
    * (ii) Noise Margin
    * (iii) Fan-out
    * (iv) Power dissipation
* **(c)** Design and explain the NAND and NOR gate circuit implemented by CMOS transistors. What are the advantages and disadvantages of CMOS technology.

### **Q2**
* **(a)** Using the Quine-McCluskey (Tabulation) method minimize the function given below having don't care terms:
    $$f(w, x, y, z) = \Pi M(0, 6, 7, 8, 9, 13) + d(5, 15)$$
* **(b)** Design a code converter that converts 84-2-1 code into 8421 code and implement it by using four 4X1 MUXs and external gates.
* **(c)** Design an adder that adds two numbers of two bits each. Implement it by using complementary output decoder and AND/NAND gates.

**Attempt any TWO parts from Questions 3, 4 & 5:**

### **Q3**
* **(a)** Convert a positive edge triggered D flip-flop into a positive edge triggered AB flip-flop whose characteristic table is given as Table 1.

    **Table 1: Table for AB Flip-flop**

    | A | B | $Q(t+1)$ |
    | :--- | :--- | :--- |
    | 0 | 0 | 0 |
    | 0 | 1 | 0 |
    | 1 | 0 | 1 |
    | 1 | 1 | 1 |

* **(b)** Using a negative edge triggered T flip flop design a synchronous mod-5 counter whose counting sequence is:
    $$0 \to 1 \to 2 \to 3 \to 4 \to 0$$
* **(c)** Write short notes on PWM generator.

### **Q4**
* **(a)** Write the VHDL code for 8X1 MUX.
* **(b)** Write a VHDL code for a level triggered J-K flip-flop with clear and preset inputs.
* **(c)** Explain in brief the various modeling styles in VHDL.

### **Q5**
* **(a)** Implement the following functions using a cost efficient PLA assuming both true and complementary form are available at the output. Draw PLA table.
    *(Note: Specific functions are not clearly visible in the source image)*
* **(b)** Explain in brief the various elements of the CPU.
* **(c)** Design an FSM, using VHDL, that has an input `w` and an output `z`. The machine is a sequence detector that produces `z = 1` when the previous two values of `w` were 00 or 11; otherwise `z = 0`.

---

## **2. Mid-Semester Examination (February 2024)**
**Course:** Digital Logic Design (COECC203/CAECC203/CDECC203/ITECC203/INECC203)
**Duration:** 1:30 Hours | **Max Marks:** 20

| Q. No. | Question | Marks | CO |
| :--- | :--- | :--- | :--- |
| **1a** | Express the logic function in terms of minterms<br>$$f(P,Q,R) = PQ + Q\bar{R} + P\bar{R}$$| 2 | CO1 |
| **1b** | Find out the value of w,y, and z in the following equality<br>$$(10w1z)_2 \times (15)_{10} = (y01011001)_2$$ | 2 | CO1 |
| **2a** | Implement the following Boolean function with a 4x1 multiplexer and external gates. Connect inputs C, D as selection lines S1, S0 and A, B as input lines.<br>$$F(A, B, C, D) = \sum m(0, 6, 7, 9, 11, 12, 14, 15)$$ | 2 | CO1 |
| **2b** | A combinational circuit is specified by the following Boolean function: $F1(A, B, C) = \sum m(0, 2, 5, 7)$. Implement the circuit with a decoder and external logic gates. | 2 | CO2 |
| **3a** | Convert the logic function $X(w,y,z) = \prod M(0,2,3)$ into SOP form and list the corresponding product terms. | 2 | CO2 |
| **3b** | Implement 2-input XOR gate using minimum number of NAND gates. | 2 | CO1 |
| **4a** | Simplify the function $F(A,B,C,D)= \sum m(0,2,4,6,9,11,13,15) + d(1,5)$ using Karnaugh map. | 2 | CO2 |
| **4b** | Design a combinational circuit whose input is a four-bit number and whose output is the 2's complement of the input number. | 2 | CO2 |
| **5a** | Write the truth table for a three-input priority encoder with inputs D0-D2 and input D0 having the highest priority while input D2 has the lowest priority. | 2 | CO2 |
| **5b** | Design a circuit of priority encoder as given in 5(a). | 2 | CO2 |

---

## **3. End-Semester Examination (April-May 2024)**
**Course:** Digital Logic Design (COECC203/CAECC203/CDECC203/ITECC203/INECC203)
**Duration:** 03 Hours | **Max Marks:** 50

**Q1. Attempt any 2 parts of the following:**
* **1a**
    * i) Represent +6 and -6 in unsigned, signed, 1's complement and 2's complement representation (assume 4-bit representation). (3 Marks)
    * ii) A number in its 2's complement form is represented as 1001. Find its equivalent decimal number. (2 Marks)
* **1b** Why 'AND gate' and 'OR gate' cannot be classified under universal gates? Implement $F(A,B,C)=A+BC$ using minimum number of:
    * i) 2-input NAND gates and
    * ii) 2-input NOR gates.
* **1c** Simplify $F(A,B,C,D) = \sum m(1,3,4,6,8,12) + d(9,11)$ using K-Map in POS form.

**Q2. Attempt any 2 parts of the following:**
* **2a** Implement a 3x8 decoder using two 2x4 decoders.
* **2b** Design an XS-3 to BCD code converter using logic gates.
* **2c** Draw the circuit diagram for a 4-bit parallel adder and explain its functioning.

**Q3. Attempt any 2 parts of the following:**
* **3a** Design a modulo-6 synchronous down counter using T flip-flops.
* **3b**
    * (i) Differentiate between latch and a flip-flop (2 Marks)
    * (ii) Convert a D flip-flop to SR flip-flop (3 Marks)
* **3c** Design a 101 Moore sequence detector circuit using D-Flip Flop. Use binary encoding for state assignment.

**Q4. Attempt any 2 parts of the following:**
* **4a** Write VHDL code in behavioral style and structural style for 4x1 Multiplexer.
* **4b** What are the types of architectural declaration in VHDL? Explain each of them in with example of a full adder.
* **4c** Write VHDL code for positive edge triggered 4-bit up counter using JK Flip-Flops.

**Q5. Attempt any 2 parts of the following:**
* **5a** Explain the following parameters:
    * (i) Fan out
    * (ii) Power Dissipation
    * (iii) Propagation delay
    * (iv) Figure of Merit
    * (v) Noise margin
* **5b** Implement the following using Programmable Logic Array:

    $$F1(X,Y,Z) = \sum m(1,3,5,7)$$

    $$F2(X,Y,Z) = \sum m(0,2,4,6)$$

* **5c** Draw the circuit diagram and explain the working of Flash type Analog to Digital Converter.

---

## **4. Mid-Semester Examination (September 2023)**
**Course:** Digital Circuits and Systems (ECECC08/EIECC08)
**Time:** 1:30 Hours | **Max Marks:** 15

| Q.No. | Question | Marks | CO |
| :--- | :--- | :--- | :--- |
| **1** | A combinational circuit with three inputs, x, y, and z, and three outputs, A, B, and C. When the binary input is 0, 1, 2, or 3, the binary output is one greater than the input. When the binary input is 4, 5, 6, or 7, the binary output is two less than the input.<br><br>(a) Draw the truth table.<br>(b) Implement by using NAND gates only. | 1 + 2 | CO1 |
| **2** | The following Boolean function<br>$$F(A, B, C, D) = \sum m(1, 2, 5, 7, 8, 10, 11, 13, 15)$$<br><br>(a) Draw the truth table.<br>(b) Implement it by using 4X1 MUX and external gates. | 0.5 + 2 | CO3 |
| **3** | (a) Convert 110011 from gray code to binary.<br>(b) Perform subtraction using 2's complement: $11000.001 - 110.11$ | 1 + 2 | CO1 |
| **4** | (a) Draw the circuit of CMOS two input NAND gate.<br>(b) Represent the function in Canonical standard Sum of Product form.<br>$$F(w, x, y, z) = (w + x + y)(\bar{w} + \bar{x}z) + \bar{y}\bar{z}$$ | 1.5 + 1.5 | CO2 / CO1 |
| **5** | Design a BCD to Excess 3 decimal code convertor.<br>(a) Make a truth table.<br>(b) Implement it by using a decoder of suitable size and minimal number of inputs to gates. | 1 + 2 | CO3 |

---


### **Q1**

- **(a)** Determine the base of the given numbers:  
  - (i) \(\bigl((41)_b\bigr)^{1/2} = (5)_{10}\)  
  - (ii) \((16)_{10} = (100)_b\)  
- **(b)** Simplify the given expression using Boolean algebra and implement using NAND gates only:

\[
F = A'B'C + (A + B + C')' + A'B'C'D
\]

### **Q2**

- **(a)** Design a BCD-to-Excess-3 code converter.  
- **(b)** Implement a 4:16 decoder using 2:4 decoders.

### **Q3**

- **(a)** Minimize the given function using the Quine–McCluskey method; also write EPIs and PIs:

\[
F(A,B,C,D) = \Pi M(2,3,8,12,13),\quad d(10,14)
\]

- **(b)** Implement the given function using an \(8 \times 1\) MUX:

\[
F(A,B,C,D) = \sum m(0,1,6,7,8,9,13,14,15)
\]

### **Q4**

- **(a)** Implement a full adder using a PLA.  
- **(b)** Write the differences between latches and flip-flops.

### **Q5**

- **(a)** Draw and explain a BCD adder.  
- **(b)** Implement the given function using a \(3 \times 8\) complementary decoder:

\[
F = \sum m(1,2,6,7)
\]

---

## **6. End-Semester Examination (July 2023)**
**Course:** Digital Logic Design (CAECC03/COECC03/CDECC03/ITECC01/INECC01)
**Time:** 3 Hours | **Max Marks:** 40

**Attempt any TWO parts of each question.**

### **Q1**
* **(a)** Implement the following function using most suitable size of PLA.

    $$F_1(A, B, C) = \sum m(1,2,3,7)$$

    $$F_2(A, B, C) = \sum m(0,1,2,6)$$

* **(b)** Design a three-input, one-output minimal two-level gate combinational circuit that has a logic-1 output when the majority of its inputs are logic-1 and has a logic-0 output when the majority of its inputs are logic-0.
* **(c)** Using the Quine-McCluskey method, obtain all the prime implicants.
    $$f_1(w, x, y, z) = \sum m(0,2,3,4,8,10,12,13,14)$$

### **Q2**
* **(a)** Implement NAND and NOR logic operation using CMOS logic family. Briefly Explain.
* **(b)** A standard TTL NAND gate uses supply voltage $V_{cc}$ of 5V with average rising and falling propagation delay of 10 ns each and has current drains $I_{CCH} = 2$ mA and $I_{CCL} = 5$ mA. Find average power dissipation and find figure of merit.
* **(c)** Convert each of the following binary number into its equivalent in the octal and hexadecimal number systems.
    * i) `101001.010`
    * ii) `111001011`

### **Q3**
* **(a)** Write VHDL code of a J K flip flop using all three styles of coding.
* **(b)** Write VHDL code of a 4 X 1 Multiplexer using behavioral style with conditional statements.
* **(c)** Realize a 2-bit Magnitude comparator using any combinational circuit. Given that A and B are two binary nos. containing 2 bits each ($A=A_1A_0$, $B=B_1B_0$), Outputs are G = A>B, L = A<B, E = A=B.

### **Q4**
* **(a)** Design a MOD-5 counter using T flipflop which goes through the sequence as $000 \to 010 \to 011 \to 101 \to 111$.
* **(b)** Implement a 4-bit Universal shift register using D flipflop which performs following action:

    | s0 | s1 | function |
    | :--- | :--- | :--- |
    | 0 | 0 | hold state |
    | 0 | 1 | shift right |
    | 1 | 0 | shift left |
    | 1 | 1 | load new input |

* **(c)** If there are 6 states a, b, c, d, e and f in an FSM. Show state assignment in binary code, gray code and one-hot encoding method.

### **Q5**
* **(a)** Design a Mealy and Moore FSM to detect a sequence of '110'. Also mention present state, next state and output in each case.
* **(b)** Realize a BCD to seven segment display using a suitable size of decoder.
* **(c)** Briefly explain (any two):
    * i) A/D and D/A converter
    * ii) Datapath in computers
    * iii) RAM and ROM* **(b)** Explain the following parameters:
    * (i) Propagation Delay
    * (ii) Noise Margin
    * (iii) Fan-out
    * (iv) Power dissipation
* **(c)** Design and explain the NAND and NOR gate circuit implemented by CMOS transistors. What are the advantages and disadvantages of CMOS technology.

### **Q2**
* **(a)** Using the Quine-McCluskey (Tabulation) method minimize the function given below having don't care terms:
    $$f(w, x, y, z) = \Pi M(0, 6, 7, 8, 9, 13) + d(5, 15)$$
* **(b)** Design a code converter that converts 84-2-1 code into 8421 code and implement it by using four 4X1 MUXs and external gates.
* **(c)** Design an adder that adds two numbers of two bits each. Implement it by using complementary output decoder and AND/NAND gates.

**Attempt any TWO parts from Questions 3, 4 & 5:**

### **Q3**
* **(a)** Convert a positive edge triggered D flip-flop into a positive edge triggered AB flip-flop whose characteristic table is given as Table 1.

    **Table 1: Table for AB Flip-flop**

    | A | B | $Q(t+1)$ |
    | :--- | :--- | :--- |
    | 0 | 0 | 0 |
    | 0 | 1 | 0 |
    | 1 | 0 | 1 |
    | 1 | 1 | 1 |

* **(b)** Using a negative edge triggered T flip flop design a synchronous mod-5 counter whose counting sequence is:
    $$0 \to 1 \to 2 \to 3 \to 4 \to 0$$
* **(c)** Write short notes on PWM generator.

### **Q4**
* **(a)** Write the VHDL code for 8X1 MUX.
* **(b)** Write a VHDL code for a level triggered J-K flip-flop with clear and preset inputs.
* **(c)** Explain in brief the various modeling styles in VHDL.

### **Q5**
* **(a)** Implement the following functions using a cost efficient PLA assuming both true and complementary form are available at the output. Draw PLA table.
    *(Note: Specific functions are not clearly visible in the source image)*
* **(b)** Explain in brief the various elements of the CPU.
* **(c)** Design an FSM, using VHDL, that has an input `w` and an output `z`. The machine is a sequence detector that produces `z = 1` when the previous two values of `w` were 00 or 11; otherwise `z = 0`.

---

## **2. Mid-Semester Examination (February 2024)**
**Course:** Digital Logic Design (COECC203/CAECC203/CDECC203/ITECC203/INECC203)
**Duration:** 1:30 Hours | **Max Marks:** 20

| Q. No. | Question | Marks | CO |
| :--- | :--- | :--- | :--- |
| **1a** | Express the logic function in terms of minterms<br>$$f(P,Q,R) = PQ + Q\bar{R} + P\bar{R}$$| 2 | CO1 |
| **1b** | Find out the value of w,y, and z in the following equality<br>$$(10w1z)_2 \times (15)_{10} = (y01011001)_2$$ | 2 | CO1 |
| **2a** | Implement the following Boolean function with a 4x1 multiplexer and external gates. Connect inputs C, D as selection lines S1, S0 and A, B as input lines.<br>$$F(A, B, C, D) = (0, 6, 7, 9, 11, 12, 14, 15)$$ | 2 | CO1 |
| **2b** | A combinational circuit is specified by the following Boolean function:$$F1 (A, B, C) = \Sigma m (0, 2, 5, 7)$$. Implement the circuit with a decoder and external logic gates. | 2 | CO2 |
| **3a** | Convert the logic function $$X (w,y,z) = \Pi M (0,2,3)$$into SOP form and list the corresponding product terms. | 2 | CO2 |
| **3b** | Implement 2-input XOR gate using minimum number of NAND gates. | 2 | CO1 |
| **4a** | Simplify the function$$F(A,B,C,D)= \Sigma m (0,2,4,6,9,11,13,15) + d (1,5)$$ using Karnaugh map. | 2 | CO2 |
| **4b** | Design a combinational circuit whose input is a four-bit number and whose output is the 2’s complement of the input number. | 2 | CO2 |
| **5a** | Write the truth table for a three-input priority encoder with inputs D0-D2 and input D0 having the highest priority while input D2 has the lowest priority. | 2 | CO2 |
| **5b** | Design a circuit of priority encoder as given in 5(a). | 2 | CO2 |

---

## **3. End-Semester Examination (April-May 2024)**
**Course:** Digital Logic Design (COECC203/CAECC203/CDECC203/ITECC203/INECC203)
**Duration:** 03 Hours | **Max Marks:** 50

**Q1. Attempt any 2 parts of the following:**
* **1a**
    * i) Represent +6 and -6 in unsigned, signed, 1's complement and 2's complement representation (assume 4-bit representation). (3 Marks)
    * ii) A number in its 2's complement form is represented as 1001. Find its equivalent decimal number. (2 Marks)
* **1b** Why 'AND gate' and 'OR gate' cannot be classified under universal gates? Implement $$F(A,B,C)=A+BC$$using minimum number of:
    * i) 2-input NAND gates and
    * ii) 2-input NOR gates.
* **1c** Simplify$$F(A,B,C,D) = \Sigma m (1,3,4,6,8,12) + d(9,11)$$ using K-Map in POS form.

**Q2. Attempt any 2 parts of the following:**
* **2a** Implement a 3x8 decoder using two 2x4 decoders.
* **2b** Design an XS-3 to BCD code converter using logic gates.
* **2c** Draw the circuit diagram for a 4-bit parallel adder and explain its functioning.

**Q3. Attempt any 2 parts of the following:**
* **3a** Design a modulo-6 synchronous down counter using T flip-flops.
* **3b**
    * (i) Differentiate between latch and a flip-flop (2 Marks)
    * (ii) Convert a D flip-flop to SR flip-flop (3 Marks)
* **3c** Design a 101 Moore sequence detector circuit using D-Flip Flop. Use binary encoding for state assignment.

**Q4. Attempt any 2 parts of the following:**
* **4a** Write VHDL code in behavioral style and structural style for 4x1 Multiplexer.
* **4b** What are the types of architectural declaration in VHDL? Explain each of them in with example of a full adder.
* **4c** Write VHDL code for positive edge triggered 4-bit up counter using JK Flip-Flops.

**Q5. Attempt any 2 parts of the following:**
* **5a** Explain the following parameters:
    * (i) Fan out
    * (ii) Power Dissipation
    * (iii) Propagation delay
    * (iv) Figure of Merit
    * (v) Noise margin
* **5b** Implement the following using Programmable Logic Array:
    $$F1 (X,Y,Z) = \Sigma m(1,3,5,7)$$
    $$F2 (X,Y,Z) = \Sigma m(0,2,4,6)$$
* **5c** Draw the circuit diagram and explain the working of Flash type Analog to Digital Converter.

---

## **4. Mid-Semester Examination (September 2023)**
**Course:** Digital Circuits and Systems (ECECC08/EIECC08)
**Time:** 1:30 Hours | **Max Marks:** 15

| Q.No. | Question | Marks | CO |
| :--- | :--- | :--- | :--- |
| **1** | A combinational circuit with three inputs, x, y, and z, and three outputs, A, B, and C. When the binary input is 0, 1, 2, or 3, the binary output is one greater than the input. When the binary input is 4, 5, 6, or 7, the binary output is two less than the input.<br><br>(a) Draw the truth table.<br>(b) Implement by using NAND gates only. | 1 + 2 | CO1 |
| **2** | The following Boolean function<br>$$F (A, B, C, D) = \Sigma ( 1, 2, 5, 7, 8, 10, 11, 13, 15)$$<br><br>(a) Draw the truth table.<br>(b) Implement it by using 4X1 MUX and external gates. | 0.5 + 2 | CO3 |
| **3** | (a) Convert 110011 from gray code to binary.<br>(b) Perform subtraction using 2's complement: $$11000.001 - 110.11$$| 1 + 2 | CO1 |
| **4** | (a) Draw the circuit of CMOS two input NAND gate.<br>(b) Represent the function in Canonical standard Sum of Product form.<br>$$F(w, x, y, z) = (w + x + y)(\bar{w} + \bar{x}z) + \bar{y}\bar{z}$$ | 1.5 + 1.5 | CO2 / CO1 |
| **5** | Design a BCD to Excess 3 decimal code convertor.<br>(a) Make a truth table.<br>(b) Implement it by using a decoder of suitable size and minimal number of inputs to gates. | 1 + 2 | CO3 |

---

## **5. Mid-Semester Examination (February 2020)**
**Course:** Digital Logic Design (CEECC03/ITECC03/CAECC03)
**Time:** 1.5 hrs | **Max Marks:** 15

### **Q1**
* **(a)** Determine the base of the given numbers:
    * i)$$((41)_b)^{1/2} = (5)_{10}$$
    * ii) $$(16)_{10} = (100)_b$$
* **(b)** Simplify the given expression using Boolean algebra and implement using NAND gates only.
    $$F = A'B'C + (A+B+C')' + A'B'C'D$$

### **Q2**
* **(a)** Design a BCD to Excess-3 code converter.
* **(b)** Implement 4:16 decoder using 2:4 decoder.

### **Q3**
* **(a)** Minimize the given function using Quine Mc-cluskey method. Also, write EPI and PI.
    $$F(A,B,C,D) = \Pi M (2,3,8,12,13) \cdot d(10,14)$$
* **(b)** Implement the given function using 8x1 Mux:
    $$F(A,B,C,D) = \Sigma m(0,1,6,7,8,9,13,14,15)$$

### **Q4**
* **(a)** Implement full adder using PLA.
* **(b)** Write the differences between Latches and Flip Flops.

### **Q5**
* **(a)** Draw and explain BCD adder.
* **(b)** Implement the given function using a 3x8 complementary decoder.
    $$F = \Sigma m(1,2,6,7)$$

---

## **6. End-Semester Examination (July 2023)**
**Course:** Digital Logic Design (CAECC03/COECC03/CDECC03/ITECC01/INECC01)
**Time:** 3 Hours | **Max Marks:** 40

**Attempt any TWO parts of each question.**

### **Q1**
* **(a)** Implement the following function using most suitable size of PLA.
    $$F_1(A, B, C) = \Sigma m (1,2,3,7)$$
    $$F_2(A, B, C) = \Sigma m (0,1,2,6)$$
* **(b)** Design a three-input, one-output minimal two-level gate combinational circuit that has a logic-1 output when the majority of its inputs are logic-1 and has a logic-0 output when the majority of its inputs are logic-0.
* **(c)** Using the Quine-McCluskey method, obtain all the prime implicants.
    $$f_1(w, x, y, z) = \Sigma m (0,2,3,4,8,10,12,13,14)$$

### **Q2**
* **(a)** Implement NAND and NOR logic operation using CMOS logic family. Briefly Explain.
* **(b)** A standard TTL NAND gate uses supply voltage $V_{cc}$ of 5V with average rising and falling propagation delay of 10 ns each and has current drains $I_{CCH} = 2$ mA and $I_{CCL} = 5$ mA. Find average power dissipation and find figure of merit.
* **(c)** Convert each of the following binary number into its equivalent in the octal and hexadecimal number systems.
    * i) `101001.010`
    * ii) `111001011`

### **Q3**
* **(a)** Write VHDL code of a J K flip flop using all three styles of coding.
* **(b)** Write VHDL code of a 4 X 1 Multiplexer using behavioral style with conditional statements.
* **(c)** Realize a 2-bit Magnitude comparator using any combinational circuit. Given that A and B are two binary nos. containing 2 bits each ($A=A_1A_0$, $B=B_1B_0$), Outputs are G = A>B, L = A<B, E = A=B.

### **Q4**
* **(a)** Design a MOD-5 counter using T flipflop which goes through the sequence as $000 \to 010 \to 011 \to 101 \to 111$.
* **(b)** Implement a 4-bit Universal shift register using D flipflop which performs following action:

    | s0 | s1 | function |
    | :--- | :--- | :--- |
    | 0 | 0 | hold state |
    | 0 | 1 | shift right |
    | 1 | 0 | shift left |
    | 1 | 1 | load new input |

* **(c)** If there are 6 states a, b, c, d, e and f in an FSM. Show state assignment in binary code, gray code and one-hot encoding method.

### **Q5**
* **(a)** Design a Mealy and Moore FSM to detect a sequence of ‘110’. Also mention present state, next state and output in each case.
* **(b)** Realize a BCD to seven segment display using a suitable size of decoder.
* **(c)** Briefly explain (any two):
    * i) A/D and D/A converter
    * ii) Datapath in computers
    * iii) RAM and ROM
