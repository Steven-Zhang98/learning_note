---
tags:
  - CS
  - Project
时间: 2024-03-15T08:53:00
---
```python
class StationInfo:
    m_name_to_id_dict = {}
    m_id_to_name_dict = {}
    m_id_neighbours = {}

    @classmethod
    def LoadData(cls, filename):
        with open(filename, 'r') as file:
            for line in file:
                parts = line.strip().split('|')
                if len(parts) >= 4:
                    station_id, station_name, neighbours = parts[0], parts[1], parts[3]
                    cls.m_name_to_id_dict[station_name] = station_id
                    cls.m_id_to_name_dict[station_id] = station_name
                    cls.m_id_neighbours[station_id] = neighbours.split(',')

    @classmethod
    def GetNameFromID(cls, id):
        return cls.m_id_to_name_dict.get(id, "Station ID not found")

    @classmethod
    def GetIDFromName(cls, name):
        return cls.m_name_to_id_dict.get(name, "Station name not found")

    @classmethod
    def GetNeighboursFromID(cls, id):
        return cls.m_id_neighbours.get(id, [])
class StationNode:
    def __init__(self, node_id):
        self.node_id = node_id
        self.neighbours = []

    def InsertNeighbours(self, neighbour_ids):
        self.neighbours.extend(neighbour_ids)

    def GetNeighbours(self):
        return self.neighbours
class StationTree:
    def __init__(self, from_station_id):
        self.root = StationNode(from_station_id)

    def GetPathsTo(self, to_station_id):
        paths = []
        queue = [(self.root, [self.root.node_id])]
        while queue:
            current_node, path = queue.pop(0)
            if current_node.node_id == to_station_id:
                paths.append(path)
                continue
            for neighbour_id in StationInfo.GetNeighboursFromID(current_node.node_id):
                if neighbour_id not in path:
                    new_node = StationNode(neighbour_id)
                    queue.append((new_node, path + [neighbour_id]))
        return paths
class StationFinder:
    def __init__(self):
        self.station_info = StationInfo

    def GetPaths(self, from_station_name, to_station_name):
        from_station_id = self.station_info.GetIDFromName(from_station_name)
        to_station_id = self.station_info.GetIDFromName(to_station_name)
        if from_station_id == "Station name not found" or to_station_id == "Station name not found":
            return []
        tree = StationTree(from_station_id)
        return tree.GetPathsTo(to_station_id)
if __name__ == "__main__":
    StationInfo.LoadData('stations.txt')  # 假设 'stations.txt' 是您的数据文件

    while True:
        from_station = input("Enter the start station: ")
        to_station = input("Enter the destination station: ")
        finder = StationFinder()
        possible_paths = finder.GetPaths(from_station, to_station)
        for path in possible_paths:
            print("One possible path:")
            for station_id in path:
                print(StationInfo.GetNameFromID(station_id), end=" -> ")
            print("\n")
        break  # 根据需要可以去掉这行来允许多次查询

```

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
class StationInfo:

  m_name_to_id_dict
  m_id_to_name_dict
  m_id_neighbours # id -> [neighbour_id1, neighbour_id2, neighbour_id3...]

  # TODO: check and compare static method and class method

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