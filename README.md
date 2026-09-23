# DAA-practical01-8847

A comprehensive repository for the Design and Analysis of Algorithms (DAA) course. This collection contains practical implementations and explanations of essential algorithms used in computer science.

## **Practical 001 — Sorting Algorithms**

This practical explores the fundamental sorting algorithms that form the backbone of computer science. You'll learn how different sorting techniques work, their strengths and weaknesses, and when to use each one effectively.

### Bubble Sort

Bubble Sort is one of the most intuitive sorting algorithms, often the first one taught to beginners. It works by repeatedly stepping through the list, comparing adjacent elements, and swapping them if they are in the wrong order.

### Selection Sort

Selection Sort works by dividing the array into two parts: the sorted portion (at the beginning) and the unsorted portion (the rest). The algorithm repeatedly finds the minimum element from the unsorted part and moves it to the end of the sorted portion.

### Insertion Sort

Insertion Sort builds the sorted array one element at a time by inserting each new element into its correct position within the already-sorted portion. It works similarly to how people organize playing cards in hand.

### Merge Sort

Merge Sort is a divide-and-conquer algorithm. It recursively divides the array into two halves until single-element arrays are reached, then merges the sorted halves back together in sorted order.

### Quick Sort

Quick Sort selects a pivot element and partitions the array so that elements less than the pivot come before it and greater elements come after. It then recursively sorts the partitions.

### Linear Search

Linear Search scans through a list sequentially until the target element is found or the list ends. This algorithm works on both sorted and unsorted data.

### Binary Search

Binary Search is an efficient algorithm that finds a target in a sorted array by repeatedly dividing the search interval in half.

### Max-Heap Sort (Heap Sort)

Heap Sort leverages the heap data structure to achieve efficient sorting. A heap is a complete binary tree with the heap property: in a max-heap, every parent node is greater than or equal to its children.

---

## **Practical 002 — Searching: Linear and Binary Search**

This practical demonstrates two essential search techniques and compares their effectiveness. You'll understand the fundamental difference between brute-force searching and smart searching, and learn when each algorithm is appropriate.

### Linear Search: Understanding Sequential Search

Linear Search is the most fundamental search algorithm: examine elements one by one until the target is found. Time complexity is O(n).

### Binary Search: The Power of Divide and Conquer

Binary Search dramatically outperforms Linear Search for sorted data by halving the search space each step. Time complexity is O(log n).

### Comparing Performance: Linear vs. Binary Search

On small datasets the performance difference is negligible, but for large sorted datasets Binary Search is vastly superior (O(log n) vs O(n)).

---

## **Practical 003 — Max-Heap Sort Algorithm**

This practical provides an in-depth exploration of heap-based sorting. You'll understand how heap data structures work and how they can be leveraged to create an efficient, in-place sorting algorithm.

### Understanding the Heap Data Structure

A heap is a specialized tree-based data structure that satisfies the heap property. In a max-heap, every parent node has a value greater than or equal to its children, and the largest element is at the root.

### The Heapify Operation: Maintaining Heap Property

Heapify fixes violations of the heap property by sifting elements down the tree. This operation is crucial for maintaining the heap structure during sorting.

### Building a Max-Heap: From Array to Heap

A common method is to call heapify from the last non-leaf node down to the root to build a heap in O(n) time.

### Heap Sort: Extracting and Sorting

Heap Sort repeatedly extracts the maximum element and places it at the end of the array, restoring the heap after each extraction.

---

## **Practical 004 — Recursion: Iterative and Recursive Factorial**

This practical explores the concept of recursion through the lens of factorial calculation. You'll understand how recursive functions work, compare their efficiency with iterative approaches, and learn the importance of base cases.

### Understanding Factorial and Its Applications

Factorial n! represents the product of all positive integers from 1 to n. For example, 5! = 120 and 0! = 1. Factorials appear in combinatorics, permutations, and probability.

### Iterative Factorial: The Loop-Based Approach

Iterative factorial uses loops to compute the result and avoids call stack overhead. This approach is memory-efficient and preferred for large values of n.

### Recursive Factorial: The Self-Referential Approach

Recursive factorial relies on the definition n! = n × (n-1)! with a base case to stop recursion. This elegant approach is more intuitive but uses more memory due to function call overhead.

### Comparing Iterative vs. Recursive Factorial

Iteration avoids call stack overhead and is typically more memory-efficient; recursion can be more expressive but risks stack overflow for large n.

---

## **Practical 005 — Knapsack Problem**

The Knapsack Problem (0/1 Knapsack) is a fundamental optimization problem in computer science and combinatorial optimization. Given a set of items, each with a weight and a value, the task is to determine the most valuable subset that fits within a capacity constraint.

Dynamic Programming (DP) Approach:

- Idea: Build a DP table where dp[i][w] represents the maximum value achievable using the first i items with a knapsack capacity of w.
- Recurrence:
  - If the weight of the i-th item is greater than w, the item cannot be included: dp[i][w] = dp[i-1][w]
  - Otherwise, choose the better of including or excluding the item:
    dp[i][w] = max(values[i-1] + dp[i-1][w - weights[i-1]], dp[i-1][w])
- Initialization: dp[0][w] = 0 for all w and dp[i][0] = 0 for all i.

Reconstruction of Selected Items:
- After filling the DP table, the maximum value is dp[n][capacity]. To find which items were included, backtrack from dp[n][capacity] to dp[0][...]. If dp[i][w] != dp[i-1][w], item i-1 was included.

Complexity:
- Time: O(n * W) where n is the number of items and W is the knapsack capacity.
- Space: O(n * W) for the full DP table (can be optimized to O(W) for value computation but reconstruction becomes more complex).

---

## **Practical 006 — Cross Matrix Multiplication**

This practical explores matrix multiplication, specifically the cross product and efficient algorithms for multiplying matrices. You'll understand different approaches to matrix multiplication and the importance of optimization in large-scale computations.

### Understanding Matrix Multiplication

Matrix multiplication is a fundamental operation in linear algebra and computer science. Given two matrices A (m × n) and B (n × p), the resulting matrix C (m × p) is computed by taking the dot product of rows and columns.

### Standard Matrix Multiplication Algorithm

The standard algorithm performs the basic row-by-column dot product calculation. This is the most intuitive approach and has a time complexity of O(m * n * p) for multiplying an m × n matrix with an n × p matrix.

### Cross Product in 3D Space

The cross product is a special case of matrix multiplication applicable to 3D vectors. Given two vectors u and v, the cross product u × v results in a vector perpendicular to both u and v. The magnitude depends on the angle between them.

### Strassen's Algorithm: Divide and Conquer Approach

Strassen's Algorithm reduces the number of scalar multiplications required by recursively dividing matrices into smaller submatrices. It achieves O(n^2.807) time complexity compared to O(n^3) for the classical method.

### Applications of Matrix Multiplication

Matrix multiplication has widespread applications in computer graphics (transformations), machine learning (neural networks), physics simulations, and solving systems of linear equations.

### Complexity Analysis

- Standard Algorithm: O(m * n * p)
- Strassen's Algorithm: O(n^2.807)
- Space Complexity: O(m * p) for the result matrix

---

## **Practical 007 — Coin Change Problem**

This practical explores the classic Coin Change problem, a fundamental optimization problem in dynamic programming. You'll learn how to determine the minimum number of coins needed to make a target amount using a given set of denominations.

### Introduction to the Coin Change Problem

A common real-world problem is making change with the fewest possible coins. Given a target amount and available coin denominations, the goal is to minimize the count of coins while using valid denominations.

### Dynamic Programming Approach

The problem can be solved efficiently using dynamic programming by defining dp[a] as the minimum number of coins needed to make amount a. Each amount is built from smaller amounts, and the best solution is chosen by trying each coin.

### Recurrence Relation

- dp[0] = 0
- For each amount a from 1 to target:
  - dp[a] = min(dp[a], 1 + dp[a - coin]) for every valid coin
- If no combination exists, the value remains unreachable.

### Example

Suppose the coins are [1, 3, 6, 10] and the target amount is 85. The algorithm computes the minimum number of coins needed to make the amount.

### Why This Works

This method stores optimal subproblems and reuses them to build larger solutions. Since each amount depends only on smaller amounts, the problem structure is well-suited for dynamic programming.

### Applications of Coin Change

Coin Change is used in:
- Banking and cash systems
- Dynamic programming optimization problems
- Resource allocation and scheduling
- Change-making algorithms in finance and software systems

### Complexity Analysis

- Time Complexity: O(amount × number_of_coins)
- Space Complexity: O(amount)

---

## **Practical 008 — Graph Traversal: DFS and BFS**

This practical introduces two fundamental graph traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS). You'll learn how these algorithms systematically visit vertices and edges in a graph.

### Understanding Graphs and Graph Traversal

A graph consists of vertices, also called nodes, and edges that connect pairs of vertices. Graphs can be directed or undirected, and they may be represented using an adjacency matrix or an adjacency list.

### Depth-First Search (DFS)

Depth-First Search explores a graph by following one path as deeply as possible before backtracking to visit other unvisited paths. It can be performed using recursion or an explicit stack. A visited set prevents infinite loops in cyclic graphs.

### DFS Traversal Process

DFS begins at a selected starting vertex, marks it as visited, and then explores each unvisited neighboring vertex before returning to earlier vertices. This depth-oriented strategy is useful for exploring all reachable nodes.

### Breadth-First Search (BFS)

Breadth-First Search explores a graph level by level. It visits all immediate neighbors of the starting vertex before moving to vertices at the next level. BFS uses a queue to preserve the order in which nodes are processed.

### BFS Traversal Process

BFS begins at a selected starting vertex, marks it as visited, and places it in a queue. It repeatedly removes the next vertex from the queue and adds each of its unvisited neighbors. This continues until all nodes are visited.

### Comparing DFS and BFS

DFS prioritizes depth and is commonly associated with recursion or a stack, while BFS prioritizes breadth and uses a queue. DFS is useful when complete paths or backtracking are required, whereas BFS is ideal for shortest-path problems in unweighted graphs.

### Applications of DFS and BFS

DFS is used in cycle detection, connected-component analysis, topological sorting, maze solving, and path exploration. BFS is used in shortest-path problems on unweighted graphs, network broadcasting, and level-order traversal.

### Complexity Analysis

- DFS Time Complexity: O(V + E)
- BFS Time Complexity: O(V + E)
- Space Complexity: O(V) for the visited structure and traversal data structure

Here, V represents the number of vertices and E represents the number of edges in the graph.

---

## File Structure
```
DAA-practical01-8847/
├── DAA_practical_01.ipynb      # Sorting algorithms implementation
├── DAA_practial02.ipynb        # Linear and Binary Search implementation
├── DAA_practical03.ipynb       # Max-Heap Sort implementation
├── DAA_Practical04.ipynb       # Recursion: Factorial (Iterative & Recursive)
├── DAA_Practical05.ipynb       # Knapsack Problem (0/1 Knapsack)
├── DAA_practical_06.ipynb      # Cross Matrix Multiplication
├── DAA_practical_07.ipynb      # Coin Change Problem (Dynamic Programming)
├── DAA_practical_08.ipynb      # Graph Traversal: DFS and BFS
└── README.md                   # This file
```

## Author
**Lasya Jangapelli**

## License
This project is part of the DAA (Design and Analysis of Algorithms) practical coursework.
