---
tags:
  - CS
---
How can we traverse the whole tree?
?

What is the meaning of traversal? 

How to use pictures to show the process of BFS?
![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202403082206273.png)


What is the initial step of the traversal tree in BFS?

What is the meaning of a visit?

What is the meaning of exploration?

What is the repeating step of the traversal tree in BFS?

![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202403082207172.png)

## Implementation

```python
from collections import deque

class TreeNode:
    """Binary tree node class"""
    def __init__(self, val: int):
        self.val: int = val                # value
        self.left: TreeNode | None = None  # left pointer
        self.right: TreeNode | None = None # right pointer
```

```python
def list_to_tree_dfs(arr: list[int], i: int) -> TreeNode | None:
    """ lists to binary trees: recursion """
    # prevent index error
    if i < 0 or i >= len(arr) or arr[i] is None:
        return None
    # build the current node
    root = TreeNode(arr[i])
    # build the left and right tree
    root.left = list_to_tree_dfs(arr, 2 * i + 1)
    root.right = list_to_tree_dfs(arr, 2 * i + 2)
    return root

def list_to_tree(arr: list[int]) -> TreeNode | None:
    """ list into binary tree """
    return list_to_tree_dfs(arr, 0)
```

```python
def level_order(root: TreeNode | None) -> list[int]:
    """ level order traversal """
    # initialise the queue, add root node
    queue: deque[TreeNode] = deque()
    queue.append(root)
    # initialise a list to hold the traversal sequence
    res = []
    while queue:
        node: TreeNode = queue.popleft()  # dequeue 
        res.append(node.val)  # save node value
        if node.left is not None:
            queue.append(node.left)  # left child enqueues
        if node.right is not None:
            queue.append(node.right)  # right child enqueue
    return res

"""Driver Code"""
if __name__ == "__main__":
    # Initialising a binary tree
    # generates a binary tree from an array
    root = list_to_tree(arr=[1, 2, 3, 4, 5, 6, 7])

    # level order traversal
    res = level_order(root)
    print("\n print sequence of nodes in level order traversal = ", res)
```
### Recursion

What is recursion?

How to write recursion code?

What is the relationship between recursion and math?

What is the relationship between memory and breaking problems into smaller problems?
### Iteration

What is iteration?

How to write iteration code?


