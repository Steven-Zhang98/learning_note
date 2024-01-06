```python
class Node:
    def __init__(self, val):
        self.m_val = val
        self.m_next = None

    def get_val(self):
        return self.m_val

    def set_next(self, n): 
        self.m_next = n

    def get_next(self):
        return self.m_next


class LinkedList:
    def __init__(self, val):
        self.head = Node(val)

    def insert(self, val):
        new_node = Node(val)
        new_node.set_next(self.head)
        self.head = new_node

    def exist(self, val):
        current = self.head
        while current:
            if current.get_val() == val:
                return True
            current = current.get_next()
        return False

    def print_list(self):
        current = self.head
        while current:
            print(current.get_val(), end=" ")
            current = current.get_next()
        print()


# Testing the LinkedList class
if __name__ == "__main__":
    list = LinkedList(5)
    list.insert(4)
    list.insert(3)
    list.insert(6)
    print("6 is in linked list:", list.exist(6))
    print("16 is not in linked list:", list.exist(16))
    list.print_list()
    print("done")

```
