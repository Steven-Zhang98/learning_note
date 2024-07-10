Imagine you have a large dataset, like a phone book with thousands of names. You need to be able to quickly find a specific name, add new names, and remove outdated ones. If you were to use a simple list, these operations could become very slow as the dataset grows.

```python
class tree
	pass
	def level_order(root: TreeNode):
		queue = [root]
		res = []
		while queue:
			cur_node = queue.pop(0)
			res.append(cur_node)
			if cur_node.left() is not None:
				queue.append(cur_node.left())
			if cur_node.right() is not None:
				queue.append(cur_node.right())
		return res

				
				
		

```
