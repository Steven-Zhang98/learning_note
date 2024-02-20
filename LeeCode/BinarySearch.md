---
tags:
  - CS
---

```python
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

## Guess Number Higher or Lower

