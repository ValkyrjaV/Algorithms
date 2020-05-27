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
def threeSum(self, nums):
    counter = Counter(nums)
    if counter[0] < 3:
        result = []
    else:
        result = [(0, 0, 0)]
    negative = []
    positive = []
    for elem in counter:
        if elem <= 0:
            negative.append(elem)
        else:
            positive.append(elem)
    for neg in negative:
        for pos in positive:
            elem = -neg-pos
            if elem in counter:
                if elem in {neg, pos} and counter[elem] > 1 or \
                        neg < elem < pos:
                    result.append((neg, elem, pos))
    return result

```

## Subarray Sum Equals k

https://leetcode.com/problems/subarray-sum-equals-k/

```python

```
