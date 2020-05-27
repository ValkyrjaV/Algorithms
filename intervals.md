# Intervals

+ [Insert Interval](#insert-interval)
+ [Merge Intervals](#merge-intervals)
+ [Non-overlapping Intervals](#non-overlapping-intervals)

## Insert Interval

https://leetcode.com/problems/insert-interval/

```python
def insert(self, intervals, newInterval):
    mid = [newInterval[0], newInterval[1]]
    left = []
    right = []

    for elem in intervals: 
        if elem[1] < mid[0]: 
            left.append(elem)
        elif interv[0] > mid[1]: 
            right.append(elem)
        else: 
            mid[0] = min(elem[0], mid[0])
            mid[1] = max(elem[1], mid[1])
    return left + [mid] + right

```

## Merge Intervals

https://leetcode.com/problems/merge-intervals/

```python

```

## Non-overlapping intervals

https://leetcode.com/problems/non-overlapping-intervals

```python

```
