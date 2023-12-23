## 摘要

在这篇文章中我的写作思路如下：1. 首先我写了一个狗的代码 2. 我发现代码中出现了变量复用（variable reuse）这会导致一旦定义了 dog 2 dog 1 的名字和位置信息就发生了丢失，我也无法修改这些信息。3. 于是我想到用字典保存狗的信息，然后将 dog 1 dog 2 储存在列表中 4. 但是我发现，我创建一只狗特别麻烦，并且如果哪天我想给狗添加更多信息（比如狗的身高，体重）会特别麻烦。于是 5. 我创建一个狗类

## 正文
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

Because dog 1 and dog 2 use the same variable dog_name and dog_position, when we create dog 2, the dog_name and dog_position will change from dog 1's name and position and dog'2 name and position. This is called variable reuse. But if we reuse the variable, The position updates and the movements of the dogs can not be interactive.

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

I find it hard to add new users to the user_list; I have to input the name, age, and bio in a dictionary and add the dictionary to the user_list. And i also find it hard for me to input some new information into the dictionary, for example, i want to add the (a person's) height.
So I think i can create a user class, it is very convenient for me to add new information into the class.

```python
class User:
    def __init__(self, name, age, bio, height=None):
        self.name = name
        self.age = age
        self.bio = bio
        self.height = height

    def update_height(self, new_height):
        self.height = new_height

# Creating a user
user1 = User("fanfan", 24, "bio")

# Adding a new user
user_list = [user1]
user2 = User("newuser", 30, "new bio")
user_list.append(user2)

# Updating user information
user1.update_height(170)

```