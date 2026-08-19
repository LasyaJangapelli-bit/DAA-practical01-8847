# DAA-practical01-8847

Brief, readable descriptions of common sorting and searching algorithms used in these practicals.

---

**<mark>Bubble Sort</mark>**
- Repeatedly compares adjacent elements and swaps them if out of order until the list is sorted.
- Time: O(n^2) worst/average, O(n) best. Space: O(1). Stable, in-place.

**<mark>Selection Sort</mark>**
- Selects the minimum (or maximum) element from the unsorted portion and moves it to the front.
- Time: O(n^2) for all cases. Space: O(1). In-place, not stable by default.

**<mark>Insertion Sort</mark>**
- Builds the sorted list one element at a time by inserting each item into its correct position.
- Time: O(n^2) worst/average, O(n) best (nearly sorted). Space: O(1). Stable, in-place.

**<mark>Merge Sort</mark>**
- Divide-and-conquer: split the list, sort halves, then merge them.
- Time: O(n log n) all cases. Space: O(n). Stable, needs extra space.

**<mark>Quick Sort</mark>**
- Picks a pivot, partitions elements around it, then recursively sorts partitions.
- Time: O(n log n) average, O(n^2) worst (bad pivot). Space: O(log n) average. In-place typically, not stable.

**<mark>Linear Search</mark>**
- Scans elements sequentially until the target is found or the list ends.
- Time: O(n) in the worst case. Space: O(1).

**<mark>Binary Search</mark>**
- Efficiently searches a sorted list by repeatedly dividing the search interval in half.
- Time: O(log n). Space: O(1) for iterative implementation. Requires sorted input.

**<mark>Max-Heap Sort (Heap Sort)</mark>**
- Builds a max-heap from the data, then repeatedly extracts the maximum to build the sorted array.
- Time: O(n log n) in all cases. Space: O(1) in-place variants. Not stable.

---

## Practical 03 — Max-Heap Sort Algorithm

This section includes the contents of `DAA_practical03.ipynb`: an interactive Python implementation of the Max-Heap Sort algorithm.

### Overview
Max-Heap Sort is a comparison-based sorting algorithm that uses the heap data structure to sort an array. It works by building a max-heap and then repeatedly extracting the maximum element to produce a sorted array.

### Algorithm Description

#### How Max-Heap Sort Works:
1. **Build Max-Heap**: Convert the array into a max-heap structure where each parent node is greater than or equal to its children.
2. **Extract Elements**: Repeatedly swap the root (maximum element) with the last element and heapify the remaining heap.
3. **Result**: Elements are sorted in ascending order.

### Implementation

#### Heapify Function
```python
def heapify(arr, n, i):
    largest = i  # Initialize largest as root
    l = 2 * i + 1  # left = 2*i + 1
    r = 2 * i + 2  # right = 2*i + 2

    # See if left child of root exists and is greater than root
    if l < n and arr[l] > arr[largest]:
        largest = l

    # See if right child of root exists and is greater than root
    if r < n and arr[r] > arr[largest]:
        largest = r

    # Change root, if needed
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]  # swap

        # Heapify the root.
        heapify(arr, n, largest)
```

**Purpose**: Maintains the max-heap property by ensuring the parent node is greater than its children.

#### Max-Heap Sort Function
```python
def max_heap_sort(arr):
    n = len(arr)

    # Build a maxheap.
    # Since last parent will be at ((n//2)-1) we can start there.
    for i in range(n // 2 - 1, -1, -1):
        heapify(arr, n, i)

    # One by one extract elements
    for i in range(n - 1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]  # swap
        heapify(arr, i, 0)
```

**Purpose**: Sorts the array by first building a max-heap and then extracting the maximum element repeatedly.

#### Main Execution
```python
# Take input from the user
user_input = input("Enter numbers separated by spaces: ")
numbers = list(map(int, user_input.split()))

print("Original array:", numbers)

max_heap_sort(numbers)

print("Sorted array (Max-Heap Sort):", numbers)
```

### Example

**Input:**
```
Enter numbers separated by spaces: 5 1 8 9 5 7 6
```

**Output:**
```
Original array: [5, 1, 8, 9, 5, 7, 6]
Sorted array (Max-Heap Sort): [1, 5, 5, 6, 7, 8, 9]
```

### Time & Space Complexity

| Aspect | Complexity |
|--------|-----------|
| **Time Complexity** | O(n log n) |
| **Space Complexity** | O(1) - In-place sorting |

### Key Features
- ✅ Efficient sorting with O(n log n) time complexity
- ✅ In-place sorting (O(1) extra space)
- ✅ Handles duplicate elements correctly
- ✅ User-friendly input interface

### How to Run
1. Run the Jupyter notebook (`DAA_practical03.ipynb`)
2. Execute all cells in order
3. Enter numbers separated by spaces when prompted
4. View the original and sorted arrays

---

## Practical 02 — Searching: linear and binary search

This section includes the contents of `DAA_practial02.ipynb`: a short interactive Python example that demonstrates Linear Search and Binary Search, measures their run times, and prints results.

### How to run

1. You can run the code below in a Python interpreter or in a Jupyter/Colab notebook.
2. The script asks for a list of integers (space-separated) and a target value to search for.

### Example input

Enter a list of numbers separated by spaces (e.g., 10 20 30 40 50):

```
59 67 89 34 43 22 10 0
```

Enter the target number to search for:

```
67
```

### Python code (from DAA_practial02.ipynb)

```python
import time

# Read input (interactive)
list_input = input("Enter a list of numbers separated by spaces (e.g., 10 20 30 40 50): ")
numbers = [int(x) for x in list_input.split()]

target_input = input("Enter the target number to search for: ")
target = int(target_input)

print(f"\nInput list: {numbers}")
print(f"Target value: {target}")

# Linear Search

def linear_search(arr, x):
    for i in range(len(arr)):
        if arr[i] == x:
            return i
    return -1

start_time = time.time()
linear_search_result = linear_search(numbers, target)
end_time = time.time()

if linear_search_result != -1:
    print(f"Linear Search: Element {target} found at index {linear_search_result}")
else:
    print(f"Linear Search: Element {target} not found in the list")
print(f"Time taken by Linear Search: {(end_time - start_time):.6f} seconds")

# Binary Search

def binary_search(arr, low, high, x):
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == x:
            return mid
        elif arr[mid] < x:
            low = mid + 1
        else:
            high = mid - 1
    return -1

sorted_numbers = sorted(numbers)
print(f"\nSorted list for Binary Search: {sorted_numbers}")

start_time = time.time()
binary_search_result = binary_search(sorted_numbers, 0, len(sorted_numbers) - 1, target)
end_time = time.time()

if binary_search_result != -1:
    print(f"Binary Search: Element {target} found at index {binary_search_result} in the sorted list")
else:
    print(f"Binary Search: Element {target} not found in the sorted list")
print(f"Time taken by Binary Search: {(end_time - start_time):.6f} seconds")
```

### Example output (from a sample run)

```
Input list: [59, 67, 89, 34, 43, 22, 10, 0]
Target value: 67
Linear Search: Element 67 found at index 1
Time taken by Linear Search: 0.000052 seconds

Sorted list for Binary Search: [0, 10, 22, 34, 43, 59, 67, 89]
Binary Search: Element 67 found at index 6 in the sorted list
Time taken by Binary Search: 0.000119 seconds
```

### Notes and suggestions

- Binary Search requires the input list to be sorted; the notebook sorts a copy of the list before performing binary search.
- Timings in the example are illustrative and depend on the machine and runtime environment; for meaningful benchmarking use larger inputs and multiple runs (timeit or repeated loops).
- Consider adding additional search algorithms or visualizations for teaching purposes (e.g., step-by-step visualization of binary search splitting).

---

## File Structure
```
DAA-practical01-8847/
├── DAA_practical03.ipynb    # Max-Heap Sort implementation
├── DAA_practical02.ipynb    # Linear and Binary Search
├── DAA_practical01.ipynb    # Sorting algorithms
└── README.md                # This file
```

## Author
**Lasya Jangapelli**

## License
This project is part of the DAA (Design and Analysis of Algorithms) practical coursework.
