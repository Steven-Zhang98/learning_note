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
Assign a value to a variable and pass parameters to function both copy the address.

- change reference vs change object



```python
list_1 = [1,2,3,4]
list_2 = list_1 
list_2[0] = 100
print(id(list_1), id(list_2))

num_1 = 10
num_2 = num
num_2 = 20
print(id(num_1), id(num_2))

```

- change the object
![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202404221029372.png)

- change the reference

![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202404221103057.png)

## Tuple store the address
 ![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202404221057813.png)
```python
tuple_1 = (1,2,'abc', [3,4], 12.3, True)
tuple_1[3].append(5)
print(tuple_1)
```


```python
tuple_1 = (1,2,'abc', [3,4], 12.3, True)
# error
tuple_1[3] = [3,4,5]
```

## Pass by value or pass by object

Pass by Value: In this type of pass, what is passed to the function is a copy of the variable's value. Any changes made to the value inside the function will not affect the original data.

Pass by Reference: In this method, a reference to the variable, i.e., a memory address, is passed. Therefore, the original data directly reflects any changes made within the function.

```python
# Immutable object: behaves like pass by value
def increment(x):
    x += 1  # This creates a new object, does not affect the original x
    return x

# Mutable object: behaves like pass by reference
def append_value(lst):
    lst.append(42)  # This modifies the original list in place


if __name__ == "__main__":
    # Test with immutable object
    a = 1
    new_a = increment(a)
    print("Original 'a':", a)  # Should still be 1
    print("Incremented 'a':", new_a)  # Should be 2
    
    # Test with mutable object
    my_list = [1, 2, 3]
    append_value(my_list)
    print("Modified list:", my_list)  # Should now contain [1, 2, 3, 42]

```

## Incubation area