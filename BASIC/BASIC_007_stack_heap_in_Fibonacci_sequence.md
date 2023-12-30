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

## 作用域(out of scope)

## 栈溢出 stack overflow

## 什么是内存堆 memory heap