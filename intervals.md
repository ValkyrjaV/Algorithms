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
def merge(self, intervals: List[List[int]]) -> List[List[int]]:
    ans = []
    sort = sorted(intervals, key=lambda x: x[0])
    for i in sort:
        if ans and i[0] <= ans[-1][1]:
            ans[-1][1] = max(ans[-1][1], i[1])
        else:
            ans += i,
    return ans

```

## Non-overlapping intervals

https://leetcode.com/problems/non-overlapping-intervals

```python

```
