# DAA-practical01-8847

A comprehensive repository for the Design and Analysis of Algorithms (DAA) course. This collection contains practical implementations and explanations of essential algorithms used in computer science.

## **Practical05 — Knapsack Problem**

The Knapsack Problem (0/1 Knapsack) is a fundamental optimization problem in computer science and combinatorial optimization. Given a set of items, each with a weight and a value, the task is to determine the subset of items to include in a knapsack so that the total weight does not exceed a given capacity and the total value is maximized. In the 0/1 variant, each item can be chosen at most once.

Dynamic Programming (DP) Approach:

- Idea: Build a DP table where dp[i][w] represents the maximum value achievable using the first i items with a knapsack capacity of w.
- Recurrence:
  - If the weight of the i-th item is greater than w, the item cannot be included: dp[i][w] = dp[i-1][w]
  - Otherwise, choose the better of including or excluding the item:
    dp[i][w] = max(values[i-1] + dp[i-1][w - weights[i-1]], dp[i-1][w])
- Initialization: dp[0][w] = 0 for all w (0 items -> 0 value) and dp[i][0] = 0 for all i (capacity 0 -> 0 value).

Reconstruction of Selected Items:
- After filling the DP table, the maximum value is dp[n][capacity]. To find which items were included, backtrack from dp[n][capacity] to dp[0][...]. If dp[i][w] != dp[i-1][w], item i-1 was included; subtract its weight from w and continue.

Complexity:
- Time: O(n * W) where n is the number of items and W is the knapsack capacity.
- Space: O(n * W) for the full DP table (can be optimized to O(W) for value computation but then reconstruction becomes more complex).

Example (from the implementation in DAA_Practical05.ipynb):
- A DP implementation computes the maximum value and reconstructs the indices of included items. The algorithm prompts the user for number of items, weights, values, and capacity, then outputs the maximum value and the selected item indices with corresponding weights and values.

---

## Practical 001 — Sorting Algorithms

This practical explores the fundamental sorting algorithms that form the backbone of computer science. You'll learn how different sorting techniques work, their strengths and weaknesses, and when to use them. Implementations and explanations cover common algorithms and their complexities.

### Bubble Sort
Bubble Sort is one of the most intuitive sorting algorithms, often the first one taught to beginners. It works by repeatedly stepping through the list, comparing adjacent elements, and swapping them if they are in the wrong order. Repeated passes move larger elements toward the end of the list.

### Selection Sort
Selection Sort works by dividing the array into two parts: the sorted portion (at the beginning) and the unsorted portion (at the end). The algorithm repeatedly finds the minimum element from the unsorted portion and swaps it with the first unsorted element.

### Insertion Sort
Insertion Sort builds the sorted array one element at a time by inserting each new element into its correct position within the already-sorted portion. It works similarly to how people organize playing cards in their hands.

### Merge Sort
Merge Sort represents a leap forward in algorithm design by employing the divide-and-conquer paradigm. The algorithm works by recursively dividing the array into two halves until each element stands alone, then merging the sorted halves back together.

### Quick Sort
Quick Sort is one of the most popular sorting algorithms in practice due to its efficiency and elegant approach. It works by selecting a "pivot" element and partitioning the array around it—elements less than the pivot to one side and greater to the other—then recursively sorting the partitions.

### Linear Search
Linear Search is the simplest search algorithm, scanning through a list sequentially until the target element is found or the list ends. This algorithm works on both sorted and unsorted data, requiring O(n) time in the worst case.

### Binary Search
Binary Search is a highly efficient algorithm that finds a target in a sorted array by repeatedly dividing the search interval in half. Starting with the entire array, it examines the middle element and discards the half that cannot contain the target, repeating until found or the interval is empty.

### Max-Heap Sort (Heap Sort)
Heap Sort leverages the heap data structure to achieve efficient sorting. A heap is a complete binary tree with the heap property: in a max-heap, every parent node is greater than or equal to its children. Heap sort uses heapify to build a max-heap and then repeatedly extracts the maximum to build the sorted array.

---

## Practical 002 — Searching: Linear and Binary Search

This practical demonstrates two essential search techniques and compares their effectiveness. You'll understand the fundamental difference between brute-force searching and smart searching, and learn how to implement both algorithms and measure their performance.

### Linear Search: Understanding Sequential Search
Linear Search is the most fundamental search algorithm, representing the brute-force approach to finding an element. It works by examining elements one by one in sequence, starting from the first element until the target is found or the end is reached.

### Binary Search: The Power of Divide and Conquer
Binary Search is a highly efficient algorithm that dramatically outperforms Linear Search for sorted data. The algorithm works by dividing the search problem in half with each step, eliminating half the search space every iteration.

### Comparing Performance: Linear vs. Binary Search
Understanding when to use Linear Search versus Binary Search is crucial for practical algorithm selection. On small datasets (typically under 1000 elements), the performance difference is negligible depending on implementation and constant factors, but for large datasets binary search is asymptotically superior.

### Practical Implementation Considerations
Implementing search algorithms efficiently requires attention to several practical details. For Linear Search, you need to handle early termination when the element is found and ensure the function returns appropriate indicators when not found. Binary Search requires careful handling of indices to avoid infinite loops.

---

## Practical 003 — Max-Heap Sort Algorithm

This practical provides an in-depth exploration of heap-based sorting. You'll understand how heap data structures work and how they can be leveraged to create an efficient, in-place sorting algorithm for arrays.

### Understanding the Heap Data Structure
A heap is a specialized tree-based data structure that satisfies the heap property. In a max-heap, every parent node has a value greater than or equal to its children. Heaps are typically implemented as arrays with parent/child index calculations.

### The Heapify Operation: Maintaining Heap Property
The heapify operation is the core mechanic that maintains the max-heap property after modifications. When a node violates the heap property (its parent is smaller than itself), heapify fixes this by swapping elements down the tree until the property is restored.

### Building a Max-Heap: From Array to Unsorted Array
Building a max-heap from an unsorted array is a fundamental operation that prepares data for heap sort or other heap-based algorithms. A common method is to call heapify from the last non-leaf node down to the root.

### Heap Sort: Extracting and Sorting
Heap Sort completes the sorting process by repeatedly extracting the maximum element from the heap and placing it in its final sorted position. After building the max-heap, the root contains the maximum element which is swapped to the end and the heap size reduced.

### Applications and Advantages of Heap Sort
Heap Sort's guaranteed O(n log n) time complexity and O(1) space complexity make it valuable in specific scenarios. When consistent, predictable performance is essential and memory is constrained, Heap Sort is a good candidate.

---

## Practical 004 — Recursion: Iterative and Recursive Factorial

This practical explores the concept of recursion through the lens of factorial calculation. You'll understand how recursive functions work, compare their efficiency with iterative approaches, and learn how to reason about base cases and recursion depth.

### Understanding Factorial and Its Applications
Factorial is a fundamental mathematical operation denoted as n!, which represents the product of all positive integers from 1 to n. For example, 5! = 5 × 4 × 3 × 2 × 1 = 120. By definition, 0! = 1.

### Iterative Factorial: The Loop-Based Approach
Iterative factorial calculation uses loops to compute the result by multiplying successive integers. The algorithm starts with a result variable initialized to 1, then iterates from 1 to n, multiplying into the result.

### Recursive Factorial: The Self-Referential Approach
Recursive factorial calculation relies on the mathematical definition n! = n × (n-1)!. The recursive function calls itself with a smaller input until reaching the base case (0! = 1), then unwinds returning the result.

### Comparing Iterative vs. Recursive Factorial
Comparing iterative and recursive factorial implementations reveals important trade-offs in algorithm design. Iteration avoids call stack overhead, while recursion can be more concise and mirrors the mathematical definition.

### Understanding Recursion: Base Cases and Recursive Cases
Recursion relies on two critical components: a base case and a recursive case. The base case defines when recursion stops, preventing infinite loops and stack overflow. For factorial, the base case is n <= 1.

---

## Practical 007 — Pattern Matching and String Algorithms

This practical explores fundamental string matching algorithms and pattern recognition techniques. You'll learn how different algorithms find patterns within text and understand their performance characteristics and trade-offs.

### Introduction to Pattern Matching
Pattern matching is a core problem in computer science with applications ranging from text editors and search engines to bioinformatics and data analysis. The basic problem is: given a text string and a pattern, find all occurrences of the pattern in the text.

### Naive String Matching Algorithm
The naive pattern matching approach is the most straightforward: position the pattern at each location in the text and check character-by-character for a match. If all characters match, the pattern is found at that position.

### The Knuth-Morris-Pratt (KMP) Algorithm
The Knuth-Morris-Pratt algorithm improves upon naive string matching by using information from previous comparisons to avoid redundant checks. KMP preprocesses the pattern to build a "failure function" (lps array) that tells how far to jump when a mismatch occurs.

### The Boyer-Moore Algorithm
Boyer-Moore is another efficient string matching algorithm that often outperforms KMP in practice, especially for longer patterns and larger alphabets. It works from right to left within the pattern and uses heuristics like the bad-character rule and good-suffix rule.

### Rabin-Karp Algorithm: Hashing for Pattern Matching
Rabin-Karp uses a different approach by computing hash values for the pattern and text substrings. It slides a window of pattern length across the text, computing rolling hashes efficiently without recomputing from scratch each time.

### Applications and Performance Considerations
Pattern matching algorithms have diverse applications depending on their characteristics. For simple, short patterns, naive matching suffices. For longer patterns or large texts where efficiency matters, algorithms like KMP, Boyer-Moore, and Rabin-Karp provide significant benefits.

---

## File Structure
```
DAA-practical01-8847/
├── DAA_practical_01.ipynb      # Sorting algorithms implementation
├── DAA_practial02.ipynb        # Linear and Binary Search implementation
├── DAA_practical03.ipynb       # Max-Heap Sort implementation
├── DAA_Practical04.ipynb       # Recursion: Factorial (Iterative & Recursive)
├── DAA_Practical05.ipynb       # Knapsack Problem (0/1 Knapsack)
├── DAA_practical_07.ipynb      # Pattern Matching and String Algorithms
└── README.md                    # This file
```

## Author
**Lasya Jangapelli**

## License
This project is part of the DAA (Design and Analysis of Algorithms) practical coursework.
