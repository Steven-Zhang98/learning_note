## Recursion

```python
def fib(n):
    if n == 0:
        return 0
    if n == 1:
        return 1
        
    # n>=2
    return fib(n-1) + fib(n-2)
    
result = fib(9)
print("Fib result:", result)
```

Recursion is an exciting concept in coding. Because recursive consists of two parts. One is the base case, which doesn't need to recursion. The other is the recursive case, which shows the relationship between the f (n) and f (n-1) and f (n-2). f (0) and f (1) are the start of the Fibonacci sequence but are also the start of returning the result.

Take fib (4) as an example, showing how recursion works. There are two steps. 

### (1) Call the function. 
When we try to calculate fib (4), we have to compute fib (3) and fib (2).

For fib (3), it is further necessary to compute fib (2) and fib (1). 

For fib (2), it is further necessary to compute fib (1) and fib (0).

### (2) Return the results 

Once we calculate the fib (2),  we return it to fib (3), and then we can calculate fib (3). And repeat it. 
## Convert to Iterative

```python
def fib(n):
    num_0 = 0
    num_1 = 1
    # num_2 = num_1 + num_0
    # num_3 = num_2 + num_1
    # num_4 = num_3 + num_2
    # num_5 = num_4 + num_3
    if n == 0:
        return num_0
    elif n == 1:
        return num_1
    else:
        for i in range(2,n+1):
            sum = num_0 + num_1
            num_0 = num_1
            num_1 = sum
        return sum
print(fib(4))
```

The number of cycles is n- 2 because literation starts from 2, so the range is (2,n) because the sequence does not include the second parameter, so the content is (2, n+1)

## Recursion VS literation

If we want to write code on small microcontrollers that don't have too much memory, iteration is more beneficial than recursion. 

## Optimise Recursion with Memoization

```python
def fib(n, memo={}):
    if n in memo:
        return memo[n]
    if n <= 1:
        return n

    memo[n] = fib(n - 1, memo) + fib(n - 2, memo)
    return memo[n]

print(fib(9))  # Example usage
```

I found some repeated calculation steps in traditional recursion. What if we can store some Intermediate results? Our code could be more effective.

The first step is to ensure a shared dictionary among all fib function calls. If we define a dictionary in function arguments, the dictionary will only be determined once.

Whenever we find a new number not included in the dictionary, it will store the result in this shared memo dictionary and Pass the memo dictionary to each recursive call.

## Optimise Iteration in Memoization

```python
def fib(n,memo = {}):
    memo[0] = 0
    memo[1] = 1
    if n in memo:
        return memo[n]
    else:
        for i in range(2,n+1):
            memo[i] = memo[i-1] + memo[i-2]
        return memo[n]
```

## Real-World Application

Suppose we working on software for financial markets, and we need to analyse investment patterns. One of your tasks is to predict the growth of investments based on certain recursive patterns, similar to the Fibonacci sequence, where future values depend on the sum of a number of previous values.

```python
def investment_growth_model(n, j, initial_values):
    memo = {i: initial_values[i] for i in range(j)}
    
    def calculate_growth(current_n):
        if current_n in memo:
            return memo[current_n]

        total = 0
        for i in range(1, j + 1):
            total += calculate_growth(current_n - i)
        
        memo[current_n] = total
        return total

    if n < j:
        return initial_values[n]
    
    return calculate_growth(n)

# Example usage
initial_values = [100, 110, 120]  # Example initial values for intervals 0, 1, 2
print(investment_growth_model(5, 3, initial_values))

```

This function has two parts: one is the outer function used to initialise the dictionary and set up the base case. 

The second part is recursion, which calls itself to summing the growth values of previous intervals up to 'j' intervals back. And check if the current interval is in the dictionary. If not in the dictionary, it computes the values and adds them to the dictionary, and then return it.
## Stack Heap Memory And Concert Stage

Imagine there are performers, a stage, and a scoreboard on the concert stage. Memory is the stage, the stack is the performers, and the dictionary is the scoreboard stored in the heap. 

Every time we call a function, a performer will go to the stage, Since this is a recursive function, n dancers will be called to the stage, and only after the nth dancer finishes and exits the stage will the n-1 th dancer begin to perform. 

But gathering many performers on the stage will overwhelm the stage, called the stackoverflow. 

The scoreboard is shared with every performer and records every performer's score. When nobody is using the scoreboard, the scoreboard will be taken away. 