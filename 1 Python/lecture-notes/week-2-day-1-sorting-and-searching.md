# Week 2, day 1-2

## Binary Search review

We reviewed binary search and went through [the lab where we implemented both a recursive and an imperative version](../labs/binary_search.md).

### Testing

I mentioned that when I tell students they **shoud** write tests, they usually end up not doing it. So we all walked through setting up [pytest](https://docs.pytest.org/en/latest/) and wrote some tests for binary search. Going forward I will require you all to write tests for your labs!
 
## Sorting Algorithms

Since binary search depends on a sorted list, we then took a look at various ways of sorting a list. Each student [implemented a sorting algorithm and presented on it](../labs/sorting.md).

Remember, each sorting algorithm has its own tradeoffs. When choosing a sort, consider the following:

* what are the best/worse case scenarios
* what is the time/space complexity
* what scenarios should this sort be preferred/avoided
* do I need an in-place sort or a new array?
* do I need a "stable" sort?

For whiteboarding interviews at tech companies, focus on the most common sorts such as the ones we learned in class, and you should be fine.
