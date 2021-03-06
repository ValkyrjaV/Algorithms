# Tree

+ [Binary Tree Inorder Traversal](#binary-tree-inorder-traversal)
+ [Symmetric Tree](#symmetric-tree)
+ [Maximum Depth Of Binary Tree](#maximum-depth-of-binary-tree)
+ [Same Tree](#same-tree)
+ [Invert Binary Tree](#invert-binary-tree)
+ [Path Sum](#path-sum)
+ [Binary Tree Level Order Traversal](#binary-tree-level-order-traversal)
+ [Subtree Of Another Tree](#subtree-of-another-tree)
+ [Kth Smallest Element In a BST](#kth-smallest-element-in-a-bst)
+ [Validate Binary Search Tree](#validate-binary-search-tree)
+ [Binary Search Tree Iterator](#binary-search-tree-iterator)

## Binary Tree Inorder Traversal

https://leetcode.com/problems/binary-tree-inorder-traversal/

```python
def inorderTraversal(self, root: TreeNode) -> List[int]:
    stack = []
    answer = []
    while stack or root:
        while root:
            stack.append(root)
            root = root.left
        root = stack.pop()
        answer.append(root.val)
        root = root.right
    return answer

```

## Symmetric Tree

https://leetcode.com/problems/symmetric-tree/

```python
def isSymmetric(self, root: 'TreeNode') -> 'bool':
    if root is None:
        return True
    stack = [(root.left, root.right)]
    while stack:
        rightnode, leftnode = stack.pop()
        if not rightnode and not leftnode:
            continue
        if not rightnode or not leftnode:
            return False
        if rightnode.val != leftnode.val:
            return False
        stack.append((rightnode.left, leftnode.right))
        stack.append((rightnode.right, leftnode.left))
    return True

```

## Maximum Depth Of Binary Tree

https://leetcode.com/problems/maximum-depth-of-binary-tree/

```python
# Solution №1
def maxDepth(self, root: TreeNode) -> int:
    if root is None:
        return 0
    queue = []
    queue.append(root)
    depth = 0
    while queue:
        l = len(queue)
        for _ in range(l):
            root = queue.pop(0)
            if root.left:
                queue.append(root.left)
            if root.right:
                queue.append(root.right)
        depth += 1
    return depth

# Solution №2
def maxDepth(self, root: TreeNode) -> int:
    if root is None:
        return 0
    return max(self.maxDepth(root.left), self.maxDepth(root.right)) + 1

```

## Same Tree

https://leetcode.com/problems/same-tree/

```python
def isSameTree(self, p: 'TreeNode', q: 'TreeNode') -> 'bool':
    if p and q:
        return p.val == q.val and self.isSameTree(p.left, q.left) and \
            self.isSameTree(p.right, q.right)
    else:
        return p is q

```

## Invert Binary Tree

https://leetcode.com/problems/invert-binary-tree/

```python
def invertTree(self, root: TreeNode) -> TreeNode:
    if root is None:
        return root
    root.right, root.left = root.left, root.right
    self.invertTree(root.right)
    self.invertTree(root.left)
    return root

```

## Path Sum

https://leetcode.com/problems/path-sum/

```python
def hasPathSum(self, root: 'TreeNode', total: 'int') -> 'bool':
    if not root:
        return False
    elif (not root.left and not root.right and root.val == total):
        return True
    else:
        return (self.hasPathSum(root.left, total - root.val) or
                self.hasPathSum(root.right, total - root.val))

```

## Binary Tree Level Order Traversal

https://leetcode.com/problems/binary-tree-level-order-traversal/

```python
def levelOrder(self, root: TreeNode) -> List[List[int]]:
    result = []
    if root is None:
        return result
    queue = [root]
    while queue:
        level = []
        qsize = len(queue)
        for _ in range(qsize):
            node = queue.pop(0)
            if node is not None:
                level.append(node.val)
                if node.left:
                    queue.append(node.left)
                if node.right:
                    queue.append(node.right)
        result.append(level)
    return result

```

## Subtree Of Another Tree

https://leetcode.com/problems/subtree-of-another-tree/

```python
# Solution №1
def isSubtree(self, s: 'TreeNode', t: 'TreeNode') -> 'bool':

    def is_same(s, t):
        if s and t:
            return s.val == t.val and is_same(s.left, t.left) and \
                is_same(s.right, t.right)
        else:
            return s is t

    stack = s and [s]
    while stack:
        node = stack.pop()
        if node:
            if is_same(node, t):
                return True
            stack.append(node.right)
            stack.append(node.left)
    return False

# Solution №2
def isSubtree(self, s: TreeNode, t: TreeNode) -> bool:
    if s and t:
        return self.is_same(s, t) or self.isSubtree(s.left, t) or \
            self.isSubtree(s.right, t)
    return s is t


def is_same(self, s: TreeNode, t: TreeNode) -> bool:
    if s and t:
        return s.val == t.val and self.is_same(s.left, t.left) and \
            self.is_same(s.right, t.right)
    return s is t

```

## Kth Smallest Element In a BST

https://leetcode.com/problems/kth-smallest-element-in-a-bst/

```python
# Solution №1
def kthSmallest(self, root: TreeNode, k: int) -> int:
    stack = []
    result = [float("+infinity")]*k
    while stack or root:
        while root:
            stack.append(root)
            root = root.left
        root = stack.pop()
        if root.val < max(result):
            result.sort()
            result[k-1] = root.val
        root = root.right
    return result.pop()

# Solution №2
def flattening(self, root: TreeNode) -> List[int]:
    if root:
        return self.flattening(root.left) + [root.val] + self.flattening(root.right)
    return []

def kthSmallest(self, root: TreeNode, k: int) -> int:
    flattree = self.flattening(root)
    return flattree[k - 1]
    
# Solution №3
def kthSmallest(self, root: TreeNode, k: int) -> int:
    stack = []
    curNode = root
    while curNode or stack:
        while curNode:
            stack.append(curNode)
            curNode = curNode.left
        curNode = stack.pop()
        k -= 1
        if k == 0:
            return curNode.val
        curNode = curNode.right

```

## Validate Binary Search Tree

https://leetcode.com/problems/validate-binary-search-tree/

```python
def helper(self, root, left=float('-inf'), right=float('inf')):
    """
    :type root: TreeNode
    :rtype: bool
    """
    if root is None:
        return True
    if not left < root.val < right:
        return False
    return self.helper(root.left, left, root.val) and \
        self.helper(root.right, root.val, right)


def isValidBST(self, root: TreeNode) -> bool:
    return self.helper(root)

```

## Binary Search Tree Iterator

https://leetcode.com/problems/binary-search-tree-iterator/

```python
class BSTIterator:
    def __init__(self, root: TreeNode):
        self.nodes = []
        self.traverse(root)

    def traverse(self, root):
        if not root:
            return
        self.traverse(root.left)
        self.nodes.append(root.val)
        self.traverse(root.right)

    def next(self) -> int:
        return self.nodes.pop(0)

    def hasNext(self) -> bool:
        return self.nodes

```
