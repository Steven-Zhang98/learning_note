0 1 1 2 3 5 8 13 ...

An = An-1 + An-2
## For 

```python
def fbn(num):
	num_0 = 0
	num_1 = 1
	if num == 0:
		return 0
	if num == 1:
		return 1
	else:
		i = num - 1
		while i > 0:
		result = num_0 + num_1
		num_1 = result
		num_0 = num_1
		i -= 1 
	return result
print(fbn(10))
```
如何储存 An-2 和 An - 1 的值并把他赋给 An？

上一步求出来的 a 会作为下一步的参数穿进去，再加上，上上一步传入的 a，所以我们要引出一个新的变量
result = j

什么是变量？
## 递归

```python
def fbn(num):
	if num <= 1
		return num
	else:
		num_n = fbn(num-1) + fbn(num-2)
```

[[实现斐波那契数列过程中，记忆容量不足导致推不出规律，最后用写在纸上解决]]

[[斐波那契数列是张老师对循环和递归的理解，如何形成自己的理解]]

## 中间变量

Stackoverflow

Temporary variable

Function call

