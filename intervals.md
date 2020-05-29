# Intervals

+ [Insert Interval](#insert-interval)
+ [Merge Intervals](#merge-intervals)
+ [Non-overlapping Intervals](#non-overlapping-intervals)

## Insert Interval

https://leetcode.com/problems/insert-interval/

```python

```

## Merge Intervals

https://leetcode.com/problems/merge-intervals/

```python

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
