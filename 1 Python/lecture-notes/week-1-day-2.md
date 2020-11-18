The following is inspired by, and in some parts taken from, a famous computer science textbook [Structure and Interpretation of Computer Programs](https://mitpress.mit.edu/sites/default/files/sicp/full-text/book/book-Z-H-10.html#%_sec_1.1.7).

## Wishful Thinking

Today we looked at the idea of "wishful thinking", which allowed us to put off filling in the details of a helper-function, and focus on the higher level algorithm. When the higher level plan is finished, we returned to our helper-functions and filled in the implementation.

This was an example of "top-down design", where you start from the top (the higher level of abstraction), and work your way down.

We also saw an example of a recursive function!

Here is the example code:

```python
def sqrt(x):
    return sqrtIter(1.0, x)

def sqrtIter(guess, x):
    if isGoodEnough(guess, x):
        return guess
    else:
        newGuess = improve(guess, x)
        return sqrtIter(newGuess, x)

def isGoodEnough(guess, x):
    difference = x - guess**2
    return -0.001 < difference < 0.001

def improve(guess, x):
    return average(x / guess, guess)

def average(a,b):
    return (a+b) / 2

print(sqrt(9))

```