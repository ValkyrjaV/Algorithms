# Arrays

+ [Two Sum](#two-sum)
+ [3Sum](#3sum)
+ [Subarray Sum Equals k](#subarray-sum-equals-k)

## Two Sum

https://leetcode.com/problems/two-sum/

```python

```

## 3Sum

https://leetcode.com/problems/3sum/

```python

```

## Subarray Sum Equals k

https://leetcode.com/problems/subarray-sum-equals-k/

```python
def subarraySum(self, nums: List[int], k: int) -> int:
    hash = {0: 1}
    index = 0
    count = 0
    for elem in nums:
        index = index + elem
        diff = index - k
        if diff in hash:
            count += hash[diff]
        hash[index] = hash.setdefault(index, 0) + 1
    return count

```
