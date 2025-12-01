# Algorithm Design and Analysis – Questions Sorted by Syllabus Units
## Compiled from 25 Exam Papers (2012–2024)

**Total Questions:** 215+  
**Organization:** 6 Units as per DTU Syllabus  
**Date Range:** May 2012 – Nov 2024  

> **Acknowledgement:** Most of the papers were sourced courtesy of my senior Madhav Gupta. Many thanks to him.

---

## Table of Contents

- [UNIT 1: INTRODUCTION](#unit-1-introduction---algorithmic-efficiency-run-time-analysis-asymptotic-notations--masters-theorem)
  - [1.1 Asymptotic Notations (Big-O, Omega, Theta)](#11-asymptotic-notations-big-o-omega-theta)
  - [1.2 Master’s Theorem & Recurrence Relations](#12-masters-theorem--recurrence-relations)
  - [1.3 Recurrence Tree Method & Substitution Method](#13-recurrence-tree-method--substitution-method)
  - [1.4 Time Complexity Analysis of Programs](#14-time-complexity-analysis-of-programs)
- [UNIT 2: SEARCHING AND SORTING](#unit-2-searching-and-sorting---divide-and-conquer-algorithms)
- [UNIT 3: GREEDY METHOD](#unit-3-greedy-method---mst-shortest-paths-huffman-coding-activity-selection)
- [UNIT 4: DYNAMIC PROGRAMMING & BACKTRACKING](#unit-4-dynamic-programming--backtracking)
- [UNIT 5: BRANCH AND BOUND](#unit-5-branch-and-bound)
- [UNIT 6: COMPUTATIONAL COMPLEXITY](#unit-6-computational-complexity---p-np-np-hard-np-complete)


---


# UNIT 1: INTRODUCTION - ALGORITHMIC EFFICIENCY, RUN TIME ANALYSIS, ASYMPTOTIC NOTATIONS & MASTER'S THEOREM
## Contact Hours: 6

### 1.1 Asymptotic Notations (Big-O, Omega, Theta)

**CO208-ADA-2019-Sept-Supp | Q6**
Write short notes on: (I) Big-oh, (II) Big-omega, (III) Big-theta, (IV) RAM Model

**CO208-ADA-May-2017-End | Q1(b)**
Explain Big O, big Ω, big Θ asymptotic notations.

**CO214-ADA-2018-August-Supp | Q6**
Write short notes on:
- (i) P and NP class
- (ii) NP-Hard problems
- (iii) Reducibility
- (iv) Big-oh
- (v) Stable sorting
- (vi) Master's Theorem
- (vii) Vertex Cover Problem

**CO214-ADA-2018-May-Endsem | Q6**
Write short notes on:
- (i) NP class
- (ii) NP complete class
- (iii) Circuit Satisfiability
- (iv) Big-oh
- (v) Big-omega
- (vi) Big-theta
- (vii) Vertex Cover Problem

**CO214-ADA-May-2012-End | Q2(a)**
What are Asymptotic notations? Define Big-Oh and Big-Omega notations.

**IT208-2019-May-End | Q1(A)**
Write and explain different type of asymptotic notations with suitable example.

**IT211-2019-May-End | Q1(c)**
What are asymptotic notations? Explain.

**SE214-2019-May-End | Q6**
Write short notes on:
- (i) Big-oh
- (ii) Big-omega
- (iii) Big-theta
- (iv) NP-Complete Problems

**CO214-ADA-May-2016-End | Q6(a)**
Explain the following terms: Big-oh, Big-omega, Big-theta

---

### 1.2 Master's Theorem & Recurrence Relations

**CO208-ADA-2018-March-Midsem | Q1**
Solve the following recurrences using the Master's Method
- (i) T(n) = 3T(n/3) + n/2
- (ii) T(n) = 7T(n/3) + n²
- (iii) T(n) = 2T(n/2) + n log n

**CO208-ADA-2019-Sept-Supp | Q1(a)**
For each of the following recurrences, solve them with the help of the master theorem:
- (I) T(n) = 3T(n/3) + n²
- (II) T(n) = 16T(n/7) + n

**CO208-ADA-2020-March-Mid | Q1(ii)**
Solve T(n) = 6T(n/3) + n² log n using the Master's Method.

**CO208-ADA-2018-May-Endsem | Q1(a)**
Solve the following recurrences:
- i. T(n) = 3T(n/2) + n
- ii. T(n) = 3T(n/3) + n/2
- iii. T(n) = 6T(n/3) + n² log n

**CO208-ADA-May-2017-End | Q1(a)**
For each of the following recurrences, solve them with the help of the master theorem:
- (1) T(n) = 0.5T(n/2) + n²
- (ii) T(n) = √2T(n/2) + log n

**CO208-ADA-2019-March-Mid | Q1(i), Q1(ii), Q1(iii)**
- Solve T(n) = 2T(n/2) + n log n
- Solve T(n) = 3T(n/4) + n log n
- Solve T(n) = 5T(n/3) + n log n

**CO208-Mid-2023 | Q1(a)(i), Q1(a)(ii)**
- Solve T(n) = 6T(n/3) + n² log n
- Solve T(n) = 2T(√n) + log n

**CO214-ADA-2018-August-Supp | Q1(a)**
For each of the following recurrences, solve with master theorem:
- (i) T(n) = T(3n) + n
- (ii) T(n) = 4T(n/4) + n log n

**CO214-ADA-2018-May-Endsem | Q1(a)**
For each of the following recurrences, solve with master theorem:
- (i) T(n) = 16T(n/4) + n!
- (ii) T(n) = 2T(n/2) + n^0.51

**CO208-ADA-2018-August-Supp | Q1(a)**
Solve following recurrences:
- i. T(n) = 3T(n/4) + n log n
- ii. T(n) = (2^n)T(n/2) + n^n [CORRECTED FROM OCR ERROR]
- iii. T(n) = 64T(n/8) + n² log n

**CO208-ADA-March-2017-Mid | Q1(a)**
Apply master method to find complexity:
- T(n) = 4T(n/3) + n
- T(n) = 4T(n/3) + n²

**CO208-ADA-2019-May-End-SUPP | Q1(a), Q1(b)**
- Suppose divide and conquer algorithm solves problem of size n by first solving three instances of size n/2 then taking O(n) additional steps. If time to create three instances is O(n²), what is running time T(n)?
- Solve: T(n) = 8T(n/2) + n³ and T(n) = 7T(n/2) + n³

**IT208-2019-Sept-Supp-INCOMPLETE | Q1(B)**
What is the use of Master Theorem. Explain it with suitable example. Whether we can solve the following relation using Master Theorem T(n)= 2T(n/2+17)+n, if yes then what will the time complexity and otherwise justify why we cannot solve it.

**IT208-2018-May-Endsem | Q1(A)**
Give the run time complexity of the following:
- i. T(n) = T(n/2) + n(2 - cos n)
- ii. T(n) = 16T(n/4) + n
- iii. T(n) = 6T(n/3) + n² log n

**IT208-2018-August-Supp | Q1(A)**
Give the run time complexity of the following:
- i. T(n)= T(n/3) + T(2n+3) + n (Using recurrence tree method)
- ii. T(n)=4T(n/2) + n³ (Using Master method)
- iii. T(n)= 6T(n/3) + n² log n (Using Master Method)

**IT211-2019-May-End | Q1(b)**
Solve the following recurrence relations using master method:
- i) T(n) = T(n/2) + 2n
- ii) T(n) = 4T(1/2) + n²

**IT208-2019-May-End | Q1(B)(1)**
For each of the following recurrences, give an expression for the runtime T(n) if the recurrence can be solved with the Master Theorem. Otherwise, indicate that the Master Theorem does not apply.
- a) T(n) = 2^T(n/2) + n^
- b) T(n) = √2T(n/2) + log n

**SE214-2019-May-End | Q1(a)**
For each of the following recurrences, solve them with the help of master theorem:
- (i) T(n) = 3T(n/2) + n
- (ii) T(n) = 16T(n/4) + n²

**CO214-ADA-May-2016-End | Q1(a)**
For each of the following recurrences, solve them with the help of master theorem:
- (i) T(n) = 3T(n/2) + n²
- (ii) T(n) = 16T(n/4) + n
- (iii) T(n) = 3T(n/3) + n/2
- (iv) T(n) = 2T(n/2) + O(n)

**CO214-ADA-May-2012-End | Q1(a)**
Solve the following recurrence using master's theorem: T(n) = 7T(n/2) + n²

---

### 1.3 Recurrence Tree Method & Substitution Method

**CO208-ADA-2018-March-Midsem | Q2**
Solve the following recurrence using the recurrence tree method, showing complete steps.
- T(n) = 7T(n/3) + n²

**CO208-ADA-2019-Sept-Supp | Q1(b)**
Solve T(n) = 7T(n/3) + n² with the help of the recursion tree method. Show each step involved.

**CO208-ADA-2020-March-Mid | Q1(i)**
Solve T(n) = 3T(n/4) + n² using the recursion tree method.

**CO214-ADA-2018-August-Supp | Q1(b)**
Solve T(n) = 2T(n/2) + n with recursion tree method. Show each step involved.

**CO214-ADA-2018-May-Endsem | Q1(b)**
Solve T(n) = 7T(n/2) + n² with recursion tree method. Show each step involved.

**CO208-ADA-March-2017-Mid | Q1(b)**
For recurrence T(n) = T(n/3) + T(2n/3) + n:
- Apply recurrence tree method to find complexity. Show each step.
- For complexity calculated, use substitution method to prove. Use log₂3 and log₂(3/2) as 3/2 and √1/2 respectively. Write minimum constant c for which proof holds.

**IT208-ADA-2018-March-Midsem | Q2(A), Q2(B)**
- Find the run time complexity of: Program with nested loops, T(n)=2T(√n) + log n, T(n) = 2T(n - 1) – 1
- Explain Recurrence Tree method and also find worst case running time of: T(n)= T(n/3)+ T(2n/3)+O(n).

**IT211-2018-May-Endsem | Q1(B), Q1(C)**
- Explain Recurrence Tree method and find worst case running time of: T(n)= T(n/3)+ T(2n/3)+O(n)
- Find the run time complexity of: nested loops, T(n)= 2T(√n) + log n, T(n) = 2T(n - 1)

**IT208-2019-Sept-Supp-INCOMPLETE | Q1(A)**
Discuss the types of complexity to analyze the algorithm. Explain the run time analysis of Insertion sort.

**IT211-2018-August-Supp | Q1(B)**
Explain Recurrence Tree method and also find the worst case running time of: T(n)= T(n/3) + T(2n/3) + O(n).

**CO214-ADA-May-2012-End | Q2(b), Q2(c)**
- Consider the recurrence T(n) = 2T(n/2) + n². Solve it using recurrence tree method.
- Explain heap sort algorithm in detail. Also analyse its complexity.

**CO214-ADA-May-2016-End | Q1(b)**
Solve T(n) =7T(n/3) + n² with the help of recursion tree method. Show each step involved.

**IT208-ADA-2018-March-Midsem | Q3(C)**
Use the substitution method to prove that the recurrence T(n)= T(n-1)+(n) has the solution T(n)= Θ(n²).

**IT211-2018-May-Endsem | Q2(C)**
Use the substitution method to prove that the recurrence T(n)= T(n-1)+ (n) has the solution T(n)= (n²).

---

### 1.4 Time Complexity Analysis of Programs

**CO208-Mid-2023 | Q1(b)**
Find time complexity of the following program:
```
void fun(n) {
  int i, j, count=0;
  for(i=n; i>0; i=i/2)
    for(j=0; j<=i; j++)
      count++;
}
```

**IT208-ADA-2018-March-Midsem | Q2(A)**
Find the run time complexity of nested loop programs.

**IT208-ADA-2018-March-Midsem | Q3(A), Q3(B)**
- What is the running time of heap sort on an array A of length n that is already sorted in increasing order? What about decreasing order?
- What is the running time of Quicksort when all elements of array A have the same value?

**IT211-2018-August-Supp | Q1(C)**
Write insertion sort algorithm. Explain best case and worst case time complexity of insertion sort.

**IT208-2018-August-Supp | Q1(B)**
Write insertion sort algorithm. Explain best case and worst case time complexity of insertion sort.

**CO214-ADA-May-2012-End | Q1(b), Q1(c), Q1(e)**
- Define principle of optimality
- Greedy approach guarantees to produce optimal solution. True or false? Justify your answer.
- How does traversal occur in breadth first search.

# CO208 END TERM EXAMINATION (MAY 2024)
**Q1(a).** An array of 50 distinct elements is to be sorted using quicksort. Assume that the pivot element is chosen uniformly at random. Find the probability that the pivot element gets placed in the worst possible location in the first round of partitioning. [CO2][2M]

**Q1(b).** Write an efficient algorithm to find prime numbers from 1 to n, where n is the input from the user. Discuss the time and space complexity. [CO1][2M]

**Q1(c).** What is the order of the return value of `k` produced by the following function:
```
int foo(int n) {
int i, j, k = 0;
for (i = n/2; i <= n; i++)
for (j = 2; j <= n; j = j * 2)
k = k + n/2;
return k;
}
```
[CO1][2M]

---

---

# UNIT 2: SEARCHING AND SORTING - DIVIDE AND CONQUER ALGORITHMS
## Contact Hours: 6

### 2.1 Binary Search

**CO208-ADA-2019-Sept-Supp | Q2(b)**
Write down the recursive binary-search algorithm and apply it to find the value 2 in the array: {1,2,3,4,5,6,7,8,9,10}.

**CO208-ADA-2020-March-Mid | Q5**
Suppose you are given a sorted array A[1..n] of integers that has been circularly shifted k positions. Example: {35, 42, 5, 15, 27, 29} is shifted k = 2. Describe an O(log n) algorithm to find the largest element.

**CO208-ADA-2019-March-Mid | Q2**
You are given sorted array of n elements which has been circularly shifted. Example: {35, 42, 5, 12, 23, 26} is sorted array shifted by 2 positions. Give O(log n) algorithm to find largest element. Number of positions shifted is unknown.

**CO208-ADA-March-2017-Mid | Q2**
Given sorted array of non-repeated integers A[1...n], check whether index i exists for which A[i]=i. Modify divide and conquer algorithm/pseudo code for binary search to do needful. Give example. Analyze complexity.

**CO208-ADA-2018-March-Midsem | Q3**
Given an array A which stores 0s and 1s, such that all entries containing 0 appear before all entries containing 1. Design an algorithm with O(log n) time complexity to find the smallest index i in the array A such that A[i] = 1.

**CO208-Mid-2023 | Q3**
Given sorted array of distinct integers A[1, ..., n], find whether there is index "i" for which A[i] = i+1. Give divide-and-conquer algorithm running in O(log n).

**CO208-ADA-2019-March-Mid | Q5**
Given sorted array of distinct integers (may be negative), give algorithm to find index i such that 1<=i<=n and A[i]=i, if such index exists.

**SE214-2019-May-End | Q2(b)**
Write down recursive binary-search algorithm and apply the same to find the value 2 in the following array. Array is as follows 1,2,3,4,5,6,7,8,9,10.

---

### 2.2 Quicksort & Merge Sort

**CO208-ADA-2019-Sept-Supp | Q2(a), Q2(b), Q7(b)**
- Write the quicksort algorithm. Derive the worst-case and best-case complexity for this algorithm.
- Write an algorithm for quicksort. Explain with an example and show the analysis for the algorithm.

**CO208-ADA-May-2017-End | Q2(a)**
Write down the randomized quicksort algorithm. Also explain in detail what special insight the average-case gives to us.

**CO214-ADA-2018-August-Supp | Q2(a)**
Write quick sort algorithm. Analyze efficiency. Apply to sort list {4,1,6,3,9,2,7,5}

**CO214-ADA-May-2016-End | Q2(a)**
Write quick sort algorithm. Drive worst case complexity for this algorithm. Also explain in detail what special insight does average-case give to us?

**SE214-2019-May-End | Q2(a)**
Write quick sort algorithm. Drive worst case and best case complexity for this algorithm.

**IT208-2019-May-End | Q2(A)**
Discuss merge sort and quick sort algorithm. "Merge sort is good choice instead of quick sort". Do you agree with the statement. Justify your answer.

**IT208-2019-Sept-Supp-INCOMPLETE | Q2(A)**
Discuss the algorithm of merge sort and validate it with suitable example.

**IT208-ADA-2018-March-Midsem | Q1**
Insertion Sort can be expressed as a recursive procedure as follows. In order to sort A[1...n], we recursively sort A[1...n-1] and then insert A[n] into the sorted array A[1..n-1]. Write pseudocode of this recursive procedure (Recursive-Insertion-Sort).

**IT211-2018-May-Endsem | Q1(A)**
Insertion Sort can be expressed as a recursive procedure. Write pseudocode of this recursive procedure (Recursive-Insertion-Sort).

---

### 2.3 Heap Sort & Heap Operations

**CO214-ADA-2018-May-Endsem | Q2(a)**
Write algorithm to convert random array into Max-heap. Write algorithms for delete-Max() and Insert() for this Max-heap.

**IT208-ADA-2018-March-Midsem | Q3(A), Q3(D)**
- What is the running time of heap sort on an array A of length n that is already sorted in increasing order? What about decreasing order?
- Illustrate the operation of Heap-Extract-Max on the heap A = {15, 13, 9, 5, 12, 8, 7, 4, 0, 6, 2, 1}.

**IT211-2018-May-Endsem | Q2(A), Q3(A)**
- What is the running time of heap sort on an array A that is already sorted?
- Illustrate the operation of Heap-Extract-Max on the heap A = {15, 13, 9, 5, 12, 8, 7, 4, 0, 6, 2, 1}.

**IT211-2018-August-Supp | Q1(A)**
Illustrate the operation of Heap-Extract-Max on the heap A = {15, 13, 9, 5, 12, 8, 7, 4, 0, 6, 2, 1}.

# CO208 END TERM EXAMINATION (MAY 2024):

### Unit 2: Searching and Sorting
**Q2(b).** You are given `k` sorted integer arrays (each array of size `n`) in the form of a 2D integer matrix of size `k × n`. Write an optimized algorithm to merge them into a single array and return it. Also discuss the time and space complexity of the proposed algorithm. [CO2][5M]
*Example:* Input: `k = 3`, `n = 4`, array = `{{1, 3, 5, 7}, {2, 4, 6, 8}, {0, 9, 10, 11}}`
Output: `0 1 2 3 4 5 6 7 8 9 10 11`


**Q5(b).** The operation `HEAP-delete(A, item)` deletes the item in a binary heap `A` containing `n` elements. Propose an implementation of `HEAP-delete` that runs in `O(log n)` time for a max heap. [4M][CO3]



---

### 2.4 Divide and Conquer - Finding Min & Max

**CO208-ADA-2018-May-Endsem | Q4(a)**
Give divide-and-conquer pseudocode to find the minimum and maximum elements in an array. Form the recurrence relation and solve it to obtain complexity.

**CO208-Mid-2023 | Q2**
Using divide and conquer approach, write recursive function to find maximum and minimum elements of set containing 2^n elements. Write recurrence relation and solve it.

**IT208-2019-May-End | Q1(B)(2)**
Solve the following relation by recursive method T(n)= 2T(n/2+17)+n

---

### 2.5 Strassen's Matrix Multiplication

**CO208-ADA-March-2017-Mid | Q4**
Explain Strassen's method of matrix multiplication. Write down algorithm and equations involved. Explain complexity.

**IT208-2018-May-Endsem | Q1(C)**
Explain the Strassen Matrix Multiplication procedure. Evaluate the optimal parenthesis of p = <4, 3, 5, 2, 6, 2> explaining all the steps.

**IT211-2019-May-End | Q7(a)**
Write short notes on:
- ii) Strassen's method for matrix multiplication

---

### 2.6 Missing Number & Array Manipulation

**CO208-ADA-2018-May-Endsem | Q4(b)**
An array of n elements contains all but one of the integers from 1 to n+1. Give algorithms for finding the missing number if the array is (i) sorted and (ii) unsorted, and analyze their worst-case running times.

**CO208-ADA-2019-May-End-SUPP | Q4(b)**
Using divide and conquer strategy count number of inversions (out of order pairs) in array. Elements x1, ..., Xn. Inversion if xi > xj and i < j.

---

### 2.7 Interleaving & Advanced D&C Problems

**CO208-ADA-2018-May-Endsem | Q5(a)**
Given bit strings X, Y, and Z, where Z is an interleaving of X and Y. Give the most efficient algorithm to determine if Z is an interleaving of X and Y. Prove it is correct and analyze its time complexity.

**CO208-ADA-2019-May-End-SUPP | Q8(b)**
Let x = X1X2...Xn, y = Y1Y2...Ym, z = Z1Z2...Zn+m be strings of length n, m, n+m. Z is merge of x and y if x and y found as disjoint subsequences in z. Define function Merge(i,j) and write code.

---

### 2.8 Graph Basics & DFS Traversal

**CO208-ADA-2018-August-Supp | Q6(b)**
What are types of edges you encounter when running DFS on directed graph?

**IT211-2019-May-End | Q4(a)**
What is topological sorting? Explain the algorithm with an example.

**IT211-2019-May-End | Q7(a)**
Write short notes on:
- i) Connected Component graph

**CO214-ADA-May-2012-End | Q1(e)**
How does traversal occur in breadth first search.

---

---

# UNIT 3: GREEDY METHOD - MST, SHORTEST PATHS, HUFFMAN CODING, ACTIVITY SELECTION
## Contact Hours: 12

### 3.1 Huffman Coding

**CO208-ADA-2020-March-Mid | Q2**
Write an algorithm for Huffman coding and find Huffman codes for the following data:
- Characters: a, b, c, d, e, f, g
- Frequencies: 37, 18, 29, 13, 30, 17, 6
- Compute the average code length.

**CO208-ADA-2018-May-Endsem | Q1(b)**
Apply Huffman coding to the characters (A, B, C, D, E, F, G, H) with frequencies (10, 4, 3, 5, 15, 3, 2, 1).

**CO208-ADA-May-2017-End | Q6(b)**
Write pseudocode and obtain Huffman codes for following:
- Characters: a, b, c, d, e, f, g, h
- Occurrences (thousands): 1, 1, 2, 3, 5, 8, 13, 21
- Analyze complexity.

**CO208-ADA-2019-March-Mid | Q3**
Write algorithm for Huffman coding and apply on following data:
- Char: a, b, c, d, e, f, g, h, i
- Frequency: 5, 1, 3, 21, 5, 9, 3, 6, 8
- Also compute average code size.

**IT208-ADA-2018-March-Midsem | Q5**
Write an algorithm to construct the Huffman code. Also encode following characters:
- Characters: A, B, C, D, E, F, G
- Frequency: 37, 18, 29, 13, 30, 17, 6

**IT211-2018-May-Endsem | Q2(D)**
Write an algorithm to construct the Huffman code. Also encode following characters:
- Characters: A, B, C, D, E, F, G
- Frequency: 37, 18, 29, 13, 30, 17, 6

**IT208-2018-August-Supp | Q2(B)**
Symbols A, B, C, D, E, F are being produced by information source with probabilities (in percentage) 30, 40, 6, 10, 15, 4 respectively. Find the binary Huffman code for above symbol.

**IT211-2018-August-Supp | Q2(A)**
Symbols A, B, C, D, E, F are being produced by information source with probabilities (in percentage) 30, 40, 6, 10, 15, 4 respectively. Find the binary Huffman code for above symbol.

**CO214-ADA-May-2012-End | Q3(b)**
Given the characters <a, b, c, d, e, f> with the following probability of occurrence P=<45, 13, 12, 16, 9, 5>. Build a binary tree according to greedy strategy for defining an optimal Huffman code.

---
### 3.13 Disjoint Set Data Structures

**CO205-DAA-Nov-2024-Endsem | Q5(a)**
Following diagram shows representation of disjoint sets S1={c, h, e, b} and S2={f, g, d} using linked lists. For every set S, we have head[S], and tail[S].
Design best possible algorithms for following operations:
Make-set(), Find-Set(), Union()

---
### 3.2 Fractional Knapsack & Greedy Approach

**CO208-ADA-2018-August-Supp | Q7(a)**
Write algorithm for solving fractional Knapsack problem.

**IT208-2019-Sept-Supp-INCOMPLETE | Q3(A)**
Solve the given fractional knapsack problem using greedy approach, where knapsack capacity is 22.
- Item: 1, 2, 3
- Weight: 20, 17, 12
- Profit: 32, 23, 20

**IT208-2019-May-End | Q3(A)**
Solve the given fractional knapsack problem using greedy approach, where knapsack capacity is 20.
- Item: 1, 2, 3
- Weight: 18, 15, 10
- Profit: 30, 21, 18

**IT208-2018-May-Endsem | Q3(A)**
What is Knapsack problem? How is greedy knapsack different from 0/1 Knapsack? Solve for W=18Kg:
- Item: A, B, C, D, E
- Weight: 10, 7, 8, 4, 6
- Value: 100, 63, 56, 12, 34

**IT208-2018-August-Supp | Q5(A)**
What is Knapsack problem? How is greedy knapsack different from 0/1 Knapsack? Solve for W=18Kg.

**CO214-ADA-May-2016-End | Q4(b)**
Support your reason for solving fractional knapsack problem with greedy approach by identifying ingredients of greedy strategy in it. Write appropriate pseudo code that would have solved fractional knapsack with greedy choice.

---

### 3.3 Activity Selection Problem

**CO208-ADA-2020-March-Mid | Q3**
You are given n events where each takes one unit of time. Event i provides a profit of gi > 0 dollars if started at or before time ti. Give the most efficient algorithm to find a schedule that maximizes profit.

**CO208-Mid-2023 | Q4**
Given the following jobs, deadlines and profits. Schedule on uniprocessor system where profit awarded only if job completed within deadline. Using greedy approach:
- Jobs: J1, J2, J3, J4, J5, J6
- Deadlines: 5, 3, 2, 2, 4, 1
- Profits: 200, 180, 190, 300, 120, 100

**IT208-2019-Sept-Supp-INCOMPLETE | Q3(B)**
Solve the given Activity selection problem using greedy approach for the given data:
- ai: 1-9
- Si: 3, 3, 5, 3, 7, 10, 11, 12, 14
- Fi: 5, 6, 8, 10, 11, 12, 13, 13, 17

**IT208-2019-May-End | Q3(B)**
Solve the given Activity selection problem using greedy approach:
- ai: 1-9
- si: 1, 2, 4, 1, 5, 8, 9, 11, 13
- fi: 3, 5, 7, 8, 9, 10, 11, 14, 16

**IT208-ADA-2018-March-Midsem | Q3(B)**
What is the running time of Quicksort when all elements of array A have the same value?

**IT211-2018-May-Endsem | Q2(E)**
Write an algorithm to solve the problem of Selection Activity using recursive method. Also solve following set of activities.

**CO214-ADA-May-2012-End | Q6(b)**
Explain the greedy approach to solve the activity section problem. Give example.

---

### 3.4 Prim's Minimum Spanning Tree Algorithm

**CO208-ADA-2018-August-Supp | Q5(a)**
What is Spanning tree? Explain Prim's Minimum cost spanning tree algorithm with suitable example.

**IT208-2018-May-Endsem | Q2(A)**
Write Kruskal's algorithm. What are its applications? How is it different from Prim's algorithm?

**IT211-2018-August-Supp | Q6(A)**
Write Kruskal's algorithm. What are its applications? How is it different from Prim's algorithm?

---

### 3.5 Kruskal's Minimum Spanning Tree Algorithm

[Note: Kruskal's algorithm questions require graph diagrams, which have been excluded per extraction criteria]

---

### 3.6 Dijkstra's Single Source Shortest Path Algorithm

**CO208-ADA-May-2017-End | Q3(a)**
Write down the Floyd Warshall algorithm and its complexity. Show step by step implementation on given graph.

**IT208-2018-May-Endsem | Q2(B)**
Give the difference between Dijkstra's and Bellman Ford algorithm. Explain using algorithm, example, application and time complexity.

**IT211-2019-May-End | Q4(b)**
State and explain Dijkstra algorithm for solving single-source shortest path problem and discuss its run time complexity. List one shortcoming of the algorithm as compared to one given by Bellman Ford.

**IT211-2018-August-Supp | Q6(B)**
Give the difference between Dijkstra's and Bellman Ford algorithm. Explain using algorithm, example, application and time complexity.

---

### 3.7 Bellman-Ford Algorithm

[Note: Bellman-Ford algorithm questions require graph diagrams, which have been excluded per extraction criteria]

---

### 3.8 Shortest Path - Greedy Method

**IT208-2019-Sept-Supp-INCOMPLETE | Q2(B)**
State single source shortest path problem. Write an algorithm based on greedy method to obtain solution for shortest path problem.

**IT208-2019-May-End | Q2(B)**
State single source shortest path problem. Write an algorithm based on greedy method to obtain solution to shortest path problem. Also discuss how running time is affected by representation of graph.

---

### 3.9 Greedy Method Overview & Divide & Conquer Strategy

**IT208-2018-May-Endsem | Q1(B)**
Describe Greedy Method and Divide & Conquer strategy to find optimal solution to the problem.

**IT211-2019-May-End | Q2(a)**
Explain the divide and conquer strategy. How can we use it to design optimized algorithms?

**CO214-ADA-May-2012-End | Q1(c)**
Greedy approach guarantees to produce optimal solution. True or false? Justify your answer.

# CO208 END TERM EXAMINATION (MAY 2024):

**Q1(e).** Let `G` be a connected undirected graph of 100 vertices and 300 edges. The weight of a minimum spanning tree of `G` is 500. When the weight of each edge of `G` is increased by 5, then what would be the weight of a minimum spanning tree? [CO3][2M]

**Q4(a).** Find the greedy solution for the following job sequencing problem with deadlines with a total number of jobs `n = 7`. [3M][CO3]

| Job S. No | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| Profit | 3 | 5 | 20 | 18 | 1 | 6 | 30 |
| Deadline | 1 | 3 | 4 | 3 | 2 | 1 | 2 |


---

### 3.10 Merge Lists Problem

**CO208-ADA-2019-May-End-SUPP | Q2(a)**
We want to merge n sorted lists L1, L2, ..., Ln of sizes l1, l2, ..., ln. Only merging two sorted lists allowed at any time. Effort of merging two lists of sizes u and v is u+v. Select merging sequence minimizing total effort. Design efficient algorithm. For n=4 lists with sizes 10,20,30,40, find efforts for both sequences.

---

### 3.11 Gas Station Problem

**CO208-ADA-May-2017-End | Q2(b)**
Suppose you were to drive from St. Louis to Denver along I-70. Your gas tank holds enough gas to travel m miles. You have a map with distances between gas stations. Let d₁ < d₂ < ... < dn be locations of gas stations. Distance between neighboring gas stations is at most m miles. Goal is to make as few gas stops as possible. Apply the greedy approach to solve.

---

### 3.12 CD Storage Problem

**CO208-ADA-2019-May-End-SUPP | Q5(b)**
Given sequence of n songs where song i is ti minutes long. Place all songs on ordered series of CDs where each CD holds m minutes. Songs recorded in given order, all included, no song split. Minimize CDs needed. Give most efficient algorithm and analyze time complexity.

---

---

# UNIT 4: DYNAMIC PROGRAMMING & BACKTRACKING
## Contact Hours: 12

### 4.1 Dynamic Programming - Principles & Applications

**CO208-ADA-2019-Sept-Supp | Q7(a)**
Explain the characteristics of a problem that can be solved efficiently using the Dynamic Programming technique.

**CO208-ADA-May-2017-End | Q3(b)**
Consider the recursive algorithm for calculating factorial of an integer n. First analyze time complexity. Then modify to calculate series 1! + 2! + ... + n! without disturbing divide and conquer nature. Transform modified algorithm to bottom up dynamic programming. Compare algorithms.

**SE214-2019-May-End | Q7(a)**
Explain the characteristics of a problem that can be solved efficiently using Dynamic programming technique.

**IT208-2018-May-Endsem | Q5(A)**
Define the following terms:
- i. Polynomial Time
- ii. Space Vs Time complexity of an algorithm
- iii. NP-Complete Problems
- iv. Deterministic and Non Deterministic Algorithm

### Unit 4: Dynamic Programming & Backtracking
# CO208 END TERM EXAMINATION (MAY 2024)

**Q2(a).** How can the backtracking algorithm be optimized for solving the 8-queen problem, and what are the key steps involved in implementing this algorithm to ensure that no two queens attack each other on an 8x8 chessboard? [CO5][5M]

**Q3(a).** Rod Cutting Problem: We are given a rod of size `N`. It can be cut into pieces. Each length of a piece has a particular price given by the price array. Our task is to find the maximum revenue that can be generated by selling the rod after cutting (if required) into pieces. You are given a rod of 8 metres in length. Below is a table detailing the prices:
| Length | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
|---|---|---|---|---|---|---|---|---|
| Price | 1 | 5 | 8 | 9 | 10 | 17 | 17 | 20 |

Solve this problem using dynamic programming strategy. Determine the maximum profit. [CO5][6M]

**Q3(b).** Perform the matrix chain multiplication using the dynamic programming approach. Given four matrices A, B, C and D with order `40x20`, `20x30`, `30x10`, and `10x30`, respectively. Find the minimum number of multiplications required to produce the output. [CO5][4M]

**Q5(a).** Tower of Hanoi is a mathematical puzzle with three rods (S, D, T) and n disks.

i). Write a recursive code to move all `n` disks from S (source) to D (destination).

ii). Write the recurrence relation for the recursive code and solve it. Discuss the time complexity for Tower of Hanoi.

iii). How many moves are required to move `n` disks from S to D. [6M][CO3]


---

### 4.2 Longest Common Subsequence (LCS) - Dynamic Programming

**CO208-ADA-2019-Sept-Supp | Q3(a)**
Determine the LCS of <A,B,B,A,B,A,B,A> and <B,A,B,A,A,B,A,A,B> using dynamic programming. Write algorithm and runtime complexity.

**CO208-ADA-2018-May-Endsem | Q2(b)**
Compute the LCS for sequences X = <A,B,C,B,D,A,B,C,D> and Y = <B,A,C,A,D,B,C,A,A,A> using a dynamic programming algorithm and show mathematical formulation.

**CO214-ADA-2018-August-Supp | Q3(a)**
Determine LCS of <A,C,G,G,T,T,A> and <C,G,T,A,T> using dynamic programming. Write algorithm and runtime complexity.

**CO214-ADA-2018-May-Endsem | Q3(a)**
Determine LCS of <A,B,C,B,D,B,A> and <B,D,C,A,B,A> using dynamic programming. Write algorithm and runtime complexity.

**CO214-ADA-May-2012-End | Q4(a)**
Given two sequences S = ABADZBC and T = BACBAD, find maximum length common subsequence using dynamic programming.

**CO214-ADA-May-2016-End | Q3(b)**
Write Longest Common subsequence Algorithm. Apply same to find LCS for sequences "AGGTAB" and "GXTXAYB".

**IT208-ADA-2018-March-Midsem | Q3(B)**
What is the running time of Quicksort when all elements of array A have the same value?

**IT211-2018-May-Endsem | Q4**
Write algorithm to find LCS using dynamic programming and find LCS of strings abcdef and acbcf.

**IT211-2019-May-End | Q2(b)**
Write an algorithm for finding the length of the longest common subsequence and show why it would generate an optimal solution.

**SE214-2019-May-End | Q3(a)**
Determine LCS of <A,B,B,A,B,A,B,A> and <B,A,B,A,A,B,A,A,B> using dynamic programming. Write algorithm and runtime complexity.

**IT208-2019-May-End | Q4(B)**
Solve longest common subsequence using DP where x="abcbcad" and y="bacdcd".

**CO208-ADA-2018-August-Supp | Q2(b)**
Compute LCS for sequences: X = "AGGTAB" and Y = "GXTXAYB" using dynamic programming. Show mathematical formulation.

**CO208-ADA-2019-May-End-SUPP | Q2(b)**
Compute LCS for: X = "PMJYAUZ" and Y = "MZJAWPU" using dynamic programming. Show mathematical formulation.

---

### 4.3 0/1 Knapsack - Dynamic Programming

**CO214-ADA-2018-August-Supp | Q2(b)**
Solve 0/1 Knapsack problem using dynamic programming for W=5:
- Item: 1, 2, 3, 4
- Weight: 2, 1, 3, 2
- Value: 12, 10, 20, 15

**CO214-ADA-2018-May-Endsem | Q2(b)**
Solve 0/1 Knapsack problem using dynamic programming for W=16:
- Item: 1, 2, 3, 4
- Weight: 4, 7, 5, 3
- Value: 40, 42, 25, 12

**CO208-ADA-2018-August-Supp | Q1(b)**
Solve 0/1 Knapsack problem using Dynamic Programming:
- Item: 1, 2, 3, 4
- Weight: 4, 7, 5, 3
- Value: 40, 42, 25, 12

**CO208-ADA-2019-May-End-SUPP | Q1(c)**
Solve 0/1 Knapsack problem using Dynamic Programming for m=25:
- Item: 1, 2, 3, 4
- Weight: 9, 8, 12, 14
- Value: 10, 12, 14, 16

---

### 4.4 Matrix Chain Multiplication - Dynamic Programming

**CO208-ADA-May-2017-End | Q2(b)**
[Referenced in CO208-ADA-2018-August-Supp | Q5(b)]
Given chain of four matrices A1, A2, A3, A4 with dimensions (15x4), (4x6), (6x12), (12x5). Fill table in bottom-up fashion and give solution to problem.

**IT211-2019-May-End | Q1(a)**
State and apply the matrix chain multiplication algorithm to predict optimal order of parenthization for chain A1.A2.A3.A4
- Dimensions: A1(3X2), A2(2X3), A3(3X3), A4(3X2)

**CO214-ADA-May-2012-End | Q4(b)**
Given sequence of 3 matrices A1, A2, A3 with dimensions Po=3, P₁ =1, P2=2, P3=1. What are m array and S array? Also construct optimal parenthesization.

**CO214-ADA-May-2016-End | Q2(b)**
Discuss optimal substructure and overlapping sub problem w.r.t Matrix Chain Multiplication problem. Also write memoized solution.

---

### 4.5 Longest Increasing Subsequence (LIS)

**CO208-ADA-2018-May-Endsem | Q2(a)**
For the Longest Increasing Subsequence (LIS) problem, apply Dynamic Programming. Mention pseudo-code, complexity, overlapping subproblems, and optimal substructure.

---

### 4.6 Longest Palindrome Subsequence

**CO208-ADA-March-2017-Mid | Q3**
Given problem of finding Longest Palindrome Subsequence. Find optimal sub-structure, explain with example. Show graphically how recursive implementation leads to overlapping sub problems.

---

### 4.7 Floyd-Warshall - All Pair Shortest Paths

**CO208-ADA-May-2017-End | Q3(a)**
Write down the Floyd Warshall algorithm and its complexity. Show step by step implementation on given graph.

**CO214-ADA-May-2012-End | Q6(a)**
Illustrate an algorithm that efficiently solves all pair shortest path problem.

---

### 4.8 Rod Cutting Problem

[Note: Rod cutting problem requires detailed table construction which may be graph/diagram-based in some exam papers]

---

### 4.9 Travelling Salesman Problem - Dynamic Programming

**CO208-ADA-May-2017-End | Q4(a)**
How is the dynamic programming solution of the travelling salesman problem better than the naïve algorithm? Discuss with example. Also derive and compare their complexity.

**IT208-2018-May-Endsem | Q3(B)**
Discuss Branch & Bound strategy by solving TSP problem for any graph and analyze time complexity.

**IT208-2019-May-End | Q4(A)**
Explain Dynamic Programming method to solve the travelling salesman problem with given distance matrix.

**IT208-2019-Sept-Supp-INCOMPLETE | Q4(A)**
Explain Dynamic Programming method to solve the travelling salesman problem with given distance matrix (3x3).

---

### 4.10 Backtracking - N-Queens Problem

**CO208-ADA-2019-Sept-Supp | Q4(a)**
Define the backtracking phenomenon. Write pseudocode for solving the n-queens problem with the help of backtracking.

**CO208-ADA-2018-May-Endsem | Q7(a)**
Write an algorithm for solving the 8-queens problem.

**CO208-ADA-May-2017-End | Q5(b)**
Define backtracking phenomenon. Cut state space for 4-queen problem by applying backtracking. Mention how you take care of diagonal constraint in implementation.

**CO208-ADA-2018-August-Supp | Q4(a)**
What is backtracking? Give explicit and implicit constraints in 8 queen's problem.

**SE214-2019-May-End | Q4(a)**
Define backtracking phenomenon? Write pseudo code for solving n-queen problem with help of back tracking.

**SE214-2019-May-End | Q4(b)**
Define the following: 1. FIFO Branch and Bound, 2. LIFO Branch and Bound, 3. Least cost search

**IT208-ADA-2018-March-Midsem | Q3(C)**
Use the substitution method to prove that recurrence T(n)= T(n-1)+(n) has solution T(n)= Θ(n²).

**IT208-2018-May-Endsem | Q6(A)**
Explain backtracking concept. Illustrate N queens problem using backtracking to solve 4-queens problem.

**IT211-2018-August-Supp | Q5(A)**
Explain backtracking concept. Illustrate N queen's problem using backtracking to solve 4-queen's problem.

**CO214-ADA-May-2016-End | Q5(a)**
Draw the full state space for 4-queen problem. Explain LIFO branch and bound, FIFO branch and bound, LC branch and bound terminologies and draw new state space for each.

**CO214-ADA-May-2016-End | Q5(b)**
Define backtracking phenomenon? Write pseudo code for solving n-queen problem with help of back tracking.

---

### 4.11 Backtracking - Subset Sum Problem

**CO208-ADA-2018-August-Supp | Q8(a)**
Solve subset problem using backtracking: S={3,5,6,7}, d=15.

**CO208-ADA-2019-May-End-SUPP | Q8(a)**
Solve subset problem using backtracking: S = {3,5,6,7}, d=15.

**IT208-ADA-2018-March-Midsem | Q3(B)**
What is the running time of Quicksort when all elements of array A have the same value?

**IT208-2018-May-Endsem | Q6(B)**
Solve the subset sum problem for S={3, 5, 6, 7} and d=15. Construct a space state tree.

**IT211-2018-August-Supp | Q5(B)**
Solve the subset sum problem for S={3, 5, 6, 7} and d=15. Construct a space state tree.

**CO214-ADA-May-2012-End | Q3(a)**
What is back tracking approach of problem solving? Write backtracking algorithm for n-queen problem with example.

---

### 4.12 Backtracking - Hamiltonian Cycle

**CO208-ADA-2018-August-Supp | Q4(b)**
What is Hamiltonian Cycle? Explain how to find Hamiltonian path and cycle using backtracking algorithm.

---

---

# UNIT 5: BRANCH AND BOUND
## Contact Hours: 6

### 5.1 LC Branch and Bound - Definition & Strategy

**CO208-ADA-May-2017-End | Q5(a)**
What is LC branch and bound? Apply LC search on 0/1 knapsack problem with capacity 12 kg and items: (weight,value) = {(4,10), (6,15), (3,6), (5,8), (2,4)}

**CO208-ADA-2019-Sept-Supp | Q4(b)**
Define the following: 1. FIFO Branch and Bound, 2. LIFO Branch and Bound, 3. Least cost search

**SE214-2019-May-End | Q4(b)**
Define the following:
- 1. FIFO Branch and Bound
- 2. LIFO Branch and Bound
- 3. Least cost search

---

### 5.2 Branch and Bound - 0/1 Knapsack Problem

**CO208-ADA-2019-May-End-SUPP | Q4(a)**
Solve 0/1 Knapsack problem using branch and bound technique with W=10:
- Item: 1, 2, 3, 4, 5
- Weight: 2, 3, 1, 5, 3
- Value: 40, 50, 100, 95, 30

**IT208-2019-May-End | Q5(A)**
What is 0/1 Knapsack Problem. Solve this problem using Branch and bound method using suitable example.

---

### 5.3 Branch and Bound - TSP Problem

**IT208-2018-May-Endsem | Q3(B)**
Discuss Branch & Bound strategy by solving TSP problem for any graph and analyze time complexity.

**IT211-2018-August-Supp | Q1(D)**
Discuss Branch & Bound strategy by solving TSP problem for any graph and analyze time complexity.

**CO214-ADA-May-2016-End | Q4(a)**
State and describe Travelling salesman problem. Solve TSP using branch and bound by constructing state space diagram.

**IT211-2019-May-End | Q3(b)**
Compare and contrast different approaches to solve the travelling salesman Problem.

---

### 5.4 FIFO and LIFO Branch and Bound

**CO214-ADA-May-2016-End | Q5(a)**
Draw the full state space for 4-queen problem. Explain:
- (i) LIFO branch and bound
- (ii) FIFO branch and bound
- (iii) LC branch and bound

---

### 5.5 Difference between Backtracking and Branch & Bound

**CO208-ADA-2019-May-End-SUPP | Q6(b)**
Differentiate between "backtracking" and "branch and bound" strategies.

---
# CO208 END TERM EXAMINATION (MAY 2024) | Q1(d)** 
How does the use of pruning techniques help reduce the search space and improve the efficiency of branch and bound algorithms? [CO6][2M]
---

# UNIT 6: COMPUTATIONAL COMPLEXITY - P, NP, NP-HARD, NP-COMPLETE
## Contact Hours: 6

### 6.1 Complexity Classes - P, NP, NP-Hard, NP-Complete

**CO208-ADA-May-2017-End | Q7(a)**
Write short notes on: (i) P class, (ii) NP class, (iii) NP complete class

**CO214-ADA-2018-August-Supp | Q6**
Write short notes on:
- (i) P and NP class
- (ii) NP-Hard problems
- (iii) Reducibility
- (iv) Big-oh
- (v) Stable sorting
- (vi) Master's Theorem
- (vii) Vertex Cover Problem

**CO214-ADA-2018-May-Endsem | Q6**
Write short notes on:
- (i) NP class
- (ii) NP complete class
- (iii) Circuit Satisfiability
- (iv) Big-oh
- (v) Big-omega
- (vi) Big-theta
- (vii) Vertex Cover Problem

**CO214-ADA-May-2012-End | Q1(d)**
What are NP complete problems?

**CO214-ADA-May-2012-End | Q7(a)**
Write short notes on: P class, NP class, NP complete class

**IT208-2018-May-Endsem | Q5(A)**
Define the following terms:
- i. Polynomial Time
- ii. Space Vs Time complexity of an algorithm
- iii. NP-Complete Problems
- iv. Deterministic and Non Deterministic Algorithm

**IT208-2018-August-Supp | Q3(A)**
Define the following terms:
- i. Polynomial Time
- ii. Non-polynomial Time
- iii. NP-Hard Problems
- iv. NP-Complete Problems

**IT211-2018-May-Endsem | Q6(A)**
Define the following terms:
- Polynomial Time
- Non-polynomial Time
- NP-Hard Problems
- NP-Complete Problems

**IT208-2019-May-End | Q6(A)**
Write short notes on following:
- 1) Cook's Theorem
- 2) NP Hard and NP Complete problem
- 3) Draw the venn diagram representing P, NP and NP Complete problem

**SE214-2019-May-End | Q6**
Write short notes on:
- (i) Big-oh
- (ii) Big-omega
- (iii) Big-theta
- (iv) NP-Complete Problems

**CO214-ADA-May-2016-End | Q7(a)**
Write short notes on: P class, NP class, NP complete class

---

### 6.2 NP-Complete Problems - Examples

**CO208-ADA-2018-May-Endsem | Q6(b)**
What are NP-Complete problems? Give an example of one NP-Complete problem.

**CO208-ADA-2019-May-End-SUPP | Q7(a)**
Prove vertex cover problem is NP-complete.

**CO208-ADA-2019-May-End-SUPP | Q7(b)**
Prove CNF-satisfiability reduces to clique decision problem.

---

### 6.3 Vertex Cover Problem

**CO208-ADA-May-2017-End | Q7(b)**
Write down approximate solution for vertex cover problem. Apply same on given graph and explain complexity.

**IT208-2018-May-Endsem | Q5(B)**
What is the Vertex-cover problem and explain it with suitable example.

**IT208-2018-August-Supp | Q3(B)**
Write an algorithm to solve the Vertex-cover problem.

**IT211-2018-May-Endsem | Q6(B)**
What is the Vertex-cover problem and explain it with suitable example.

**CO214-ADA-May-2012-End | Q7(b)**
Explain the vertex cover problem and travelling salesman problem.

**CO214-ADA-May-2016-End | Q7(b)**
Describe vertex cover problem? Prove that vertex cover problem is NP-complete. Also design approximate solution.

---

### 6.4 Approximation Algorithms

**CO214-ADA-2018-August-Supp | Q4(b)**
Explain concept of Approximation algorithms. Write approximation algorithm for NP-Hard problem.

**CO214-ADA-2018-May-Endsem | Q4(b)**
Explain concept of Approximation algorithms. Write approximation algorithm for NP-Hard problem.

---

### 6.5 Circuit Satisfiability & SAT Problems

[Circuit Satisfiability mentioned in syllabus and exam notes but covered under NP-Complete theory]

---

### 6.6 NP-Hardness & Reducibility

**CO214-ADA-2018-August-Supp | Q6**
Write short notes on: Reducibility

**IT208-2019-May-End | Q6(B)**
Prove that travelling salesman's problem is NP Hard problem.

---

### 6.7 String Matching Algorithms

**IT208-2018-May-Endsem | Q5(B)**  
What is the Vertex-cover problem and explain it with suitable example.

**IT208-2018-August-Supp | Q5(B)**
Explain Naïve and Rabin Karp string matching algorithms in details.

**IT211-2018-August-Supp | Q2(B)**
Naïve and Rabin Karp string matching algorithms.

**CO208-ADA-May-2017-End | Q6(a)**
Explain Rabin-karp algorithm for string matching using example. Analyze its runtime complexity.

**IT211-2019-May-End | Q3(a)**
State naive string matching algorithm and show the comparisons the naïve string matcher makes for pattern P=0001 in text T=000010001010001.

**IT211-2019-May-End | Q7(a)**
Write short notes on:
- iv) Rabin Karp String matching algorithm

---

### 6.8 Euclid's GCD Algorithm

**IT211-2019-May-End | Q6(a), Q6(b)**
- Find the greatest common divisor of 1370 and 880 using Euclid algorithm.
- Explain Extended Euclid's algorithm for GCD and its use in RSA cryptosystem.

**IT211-2018-August-Supp | Q3(B)**
Explain Euclid's GCD algorithm in details.

**IT211-2018-May-Endsem | Q5(A)**
Explain following algorithms in details: Euclid's GCD algorithm.

---



## Total Questions by Unit:
- **Unit 1:** ~55+ questions
- **Unit 2:** ~41+ questions
- **Unit 3:** ~50+ questions
- **Unit 4:** ~62+ questions
- **Unit 5:** ~17+ questions
- **Unit 6:** ~35+ questions

*Grand Total: 215+ questions organized by syllabus unit*

---

*50+ questions across all papers requiring graph diagrams, matrix visualizations, or state space trees have been excluded from this compilation.*


