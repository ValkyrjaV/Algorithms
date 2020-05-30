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
        elif elem[0] > mid[1]: 
            right.append(elem)
        else: 
            mid[0] = min(elem[0], mid[0])
            mid[1] = max(elem[1], mid[1])
    return left + [mid] + right

```

## Merge Intervals

https://leetcode.com/problems/merge-intervals/

```python
def merge(self, intervals: List[List[int]]) -> List[List[int]]:
    ans = []
    sort_interval = sorted(intervals, key=lambda x: x[0])
    for interval in sort_interval:
        if ans and interval[0] <= ans[-1][1]:
            ans[-1][1] = max(ans[-1][1], interval[1])
        else:
            ans += [interval]
    return ans

```

## Non-overlapping intervals

https://leetcode.com/problems/non-overlapping-intervals

```python
def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
    if not intervals:
        return 0
    intervals.sort(key=lambda interval: interval[-1])
    count = len(intervals) - 1
    border = intervals[0][-1]
    for elem in intervals:
        if elem[0] >= border:
            count -= 1
            border = elem[-1]
    return count

```
