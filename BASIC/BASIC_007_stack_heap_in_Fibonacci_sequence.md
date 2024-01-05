Consider a simple function that calculates the factorial of a number

```python
def factorial(n):
	if n == 1:
		return 1
	else:
		return n * factorial(n - 1)

print(factorial(5))
```

## Memory stack

![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202401052229770.png)
Stack is a last-in-first-out (LIFO) memory structure used for storing functions and variables. In this code, if we want to compute the factorial of the (5) number, we have to store 5 stack frames in the memory (factorial (5), factorial (4), factorial (3), factorial (2), and factorial (1)), factorial (1) is the last function push in the stack but it's the first function pop out of the stack, because factorial (1) is the base case.  

## Stack overload

But if we have too many nested function calls, the stack memory will exhausted. This is called stack overflow. Sometimes, we use memoisation or non-recursive solutions to avoid stack overflow. 

## Memory heap

```python
def factorial(n,memo):
	def recursion(n):
		if n in memo:
			return memo[n]
		else:
			memo[n] = n * factorial(n - 1,memo) 
		return memo[n]
	if n == 1:
		return 1
	else:
		return recursion(n)

memo = {}
print(factorial(5,memo))
```

Heap memory is a flexible memory structure for storing data structures like dictionaries and lists. The memo is stored in heap memory in this code and can be shared with all functions, and be allowed to have dynamic size. When no function uses memo, python automatically clears the memo. 

