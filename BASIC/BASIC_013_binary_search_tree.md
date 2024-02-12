---
mindmap-plugin: basic
---

# Binary Search Tree

## Reasoning
- Understanding a Binary Search Tree

 ```python
	  class TreeNode:
	  def __init__(self, value=0, left=None, right=None):
	  self.value = value
	  self.left = left
	  self.right = rightc
	  ```

	- Sub title
		- Problem: Inserting a New Value into the BST
			- BST's property
				- star at root
				- left child
				- right child
				- Repeat

	-
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

	- Sub title
		- Problem: Searching for a Value in the BST
			- decide the direction
		- Sub title
		- Problem: Traversing the BST
			- leaf node
			- a node with one child
			- a node with two children