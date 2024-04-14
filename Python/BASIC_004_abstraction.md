## Abstraction

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    def __init__(self, position):
        self.m_position = position  

    @abstractmethod
    def move(self):
        pass

# lion class
class Lion(Animal):
    def move(self):
        print("Lion moves!")
        self.m_position += 10  # move

# test
lion = Lion(0)
lion.move()
print("Lion's current position:", lion.m_position)

```

## Errors

```python
class AnimalError(Exception):
    """ Exception raised for errors in the animal operations."""
    
    def __init__(self, message):
        super().__init__(message)
        self.message = message

from abc import ABC, abstractmethod

class Animal(ABC):
    def __init__(self, position):
        self.m_position = position

    @abstractmethod
    def move(self):
        pass

class Lion(Animal):
    pass

try:
    lion = Lion(0)
    lion.move()
    print("Lion's current position:", lion.m_position)
except TypeError as e:
    raise AnimalError(f"Failed to instantiate Lion due to an abstract method issue: {str(e)}")

```