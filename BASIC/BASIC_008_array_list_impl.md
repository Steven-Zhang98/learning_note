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

ArrayList has two member variables: size, which represents the number of elements the ArrayList actually contains at the moment, and size - 1 is the last element index in ArrayList. The other one is capacity, representing the total number of elements the ArrayList can hold. Len (self. M_array) represents the array's capacity. 