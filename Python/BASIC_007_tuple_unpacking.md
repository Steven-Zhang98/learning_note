```python
tuple_data = (1,2)
a,b = tuple_data
print(a, b)
```

```python
a, b = b, a
```

In this situation, Python creates a tuple within elements b and a, and then unpacks it and assigns its value to a and b. 

So, if we want to swap Two integers in Array

```python
def swap_integgers(self, A, index1, index2):
	# wirte your code here
	inter = 0
	inter = A[index1]
	A[index1] = A[index2]
	A[index2] = inter
		 
```

It's the same with

```python
def swap_integgers(self, A, index1, index2):
	A[index1], A[index2] = A[index2], A[index1]
```