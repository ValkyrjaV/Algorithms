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
def sortList(self, head: ListNode) -> ListNode:
    def merge(l1: ListNode, l2: ListNode) -> ListNode:
        copy = ans = ListNode()
        while l1 and l2:
            if l1.val <= l2.val:
                copy.next, l1 = l1, l1.next
            else:
                copy.next, l2 = l2, l2.next
            copy = copy.next
        if l1:
            copy.next = l1
        else:
            copy.next = l2
        return ans.next

    def merge_sort(head: ListNode) -> ListNode:
        if not head or not head.next:
            return head
        slow = fast = head
        prev = None
        while fast and fast.next:
            prev, slow, fast = slow, slow.next, fast.next.next
        prev.next = None
        left = merge_sort(head)
        right = merge_sort(slow)
        return merge(left, right)
    return merge_sort(head)

```
