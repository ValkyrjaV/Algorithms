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
    sorted_nums = [elem for elem in enumerate(nums)]
    sorted_nums.sort(key=lambda elem: elem[1])
    left = 0
    right = len(nums) - 1
    while left != right:
        if sorted_nums[left][1] + sorted_nums[right][1] == target:
            return [sorted_nums[left][0], sorted_nums[right][0]]
        elif sorted_nums[left][1] + sorted_nums[right][1] < target:
            left += 1
        else:
            right -= 1

```

## 3Sum

https://leetcode.com/problems/3sum/

```python
# Solutions №1
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

# Solutions №2
def threeSum(self, nums: List[int]) -> List[List[int]]:
    result = []
    nums.sort()
    length = len(nums)
    if length < 3:
        return ans
    for i in range(2, length):
        if i < length - 1 and nums[i] == nums[i+1]:
            continue
        left = 0
        right = i - 1
        while left != right:
            if nums[left] + nums[right] == -nums[i]:
                result.append([nums[left], nums[right], nums[i]])
                leftval = nums[left]
                rightval = nums[right]
                while left != right and nums[left] == leftval:
                    left += 1
                while left != right and nums[right] == rightval:
                    right -= 1
            elif nums[left] + nums[right] < -nums[i]:
                left += 1
            else:
                right -= 1
    return result

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
