## Abstract

在这篇文章中我的写作思路如下：1. 首先我写了一个狗的代码 2. 我发现代码中出现了变量复用（variable reuse）这会导致一旦定义了 dog 2 dog 1 的名字和位置信息就发生了丢失，我也无法修改这些信息。3. 于是我想到用字典保存狗的信息，然后将 dog 1 dog 2 储存在列表中 4. 但是我发现，我创建一只狗特别麻烦，并且如果哪天我想给狗添加更多信息（比如狗的身高，体重）会特别麻烦。于是 5. 我创建一个狗类

## I want to create a dog
```python
dog_name = "dog1"
dog_position = [1,1]
print(dog_name, "born at position", dog_position)
new_position = [1,3]
print(dog_name, "moved from", dog_position,"to position", new_position)

dog_name = "dog2"
dog_position = [1,1]
print(dog_name, "born at position", dog_position)
new_position = [1,4]
print(dog_name, "moved from", dog_position,"to position", new_position)
```

This code creates two dogs on the game map. I set their names and positions at the beginning and can later move them to different positions.

## Understanding Variable Scope
It's hard to track the positions and movements of dogs because dog 1 and dog 2 use the same variable, dog_name and dog_position; when we create dog 2, the dog_name and dog_position will change from dog 1's name and position to dog'2's name and position. This is called variable reuse. But if we reuse the variable, The position updates and the movements of the dogs can not be interactive.

## Use list to Manage Dogs
To make this code more dynamic and capable of handling multiple dogs without overwriting, one approach could be to use a list or a dictionary to store each dog's details.

```python
dog1 = {"name": "dog1", "position": [1, 2]}
print(dog1["name"])
dog2 = {"name": "dog2", "position": [1, 4]}
dog = [dog1,dog2]
print(dog[0]["name"],"bron at" ,dog[0]["position"])
dog[0]["position"] = [3,4]
print(dog[0]["name"],"bron at" ,dog[0]["position"],"move to",dog[0]["position"])

```

## Use Class to Manage Dogs
I find it hard to add a new dog to the dog list; I have to input the name, and position in a dictionary and add the dictionary to the dog list. And I also find it hard for me to input some new information into the dictionary; for example, I want to add the (a dog's) height.

So, I created a dog class; adding new information to the class is very convenient.

```python
class Dog:

def __init__(self, name:str,position:list):

self.m_name = name

self.m_position = position

dog1 = Dog("fanfan",[1,2],24)

print(dog1.m_name,"born at",dog1.m_position)

```

## The advantage of using class 

```python
class Dog:

def __init__(self, name:str,position:list, age:int):

self.m_name = name

self.m_position = position

self.m_age = age

def move(self,new_position:list):

print(self.m_name,"born at",self.m_position,"is moving to",new_position)

self.m_position = new_position

dog1 = Dog("fanfan",[1,2],24)

print(dog1.m_name,"bron at",dog1.m_position,"age is",dog1.m_age)

dog1.move([2,5])
```
