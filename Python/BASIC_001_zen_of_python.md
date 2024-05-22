---
sr-due: 2023-11-30
sr-interval: 1
sr-ease: 210
tags:
  - CS
sr-due: 2024-03-19
sr-interval: 13
sr-ease: 190
---
# Note on The Zen of Python (Xiyun's edition)

## Create a model and then optimise

```python
def is_even(number):
# Use the bitwise operator (&) to check if a number is even 
# If the number is even, then the function will return false 
	return (number & 1)
```
I optimised the program based on false assumptions without enough information when I didn't know if the bits were arranged from smallest to largest or from largest to smallest. Optimising ahead of time wasted my time and reduced the readability of the code.
1
## Readable is the most important things
