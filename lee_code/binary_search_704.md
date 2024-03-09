---
tags:
  - CS
---
## Description

Given an array of integers `nums` which is sorted in ascending order, and an integer `target`, write a function to search `target` in `nums`. If `target` exists, then return its index. Otherwise, return `-1`.

You must write an algorithm with `O(log n)` runtime complexity.

### **Example 1:**

**Input:** nums = [-1,0,3,5,9,12], target = 9
**Output:** 4
**Explanation:** 9 exists in nums and its index is 4

### **Example 2:**

**Input:** nums = [-1,0,3,5,9,12], target = 2
**Output:** -1
**Explanation:** 2 does not exist in nums so return -1

**Constraints:**

- `1 <= nums.length <= 104`
- `-104 < nums[i], target < 104`
- All the integers in `nums` are **unique**.
- `nums` is sorted in ascending order.
## Intuition

This question wants us to find a number in an ordered array. This brings me to consult the dictionary.  
We start from the middle when we want to find a word in the dictionary. 
If the word we want to find is on the page after the middle one, we will then turn to the page between the middle and last pages.

In order to convert the idea into code, I summarised two points:
1. Binary search is in an ordered series; define a search range.
2. Determine the direction by comparing the target and intermediate values.

## Approach



## Complexity

## Code

```python []
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left = 0
        right = len(nums)
        while left <= right:
            mid = left + (right - left) // 2     # integer overflow
            if nums[mid] == target:
                return mid
            if nums[mid] > target:
                right = mid -1
            else:
                left = mid + 1
        return -1
```


```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        def binary_search(left:int, right:int):
            mid = left + (right - left) // 2
            if left > right:
                return -1
            elif nums[mid] == target:
                return mid
            elif nums[mid] > target:
                return binary_search(left,mid - 1)
            else:
                return binary_search(mid+1,right)

        return binary_search(0,len(nums))

```

```python
class Solution:
    def guessNumber(self, n: int) -> int:q
		def binary_search(left, right):
            mid = left + (right - left) // 2
            result = guess(mid)
            if result == 0:
                return mid
            elif result == -1:
                return binary_search(left,mid -1)
            else:
                return binary_search(mid + 1, right)
        return binary_search(1,n)
```



