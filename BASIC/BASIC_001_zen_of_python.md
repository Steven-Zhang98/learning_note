---
sr-due: 2023-11-10
sr-interval: 1
sr-ease: 230
---

#review 

----

# Note on The Zen of Python (Xiyun's edition)

## English is better than Chinese (In Coding)

Google is better than Baidu. StackOverflow is better than CSDN (This is shit!!)


## Beautiful is better than ugly.

Let's see two examples and explore what beauty is.

```python
def is_even(number):
# Use the modulus operator (%) to check if a number is even
# If the number is divisible by 2, then it is even
	if number % 2 == 0:
		return f"{number} is even"
	else:
		return f"{number} is odd"
	
```

Compare to 

```python 
def is_even(number):
# Use the bitwise operator (&) to check if a number is even 
# If the number is even, then the function will return false 
	return (number & 1)
```

The second code seems more "beautiful" regarding simplicity and execution efficiency. Still, the second code uses the bitwise operator (&), which improves execution efficiency but may need to be more friendly to readers unfamiliar with bitwise operations. The code is not only for the machine to run but also for people to read. A readable code makes it easier for teams to work together and maintain the code.

Therefore, a "beautiful" code should balance readability and efficiency.

For example, in performance-oriented development scenarios, we can use bitwise arithmetic and add comments to explain its use. But in teaching scenarios, we need to use the simplest language and examples that others can read and understand to explain complex concepts, and then we can use modulo arithmetic.
## Explicit is better than implicit.

When we try to name a variable, clarifying the types and the names of input can better express the usefulness of the variable.

```python
from typing import TypeAlias

def is_even(input_number:int):
# Use the modulus operator (%) to check if a number is even
# If the number is divisible by 2, then it is even
	if input_number % 2 == 0:
		return f"{input_number} is even"
	else:
		return f"{input_number} is odd"
```
Type annotations do not force the input_number type to be checked, but they can help developers understand the code better.


## Simple is better than complex.



## Complex is better than complicated.

当一篇文章很难理解，你要尽量用简单的方法去解释他

## Flat is better than nested.

这一点我们可以利用在笔记层级管理上，写 Binary 用一片文章去尽量解释清楚，就比单独把 Binary 作为一个文件夹，去创建很多文档再去解释 Binary 更好

## Sparse is better than dense.

为了提升代码可读性，通过换行符增加间隔以区别不同功能的代码块
讲一个长的代码分解成小的片段


## Readability counts.

可读性特别重要
## Special cases aren't special enough to break the rules.

遇到再特殊情况也不能破坏规则，比如保持简洁，比如先进行行动而不是什么都不做

## Although practicality beats purity.

但是在为了解决问题，偶尔破坏规则也无妨

## Errors should never pass silently.

因为是小错误而选择忽略，他往往导致更加严重的后果

## Unless explicitly silenced.

除非这是被明确告知的，可以忽略的错误

## In the face of ambiguity, refuse the temptation to guess.

在面对模棱两可的情况，不要选择去猜测进而丧失了深入思考的机会

## There should be one-- and preferably only one --obvious way to do it.

通过思考就能找出唯一的方法

## Now is better than never.

从现在开始，从做一个最简单最基础的原型开始逐渐迭代，比什么都不做更好。
要时刻记住先尝试，再去优化

## Although never is often better than *right* now.

然而什么事情都去尝试，还不如不做

## If the implementation is hard to explain, it's a bad idea.

如果你无法清晰解释你学过的内容的过程，这意味着你不了解你学了什么

## Although that way may not be obvious at first unless you're Dutch.

但这种无法解释的学习在学习刚起步时是很常见的，这是因为我们往往习惯于 w 我们旧有的行为模式。
## If the implementation is easy to explain, it may be a good idea.

如果你开始每次学完一个新知识，就尝试去解释它，这是一个好的现象

## Namespaces are one honking great idea -- let's do more of those!

利用分层的命名系统，我们可以给这个系统中每一个事物进行唯一编号。

比如车辆命名系统，两辆车的车牌都是 123，单一个是川 A 一个是沪 A 标志着这是两辆车。

