# DAA-practical01-8847

A comprehensive repository for the Design and Analysis of Algorithms (DAA) course. This collection contains practical implementations and explanations of essential algorithms used in computer science.

## **Practical 001 — Sorting Algorithms**

This practical explores the fundamental sorting algorithms that form the backbone of computer science. You'll learn how different sorting techniques work, their strengths and weaknesses, and when to use each one.

### Bubble Sort

Bubble Sort is one of the most intuitive sorting algorithms, often the first one taught to beginners. It works by repeatedly stepping through the list, comparing adjacent elements, and swapping them if they're in the wrong order. Multiple passes through the array are made until no more swaps are needed.

### Selection Sort

Selection Sort works by dividing the array into two parts: the sorted portion (at the beginning) and the unsorted portion (the rest). The algorithm repeatedly finds the minimum element from the unsorted portion and moves it to the end of the sorted portion.

### Insertion Sort

Insertion Sort builds the sorted array one element at a time by inserting each new element into its correct position within the already-sorted portion. It works similarly to how people organize playing cards in their hands.

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

This practical demonstrates two essential search techniques and compares their effectiveness. You'll understand the fundamental difference between brute-force searching and smart searching, and learn when to apply each approach.

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

This practical explores the concept of recursion through the lens of factorial calculation. You'll understand how recursive functions work, compare their efficiency with iterative approaches, and learn about the call stack.

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

The Knapsack Problem (0/1 Knapsack) is a fundamental optimization problem in computer science and combinatorial optimization. Given a set of items, each with a weight and a value, the task is to determine the maximum value that can be obtained by including items in a knapsack that has a limited weight capacity.

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

This practical explores matrix multiplication, specifically the cross product and efficient algorithms for multiplying matrices. You'll understand different approaches to matrix multiplication and their computational complexities.

### Understanding Matrix Multiplication

Matrix multiplication is a fundamental operation in linear algebra and computer science. Given two matrices A (m × n) and B (n × p), the resulting matrix C (m × p) is computed by taking the dot product of rows from A with columns from B.

### Standard Matrix Multiplication Algorithm

The standard algorithm performs the basic row-by-column dot product calculation. This is the most intuitive approach and has a time complexity of O(m * n * p) for multiplying an m × n matrix with an n × p matrix.

### Cross Product in 3D Space

The cross product is a special case of matrix multiplication applicable to 3D vectors. Given two vectors u and v, the cross product u × v results in a vector perpendicular to both u and v. The magnitude of the cross product equals the area of the parallelogram formed by the two vectors.

### Strassen's Algorithm: Divide and Conquer Approach

Strassen's Algorithm reduces the number of scalar multiplications required by recursively dividing matrices into smaller submatrices. It achieves O(n^2.807) time complexity compared to O(n^3) for the standard algorithm, making it more efficient for large matrices.

### Applications of Matrix Multiplication

Matrix multiplication has widespread applications in computer graphics (transformations), machine learning (neural networks), physics simulations, and solving systems of linear equations.

### Complexity Analysis

- Standard Algorithm: O(m * n * p)
- Strassen's Algorithm: O(n^2.807)
- Space Complexity: O(m * p) for the result matrix

---

## **Practical 007 — Pattern Matching and String Algorithms**

This practical explores fundamental string matching algorithms and pattern recognition techniques. You'll learn how different algorithms find patterns within text and understand their performance characteristics.

### Introduction to Pattern Matching

Pattern matching is a core problem in computer science with applications ranging from text editors and search engines to bioinformatics and DNA sequencing.

### Naive String Matching Algorithm

The naive approach checks the pattern at each position in the text. While simple to implement, it can be slow for large texts and patterns with many repeated characters.

### The Knuth-Morris-Pratt (KMP) Algorithm

KMP preprocesses the pattern to build a failure function that allows skipping comparisons. This avoids redundant comparisons and achieves O(n + m) time complexity where n is the text length and m is the pattern length.

### The Boyer-Moore Algorithm

Boyer-Moore often outperforms KMP in practice by using bad-character and good-suffix heuristics to skip portions of the text. It's particularly efficient when the pattern and alphabet are large.

### Rabin-Karp Algorithm: Hashing for Pattern Matching

Rabin-Karp computes rolling hashes for the pattern and text substrings to find matches efficiently on average. It's useful for multiple pattern matching and has an average-case complexity of O(n + m).

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
├── DAA_practical_07.ipynb      # Pattern Matching and String Algorithms
└── README.md                    # This file
```

## Author
**Lasya Jangapelli**

## License
This project is part of the DAA (Design and Analysis of Algorithms) practical coursework.
