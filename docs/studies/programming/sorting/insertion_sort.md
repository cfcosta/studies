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

## Animation

![](https://upload.wikimedia.org/wikipedia/commons/0/0f/Insertion-sort-example-300px.gif)

## Complexity

$$ Best: \mathcal{O}(n) \\
Average: \mathcal{O}(n^2) \\
Worst: \mathcal{O}(n^2) \\
Space: \mathcal{O}(n) + \mathcal{O}(1) $$

## Pseudo-code

```
i ← 1
while i < length(A)
    j ← i
    while j > 0 and A[j-1] > A[j]
        swap A[j] and A[j-1]
        j ← j - 1
    end while
    i ← i + 1
end while
```

## Implementation

```rust
pub fn sort<T: Ord>(list: &mut Vec<T>) {
    for i in 1..list.len() {
        let mut j = i;

        while j > 0 && list[j - 1] > list[j] {
            list.swap(j, j - 1);
            j = j - 1;
        }
    }
}
```
