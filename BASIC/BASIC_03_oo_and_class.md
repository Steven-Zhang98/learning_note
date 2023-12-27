## I want to create a dog

So, I use the simplest method to create two dogs.
```python
dog_name = "dog1"
dog_position = [1, 1]
print(dog_name, "born at position", dog_position)
new_position = [1, 3]
print(dog_name, "moved from",  dog_position, "to position",  new_position)

dog_name = "dog2"
dog_position = [1,1]
print(dog_name, "born at position", dog_position)
new_position = [1,4]
print(dog_name, "moved from", dog_position, "to position", new_position)
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
I find it hard to add a new dog to the dog list; I have to input the name and position in a dictionary and add the dictionary to the dog list. And I also find it hard to input some new information into the dictionary; for example, I want to add the (a dog's) height.

So, I created a dog class; adding new information to the class is very convenient.

```python
class Dog:

	def __init__(self, name:str,position:list):

	self.m_name = name

	self.m_position = position

dog1 = Dog("fanfan",[1,2],24)

print(dog1.m_name,"born at",dog1.m_position)

```

## Inheritance 

What if I don't just want to create a dog, I want to create a cat class, bird class , or even a human class?

I decided to find the common characteristics in those classes. I found there are all animals, and all of them have names and positions. 

```python
class Animal:
    def __init__(self,name:str,position:list):
        self._m_name = name
        self._m_position = position

    def get_name(self):
        return self._m_name
    
    def get_position(self):
        return self._m_position
    
    def move(self,new_position:list):
        print(self._m_name,"born at",self._m_position,"is moving to",new_position)
        self._m_position = new_position


class Human:
    def __init__(self, name: str, position: list,pet:Animal):
        self._m_name = name
        self._m_position = position
        self._m_pet = pet
        print(f"{self._m_name} has a {self._m_pet.get_name()}")

    def move(self, new_position: list,other:Animal):
        print(self._m_name,"born at",self._m_position,"is moving to",new_position)
        self._m_position = new_position
        print(f"{other.get_name()} bron at {other.get_position()} is moving to {new_position}")
        other.get_position = new_position
    
class Cat(Animal):
    def __init__(self, name: str, position: list):
        super().__init__(name, position)

    def meow(self):
        print("miao! miao !miao!")

class Dog(Animal):
    def __init__(self, name:str,position:list, age:int):
        super().__init__(name,position)
        self.__m_age = age
        print(f"hello everyone,my name is {self.get_name()}")

    def get_age(self):
        return self.__m_age

    def bark(self):
        print("Wang! Wang!")

    def wagtail(self):
        print(f"{self.get_name()} is wag his tail!")


    def encounter(self,other:Animal):
        if isinstance(other,Cat):
            self.bark()
        elif isinstance(other,Human):
            self.wagtail()
        else:
            print(f"{self.get_name()} sees another animal but remains calm.")


class Superdog(Dog):
    def __init__(self, name: str, position: list, age: int,star:int):
        super().__init__(name, position, age) 
        self._m_star = star

    def get_star(self):
        return self._m_star
    
    def show(self):
        print(f"{self.get_name()} have {self.get_star()} super power")
    
    def bark(self):
        super().bark()
        print("super dog can bark all the times")

dog1 = Dog("fanfan",[1,2],24)
print(dog1.get_name(),"bron at",dog1.get_position(),"age is",dog1.get_age())
dog1.move([2,5])
dog1.bark()

dog2 = Superdog("xixi",[1,2],25,5)
print(dog2.get_name(),"bron at",dog2.get_position(),"age is",dog2.get_age())
dog2.move([3,4])
dog2.show()
dog2.bark()

cat1 = Cat("haha",[1,4])
cat1.meow()

human_xixi = Human("xixi",[1,1],dog1)
human_xixi.move([22,33],dog1)
dog1.encounter(human_xixi)
```


## Is-a and Has-a
I created the Animal class, and the dog and cat class is inherited from the animal class. I created the human class separately because humans are not animals; humans have animals. 

## polymorphism

I created the super-dog class, which is inherited from the dog class. The super dog's bark method is overridden because I want to show the difference between the dog and super dog classes.

## Interaction between instances

I created an encounter method to show how the instances these classes reacted to each other.


