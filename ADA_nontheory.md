### **Table 1: Non-Graph Questions (with data)**

| S.No. | Unit   | PDF Source                  | Q.No  | Problem Data / Description                                                                                                                                                                                                                                                                                                                              |
| ----- | ------ | --------------------------- | ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | Unit 2 | DAA End Sem May 2024        | Q1(a) | Quick Sort Probability:
An array of 50 distinct elements is to be sorted using quicksort. Assume that the pivot element is chosen uniformly at random. Find the probability that the pivot element gets placed in theworst possible locationin the first round of partitioning.                                                                         |
| 2     | Unit 2 | DAA End Sem May 2024        | Q1(c) | Time Complexity:
What is the order of the return value ofkproduced by the following function:
int foo(int n) {
int i, j, k = 0;
for (i = n/2; i <= n; i++)
for (j = 2; j <= n; j = j * 2)
k = k + n/2;
return k;
}                                                                                                                                      |
| 3     | Unit 2 | DAA End Sem May 2024        | Q2(b) | Merge k Sorted Arrays:
You are givenksorted integer arrays (each array of sizen) in the form of a 2D integer matrix of sizek x n. Write an optimised algorithm to merge them into a single array. Discuss time and space complexity.
Example:Input:k = 3, n = 4.
Array ={ {1, 3, 5, 7}, {2, 4, 6, 8}, {0, 9, 10, 11} }
Output:0 1 2 3 4 5 6 7 8 9 10 11 |
| 4     | Unit 2 | CO208-ADA-2018-May-Endsem   | Q4(a) | Min/Max (Divide & Conquer):
Apply the pseudo code to find the minimum and maximum of the elements:
{28, 60, 72, 56, 18, 69, 21, 95, 31, 17, 23, 90, 70, 44, 52, 24}                                                                                                                                                                                     |
| 5     | Unit 2 | CO208-ADA-2018-August-Supp  | Q8(b) | Heap Sort:
Consider following unsorted arrayA[] = {24, 12, 8, 17, 11, 76, 32, 54, 9, 23, 44}. Convert this array into a MAXHEAP. Show output in tree and array form. Now apply remaining part of heap sort algorithm and show array/tree content after every round (deleteMax).                                                                         |
| 6     | Unit 2 | CO214-ADA-May-2016-End      | Q6(b) | Heap Sort:
For the array:15, 19, 10, 7, 17, 6perform Heap-Sort operation on it. Write all the algorithms involved in it.                                                                                                                                                                                                                                |
| 7     | Unit 2 | SE214-2019-May-End          | Q2(b) | Binary Search:
Write down recursive binary-search algorithm and apply the same to find the value2in the following array:1, 2, 3, 4, 5, 6, 7, 8, 9, 10.                                                                                                                                                                                                  |
| 8     | Unit 2 | IT211-2018-May-Endsem       | Q1(A) | Recursive Insertion Sort:
Insertion Sort can be expressed as a recursive procedure as follows. In order to sortA[1...n], we recursively sortA[1...n-1]and then insertA[n]into the sorted arrayA[1...n-1]. Write a pseudocode of this recursive procedure.                                                                                               |
| 9     | Unit 3 | DAA End Sem May 2024        | Q1(e) | MST Property:
LetGbe a connected undirected graph of 100 vertices and 300 edges. The weight of a minimum spanning tree ofGis 500. When the weight of each edge ofGis increased by 5, then what would be the weight of a minimum spanning tree?                                                                                                          |
| 10    | Unit 3 | DAA End Sem May 2024        | Q4(a) | Job Sequencing (Greedy):
Find the greedy solution for the following job sequencing problem with deadlines.n = 7.
Job S.No:1, 2, 3, 4, 5, 6, 7
Profit:3, 5, 20, 18, 1, 6, 30
Deadline:1, 3, 4, 3, 2, 1, 2                                                                                                                                                |
| 11    | Unit 3 | CO208-ADA-2018-March-Midsem | Q5    | Frog Jump (Greedy):
Positions:{0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
Max Jumpr = 3. The frog begins at 0. Its goal is to get to position 10. Minimize jumps.                                                                                                                                                                                                |
| 12    | Unit 3 | CO208-ADA-2019-May-End-SUPP | Q5(a) | Huffman Coding:
Probability of occurrence:A:0.10, B:0.18, C:0.40, D:0.05, E:0.06, F:0.10, G:0.07, H:0.04. Find Huffman encoding and compute average code length.                                                                                                                                                                                        |
| 13    | Unit 3 | IT211-2018-May-Endsem       | Q2(D) | Huffman Coding:
Construct Huffman code. Encode following characters:A:37, B:18, C:29, D:13, E:30, F:17, G:6. Find percentage of bits saved vs 3-bit fixed length.                                                                                                                                                                                       |
| 14    | Unit 3 | IT208-2018-August-Supp      | Q2(B) | Huffman Coding:
Probabilities (in percentage):A:30, B:40, C:6, D:10, E:15, F:4. Find the binary Huffman code.                                                                                                                                                                                                                                           |
| 15    | Unit 3 | IT211-2018-August-Supp      | Q2(A) | Huffman Coding:
Probabilities (in percentage):A:30, B:40, C:6, D:10, E:15, F:4. Find the binary Huffman code.                                                                                                                                                                                                                                           |
| 16    | Unit 3 | CO214-ADA-May-2012-End      | Q3(b) | Huffman Coding:
Probabilities:a:45, b:13, c:12, d:16, e:9, f:5. Build a binary tree according to greedy strategy.                                                                                                                                                                                                                                       |
| 17    | Unit 3 | IT208-2018-August-Supp      | Q5(A) | Knapsack (Greedy vs 0/1):
Solve forW=18Kg.
Items (Weight, Value):A(10,100), B(7,63), C(8,56), D(4,12), E(6,34).                                                                                                                                                                                                                                         |
| 18    | Unit 3 | IT208-2019-May-End          | Q3(A) | Fractional Knapsack:
Knapsack capacityW=20.
Items (Weight, Profit):1:(18,30), 2:(15,21), 3:(10,18).                                                                                                                                                                                                                                                     |
| 19    | Unit 3 | IT208-2019-Sept-Supp        | Q3(A) | Fractional Knapsack:
Knapsack capacityW=22.
Items (Weight, Profit):1:(20,32), 2:(17,23), 3:(12,20).                                                                                                                                                                                                                                                     |
| 20    | Unit 3 | IT211-2018-May-Endsem       | Q2(E) | Activity Selection:
Solve set of activities (Si, Fi):
(3,4), (0,5), (5,6), (3,7), (5,9), (6,9), (8,10), (8,11), (2,12), (12,16).                                                                                                                                                                                                                        |
| 21    | Unit 3 | IT208-2019-May-End          | Q3(B) | Activity Selection:
Activities (Si, Fi):
(1,3), (2,5), (4,7), (1,8), (5,9), (8,10), (9,11), (11,14), (13,16).                                                                                                                                                                                                                                           |
| 22    | Unit 3 | IT208-2019-Sept-Supp        | Q3(B) | Activity Selection:
Activities (Si, Fi):
(3,5), (3,6), (5,8), (3,10), (7,11), (10,12), (11,13), (12,13), (14,17).                                                                                                                                                                                                                                       |
| 23    | Unit 4 | DAA End Sem May 2024        | Q3(a) | Rod Cutting (DP):
Rod lengthN=8. Prices for lengths1..8:[1, 5, 8, 9, 10, 17, 17, 20]. Determine the maximum profit.                                                                                                                                                                                                                                     |
| 24    | Unit 4 | DAA End Sem May 2024        | Q3(b) | Matrix Chain Multiplication:
Given four matricesA(40x20),B(20x30),C(30x10), andD(10x30). Find the minimum number of multiplications required.                                                                                                                                                                                                           |
| 25    | Unit 4 | CO208-ADA-2018-May-Endsem   | Q5(b) | Matrix Chain Multiplication:
Chain of four matricesA1(5x4), A2(4x6), A3(6x2), A4(2x7). Fill the table in bottom-up fashion and give solution.                                                                                                                                                                                                           |
| 26    | Unit 4 | IT211-2019-May-End          | Q1(a) | Matrix Chain Multiplication:
Matrices:A1(3x2), A2(2x3), A3(3x3), A4(3x2). Predict optimal order of parenthesization.                                                                                                                                                                                                                                    |
| 27    | Unit 4 | CO214-ADA-May-2012-End      | Q4(b) | Matrix Chain Multiplication:
Dimensions arrayP:[3, 1, 2, 1]. (i.e.,A1(3x1), A2(1x2), A3(2x1)). Construct m-array and s-array.                                                                                                                                                                                                                           |
| 28    | Unit 4 | IT208-2018-May-Endsem       | Q1(C) | Strassen's Matrix Multiplication:
Evaluate the optimal parenthesis ofP = <4, 3, 5, 2, 6, 2>.                                                                                                                                                                                                                                                            |
| 29    | Unit 4 | IT208-2019-May-End          | Q4(A) | TSP (DP):
Solve TSP for distance matrix:
[0, 10, 15, 20]
[5, 0, 9, 10]
[6, 13, 0, 12]
[8, 8, 9, 0]                                                                                                                                                                                                                                                      |
| 30    | Unit 4 | SE214-2019-May-End          | Q3(b) | TSP (DP):
Distance Matrix (Same as above):
[0, 10, 15, 20]
[5, 0, 9, 10]
[6, 13, 0, 12]
[8, 8, 9, 0]                                                                                                                                                                                                                                                    |
| 31    | Unit 4 | IT208-2019-Sept-Supp        | Q4(A) | TSP (DP):
Distance Matrix (Reconstructed):
[0, 12, 17, 22]
[6, 0, 10, 11]
[7, 15, 0, 14]
[9, 10, 10, 0]                                                                                                                                                                                                                                                 |
| 32    | Unit 4 | IT211-2018-May-Endsem       | Q4    | LCS (Longest Common Subsequence):
Find LCS of stringsabcdefandacbcf.                                                                                                                                                                                                                                                                                    |
| 33    | Unit 4 | IT208-2018-May-Endsem       | Q4(B) | LCS:
Find LCS of stringsabcdefandacbcf.                                                                                                                                                                                                                                                                                                                 |
| 34    | Unit 4 | IT208-2019-May-End          | Q4(B) | LCS:
Find LCS of stringsabcbcadandbacdcd.                                                                                                                                                                                                                                                                                                               |
| 35    | Unit 4 | SE214-2019-May-End          | Q3(a) | LCS:
Find LCS of<A,B,B,A,B,A,B,A>and<B,A,B,A,A,B,A,A,B>.                                                                                                                                                                                                                                                                                                |
| 36    | Unit 4 | CO214-ADA-May-2016-End      | Q4(b) | LCS:
Find LCS forAGGTABandGXTXAYB.                                                                                                                                                                                                                                                                                                                      |
| 37    | Unit 4 | CO214-ADA-May-2012-End      | Q4(a) | LCS:
Find LCS ofABADZBCandBACBAD.                                                                                                                                                                                                                                                                                                                       |
| 38    | Unit 4 | CO208-ADA-May-2017-End      | Q4(b) | General DP (Probability):
Two teams A/B.p= prob A wins a game. Letp(i,j)= prob A wins series needingiwins vs B needingjwins. Write recurrence.                                                                                                                                                                                                          |
| 39    | Unit 5 | IT208-2018-May-Endsem       | Q6(B) | Subset Sum:
Solve forS={3, 5, 6, 7}and targetd=15.                                                                                                                                                                                                                                                                                                      |
| 40    | Unit 5 | IT211-2018-August-Supp      | Q5(B) | Subset Sum:
Solve forS={3, 5, 6, 7}and targetd=15.                                                                                                                                                                                                                                                                                                      |

***

### **Table 2: Graph Diagram Questions (Images)**
*These questions rely on visual diagrams in the PDFs.*

| S.No. | Unit | PDF Source | Q.No | Topic / Algorithm |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Unit 3** | **DAA End Sem May 2024** | **Q4(b)** | **Bellman-Ford:** Source `A`. Show intermediate steps. |
| 2 | **Unit 3** | **CO208-Mid-2023** | **Q5** | **Prim's:** Find MST starting from `v6`. |
| 3 | **Unit 3** | **CO208-ADA-2018-March-Midsem** | **Q4** | **Prim's:** Construct MST showing steps. |
| 4 | **Unit 3** | **IT208-ADA-2018-March-Midsem** | **Q4** | **Prim's / Kruskal's:** Find MST cost for `Fig. 1`. |
| 5 | **Unit 3** | **CO208-ADA-2018-August-Supp** | **Q6(a)** | **Kruskal's:** Find MST. |
| 6 | **Unit 3** | **CO208-ADA-2018-May-Endsem** | **Q6(a)** | **Kruskal's:** Find MST. |
| 7 | **Unit 3** | **IT211-2018-May-Endsem** | **Q3(C)** | **Prim's:** Find MST cost & pseudocode. |
| 8 | **Unit 3** | **IT211-2018-May-Endsem** | **Q3(D)** | **Kruskal's:** Find MST cost & pseudocode. |
| 9 | **Unit 3** | **IT211-2019-May-End** | **Q5(a)** | **Kruskal's:** Apply to graph. |
| 10 | **Unit 3** | **IT208-2018-August-Supp** | **Q4(B)** | **Prim's:** Find MST. |
| 11 | **Unit 3** | **IT211-2018-August-Supp** | **Q4(B)** | **Prim's:** Find MST. |
| 12 | **Unit 3** | **CO214-ADA-May-2012-End** | **Q5(b)** | **Kruskal's:** Find MST. |
| 13 | **Unit 3** | **CO208-ADA-2020-March-Mid** | **Q4** | **Dijkstra's:** Source `S`. |
| 14 | **Unit 3** | **CO208-ADA-2019-Sept-Supp** | **Q5(a)** | **Dijkstra's:** Source `A`. |
| 15 | **Unit 3** | **CO208-ADA-2019-May-End-SUPP** | **Q6(a)** | **Dijkstra's:** Source `a`. |
| 16 | **Unit 3** | **CO214-ADA-2018-August-Supp** | **Q5(a)** | **Dijkstra's:** Source `A`. |
| 17 | **Unit 3** | **CO214-ADA-2018-May-Endsem** | **Q5(a)** | **Dijkstra's:** Source `1`. |
| 18 | **Unit 3** | **IT208-2018-August-Supp** | **Q4(A)** | **Dijkstra's:** Shortest path from `A`. |
| 19 | **Unit 3** | **IT211-2018-August-Supp** | **Q4(A)** | **Dijkstra's:** Shortest path from `A`. |
| 20 | **Unit 3** | **SE214-2019-May-End** | **Q5(a)** | **Dijkstra's:** Source `A`. |
| 21 | **Unit 3** | **CO214-ADA-May-2012-End** | **Q5(c)** | **Shortest Path:** From `V1` to `V7`. |
| 22 | **Unit 3** | **CO208-ADA-2019-Sept-Supp** | **Q5(b)** | **Bellman-Ford:** Implementation steps. |
| 23 | **Unit 3** | **CO214-ADA-2018-August-Supp** | **Q5(b)** | **Bellman-Ford:** Source `z`. |
| 24 | **Unit 3** | **CO214-ADA-2018-May-Endsem** | **Q5(b)** | **Bellman-Ford:** Implementation steps. |
| 25 | **Unit 3** | **CO214-ADA-May-2016-End** | **Q3(a)** | **Bellman-Ford:** Source `A`. |
| 26 | **Unit 3** | **SE214-2019-May-End** | **Q5(b)** | **Bellman-Ford:** Implementation steps. |
| 27 | **Unit 3** | **CO208-ADA-May-2017-End** | **Q7(b)** | **Vertex Cover:** Approx solution. |
| 28 | **Unit 4** | **CO208-ADA-2019-Sept-Supp** | **Q3(b)** | **TSP (DP):** Solve using DP. |
| 29 | **Unit 4** | **CO208-ADA-May-2017-End** | **Q3(a)** | **Floyd-Warshall:** Steps. |
| 30 | **Unit 4** | **CO208-ADA-2018-May-Endsem** | **Q7(b)** | **Floyd-Warshall:** All pair shortest path. |
| 31 | **Unit 4** | **IT208-2018-August-Supp** | **Q2(A)** | **Floyd-Warshall:** All pair shortest path. |
| 32 | **Unit 4** | **IT211-2018-August-Supp** | **Q3(A)** | **Floyd-Warshall:** All pair shortest path. |
