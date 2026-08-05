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
