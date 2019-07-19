# Insertion Sort

Insertion sort is very similar to Selection Sort, and as in it, after `k`
passes on the loop, the first `k` elements are in sorted order. The
difference however is that for selection sort, those are the `k` smallest
elements in the unsorted input, while in selection sort they are simply the
first `k` elements of the input.

The advantage of this change is that selection sort must always scan all
remaining elements to find the smallest one in the unsorted portion of the
list, while insertion sort only requires a single comparison when the `k +
1`th element is greater than the `k`th element.

When this is frequently true, in cases where the list is fully or partially
sorted, insertion sort requires about half as many comparisons as selection
sort, while on the worst case (when the input is reverse-sorted), it has to
do the same number of passes as selection sort.

However, in general insertion sort writes to the list `O(n^2)` times, and
selection sort will write only `O(n)` times, which makes it a bad option for
cases where writing to memory is significantly more expensive than reading,
such as when sorting things from disk.

## Complexity

$$ Best: O(n), Average: O(n^2), Worst: O(n^2), Space: O(n) + O(1) $$

## Implementation


