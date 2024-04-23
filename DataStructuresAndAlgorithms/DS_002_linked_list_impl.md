---
in: 
up: 
down: 
related: 
opposite: 
Create: 2024-04-23
by: 
due-date: 
rank: 
tags:
  - Incubation🌱
---
How to delete the nth node from the end of the linked list
?
fast and slow pointer

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

- add

define a pre-node
![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202404222129424.png)
```python
def add(self, location, val)
	if location > 0:
		pre = self.head
		for i in range(location - 1):
			pre = pre.next
		new_node = Node(val)
		new_node.next = pre.next
		pre.next = new_node

	elif location == 0:
		new_node = Node(val)
		new_node.next = self.head
		self.head = new_node
	

```

- get

```python
def get_var(self, position):
	cur = self.head
	for i in range(position):
		cur = cur.next
	return cur.get_val()  
```

- delete
![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202404230923603.png)

```python
def delete(self, position)
	if location > 0:
		pre = self.head
		for i in range(position - 1)
			pre = pre.next
		pre.next = pre.next.next
		
	elif location == 0:
		self.head = self.head.next
	
```

Given a linked list, remove the nth node from the end of list and return its head.

Example 1：

 Input: list = 1->2->3->4->5->null, n= 2

Output:1->2->3->5->null

```python
def remove_nth_from_end(self, n)
	fast = self.head
	slow = self.head
	# Move fast pointer n+1 steps ahead
	for i in range(n + 1)
		if fast:
			fast = fast.next
		else:
			return self.head
	# Move both fast and slow pointers until fast reaches the end
	while fast
		slow = slow.next
		fast = fast.next
		
	removed_val = slow.next.val
	slow.next = slow.next.next
	return removed_val
```


### Understanding of Linked List

LinkedList is like a train. Each node is a carriage. The carriage has its passenger (value) and is connected to the next carriage (m_next). When we want to insert a new value into the LinkedList, we must connect the new node with the head node. And set the new node to the head node. When we want to find a value, we must iterate all Linkedlist to check if the node's value equals the given value.  When we want to delete a value, we have to find that carriage, then unlink it from the train by connecting the previous carriage to the next carriage in line



## Pointer manipulation And LinkedList

It is important to know that everything in Python is an object, 


![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202402172219355.png)

## Incubation area

