Pass by Value: In this type of pass, what is passed to the function is a copy of the value of the variable. Any changes made to the value inside the function will not affect the original data.
Pass by Reference: In this method, a reference to the variable, i.e., a memory address, is passed. Therefore, any changes made within the function are directly reflected in the original data.

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

- pass by reference
![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202404221029372.png)

