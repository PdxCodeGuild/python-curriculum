# Week 3, day 1

## More Recursion

Today we took a look at "tree recursion" (how a lot of recursive algorithms can be visualized as a tree). We then discussed how tree structures appear a lot in programming, for example:

* recursive fibonnacci sequence algorithm
* parse trees
* HTML (the DOM is a tree)
* merge sort, etc.

We then whipped up an arithmetic expression evaluator to see how expressions in a programming language can be represented as trees and evaluated using recursion.

```python
# we want something like:
# exp = Number | Add exp exp | Mul exp exp

# but we have to work with simple python data structures (we haven't see classes yet, so we can't define our own datatypes)
# So we can use arrays!

# for example:
# ['Number', 2]
# ['Add', ['Number', 3], ['Number', 4]]
# ['Multiply', ['Number', 2], ['Number', 3]]

# parse('1 + 2 * 3') -> 
# ['Add', ['Number', 1], ['Multiply', ['Number', 2], ['Number', 3]]]

# eval(['Add', ['Number', 1], ['Multiply', ['Number', 2], ['Number', 3]]]) -> 7

def eval(exp):
    if exp[0] == 'Number':
        return exp[1]
    elif exp[0] == 'Add':
        return eval(exp[1]) + eval(exp[2])
    elif exp[0] == 'Multiply':
        return eval(exp[1]) * eval(exp[2])

```

The idea is `eval` will "evaluate" the expression by evaluating all the sub-expressions and performing the arithmetic operations. A 'Number' is considered a base-case expression, and evaluates to its numerical value. An 'Add' expression consists of 2 sub-expressions, and evaluates to the result of adding together the results of `eval`ing the sub-expressions. 'Multiply' works the same way as add.

This is basis for how programming languages work! The only piece missing is `parse`, which turns a given string (source code) into the parse tree representation. But that is a topic for another day!
