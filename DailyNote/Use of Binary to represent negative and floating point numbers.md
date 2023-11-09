
## Working out negative binary values

[](marginnote3app://note/587D69B2-21CE-411F-A555-AD0BCD1D591A)

### Converts a decimal integer number to binary.

1. Divide the decimal number by two.
2. Record the remainder
3. Divide the quotient from the previous step by two and repeat steps 1 and 2 until the quotient is 0. 4.
4. Arrange the remainders in reverse order (the remainder from the first step is the last one)
This inverted sequence is the binary representation of a decimal number.
Write the entire procedure in Python as follows:
#key/代码 

1
?
```python
binary_list = []

def decimal_to_binary(decimal_num):

	while decimal_num > 0:

		remainder = decimal_num % 2 #record the remainder

		binary_list.append(remainder)

		decimal_num = decimal_num // 2

	binary_list.reverse() #reverse the list

	return binary_list

decimal_num = int(input())

binary_num = decimal_to_binary(decimal_num)

print(binary_list)
	
```
### Converting binary numbers to negative numbers






