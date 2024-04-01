---
tags:
  - CS
---
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