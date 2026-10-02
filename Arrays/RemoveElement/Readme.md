# LeetCode 27 - Remove Element

## Problem

Given an integer array `nums` and an integer `val`, remove all occurrences of `val` from the array in-place.

Return the number of elements `k` that are not equal to `val`.

The first `k` elements of `nums` should contain the elements that are not equal to `val`.

The elements after index `k - 1` do not matter.

## Example

### Example 1

Input:

```text
nums = [3,2,2,3]
val = 3
```

Output:

```text
k = 2
```

The first two elements should contain:

```text
[2,2]
```

### Example 2

Input:

```text
nums = [0,1,2,2,3,0,4,2]
val = 2
```

Output:

```text
k = 5
```

The first five elements can contain:

```text
[0,1,3,0,4]
```

The order does not matter.

## Approach

Use two variables:

- `i` → checks every element in the array.
- `k` → keeps track of the position where the next valid element should be stored.

If `nums[i]` is not equal to `val`, keep that element:

```java
nums[k] = nums[i];
```

Then increase `k`:

```java
k++;
```

If `nums[i] == val`, skip it.

## Logic

```text
Start k = 0

For every element:
    If nums[i] != val:
        Store nums[i] at nums[k]
        Increase k

Return k
```

## Dry Run

Input:

```text
nums = [0,1,2,2,3,0,4,2]
val = 2
```

| i | nums[i] | Condition | Action | k |
|---|---:|---|---|---:|
| 0 | 0 | 0 != 2 | Keep 0 | 1 |
| 1 | 1 | 1 != 2 | Keep 1 | 2 |
| 2 | 2 | 2 == 2 | Skip | 2 |
| 3 | 2 | 2 == 2 | Skip | 2 |
| 4 | 3 | 3 != 2 | Keep 3 | 3 |
| 5 | 0 | 0 != 2 | Keep 0 | 4 |
| 6 | 4 | 4 != 2 | Keep 4 | 5 |
| 7 | 2 | 2 == 2 | Skip | 5 |

Final:

```text
k = 5
```

The first five elements contain:

```text
[0,1,3,0,4]
```

## Complexity

**Time Complexity:** `O(n)`

We visit each element once.

**Space Complexity:** `O(1)`

We modify the original array and do not use another array.

## Key Learning

This problem uses the **two-pointer / read-and-write pointer idea**.

```text
i → searches/checks
k → stores valid elements
```

When an element should be kept:

```java
nums[k] = nums[i];
k++;
```
