# Linked List

+ [Reverse Linked List](#reverse-linked-list)
+ [Middle Of The Linked List](#middle-of-the-linked-list)
+ [Palindrome Linked List](#palindrome-linked-list)
+ [Merge two Sorted Lists](#merge-two-sorted-lists)
+ [Remove Nth Node From End Of List](#remove-nth-node-from-end-of-list)
+ [Linked List Cycle](#linked-list-cycle)
+ [Linked List Cycle II](#linked-list-cycle-ii)
+ [Reorder List](#reorder-list)
+ [Intersection Of Two Linked Lists](#intersection-of-two-linked-lists)
+ [Sort List](#sort-list)

## Reverse Linked List

https://leetcode.com/problems/reverse-linked-list/

```python

```

## Middle Of The Linked List

https://leetcode.com/problems/middle-of-the-linked-list/

```python

```

## Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list/

```python

```

## Merge two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists/

```python

```

## Remove Nth Node From End Of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

```python
def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
    root = slow = fast = ListNode()
    slow.next = head
    while n >= 0 and fast:
        fast = fast.next
        n -= 1
    while fast:
        slow, fast = slow.next, fast.next
    slow.next = slow.next.next if slow.next else None
    return root.next

```

## Linked List Cycle

https://leetcode.com/problems/linked-list-cycle/

```python

```

## Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

```python

```

## Reorder List

https://leetcode.com/problems/reorder-list/

```python

```

## Intersection Of Two Linked Lists

https://leetcode.com/problems/intersection-of-two-linked-lists/

```python

```

## Sort List

https://leetcode.com/problems/sort-list/

```python

```
