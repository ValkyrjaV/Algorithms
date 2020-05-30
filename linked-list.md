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
def middleNode(self, head: 'ListNode') -> 'ListNode':
    fast = slow = head
    while fast and fast.next:
        slow, fast = slow.next, fast.next.next
    return slow

```

## Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list/

```python
def isPalindrome(self, head: ListNode) -> bool:
    reverse = None
    slow = fast = head
    while fast and fast.next:
        fast = fast.next.next
        reverse, reverse.next, slow = \
            slow, reverse, slow.next
    if fast:
        slow = slow.next
    while reverse and reverse.val == slow.val:
        slow = slow.next
        reverse = reverse.next
    return not reverse

```

## Merge two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists/

```python

```

## Remove Nth Node From End Of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

```python

```

## Linked List Cycle

https://leetcode.com/problems/linked-list-cycle/

```python
def hasCycle(self, head):
    slow = fast = head
    while fast and fast.next:
        slow, fast = slow.next, fast.next.next
        if fast is slow:
            return True
    return False

```

## Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

```python
def detectCycle(self, head):
    fast = slow = head
    while fast and fast.next:
        slow, fast = slow.next, fast.next.next
        if slow is fast:
            while head is not slow:
                head, slow = head.next, slow.next
            return head
    return None

```

## Reorder List

https://leetcode.com/problems/reorder-list/

```python

```

## Intersection Of Two Linked Lists

https://leetcode.com/problems/intersection-of-two-linked-lists/

```python
def getIntersectionNode(self, headA, headB):
    pointerA, pointerB = headA, headB
    while pointerA is not pointerB:
        if pointerA:
            pointerA = pointerA.next
        else:
            pointerA = headB
        if pointerB:
            pointerB = pointerB.next
        else:
            pointerB = headA
    return pointerA

```

## Sort List

https://leetcode.com/problems/sort-list/

```python

```
