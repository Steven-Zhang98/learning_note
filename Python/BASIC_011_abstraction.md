## Abstraction

```python
from abc import ABC, abstractmethod

class Animal(ABC):
	def __init__(self, position):
		m_position = []
		
	@abstractmethod
	def move():
		pass
```