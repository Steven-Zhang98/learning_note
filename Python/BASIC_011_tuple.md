---
in: 
up: 
down: 
related: 
opposite: 
Create: 
by: 
due-date: 
rank: 
tags:
  - Incubation🌱
---
- Tuple is immutable
	- using tuple as a hash key
	- return multiple values
- Tuple can store any data.


## Using tuple as a key

```python

coordinates_to_city = {
    (51.5074, -0.1278): "London",
    (40.7128, -74.0060): "New York"
}


city_in_london = coordinates_to_city[(51.5074, -0.1278)]
print("The city at coordinates (51.5074, -0.1278) is", city_in_london)  
```

## return multiple values

```python

def add_and_subtract(a, b):
    addition = a + b
    subtraction = a - b
    return addition, subtraction  # return a tuple


result = add_and_subtract(5, 3)

sum_result, difference_result = result

print("Sum:", sum_result)  
print("Difference:", difference_result)  

```

## Incubation area

What is a tuple, and why do we need a tuple?
?
The tuple is immutable; we can use tuple as a hash key and return multiple values

