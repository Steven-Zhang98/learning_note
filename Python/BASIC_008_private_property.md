```python
class Student:
	def __init__(self, name='', score = 0)
		self.name = name
		self.score = score

	def speak(self):
		print(self.name, self.score)

if __name__ == '__main__':
	stu_1 = Student('jack', 10)
	print(stu_1.name, stu_1.score)
	
``` 

 ```python
class Student:
	def __init__(self, name='', score = 0)
		self.name = name
		self.__score = score

	def speak(self):
		print(self.name, self.__score)

if __name__ == '__main__':
	stu_1 = Student('jack', 10)
	print(stu_1.name, stu_1.__score)
	
``` 

## Name mangling

```python
class Student:
	def __init__(self, name='', score = 0)
		self.name = name
		self.__score = score

	def speak(self):
		print(self.name, self.__score)

if __name__ == '__main__':
	stu_1 = Student('jack', 10)
	print(stu_1.name, stu_1._Student__score)
 
```