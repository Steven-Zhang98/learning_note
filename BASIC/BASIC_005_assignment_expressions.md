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