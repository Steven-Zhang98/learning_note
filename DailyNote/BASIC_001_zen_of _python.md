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

凡是好的东西，从审美的角度来看一定是美丽的。

```python

def is_even(number):
	if number % 2 == 0:
		return f"{number} is even"
	else:
		return f"{number} is odd"
	
```

对比

```python 
def is_even(number):
	return (number & 1)
```

从后面的代码中可以看出代码更加简短，执行效率更好，也让我意识到，“美”是需要对事物的有深刻认知的。
## Explicit is better than implicit.

在对变量命名时，更直观的变量名优于不直观的变量名，比如 [[BASIC_004_ floating_point_umbers#^5aacf6|decimal_num 就比 num 好]]
我们也可以借用
有时候我们使用 alias 函数来帮助我们 [](marginnote3app://note/45BDD625-7848-46CB-8A76-F6B5DD347B0B)- 明确输入、输出参数的类型和名称可以更好的表达变量的用处 


## Simple is better than complex.

比如说， [[BASIC_003_binary#^34cdbc|判断一个数是否是偶数，利用& 1 计算就比 % 2 更好]]

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
