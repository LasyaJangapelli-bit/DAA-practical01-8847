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

Notes:
- The headlines above are bolded and highlighted as requested; descriptions follow each headline.
- This README now includes the algorithms covered in practicals 01, 02, and 03: sorting algorithms (Bubble, Selection, Insertion, Merge, Quick, Heap) and searching algorithms (Linear, Binary).

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

If you'd like, I can also:
- Add the code as a runnable script (e.g., search_examples.py) in the repository.
- Convert the notebook to a cleaner Markdown file or include output cells inline.
- Update the README title/structure further (table of contents, badges, license).
