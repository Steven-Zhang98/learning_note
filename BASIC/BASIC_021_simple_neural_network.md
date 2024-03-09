---
tags:
  - CS
sr-due: 2024-03-07
sr-interval: 1
sr-ease: 210
---
How can we do the simplest gradient descent?
?


If we have a function like this :

 $1. y = wx + 1$

We want to simulate a function like this:

$2. t = 2x + 1$

We suppose $w = 5$, and we enter an x (e.g., 2) value into Equation 1 up to the `y` value of 11. 

When we compare the 11 and the 5, we find that 11 is bigger than 5, so we reduce $w$ to 4. And then we try to calculate the result of equation 1 again.

```python
class SimpleNeuralNetwork:
    def __init__(self, input_value, weight, bias, target):
        self.input = input_value  # 输入值
        self.weight = weight      # 权重
        self.bias = bias          # 偏置
        self.target = target      # 目标输出
        self.output = None        # 网络输出
        self.error = None         # 误差

    def forward(self):
        """前向传播计算输出"""
        self.output = self.weight * self.input + self.bias
        self.error = 0.5 * (self.output - self.target) ** 2

    def backward(self):
        """反向传播计算梯度"""
        # 计算误差对输出的导数
        dE_dOutput = self.output - self.target
        # 计算输出对权重的导数
        dOutput_dWeight = self.input
        # 链式法则计算误差对权重的导数
        dE_dWeight = dE_dOutput * dOutput_dWeight
        return dE_dWeight

    def train(self, learning_rate):
        """使用梯度下降更新权重"""
        self.forward()
        weight_gradient = self.backward()
        self.weight -= learning_rate * weight_gradient
	--去
# 创建一个简单的神经网络实例
simple_net = SimpleNeuralNetwork(input_value=2, weight=3, bias=1, target=4)--

# 打印初始状态
print("Initial state:")j
print("Weight:", simple_net.weight)
print("Output:", simple_net.output)
print("Error:", simple_net.error)

# 进行一次训练迭代
learning_rate = 0.01
simple_net.train(learning_rate)

# 打印训练后的状态
print("\nAfter training:")
print("Updated Weight:", simple_net.weight)
print("Output:", simple_net.output)
print("Error:", simple_net.error)

```