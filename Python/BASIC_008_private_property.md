```python
class Student:
	def __init__(self, name='', score = 0):
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
	def __init__(self, name='', score = 0):
		self.name = name
		self.__score = score

	def speak(self):
		print(self.name, self.__score)

if __name__ == '__main__':
	stu_1 = Student('jack', 10)
	print(stu_1.name, stu_1.__score)
	
``` 

## Setter getter


```python
class Student:
	def __init__(self, name='', score = 0):
		self.name = name
		self.__score = score

	def speak(self):
		print(self.name, self.__score)

	def get_score(self):  
		return self.__score

if __name__ == '__main__':
	stu_1 = Student('jack', 10)
	print(stu_1.name, stu_1.get_score())
```

use a setter to control 

```python
class Student:
	def __init__(self, name='', score = 0):
		self.name = name
		self.__score = score

	def speak(self):
		print(self.name, self.__score)

	def set_score(self, score):
		if score >= 0 and score <= 100:
			self.__score = score

	def get_score(self):  
		return self.__score

if __name__ == '__main__':
	stu_1 = Student('jack', 10)
	print(stu_1.name, stu_1.get_score())
```
## Name mangling


```python
class Student:
	def __init__(self, name='', score = 0):
		self.name = name
		self.__score = score

	def speak(self):
		print(self.name, self.__score)

if __name__ == '__main__':
	stu_1 = Student('jack', 10)
	print(stu_1.name, stu_1._Student__score)
 
```