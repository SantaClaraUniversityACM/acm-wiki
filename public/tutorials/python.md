# Python Tutorial

Written by Jake Esperson, 2024.

Hello everyone! If you are looking to learn Python, you have come to the right place. Python is a powerful language that is easy to learn and fun to use. It is a great language for beginners and experts alike. In this tutorial, we will cover the basics of Python and help you get started with programming.

First of all, why should you learn Python and what can you expect to get out of this?

- You're a beginner and want to learn programming with one of the easiest to learn.
- You want to leverage AI/ML libraries, which Python specializes in.
- You want a language that is versatile and can be used for web development, data analysis, and more.
- You want a quick refresher on the basics of Python.

Now, let's get started!

## Table of Contents

- [Python Tutorial](#python-tutorial)
  - [Table of Contents](#table-of-contents)
  - [Installation](#installation)
  - [Hello, World](#hello-world)
  - [Variables](#variables)
  - [Conditionals](#conditionals)
  - [Loops](#loops)
  - [Handling Input](#handling-input)
  - [Functions](#functions)
  - [Putting It All Together](#putting-it-all-together)

## Installation

Python, like most languages, is one that you must install in order to use. It is called a "runtime" language, which means that code can be run without being complied as it is complied in real time.

- Download the latest version of Python from the [official website](https://www.python.org/downloads/).
- After that is done, see if it is working by opening a command prompt and typing `py --version` for Windows and `python3 --version` for Mac/Linux. A version number should appear.
  - For the rest of the tutorial, use whatever command is appropriate for your operating system.
  - If not, you may need to add Python to your PATH. The exact instructions can vary, so look up "add Python to PATH" and follow the instructions. Remember, software engineering is just glorified Googling sometimes!
- Now that you have Python installed, we need to pick a coding environment. I will be using Visual Studio Code and I would recommend you do the same. You can download it [here](https://code.visualstudio.com/).
- With that, open VSCode and create a new file with the `.py` extension.

Now that you have Python installed and a coding environment set up, let's get started with the basics of Python.

## Hello, World

First, we will simply print "Hello, World!" to the console. This can be done with the following code:

```python
print("Hello, World!")
```

And that's it! To run the program, open the terminal in VSCode and type `py <filename>.py`. You should see `Hello, World!` printed to the console.

## Variables

Variables are extremely important in any language, so lets talk about how to do it in Python!

Most languages require you to declare the type of variable you are creating, but Python does not. This is because Python is a dynamically typed language, meaning that the type of the variable is determined at runtime. To define a variable, simply type the name of the variable and assign it a value. For example:

```python
x = 5
message = "Hello, World!"
arr = [1, 2, 3, 4, 5]
```

## Conditionals

Conditionals are used to make decisions in your program. Python uses the `if`, `elif`, and `else` keywords to create conditionals.

That could looks something like this:

```python
if x > 5:
    print("x is greater than 5")
elif x < 5:
    print("x is less than 5")
else:
    print("x is equal to 5")
```

The `if` statement checks if the condition is true, and if it is, it executes the code inside the block. The `elif` statement is short for "else if" and checks another condition if the previous condition is false. The `else` statement is executed if none of the previous conditions are true.

Python also uses a lot of English words for its operators, such as `and`, `or`, `is`, and `not`. These are used to combine multiple conditions in a single statement. For example:

```python
if x > 5 and x < 10 or not x is 0:
    print("x is between 5 and 10 or x is not 0")
```

## Loops

Loops are used to repeat a block of code multiple times. Python has two main types of loops: `for` loops and `while` loops.

A `for` loop is used to iterate over a sequence of items. A traditional `for` loop in Python looks like this:

```python
for i in range(5):
    print(i) # Output: 0, 1, 2, 3, 4
```

However, Python also has a `for-each` loop that can be used to iterate over a sequence of items. This is done using the `in` keyword:

```python
arr = [1, 2, 3, 4, 5]
for item in arr:
    print(item) # Output: 1, 2, 3, 4, 5

# You can also use the enumerate function to combine the index and item in a loop
for index, item in enumerate(arr):
    print(f"Index: {index}, Item: {item}") # Output: Index: 0, Item: 1, Index: 1, Item: 2, etc.
```

You can also break out of a loop using the `break` keyword, or skip to the next iteration using the `continue` keyword.

```python
for i in range(10):
    if i == 5:
        break
    print(i) # Output: 0, 1, 2, 3, 4
```

A `while` loop is used to repeat a block of code until a condition is false. For example:

```python
x = 0
while x < 5:
    print(x)
    x += 1 # Output: 0, 1, 2, 3, 4
```

This means you have to be careful what data types you are adding together so the program doesn't crash. Using methods like `str()` and `int()` can change types for a specific operation.

## Handling Input

To get input from the user, you can use the `input()` function. This function takes a string as an argument, which is the prompt that will be displayed to the user. For example:

```python
name = input("What is your name? ")
print(f"Hello, {name}!") # Input: Jake, Output: Hello, <name>!
```

## Functions

Functions are crucial to any project, so lets take a look at how to create them in Python.

To create a function, use the `def` keyword followed by the name of the function and any parameters it may take. For example:

```python
def say_hello(name):
    print(f"Hello, {name}!")
```

To call the function, simply type the name of the function followed by the parameters in parentheses. For example:

```python
say_hello("Jake!") # Output: Hello, Jake!
```

Another note is that Python uses indentation to determine what is inside the function and what is not. This is different from most languages, which use curly braces `{}` to denote the start and end of a function. Python also doesn't use `;` to end lines, you simply just end the line. This makes Python easy for beginners to learn and read. Also, as seen in the above code, denote comments using `#` for single line comments. However, there is no multi-line comment, so you must use `#` for each line (Hint: in VSCode, highlight the lines and press `Ctrl+/` to comment them all at once).

## Putting It All Together

Now that we have covered the basics of Python, let's put it all together in a simple program.

Your job is to make a simple number guessing game. The program should generate a random number between 1 and 100, and the user should guess the number. The program should tell the user if their guess is too high or too low, and keep track of the number of attempts it took to guess the correct number. Once the user guesses the correct number, the program should print a congratulatory message with the number of attempts it took.

So, start by creating a new Python file and writing the code for the number guessing game. There are many ways to implement this, so feel free to get creative with it!

Once you are finished or need some help, check out the final program below. Good luck!
