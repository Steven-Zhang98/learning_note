---
sr-due: 2023-11-11
sr-interval: 2
sr-ease: 250
---
Why do we call int? Float? Double? String?

 Swap Two integers in Array

```python
class Solution:

	def swap_integgers(self, A, index1, index2):
		# wirte your code here
		inter = 0
		inter = A[index1]
		A[index1] = A[index2]
		A[index2] = inter
		 
```
## Binary


|Number of digits|binary value|decimal value|
|---|---|---|
|1|1| 1|
|2|11| 3|
|3|111|7|
|4|1111|15|
|5|11111|31|
|6|111111|63|
|7|1111111|127|
|n|11111111... N| $2^n-1$ |

We find that this pattern is satisfied, so the maximum value of a 32-bit binary number without taking into account the sign bit is $2^{32}-1$ by substituting in 32.

## floating point numbers




