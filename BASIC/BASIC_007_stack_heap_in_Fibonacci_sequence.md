```python
def investment_growth_model(n,j,initial_sequence)
	memo = {i:initial_sequence[i] for i in range(j)}
	def inner_recursion(n):
		if n in memo:
			return memo[n]
		else:
			total = 0
			for i in range(1,j+1):
				total += inner_recursion(n - i)
			memo[n] = total
			return total
	if n < j:
		return memo[n]
	else:
		return inner_recursion(n)
```

## memory stack


![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202401022200284.png)

Consider a simple function that calculates the sum of two numbers:

```python
Def add (a, b):
    Result = a + b  # 'result' is a local variable
    Return result
```
When add is called, a stack frame is created for it. The local variable result is stored in this frame. Once add finishes executing, its stack frame, including the result variable, is automatically removed from the stack.
## 作用域(out of scope)

## 栈溢出 stack overflow

## 什么是内存堆 memory heap