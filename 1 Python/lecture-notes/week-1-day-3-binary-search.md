# Week 1, day 3

## Binary Search

Check out the [visualization of searching a sorted list](https://www.cs.usfca.edu/~galles/visualization/Search.html). Notice the difference between a sequential search and a binary search. Make sure to step through it one step at a time so you can see what is going on.

Note: binary search only works on a sorted list!

This technique is exactly the same as our optimization process for Guess the Number.

## Algorithm Complexity Analysis

Key points:

* "Big O Notation"
* linear time algorithms are MUCH slower than logarithmic algorithms
  * in big-O terms, O(n) is much slower than O(log(n))
  * remember the example of halving a number over and over
    * it only took 40 iterations for 1 trillion to reach 1!
    * any time you have a "repeated halving" process like this, you probably have a O(log(n)) algorithm
* Sequential search = O(n)
* Binary search = O(log(n))

## Guess the Number Solution

We saw a recursive/functional solution AND an loop-based/imperative solution.

Key points:

* both solutions equally valid
* recursive solution potentially less likely to contain bugs due to "state" (state of variables)
  * I mentioned I had a bug where I assigned the new min/max values AFTER I assigned the new guess
    * this wouldn't have happened in the recursive solution, because there were no assignment statements
  * the mutation of variables is often a source of bugs
  * "functional programming" seeks to eliminate mutations, favors recursion over loops

## Git

Key points:

* git is a "Version Control System" (VCS)
  * allows programmers to track changes to source code
  * created by Linus Torvalds (creator of Linux) to facilitate large scale open source development
    * existing VCS systems at the time were mainly meant for small teams, didn't work well for open source
* git is a "leaky abstraction"
  * this means that it exposes implementation details, making it harder to use if you don't understand the innards of git
* check out the [course docs page on version control](https://github.com/PdxCodeGuild/python-curriculum/blob/main/0%20Intro/7%20-%20Version%20Control.md)
* check out [github's Resources to learn Git](https://try.github.io/)