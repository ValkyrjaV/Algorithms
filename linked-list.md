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
# Solution №1
def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
    if not l1 or not l2:
        return l1 or l2
    if l1.val < l2.val:
        l1.next = self.mergeTwoLists(l1.next, l2)
        return l1
    else:
        l2.next = self.mergeTwoLists(l1, l2.next)
        return l2

# Solution №2
def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
    merge = pointer = ListNode()
    while l1 and l2:
        if l1.val < l2.val:
            pointer.next = l1
            l1 = l1.next
        else:
            pointer.next = l2
            l2 = l2.next
        pointer = pointer.next

    if l1:
        pointer.next = l1
    elif l2:
        pointer.next = l2
    return merge.next

```

## Remove Nth Node From End Of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

```python
def removeNthFromEnd(self, head, n):
    fast = slow = head
    for _ in range(n):
        fast = fast.next
    if fast is None:
        return head.next
    while fast.next:
        fast = fast.next
        slow = slow.next
    slow.next = slow.next.next
    return head

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
# Solution №1
def reorderList(self, head: ListNode) -> None:
    queue = []
    cur = head
    while cur:
        queue.append(cur)
        cur = cur.next
    reverse = None
    while queue:
        node = queue.pop(0)
        if reverse:
            reverse.next = node
            node.next = None
        if queue:
            reverse = queue.pop()
            reverse.next = None
            node.next = reverse
            
# Solution №2
def reorderList(self, head: ListNode) -> None:
    if head is None:
        return

    fast = slow = head
    while fast and fast.next:
        fast = fast.next.next
        slow = slow.next

    reverse = None
    while slow:
        node = slow.next
        slow.next = reverse
        reverse, slow = slow, node

    start = head
    while reverse.next:
        tmp, start.next = start.next, reverse
        start, tmp = tmp, reverse.next
        reverse.next = start
        reverse = tmp

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
