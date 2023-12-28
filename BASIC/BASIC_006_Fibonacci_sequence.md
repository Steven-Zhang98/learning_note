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

Recursion is an exciting concept in coding. Because recursive consists of two parts. One is the base case, which doesn't need to recursion. The other is the recursive case, which shows the relationship between the f (n) and f (n-1) and f (n-2). F (0) and f (1) are the start of the Fibonacci sequence but are also the start of returning the result.

Take fib (4) as an example, showing how recursion works. There are two steps. 

### Call the function. 
When we try to calculate fib (4), we have to compute fib (3) and fib (2).

For fib (3), it is further necessary to compute fib (2) and fib (1). 

For fib (2), it is further necessary to compute fib (1) and fib (0).

### Return the results 

Once we calculate the fib (2),  we return it to fib (3), and then we can calculate fib (2). And repeat it. 
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