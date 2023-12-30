```python
def f(x):

    return x + 4

numbers = [3, 7, 2, 9, 12]

old_numbers = []

for x in numbers:

	if f(x) % 2:

	old_numbers.append(f(x)) 

print(old_numbers)
```

Equal to:

```python
def f(x):
	return x + 4

numbers = [3, 7, 2, 9, 12]

old_numbers = [result for x in numbers if (result := f(x)) % 2]

print(old_numbers)

```
