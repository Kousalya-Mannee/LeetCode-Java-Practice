# LeetCode-Java-Practice
My Java DSA and LeetCode practice
# LeetCode 26 - Remove Duplicates from Sorted Array

## Problem

Given a sorted integer array, remove duplicates in-place so that each unique element appears only once.

Return the number of unique elements `k`.

## Approach

The array is sorted in non-decreasing order, so duplicate elements are next to each other.

I use two variables:

- `i` → checks each element
- `k` → position where the next unique element should be placed

If `nums[i]` is different from `nums[i - 1]`, it is a unique element.

```java
if (nums[i] != nums[i - 1])
{
    nums[k] = nums[i];
    k++;
}
