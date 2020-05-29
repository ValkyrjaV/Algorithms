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

```

## Invert Binary Tree

https://leetcode.com/problems/invert-binary-tree/

```python

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

```

## Kth Smallest Element In a BST

https://leetcode.com/problems/kth-smallest-element-in-a-bst/

```python

```

## Validate Binary Search Tree

https://leetcode.com/problems/validate-binary-search-tree/

```python

```

## Binary Search Tree Iterator

https://leetcode.com/problems/binary-search-tree-iterator/

```python

```
