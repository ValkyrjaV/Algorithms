# Arrays

+ [Two Sum](#two-sum)
+ [3Sum](#3sum)
+ [Subarray Sum Equals k](#subarray-sum-equals-k)

## Two Sum

https://leetcode.com/problems/two-sum/

```python
# Solution №1
def twoSum(nums: List[int], target: int) -> List[int]:
    hash = {}
    for diff, value in enumerate(nums):
        if (target - value) in hash:
            return [hash[target - value], diff]
        if value not in hash:
            hash[value] = diff

# Solution №2
def twoSum(self, nums: List[int], target: int) -> List[int]:
    nums = [elem for elem in enumerate(nums)]
    nums.sort(key=lambda elem: elem[1])
    left = 0
    right = len(nums) - 1
    while left != right:
        if nums[left][1] + nums[right][1] == target:
            return [nums[left][0], nums[right][0]]
        elif nums[left][1] + nums[right][1] < target:
            left += 1
        else:
            right -= 1

```

## 3Sum

https://leetcode.com/problems/3sum/

```python

```

## Subarray Sum Equals k

https://leetcode.com/problems/subarray-sum-equals-k/

```python

```
