Pass by Value: In this type of pass, what is passed to the function is a copy of the value of the variable. Any changes made to the value inside the function will not affect the original data.
Pass by Reference: In this method, a reference to the variable, i.e., a memory address, is passed. Therefore, any changes made within the function are directly reflected in the original data.

```python
def modify_list(lst):
    lst.append(100)  # This modifies the original list because lists are mutable

def modify_number(num):
    num += 100  # This does not affect the original variable because integers are immutable

# List example
original_list = [1, 2, 3]
print("Before modify_list:", original_list)
modify_list(original_list)
print("After modify_list:", original_list)

# Integer example
original_number = 5
print("Before modify_number:", original_number)
modify_number(original_number)
print("After modify_number:", original_number)

```