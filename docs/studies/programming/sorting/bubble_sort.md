# Bubble Sort

Bubble sort is a simple sorting algorithm used to teach sorting and algorithms
in general to students, because of it's simplicity of concept and
implementation. It has this name because of how the sorted elements "bubble" at
the top of the list.

It's average complexity is `O(n^2)`, which is the same as other, more efficient
sorting algorithms, but they generally run faster because the number of swaps
is much lower.

There are ways to optimize the algorithm to make it faster, specially on
already-sorted collections, but in general Insertion Sort should be used in
those cases.

## Animation

![](https://upload.wikimedia.org/wikipedia/commons/c/c8/Bubble-sort-example-300px.gif)

## Complexity

$$ Best: \mathcal{O}(n) \\
Average: \mathcal{O}(n^2) \\
Worst: \mathcal{O}(n^2) \\
Space: \mathcal{O}(n) + \mathcal{O}(1) $$

Because of how inefficient the algorithm is, the number of swaps can vary wildly:

$$ Best: \mathcal{O}(1) \\
Average: \mathcal{O}(n^2) \\
Worst: \mathcal{O}(n^2) $$

## Pseudo-code

```
i ← 0
while i < length(A)
    while j <(length(A) - 1)
      if A[j] > A[j + 1]
        swap A[j + 1] and A[j]
      end if
      j ← j + 1
    end while
    i ← i + 1
end while
```

## Implementation

```rust
pub fn sort<T: Ord>(list: &mut Vec<T>) {
    let len = list.len();
    for _ in 0..len {
        for i in 0..(len - 1) {
            if list[i] > list[i + 1] {
                list.swap(i + 1, i);
            }
        }
    }
}
```
