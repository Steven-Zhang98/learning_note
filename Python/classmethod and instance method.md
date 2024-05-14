```python
class GlobalCounter:  
    counter = 0  
  
    @classmethod  
    def increment(cls):  
        cls.counter += 1  
        return cls.counter  
  
    @classmethod  
    def get_counter(cls):  
        return cls.counter  
  
  
print(GlobalCounter.increment())  # Output: 1
  
counter = GlobalCounter()  
print(counter.increment())   # Output: 2
```

```python
class GlobalCounter:  
    def __init__(self):  
        self.counter = 0  
  
    def increment(self):  
        self.counter += 1  
        return self.counter  
  
    def get_counter(self):  
        return self.counter  
  
  
counter = GlobalCounter()  
print(counter.increment())  # Output: 1
  
counter_1 = GlobalCounter()  
print(counter_1.increment())   # Output: 1
```