
```python
class StationInfo:
	m_name_to_id = {}
	m_id_to_name = {}
	m_id_to_neighbor = {}

	@classmethod
	def load_data(cls, filename):
		with open(filename, 'r') as file:
			for line in file:
				parts = line.strip().split('|')  # split line in to parts and strip extra spaces
				if len(parts) >= 3:  # Ensure there are at least 3 parts in the line
					station_id = parts[0]
					station_name = parts[1]
					station_neighbor = parts[2]
					cls.m_name_to_id[station_name] = station_id   # station_id rather than id 
					cls.m_id_to_name[station_id] = station_name    		
					cls.m_id_to_neighbor[station_id] = station_neighbor.strip().split(',')  # split neighbor string into a list
				else:
					print(f"Skipping malformed line: {line.strip()}")
					
	@classmethod				
	def get_id_from_name(cls, name):
		return cls.m_name_to_id.get(name, "Station name not found")  # Use get method to prevent KeyError

	@classmethod
	def get_name_from_id(cls, station_id):
		return cls.m_id_to_name.get(station_id,"Station id not found")

	@classmethod
	def get_neighbor_from_id(cls, station_id):
		return cls.m_id_to_neighbor.get(station_id,[])	

	
```
What is classmethod?

How to load data?

Why is the key in the dict a string?

## Error

ValueError: too many values to unpack (expected 3)

## 2
```python
class StationNode:
	def __init__(self, node_id: str):
		self.node_id = node_id
		self.node_neighbor = StationInfo.get_id_from_neighbor(node_id)

	def get_id(self):
		return self.node_id
		
	def get_neighbor(self):
		return self.node_neighbor
```