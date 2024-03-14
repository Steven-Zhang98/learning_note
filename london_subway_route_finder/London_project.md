---
tags:
  - CS
  - Project
---
How can we save the data?
?
We first read out the data so that we can find the name of the subway from the subway ID, find the subway ID from the subway name, and find its related subway station from the subway ID; the purpose of doing so is to allow the user to enter the start station and end station of the subway station, we can be based on the name of this subway station to find the ID of the subway station, and then the shortest path between the two IDs to find out. Then, we can find the shortest path between these two IDs and print out the shortest path based on the ID and the name of the subway station.

## 
```python
class StationInfo:
    def __init__(self, filename):
        # Initialize dictionaries to store station info
        self.m_name_to_id_dict = {}
        self.m_id_to_name_dict = {}
        self.m_id_neighbours = {}

        # Load data from file
        self.load_data(filename)

    def load_data(self, filename):
        # Read the file and populate the dictionaries
        with open(filename, 'r') as file:
            for line in file:
                # Split each line into parts
                parts = line.strip().split('|')
                # Check if the line has the correct number of parts
                if len(parts) >= 3:
                    station_id, station_name, neighbours = parts[0], parts[1], parts[3]
                    # Populate name to ID and ID to name dictionaries
                    self.m_name_to_id_dict[station_name] = station_id
                    self.m_id_to_name_dict[station_id] = station_name
                    # Split the neighbours string into a list and store it
                    self.m_id_neighbours[station_id] = neighbours.split(',')

    def get_name_from_id(self, station_id):
        # Return the station name corresponding to the given ID
        return self.m_id_to_name_dict.get(station_id, "Station ID not found")

    def get_id_from_name(self, station_name):
        # Return the station ID corresponding to the given name
        return self.m_name_to_id_dict.get(station_name, "Station name not found")

    def get_neighbours_from_id(self, station_id):
        # Return the list of neighbour IDs for the given station ID
        return self.m_id_neighbours.get(station_id, [])

```

```python
class StationNode:
  def __init__(self, node):
    self.m_root = node

  def InsertNeighbours(neighbour_ids):
    pass

  def GetNeighbours():
    pass

class StationTree:
  def __init__(self, from_station):
    self.m_from_station = StationNode(from_station)

  def GetPathsTo(self, to_station):
    # level order traverse
    pass

class StationFinder:
  def GetPaths(self, from_station, to_station):
    tree = StationTree(from_station)
    tree.GetPathsTo(to_station)
```
## BFS

How can we represent the graph of the underground?
?
```python
from collections import deque, defaultdict

# 假设我们有一个地铁站图，用adjacency table表示
# 键是站点ID，值是与该站点直接相连的站点ID列表
subway_graph = {
    'A': ['B', 'D'],
    'B': ['A', 'C', 'E'],
    'C': ['B', 'F'],
    'D': ['A', 'E'],
    'E': ['B', 'D', 'F'],
    'F': ['C', 'E']
}
```


```python
# BFS函数，用于构建搜索树并查找路径
def bfs_paths(start, goal):
```

Why do we use deque to save nodes and paths to be accessed?
```python
    # 创建队列用于存放待访问节点及路径
    queue = deque([ (start, [start]) ])
    # 记录已访问节点，避免重复访问
    visited = set()
    
    # 存储从起点到各点的路径
    paths = []
    
    while queue:
        # 取出当前节点及当前路径
        current, path = queue.popleft()
        visited.add(current)
        
        # 检查是否达到目标站点
        if current == goal:
            paths.append(path)
            continue  # 如果需要找到所有路径，则不中断搜索
        
        # 遍历邻接节点
        for neighbor in subway_graph[current]:
            if neighbor not in visited:
                # 将邻居节点及路径加入队列
                queue.append((neighbor, path + [neighbor]))
    
    return paths

# 使用BFS找到从站点'A'到站点'F'的路径
start_station = 'A'
end_station = 'F'
paths = bfs_paths(start_station, end_station)

# 打印路径
for path in paths:
    print(" -> ".join(path))

``` 


What is the project like?
?
When the user inputs the start and end points of the subway station

How to understand the structure of the project?


Use a chatbot to teach me how to build the big picture of the project.


## Resource
```python
class StationInfo:
	def __init_(self):
	  m_name_to_id_dict = {}
	  m_id_to_name_dict = {}
	  m_id_neighbours = {}  # id -> [neighbour_id1, neighbour_id2, neighbour_id3...]

  @classmethod
  def LoadData(name, id):
    # populate m_name_to_id_dict
    # populate m_id_to_name_dict
    pass

  @classmethod
  def GetNameFromID(id):
    pass

  @classmethod
  def GetIDFromName(name):
    pass

  @classmethod
  def GetNeighboursFromID(id):
    pass

class StationNode:
  def __init__(self, node):
    self.m_root = node

  def InsertNeighbours(neighbour_ids):
    pass

  def GetNeighbours():
    pass

class StationTree:
  def __init__(self, from_station):
    self.m_from_station = StationNode(from_station)

  def GetPathsTo(self, to_station):
    # level order traverse
    pass

class StationFinder:
  def GetPaths(self, from_station, to_station):
    tree = StationTree(from_station)
    tree.GetPathsTo(to_station)
    

## Load file
# for loop file
# load data into StationInfo

## collect user from_station and to_station
while(True):
  # get from_station
  # get to_station
  finder = StationFinder()
  possible_paths = finder.GetPaths(from_station, to_station)
  for path in possible_paths:
    print("One possible path:")
    for i in path:
      print(StationInfo.GetNameFromID(i), ",")
```

  # TODO: check and compare static method and class method







