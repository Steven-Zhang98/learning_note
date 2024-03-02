---
sr-due: 2023-11-11
sr-interval: 2
sr-ease: 250
---
为什么叫int? float? double? string?
?
1

# Version 3.0
### 推出规律的过程

Since there are only 0's and 1's in binary, the largest binary data will always take up all the bits, no matter what type of data it is.

If we only have 1 bit of binary, the greatest number is 1

If we have 2 bit, the greatest number is 11. Converted to decimal is 3

3 bit, the greatest number is 111, convert to decimal is 7

### 引出规律

Express the largest binary number using the formula is:

$2^n - 1$  

N represents the bits
### 变式来检验是否背答案




# Binary


> In computers, all pictures, audio, and numbers are stored and manipulated in binary form like 01000101, so it's especially important for us to understand binary.
## Decimal vs Binary

How is the number 10 in binary different from and the same as the meaning expressed by the number 10 in decimal?


First of all, we need to know that for decimal, the maximum number that can be expressed is 9, and when 9 wants to go up, 9 becomes 0 and goes one place forward to 10, while for binary, the maximum number that can be expressed is 1, and when 1 wants to go up, 1 becomes 0 and goes one place forward to 10. That is to say, no matter what kind of decimal, once the maximum value of the number can be expressed, then the first digit becomes 0 and the tenth digit becomes 1. In other words, once the maximum value that can be expressed in any of the alphanumeric systems is exceeded, the first digit becomes 0 and the tenth digit becomes 1. For example, in quadrature, 3 plus 1 becomes 10, in octal, 7 plus a digit becomes 10, and in hexadecimal, f plus 1 becomes 10.

So we can propose a rule that if base = b
That is, a 1 (10) in the tens place means that there are a total of a numbers. This is equivalent to $b^1$.

Then, 1 (100) in the hundreds place represents that there are a total of a digit numbers, which is equivalent to having $b \times b$ ( $b ^ 2$ ) numbers.

In decimal, each digit represents a different power of 10, Let's take a decimal like 422.

The hundreds place represents $10^2$ , the tens place represents $10^1$ , and the ones place represents the $10^0$ .

| hundreds    | tens    | ones    |
| ------- | ------- | ------- |
| $10^2$  | $10^1$  | $10^0$  |
| $4$   |  $2$  |  $2$  |
$$422 = 4\times 10^2 + 2\times 10^1 +2\times 10^0 $$
So for a binary number like 222.

|hundreds|tens| ones|
| ---| ---|---|
|2|2|2|

$$222 = 2\times 2^2 + 2\times 2^1 +2\times 2^0 $$

*我尝试着解释为什么百位会等于 10 的二次幂，这样做的原因是当我介绍二进制时，我也可以同样引进幂的概念，但是问题是我发现我解释不了，搜集网上资料又引出了权这样的概念，我去查权这个概念，就发现更迷糊了。:: 


## The concept of bit

A bit 1 or 0, which is the smallest storage unit for numbers in a computer.
## What is the maximum amount of 32-bit int data that can be represented?

So for 32 bit data, the largest number is when all the bits represent 1, so the largest number is

$$ 1\times 2^{31} +1\times 2^{30} +1\times 2^{29} +\dots..$$


$=2^{32} - 1$

# A new version I'd like to explain


## Use the decimal system to discover patterns ##
I would like to use a familiar example to explain what the maximum 32 bit binary number is, assuming we only have 1 bit of decimal data, then the maximum value is 9, if we have two bits of decimal data, then the maximum value is 99, if we have three bits of decimal data, then the maximum value is 999

If we were to show the following process in a list, it would be

|Number of digits|decimal value|simplified|
|---|---|---|
|1|9| 10-1|
|2|99| 100 - 1|
|3|999|1000 - 1|
|4|9999|10000 - 1|
|5|99999|100000 - 1|
|6|999999|1000000 - 1|
|7|9999999|10000000 - 1|
|n|999999... N| $10^n-1$ |


We can find a pattern that in decimal, assuming there are n digits, the maximum value that can be represented is $10^n-1$, and 10 denotes the number of digits, so I'm guessing if the binary number satisfies the $2^n-1$
## Using binary to verify patterns

^d4fcd5

To test my hypothesis, I'll use a chart 

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
# Binary in code practice

^34cdbc

[[BASIC_003_binary#^d4fcd5|The last digit in binary is one then it is odd]], then we can define an algorithm accordingly. If a number & 1 (1 in hexadecimal is 000000000..... 1), if the number is even, then the result will be 0 and the Boolean value is False, if the number is 1, the result will be 1 and the Boolean value is True

The code is as follows:

```py
def is_even(number):

return (number & 1) == 0

  

# Example usage:

is_even_4 = is_even(4) # This will be True because 4 is even.

is_even_7 = is_even(7) # This will be False because 7 is odd.

num = int(input())

print(f"{num} is even,is {is_even(num)}")

print(is_even_4)

print(is_even_7)
```

^cd0116

