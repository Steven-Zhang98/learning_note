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
    """二叉树节点类"""
    def __init__(self, val: int):
        self.val: int = val                # 节点值
        self.left: TreeNode | None = None  # 左子节点引用
        self.right: TreeNode | None = None # 右子节点引用

def list_to_tree_dfs(arr: list[int], i: int) -> TreeNode | None:
    """将列表反序列化为二叉树：递归"""
    # 如果索引超出数组长度，或者对应的元素为 None ，则返回 None
    if i < 0 or i >= len(arr) or arr[i] is None:
        return None
    # 构建当前节点
    root = TreeNode(arr[i])
    # 递归构建左右子树
    root.left = list_to_tree_dfs(arr, 2 * i + 1)
    root.right = list_to_tree_dfs(arr, 2 * i + 2)
    return root

def list_to_tree(arr: list[int]) -> TreeNode | None:
    """将列表反序列化为二叉树"""
    return list_to_tree_dfs(arr, 0)


def level_order(root: TreeNode | None) -> list[int]:
    """层序遍历"""
    # 初始化队列，加入根节点
    queue: deque[TreeNode] = deque()
    queue.append(root)
    # 初始化一个列表，用于保存遍历序列
    res = []
    while queue:
        node: TreeNode = queue.popleft()  # 队列出队
        res.append(node.val)  # 保存节点值
        if node.left is not None:
            queue.append(node.left)  # 左子节点入队
        if node.right is not None:
            queue.append(node.right)  # 右子节点入队
    return res

"""Driver Code"""
if __name__ == "__main__":
    # 初始化二叉树
    # 这里借助了一个从数组直接生成二叉树的函数
    root = list_to_tree(arr=[1, 2, 3, 4, 5, 6, 7])

    # 层序遍历
    res = level_order(root)
    print("\n层序遍历的节点打印序列 = ", res)
```

### Recursion

What is recursion?

How to write recursion code?

What is the relationship between recursion and math?

What is the relationship between memory and breaking problems into smaller problems?
### Iteration

What is iteration?

How to write iteration code?


