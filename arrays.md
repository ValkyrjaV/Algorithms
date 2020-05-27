# Arrays

+ [Two Sum](#two-sum)
+ [3Sum](#3sum)
+ [Subarray Sum Equals k](#subarray-sum-equals-k)

## Two Sum

https://leetcode.com/problems/two-sum/

```python
def twoSum(nums: List[int], target: int) -> List[int]:
    hash = {}
    for diff, value in enumerate(nums):
        if (target - value) in hash:
            return [hash[target - value], diff]
        if value not in hash:
            hash[value] = diff

```

## 3Sum

https://leetcode.com/problems/3sum/

```python

```

## Subarray Sum Equals k

https://leetcode.com/problems/subarray-sum-equals-k/

```python

```
