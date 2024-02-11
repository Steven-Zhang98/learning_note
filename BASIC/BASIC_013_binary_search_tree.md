---
mindmap-plugin: basic
---
# Binary Search Tree

## Reasoning

### Understanding a Binary Search Tree
	data structure
	lookup
		- addition
		- Removal
		
	- node
		- value
		- two children
	- key property
		- left subtree
		- node's value
		- right subtree
	- BST property be maintained
		- Class node
```python
class TreeNode:
    def __init__(self, value=0, left=None, right=None):
        self.value = value
        self.left = left
        self.right = rightc
```
- Problem: Inserting a New Value into the BST
	- BST's property
		- star at root
		- left child
		- right child
		- Repeat
```python
def insert_into_bst(root, value):
    if root is None
        return TreeNode(value)
    if value < root.value:
        root.left = insert_into_bst(root.left, value)
    else:
        root.right = insert_into_bst(root.right, value)
    return root 
```

- Problem: Searching for a Value in the BST
- 
- Problem: Traversing the BST
	- leaf node
	- a node with one child
	- a node with two children

## The definition of the binary search tree
- Code ^24d2376b-d6a1-7f23

## Fundamental Components

## Member Variables Reasoning

## Insertion
Explain the text below like I'm five：
## Conclusion