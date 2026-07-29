# DAA-practical01-8847

Brief, readable descriptions of five common sorting algorithms used in this practical.

## Bubble Sort
- Repeatedly compares adjacent elements and swaps them if out of order until the list is sorted.
- Time: O(n^2) worst/average, O(n) best. Space: O(1). Stable, in-place.

## Selection Sort
- Selects the minimum (or maximum) element from the unsorted portion and moves it to the front.
- Time: O(n^2) for all cases. Space: O(1). In-place, not stable by default.

## Insertion Sort
- Builds the sorted list one element at a time by inserting each item into its correct position.
- Time: O(n^2) worst/average, O(n) best (nearly sorted). Space: O(1). Stable, in-place.

## Merge Sort
- Divide-and-conquer: split the list, sort halves, then merge them.
- Time: O(n log n) all cases. Space: O(n). Stable, needs extra space.

## Quick Sort
- Picks a pivot, partitions elements around it, then recursively sorts partitions.
- Time: O(n log n) average, O(n^2) worst (bad pivot). Space: O(log n) average. In-place typically, not stable.
