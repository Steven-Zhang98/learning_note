---
in: 
up: 
down: 
related: 
opposite: 
Create: 
by: 
due-date: 
rank: 
tags:
  - Incubation🌱
---
An ordered collection of any objects because all the elements are references.

```python
list_1 = [12, 15, 'hello world', ['a', 'b'], True]  
for i in list_1:  
    print(i, type(i))
```

## CRUD
### Create
```python
list_2 = list_1 + list_1

print(list_1 * 3)

list_2.append('fanfan')

list_2.insert(1, 'xixi')

list_1.extend(list_1)

# list_1 have changed

print(list_1)

```

### Read

```python
list_2[1:3]
list_2[:-2]

2 in list_2

if 2 in list_2:
	print(list_2.index(2))

list_2.count(2)

```
### Update
```python
list_2[2] = 100
list_2[:-2] = []
# index 1 is the last one, so 1 is not included
list_2[:1] = [1,1,2,3,4]

```

### Delete

```python
# index and return
list_2.pop(1)
# value
list_2.remove(4)

del list_2[1:5]

```

## List Manipulation

```python
result = [i for i in range(101) if i % 5 == 0]

result = [i **2 for in in range(10)]
```

## Incubation area

What is the list in Python?
?
The list is an ordered data structure that can store any object; the list can create, update, read, and delete elements.
<!--SR:!2024-04-26,4,270--> 