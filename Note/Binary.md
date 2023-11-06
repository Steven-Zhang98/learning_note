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

#难点 *我尝试着解释为什么百位会等于 10 的二次幂，这样做的原因是当我介绍二进制时，我也可以同样引进幂的概念，但是问题是我发现我解释不了，搜集网上资料又引出了权这样的概念，我去查权这个概念，就发现更迷糊了。*

## The concept of bit

A bit 1 or 0, which is the smallest storage unit for numbers in a computer.
## What is the maximum amount of 32-bit int data that can be represented?

So for 32 bit data, the largest number is when all the bits represent 1, so the largest number is

$$ 1\times 2^{31} +1\times 2^{30} +1\times 2^{29} +\dots..$$
$=2^{32} - 1$
