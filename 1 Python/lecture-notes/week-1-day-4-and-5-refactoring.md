# Week 1, days 4-5

## Refactoring

After completing the ROT13 cipher (aka Caesar Cipher), we saw how we could simplify the program by abstracting out duplicated code. We also saw some advanced techniques for reducing the LoC (lines of code) such as list comprehensions and "if expressions" (some languages call these a "ternary operator").

This process of cleaning up code without changing its behavior is called "refactoring".

You should always refactor your code after you get it working! Maintainability of code is very important, so great care and effort must be put into keeping the code clean, and file sizes small, when possible.

### Testing

During this refactoring process, we used the [pytest](https://docs.pytest.org/en/latest/) module for writing automated tests, which made refactoring much easier.

## The Unix Shell

We also played around with writing shell scripts, as well as discussed various aspects of the shell. Some of the topics covered:

  * the PATH environment variable
    * the PATH variable tells your shell where it should look for programs, so you don't have to type the full path of common programs
    * you will often need to add new directories to your PATH when installing new tools
    * you can add your own directory to your PATH where you can put your own custom scripts
  * using the `cat` command to print the contents of a file
  * passing command line arguments to python programs using the `argparse` module
  * discussed a bit about the [Unix Philosophy](https://en.wikipedia.org/wiki/Unix_philosophy)
    * namely, passing arguments and redirecting I/O instead of writing programs that prompt for input
      * programs that prompt for input usually are harder to connect with other programs, and incorporate into scripts
  * discussed the importance of becoming comfortable on the command line