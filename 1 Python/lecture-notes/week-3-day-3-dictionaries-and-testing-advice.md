# Week 3, day 3

## More on dictionaries

Today we talked about dictionaries more, specifically we talked about how dictionaries can sometimes be used to replace if-statements in a more concise way. Specifically we talked about how this could be used in the unit converter application, where the conversion values could be stored in a dictionary, and then you could look up the conversion factor of the unit you want to convert to using your dictionary (instead of having a bunch of if-else statements).

## Advice for testing

We talked about how often times it can be difficult to write tests for your code, even if that code is finsihed and working. The first secret is to break things out into smaller pieces that can be tested individually. For example, maybe putting something into a function, and then testing that function. The second secret is to be ok with not testing every line of code. Testing more and more of your code offers diminishing returns, so 100% test coverage is  generally not necessary. As you gain more experience, you will figure out ways to test more and more of your code. But for now, aim to just test the core pieces, and maybe avoid the "user interaction" stuff, such as I/O to the console. If code prompts the user for input, or prints something to the terminal, you might want to avoid testing that section for now.

Here is an example of a program that worked, but was difficult to test. The program is called "shout", and it simply uppercases a string and adds an exclamation point. So "hello" would turn into "HELLO!".

```python
while True:
    text = input('enter some text: ')
    print(text.upper() + '!')

    should_continue = input('enter "y" to continue, "n" to stop: ')
    if should_continue == 'n':
        break
```

How can we test the "shout" functionality? Basically we just want to test that we properly transform our string. The problem is that code is wound up within all this unrelated logic of looping, getting user input, etc.

Here we see how we can refactor our code to enable us to test the `shout` functionality. The key is to break out the code into its own function, and then we can test that function.

```python
def shout(s):
    return s.upper() + '!'


def main():
    while True:
        text = input('enter some text: ')
        print(shout(text))

        should_continue = input('enter "y" to continue, "n" to stop: ')
        if should_continue == 'n':
            break

# This will run main if the program is being executed as a script, otherwise it won't run main
# That means main won't get run when we import this file in our test file. (which is what we want in this case) 
if __name__ == '__main__':
    main()
```

And here is the accompanying test file

```python
import shout

def test_shout():
    s = 'hello'
    assert shout.shout(s) == 'HELLO!'

```