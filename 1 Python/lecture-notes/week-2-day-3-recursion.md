# Week 2, day 3

## Recursion

We talked more about recursion, specifically looking at iterative and recursive algorithms side by side, and then finally showing how an iterative algorithm can be written recursively.

Here is the code we wrote during lecture:

```python
def factorial(n):
    return 1 if n == 0 or n == 1 else n * factorial(n-1)

def factorial_loops(n):
    accumulator = 1
    for i in range(1,n+1):
        accumulator = accumulator * i

    return accumulator


# fibonnaci sequence
# 0 1 1 2 3 5 8 13 21 34 ...

# fib(0) -> 0
# fib(1) -> 1
# fib(6) -> 8

def fib(n):
    return n if n < 2 else fib(n-1) + fib(n-2)

# O(fib(n)) or ~O(2^n)

# using a lambda we could write it like this:
# fib = lambda n: n if n < 2 else fib(n-1) + fib(n-2)

# loop version: O(n)
def fib_loops(n):
    a, b = 0, 1

    for i in range(n):
        a, b = b, a+b

    return a

# this example shows how we can rewrite the iterative algorithm using recursion (a function that calls itself).
# even though we are using recurion, technically, this is the same as the iterative algorithm, and so it is O(n)
def fib_loops_recursion(n, a, b, i):
    return a if i == n else fib_loops_recursion(n, b, a+b, i+1)

# example of how we might call it: note we must pass in the starting values of the sequence
# we could clean this up a bit if we used "default arguments", but we will save that for another day :)
# fib_loops_recursion(6, 0, 1, 0)

```