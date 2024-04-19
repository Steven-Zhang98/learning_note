- We use the constructor to declare what properties this class have.
- The self keyword means calling the object itself. Using the self keyword can simplify the code.

```python
class Student:
	def __init__(self, name='', score = 0):
		self.name = name
		self.score = score

	def speak(self):
		print(self.name, self.score)

if __name__ == '__main__':
	stu_1 = Student('jack', 10)
	stu_1.speak()
```

```python
class Student:
	def __init__(self, name='', score = 0):
		self.name = name
		self.score = score
		self.speak()

	def speak(self):
		print(self.name, self.score)

if __name__ == '__main__':
	stu_1 = Student('jack', 10)
```