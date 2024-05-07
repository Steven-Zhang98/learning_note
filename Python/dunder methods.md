- dunder method means give the instance more function
## lt method
```python
class Student:  
    def __init__(self, marks, height):  
        self.m_marks = marks  
        self.m_height = height  
  
    def __lt__(self, other):  
        return self.m_marks < other.m_marks  
  
  
if __name__ == "__main__":  
    student_1 = Student(89, 110)  
    student_2 = Student(90, 109)  
    print(student_1 < student_2)  
    print(student_1 > student_2)
```

## str method

```python
class Student:  
    def __init__(self, marks, height):  
        self.m_marks = marks  
        self.m_height = height  
  
    def __lt__(self, other):  
        return self.m_marks < other.m_marks  
  
    def __str__(self):  
        return f"{self.m_marks}, {self.m_height}"  
  
  
if __name__ == "__main__":  
    student_1 = Student(89, 110)  
    student_2 = Student(90, 109)  
    print(student_1)  
    print(student_2)
```
