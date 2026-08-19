# DAA-practical01-8847

A comprehensive repository for the Design and Analysis of Algorithms (DAA) course. This collection contains practical implementations and explanations of essential algorithms used in computer science.

---

## Practical 001 — Sorting Algorithms

This practical explores the fundamental sorting algorithms that form the backbone of computer science. You'll learn how different sorting techniques work, their strengths and weaknesses, and when to use them.

### Bubble Sort
Bubble Sort is one of the most intuitive sorting algorithms, often the first one taught to beginners. It works by repeatedly stepping through the list, comparing adjacent elements, and swapping them if they're in the wrong order. The algorithm continues passes through the data until no more swaps are needed, indicating the list is sorted. While simple to understand and implement, Bubble Sort has O(n²) time complexity, making it inefficient for large datasets.

### Selection Sort
Selection Sort works by dividing the array into two parts: the sorted portion (at the beginning) and the unsorted portion (at the end). The algorithm repeatedly finds the minimum element from the unsorted portion and places it at the end of the sorted portion. This process continues until the entire array is sorted. Like Bubble Sort, Selection Sort has O(n²) time complexity but performs fewer swaps, making it slightly more efficient in practice.

### Insertion Sort
Insertion Sort builds the sorted array one element at a time by inserting each new element into its correct position within the already-sorted portion. It works similarly to how people organize playing cards in their hands. The algorithm is adaptive, meaning it performs better on nearly-sorted data with O(n) complexity in the best case, though it remains O(n²) in the average and worst cases.

### Merge Sort
Merge Sort represents a leap forward in algorithm design by employing the divide-and-conquer paradigm. The algorithm works by recursively dividing the array into two halves until each element stands alone, then merging them back together in sorted order. With O(n log n) time complexity in all cases, Merge Sort is efficient but requires O(n) additional space for the merge operation.

### Quick Sort
Quick Sort is one of the most popular sorting algorithms in practice due to its efficiency and elegant approach. It works by selecting a "pivot" element and partitioning the array around it—elements smaller than the pivot go to the left, and larger elements go to the right. This process repeats recursively on the partitions. Average-case time complexity is O(n log n), though worst-case can be O(n²) with poor pivot selection.

### Linear Search
Linear Search is the simplest search algorithm, scanning through a list sequentially until the target element is found or the list ends. This algorithm works on both sorted and unsorted data, requiring O(n) time complexity. It's useful for small lists or unsorted data where binary search isn't applicable.

### Binary Search
Binary Search is a highly efficient algorithm that finds a target in a sorted array by repeatedly dividing the search interval in half. Starting with the entire array, it examines the middle element and eliminates half the remaining elements with each comparison. This results in O(log n) time complexity, making it dramatically faster than linear search for large sorted datasets.

### Max-Heap Sort (Heap Sort)
Heap Sort leverages the heap data structure to achieve efficient sorting. A heap is a complete binary tree with the heap property: in a max-heap, every parent node is greater than or equal to its children. Heap Sort builds a max-heap from the input, then repeatedly extracts the maximum element and places it in its final sorted position. It guarantees O(n log n) time complexity with O(1) additional space.

---

## Practical 002 — Searching: Linear and Binary Search

This practical demonstrates two essential search techniques and compares their effectiveness. You'll understand the fundamental difference between brute-force searching and smart searching, and learn to select the right algorithm for your use case.

### Linear Search: Understanding Sequential Search
Linear Search is the most fundamental search algorithm, representing the brute-force approach to finding an element. It works by examining elements one by one in sequence, starting from the first element until the target is found or the list ends. The algorithm has a time complexity of O(n) and requires no additional space beyond the input. It's best used for small datasets or unsorted collections where more sophisticated algorithms aren't applicable.

### Binary Search: The Power of Divide and Conquer
Binary Search is a highly efficient algorithm that dramatically outperforms Linear Search for sorted data. The algorithm works by dividing the search problem in half with each step, eliminating half of the remaining search space. By continuously narrowing down the search interval, Binary Search achieves O(log n) time complexity. For example, searching a million sorted elements requires at most 20 comparisons.

### Comparing Performance: Linear vs. Binary Search
Understanding when to use Linear Search versus Binary Search is crucial for practical algorithm selection. On small datasets (typically under 1000 elements), the performance difference is negligible due to modern CPU caching and simplicity of Linear Search. However, as dataset size grows, Binary Search's logarithmic complexity vastly outperforms Linear Search's linear complexity. The trade-off is that Binary Search requires the data to be sorted beforehand.

### Practical Implementation Considerations
Implementing search algorithms efficiently requires attention to several practical details. For Linear Search, you need to handle early termination when the element is found and ensure the function returns the correct index or indicator value. For Binary Search, careful management of boundary conditions (inclusive vs. exclusive bounds) is critical to avoid off-by-one errors and infinite loops.

---

## Practical 003 — Max-Heap Sort Algorithm

This practical provides an in-depth exploration of heap-based sorting. You'll understand how heap data structures work and how they can be leveraged to create an efficient, in-place sorting algorithm with guaranteed O(n log n) performance.

### Understanding the Heap Data Structure
A heap is a specialized tree-based data structure that satisfies the heap property. In a max-heap, every parent node has a value greater than or equal to its children. Heaps are typically implemented as arrays where for any node at index i, its left child is at 2i+1 and its right child is at 2i+2. This compact representation makes heaps memory-efficient and cache-friendly compared to pointer-based tree implementations.

### The Heapify Operation: Maintaining Heap Property
The heapify operation is the core mechanic that maintains the max-heap property after modifications. When a node violates the heap property (its parent is smaller than itself), heapify fixes this by swapping the violating node with its parent and recursively checking up the tree. This downward percolation process continues until the heap property is restored, with time complexity O(log n).

### Building a Max-Heap: From Array to Unsorted Array
Building a max-heap from an unsorted array is a fundamental operation that prepares data for heap sort or other heap-based algorithms. A naive approach would be to insert elements one by one into an empty heap with O(n log n) complexity. However, the optimal approach is bottom-up heapification, starting from the last non-leaf node and calling heapify on each node, which achieves O(n) time complexity.

### Heap Sort: Extracting and Sorting
Heap Sort completes the sorting process by repeatedly extracting the maximum element from the heap and placing it in its final sorted position. After building the max-heap, the root contains the maximum element. By swapping the root with the last element and reducing the heap size, then heapifying, we repeatedly extract elements in sorted order. This phase takes O(n log n) time.

### Applications and Advantages of Heap Sort
Heap Sort's guaranteed O(n log n) time complexity and O(1) space complexity make it valuable in specific scenarios. When consistent, predictable performance is essential and memory is constrained, Heap Sort is an excellent choice. It's also used in priority queue implementations and is the basis for efficient selection algorithms that find the k-th smallest/largest element without full sorting.

---

## Practical 004 — Recursion: Iterative and Recursive Factorial

This practical explores the concept of recursion through the lens of factorial calculation. You'll understand how recursive functions work, compare their efficiency with iterative approaches, and learn about the trade-offs between elegance and performance.

### Understanding Factorial and Its Applications
Factorial is a fundamental mathematical operation denoted as n!, which represents the product of all positive integers from 1 to n. For example, 5! = 5 × 4 × 3 × 2 × 1 = 120. By definition, 0! = 1 to maintain mathematical consistency. Factorials appear frequently in combinatorics, probability theory, and algorithm analysis, making them essential for understanding recursive problem-solving.

### Iterative Factorial: The Loop-Based Approach
Iterative factorial calculation uses loops to compute the result by multiplying successive integers. The algorithm starts with a result variable initialized to 1, then iterates from 1 to n, multiplying the result by each successive integer. This approach requires O(n) time and O(1) space, making it memory-efficient. Iterative solutions avoid the overhead of function calls and stack space.

### Recursive Factorial: The Self-Referential Approach
Recursive factorial calculation relies on the mathematical definition n! = n × (n-1)!. The recursive function calls itself with a smaller input until reaching the base case (0! = 1), then returns and unwinds, multiplying the results back up the call stack. While elegant and intuitive, recursion introduces function call overhead and uses O(n) stack space, potentially causing stack overflow for large n.

### Comparing Iterative vs. Recursive Factorial
Comparing iterative and recursive factorial implementations reveals important trade-offs in algorithm design. Iteratively, the computation is straightforward: perform n multiplications in sequence and return the result. Recursively, the same computation involves n function calls, stack frames, and unwinding. For small n, recursion's clarity may outweigh performance costs, but for large n, iteration is more practical.

### Understanding Recursion: Base Cases and Recursive Cases
Recursion relies on two critical components: a base case and a recursive case. The base case defines when recursion stops, preventing infinite loops and stack overflow. For factorial, the base case is 0! = 1. The recursive case defines how the problem reduces: n! = n × (n-1)!. Well-designed recursion problems have clear, achievable base cases and guaranteed reduction toward them.

---

## Practical 007 — Pattern Matching and String Algorithms

This practical explores fundamental string matching algorithms and pattern recognition techniques. You'll learn how different algorithms find patterns within text and understand their performance characteristics in various scenarios.

### Introduction to Pattern Matching
Pattern matching is a core problem in computer science with applications ranging from text editors and search engines to bioinformatics and data analysis. The basic problem is: given a text string and a pattern string, find all occurrences of the pattern within the text. Different algorithms employ various strategies, from naive brute-force approaches to sophisticated algorithms that preprocess the pattern or use automata-based methods.

### Naive String Matching Algorithm
The naive pattern matching approach is the most straightforward: position the pattern at each location in the text and check character-by-character for a match. If all characters match, the pattern is found; otherwise, move to the next position and repeat. While simple to understand and implement, this algorithm has O((n-m+1) × m) worst-case time complexity, where n is the text length and m is the pattern length. For large texts or patterns, this inefficiency becomes problematic.

### The Knuth-Morris-Pratt (KMP) Algorithm
The Knuth-Morris-Pratt algorithm improves upon naive string matching by using information from previous comparisons to avoid redundant checks. KMP preprocesses the pattern to build a "failure function" (also called LPS or Longest Proper Prefix which is also Suffix). When a mismatch occurs, KMP uses this function to jump ahead in the pattern rather than starting from the beginning. This results in O(n + m) time complexity, with a single pass through the text after O(m) preprocessing.

### The Boyer-Moore Algorithm
Boyer-Moore is another efficient string matching algorithm that often outperforms KMP in practice, especially for longer patterns and larger alphabets. It works from right to left within the pattern and employs two heuristics: the bad-character rule and the good-suffix rule. When a mismatch is found, it skips forward in the text by the maximum amount indicated by these rules. Boyer-Moore has O(n/m) best-case complexity and O(n + m) worst-case complexity.

### Rabin-Karp Algorithm: Hashing for Pattern Matching
Rabin-Karp uses a different approach by computing hash values for the pattern and text substrings. It slides a window of pattern length across the text, computing rolling hashes efficiently without recomputing from scratch each time. When hash values match, the algorithm verifies actual character equality to confirm a match (avoiding hash collision false positives). This algorithm excels at finding multiple patterns and has O(n + m) average-case complexity.

### Applications and Performance Considerations
Pattern matching algorithms have diverse applications depending on their characteristics. For simple, short patterns, naive matching suffices. For longer patterns or large texts where efficiency matters, KMP and Boyer-Moore excel. Rabin-Karp becomes advantageous when searching for multiple patterns simultaneously or in streaming scenarios. Understanding these trade-offs helps select the right algorithm for specific problem constraints and performance requirements.

---

## File Structure
```
DAA-practical01-8847/
├── DAA_practical_01.ipynb      # Sorting algorithms implementation
├── DAA_practial02.ipynb        # Linear and Binary Search implementation
├── DAA_practical03.ipynb       # Max-Heap Sort implementation
├── DAA_Practical04.ipynb       # Recursion: Factorial (Iterative & Recursive)
├── DAA_Practical07.ipynb       # Pattern Matching and String Algorithms
└── README.md                    # This file
```

## Author
**Lasya Jangapelli**

## License
This project is part of the DAA (Design and Analysis of Algorithms) practical coursework.
