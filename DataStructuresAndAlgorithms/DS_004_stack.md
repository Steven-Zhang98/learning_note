---
Create: 2024-04-23
in: 
up: 
down: 
related: 
opposite: 
by:
---
What is the key point of the stack
?
- Implement a stack based on the list(push, pop, peek, is_empty())
- Call stack
- Stack Overflow

## What is stack

The Stack is a data structure that follows the first-in-last-out (LIFO) principle, similar to a stack of plates or ammunition in the magazine.  The last added element will be the first to be removed from the structure.

An array and linked list can implement the stack. So, the stack describes the logical relationship of how the elements are added and removed.

The way we use stack is like loading ammunition into the magazine. When we push an element in the stack, it is like adding ammunition to the magazine. When we pop an element, it is like firing bullets from a magazine.

![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202403261730362.png)

- Implement

Implement stack based on list
The tail of the list is equivalent to the top of the stack.
![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202404231515185.png)

### Practice

Given a string containing just the characters  ' ( ', ' ) ', ' { ' ,' } '[' and ']',  determine if
the input string is valid.

The brackets must close in the correct order， "（）"and "（）［］｛｝"are all valid but "（］" and "
（［）1"are not.

```python
def isValidParentheses(self, s):
	stack = []
	for char in s:
		# push stack
		if char == '[' or char == '(' or char == '{':
			stack.append(char)
		else:
			 # check the stack if none
			 if not stack:
				 return False
			# check the top of the stack
			if char == ']' and stack[-1] != '[' or char == ')' and stack[-1] != '(' or char == '}' and stack[-1] != '{':
				return False
			stack.pop()
	return not stack

```

## Call stack and stack overflow

When we call the main function, we push the main function address in the stack and then call the foo function.

When we call the function recursively, and it never pops out of the stack, it will cause a stack overflow.

```python
def main():
	num = 10
	foo()
	
def foo():
	name = 'abc'
	bar()

def bar():
	baz()
	arr = [1,2,3]
	for num in arr：
		print (num)
		
def baz():
	print（'I am baz function.'）
if __name__ == '__main__':
main()
```

![image.png](https://obsidianpicture-1320276993.cos.ap-hongkong.myqcloud.com/Obsidian/Picture/202404231701945.png)

