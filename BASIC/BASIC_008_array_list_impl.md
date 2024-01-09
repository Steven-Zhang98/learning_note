---
tags:
  - CS
---
```python
class ArrayList:
    def __init__(self):
        self.m_array = [None] * 2  # default size = 2
        self.m_size = 0
        print(f"ArrayList init size: {len(self.m_array)}")

    def add(self, val):
        if self.m_size >= len(self.m_array):
            print("auto resizing")
            new_array = [None] * (len(self.m_array) * 2)
            for i in range(len(self.m_array)):
                new_array[i] = self.m_array[i]
            self.m_array = new_array
            print(f"ArrayList updated size: {len(new_array)}")

        self.m_array[self.m_size] = val
        self.m_size += 1

    def get(self, idx):
        if idx < 0 or idx >= self.m_size:
            print(f"idx out of range: {idx}")
            return None
        return self.m_array[idx]

    def delete(self, idx):
        if 0 <= idx < self.m_size:
            self.m_array[idx] = None  # This doesn't actually remove the item, just sets it to None
            self.m_size -= 1

    def size(self):
        return self.m_size


# Testing the ArrayList class
if __name__ == "__main__":
    array_list = ArrayList()

    # Basic test
    array_list.add(100)
    get_val = array_list.get(0)
    print(f"get val from ArrayList: {get_val}")
    print(f"ArrayList size: {array_list.size()}")

    array_list.add(101)
    get_val = array_list.get(1)
    print(f"get val from ArrayList: {get_val}")
    print(f"ArrayList size: {array_list.size()}")

    # idx out of range
    get_val = array_list.get(2)

    # auto resize
    array_list.add(103)
    get_val = array_list.get(2)
    print(f"get val from ArrayList: {get_val}")
    print(f"ArrayList size: {array_list.size()}")

    print("done")

```

ArrayList can adjust its size dynamically because it distinguishes between the capacity of a list and its actual size. 

ArrayList has two member variables: size, which represents the number of elements the ArrayList actually contains at the moment, and size - 1 is the last element index in ArrayList. The other one is capacity, representing the total number of elements the ArrayList can hold. Len (self. M_array) represents the array's capacity. 

![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202401071033782.png)


We must check if there is enough capacity (`size < capacity`) before we add new elements to the ArrayList. When the list has been filled, we create a new list and double its length. And add the original elements to the new list. 

![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202401071035518.png)

When we want to delete the elements in the list, we find the element's index and set it to none and size minus 1. 

![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202401071036439.png)

## Upgraded

```python
class ArrayList:
    def __init__(self) :
        self.m_size = 0
        self.m_list = [None] * 2   
    
    def add(self,val):
        if self.m_size >= len(self.m_list):
            print("ArrayList auto resizing")
            new_list = [None] * (len(self.m_list) * 2)
            for i in range(len(self.m_list)):
                new_list[i] = self.m_list[i]
            self.m_list = new_list 

        self.m_list[self.m_size] = val
        self.m_size += 1

    def delete(self,idx):
        if idx < 0 or idx >= self.m_size:
            print("Please input the correct index") 
        else:
            for i in range(idx,self.m_size - 1):
                self.m_list[i] = self. m_list[i + 1]
            self.m_list[self.m_size - 1] = None
            self.m_size -= 1
        
        if self.m_size < len(self.m_list) // 2:
            new_list = [None] * (len(self.m_list) // 2)
            for i in range(self.m_size):
                new_list[i] = self.m_list[i]
            self.m_list = new_list
            print("Array auto resizing")
        print("Delete successful")

    def size(self):
        return self.m_size

    def get(self,idx):
        if idx < 0 or idx >= self.m_size:
            print("Please input the correct index")
        return self.m_list[idx]    

if __name__ == "__main__":
    array_list = ArrayList() 
    array_list.add(1)
    array_list.add(2)
    array_list.add(3)
    array_list.add(4)
    print(array_list.get(3))
    print(f"array_list size is : {array_list.size()}")
    array_list.add(5)
    array_list.add(6)
    array_list.add(7)
    array_list.add(8)
    array_list.add(9)
    array_list.delete(0)
    array_list.delete(0)
    array_list.delete(0)
    array_list.delete(0)
    array_list.delete(0)
    array_list.delete(0)
    
```

### Member variable and avoiding IndexError

Understanding the meaning of `m_size` is crucial for avoiding IndexError. 

1. `m_size` defines the valid index range. My size means the number of elements actually stored in the ArrayList at the moment. This is means that any valid index must be in the range 0 to size - 1. 
2. In get method, 