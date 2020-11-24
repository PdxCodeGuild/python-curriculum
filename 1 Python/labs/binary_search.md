# Binary Search

We've seen binary search in action when we did the Guess the Number lab. This time, we are using binary search to search an array (list).

Your function should take in a list (assume it is sorted) and an element to search for. Your function should return the index of the element if it is found, and -1 if it is not found.

Example:

```python
search([1,2,3,4,5,6], 3) # should return 2

search([1,2,4,5,6], 3) # should return -1
```

## Testing

Here is an example pytest file:

```python
# import your search function from your main source code file
from binary_search import search

def test_binary_search():
    assert search([1,2,3,4], 3) == 2
    assert search([1,2,3,4], 5) == -1
    assert search([1,2,3,4], 1) == 0
    assert search([1,2,3,4], 4) == 3
    assert search([1,2,3,4,5], 1) == 0
    assert search([1,2,3,4,5], 5) == 4
    assert search([1,2,3,4,5], 3) == 2
```

## Version 2

When we looked at Guess the Number, we saw two different ways to implement the search. One way used loops, the other way used a recursive function.

For version 2 of the assignment, implement binary search again, but this time use the other method. Use recursion if you used loops previously, use loops if you used recursion previously.

Once you are complete, ask yourself which version do you prefer?
