---
mindmap-plugin: basic
---

# Sub title

## Reasoning
- Understanding a Binary Search Tree
	- data structure
		- lookup
		- addition
		- removal
	- node
		- value
		- two children
	- key property
		- left subtree
		- node's value
		- right subtree
	- BST property be maintained
		- Class node
- Problem: Inserting a New Value into the BST
	- BST's property
		- star at root
		- left child
		- right child
		- repeat
- Problem: Searching for a Value in the BST
- Problem: Traversing the BST

## The definition of the binary search tree
- Code ^24d2376b-d6a1-7f23

  ```python
class TreeNode:
	def __init__(self, val):
	  self.val = val
	  self.left = None
	  self.right = None
	  
class BinarySearchTree:
	def __init__(self, root_val):
	  self.root = TreeNode(root_val)
	  
	def insert(self, val):
	  self._insert(self.root, val)
	  
	def _insert(self, root, val):
	  if val > root.val:
if root.right is None:
	  root.right = TreeNode(val)
	  else:
	  self._insert(root.right, val)
	  else:
	  if root.left is None:
	  root.left = TreeNode(val)
	  else:
	  self._insert(root.left, val)
	  
	  def print_in_order(self):
	  print("In order visit:")
	  self._in_order_visit(self.root)
	  
	  def _in_order_visit(self, root):
	  if root is not None:
	  self._in_order_visit(root.left)
	  print("Visiting:", root.val)
	  self._in_order_visit(root.right)
	  
	  def print_pre_order(self):
	  print("Pre order visit:")
	  self._pre_order_visit(self.root)
	  
	  def _pre_order_visit(self, root):
	  if root is not None:
	  print("Visiting:", root.val)
	  self._pre_order_visit(root.left)
	  self._pre_order_visit(root.right)
	  
	  # Main execution
	  if __name__ == "__main__":
	  tree = BinarySearchTree(5)
	  tree.insert(4)
	  tree.insert(3)
	  tree.insert(6)
	  tree.print_in_order()
	  tree.print_pre_order()
	  print("Done")
	  
	  ```


## Fundamental Components

## Member Variables Reasoning

## Insertion

## Conclusion