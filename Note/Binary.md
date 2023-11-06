	In computers, all pictures, audio, and numbers are stored and manipulated in binary form like 01000101, so it's especially important for us to understand binary.
## Decimal vs Binary

在二进制中的 10 这个数，与十进制中的 10 这个数所表达的含义有哪些不同，有哪些相同？


首先我们要知道，对于十进制而言，最大的能表示的数字是 9，而当 9 想继续往上递增时，9 就会变成 0，并往前进一位变成 10。而对于二进制来说，最大能表示的数字是 1，而 1 想往上递增时，1 就会变成 0，并往前进一位变成 10. 也就是说，无论哪种进制，一旦超过了该进制所能表达的最大值，那么个位数就会变成 0，十位数就会变成 1，比如在四进制中，3 再加上 1 就会变成 10，八进制中 7 再加上一个数字就会变成 10，十六进制中 f 再加上 1 就会变成 10.

那么我们可以提出一个规则，如果基数 = a
也就是说，十位上的 1 （10）代表一共有 a 个数。相当于有 $a^1$ 个数。

那么，百位上的 1（100）就代表一共有 a 个个位上的数，相当于有 $a \times a$ ( $a ^ 2$ )个数。

在十进制中，每一位都代表 10 的不同幂次， Let's take a decimal like 422.

百位代表着 $10^2$ ,十位代表着 $10^1$ ,个位代表着 10^0 次方，

| hundreds    | tens    | ones    |
| ------- | ------- | ------- |
| $10^2$  | $10^1$  | $10^0$  |
| $4$   |  $2$  |  $2$  |

$$422 = 4\times 10^2 + 2\times 10^1 +2\times 10^0 $$
那么对于 222 这样的二进制数字而言

|hundreds|tens| ones|
| ---| ---|---|
|2|2|2|
$$222 = 2\times 2^2 + 2\times 2^1 +2\times 2^0 $$

#难点 *我尝试着解释为什么百位会等于 10 的二次幂，这样做的原因是当我介绍二进制时，我也可以同样引进幂的概念，但是问题是我发现我解释不了，搜集网上资料又引出了权这样的概念，我去查权这个概念，就发现更迷糊了。*

## bit 的概念

A bit 1 or 0, which is the smallest storage unit for numbers in a computer.
## What is the maximum amount of 32-bit int data that can be represented?

那么对于 32bit 的数据而言，全部位上都表示 1 就是最大的数字，所以最大数字是

$$ 1\times 2^{31} +1\times 2^{30} +1\times 2^{29} +\dots..$$
$2^{32} - 1$