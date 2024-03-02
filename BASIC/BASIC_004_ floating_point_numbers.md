## If VS Iteration


 
## Working out negative binary values

### Converts a decimal integer number to binary.

1. Divide the decimal number by two.
2. Record the remainder
3. Divide the quotient from the previous step by two and repeat steps 1 and 2 until the quotient is 0. 4.
4. Arrange the remainders in reverse order (the remainder from the first step is the last one)
This inverted sequence is the binary representation of a decimal number.
Write the entire procedure in Python as follows:


如何写一个将十进制转换成二进制的函数
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

^5aacf6

### Converting binary numbers to negative numbers

以一个 8bit 位的二进制数 0001000 (十进制的 8)，以它为例子将表示如何表示二进制负数。

| Origin     | 0   | 0   | 0   | 1   | 0   | 0   | 0   |
| ---------- | --- | --- | --- | --- | --- | --- | --- |
| Converting | 1   | 1   | 1   | 0   | 1   | 1   | 1   |
| Add    + 1     |  1   |   1  |   1  |   1  |   0  |  0   |   0  |

那么 1110001 就是他的-8 的二进制表达形式。此时第一个数用来表示符号位，0 代表正数，1 代表负数。
### 表示浮点数

将一个二进制数用科学记数法表示出来，以 $1.123\times{10}^4$，拆分成1.123 （表示尾数），以及 $10^4$，两者分别用二进制表示出来

|  |   0.123  |
| ----- | --- |
|    0  |  0.246  |
 |  0   |   0.492
  |   0  | 0.984|
|1|1.968|
|1|936|

0.00011
+
1

=1.00011



