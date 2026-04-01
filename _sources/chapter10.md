# Chapter 10: Functions

A function is a very useful technique all programmers use in their everyday life. Not only programmers use functions to improve their code, making it work better and even faster, but scientists like mathematicians, physicists, etc, also use functions all the time.

In this article you will learn what a function is, how you can create and use functions in your Python programs, and what are some of the most commonly used Python built-in functions.

## What is a function? The mathematical definition

Mathematically speaking, a function is a relation, mapping or rule between two or more sets (numbers) with some particular properties. Let's think of a function relating two sets for simplicity, represented by the variable names `x` and `y`. The relation between both sets have to be such that for each value of `x` there is only one related value of `y`. The `x` set is called the *domain* of the function, while the `y` set is the *range*.

Functions are commonly represented as `y=f(x)`, which reads 'y is equal to f of x'. The variable `x` is said to be *independent*, while `y` is *dependent*. This means that to obtain a value of the variable `y`, the variable `x` has to be set first.

The letter `f` represents the rule between variables `x` and `y`. The rule can be of various forms; for example a linear function has the form `f(x)=ax+b`, where `a` and `b` are given constant numbers. `x` is the independent variable which can take any real value. After making the operations (`a` multiplied by `x` and added to `b`) a new value is obtained, which is the result assigned to the dependent variable `y`.

## Functions in Python

Let's see how to make a linear function using Python. To create a new function you need to use the keyword `def`, followed by a function name (in this case let's just use `f`), and finally a set of parentheses containing the independent variable `x`. In Python, the independent variable is called the **parameter** of the function. A function can have more than one parameter, as you will see later. Finish the statement with a colon `:`.

Below the `def` statement comes the body of the function, which has to be indented, similar to the `if` and `for` statements. In this case we just need to compute a linear function and return its value. The linear function can be something like `2*x+1` (feel free to try something different yourself). The `return` statement is used for the function to give a value back when is called in the main program.

```python
def f(x):
  return 2*x + 1
```

You have just defined the function `f`. How do you call this function to show a resulting value, given a value of `x`? To call the function, simply write its name (in this case `f`) followed by a value (a number) between parentheses. Make use of the `print` function to show the result on the screen.

```python
def f(x):
  return 2*x + 1

print(f(2))

# 5
```

When you give a concrete value for the parameter, that is called the **argument** of the function you just called. You could have defined the function in a slightly different way. First compute the value of `2x+1`, save the result in a variable called `y`, and lastly return `y`.

```python
def f(x):
  y = 2*x + 1
  return y
```

Calling the function defined this way will work exactly the same as the previous example.

> The difference between a **parameter** and an **argument** can be subtle at first. A parameter is the name used in the function definition at the def statement level. An argument is the value you give the parameter when the function is called.

### Functions with more than one parameter

You can define a function that takes more than only one parameter. Let's make a function with three numerical parameters, `x`, `y` and `z`. Define the function `f` similar to the previous example, and separate each parameter with a comma.

```python
def f(x, y, z):
  return x+y+z

print(f(1, 2, 3))

# 6
```

In this example the `return` statement computes the sum over the three arguments. There is no need to include all parameters in the `return` statement. For example:

```python
def f(x, y, z):
  return 2*y*z

print(f(1, 2, 3))

# 12
```

### Functions which returns more than one value

Functions can return more than one value. In the `return` statement separate each returned value with a comma. When calling the function (and printing the output) you will get a tuple containing each returned value.

```python
def f(x, y, z):
  return x+y, x+z

print(f(1, 2, 3))

# (3, 4)
```

### Functions with arbitrary data types

So far you have seen different examples of functions, all of them working with numerical data types. But with Python you can define functions that takes any data type values as parameters, and also return any data type values.

Let's set an example where a function takes a string (could be a name) and outputs another string with a welcoming message.

```python
def hello(name):
  return 'Welcome ' + name +'. Happy coding!'

print(hello('John'))

# Welcome John. Happy coding!
```

### Default arguments

What happens if you don't give the necessary arguments to a function? You will learn more on this with the exercises at the end of the article, but you can guess already that you may encounter some sort of error. You can give a specific parameter a default value for cases where you don't specify it when calling a function.

To set a default value for a parameter, make an equal sign `=` after its name in the `def` statement and specify the value you want it to take:

```python
def hello(name='guest'):
  return 'Welcome ' + name +'. Happy coding!'

print(hello())

# Welcome guest. Happy coding!
```

As you can see, calling the function without any arguments makes the `name` parameter take the value of 'guest'. But if you call the function giving an argument, like 'Karen', the `name` parameter will take that value. The function will ignore the default value:

```python
def hello(name='guest'):
  return 'Welcome ' + name +'. Happy coding!'

print(hello('Karen'))

# Welcome Karen. Happy coding!
```

## Built-in functions

Python has many functions that are already implemented for you to use directly. You have been using a couple of them throughout the course: the `print()` and the `len()` functions. Let's see how they work in more detail.

### The print function

The print function, as you have seen throughout the course, is used to show certain information on the screen. You can use it to print a message using a string, or to show the value of certain variables, and even combine both.

```python
print('Hello World!')
# Hello World!

pi = 3.14
print(pi)
# 3.14

print('The value of pi is ' + str(pi))
# The value of pi is 3.14
```

But you can do more with the print function. Imagine you want to print a list of names. You can do it by using the print function for each of the names, which will result in the list of names printed one below the other:

```python
print('John')
print('Jane')
print('Karen')

# John
# Jane
# Karen
```

The names are shown each in a different line by default. What if you wanted to show them in the same line, with each name separated by a comma? The print function can take an additional parameter `end`, which indicates what should be printed at the end of the line. The default value for the `end` parameter is the new line character `\n`, that's why the default behaviour is to print the names in different lines.

Let's repeat the last example, this time giving each print function a value for the `end` parameter. The first two will have an `end` value of `', '`, that is a comma and a space. The last print will have an end value of `'.'`, so that the last one ends with a period.

```python
print('John', end=', ')
print('Jane', end=', ')
print('Karen', end='.')

# John, Jane, Karen.
```

Looks much better! Another way to get the same result is to use a single print statement with each name separated with a comma:

```python
print('John', 'Jane', 'Karen')

# John Jane Karen
```

The names are separated with a space by default. You can specify a different separator with the `sep` parameter. Let's give the print function a `sep` parameter with a value of `', '` (comma and space):

```python
print('John', 'Jane', 'Karen', sep=', ')

# John, Jane, Karen
```

So, the `sep` parameter has a default value of `' '`, which is a space character. What about the period at the end? You can include the `end` parameter with a value of `'.'`:

```python
print('John', 'Jane', 'Karen', sep=', ', end='.')

# John, Jane, Karen.
```

And there you have it! You just made the same example in just one line of code.

### The len function

The `len()` function is simpler than the `print()` function because it doesn't have any extra arguments. The `len()` function returns the number of items in an object, such as a list.

```
>>> len(['John', 38, 'California'])
3
```

When the `len()` function is applied to a string, it returns the number of characters of it:

```
>>> len('Hello World!')
12
```

There are specific cases like *sets*, where you have to pay attention because the number you see may not be equal to what the `len()` function returns:

```
>>> len({'a', 'b', 'c', 'a'})
3
```

In this example the output is 3, and not 4, because the set returns the unique elements of it, which in this case is `{'a', 'b', 'c'}`. The character `'a'` is repeated.

### The input function

This is a very interesting and useful function that helps Python programs interact with the user. The `input()` function takes a single string parameter. When the function is called, a message is shown and the program waits for the user to input a string text.

```
>>> input('Enter your name: ')
Enter your name:
```

In this example we are using the terminal but you can try this with a script file and executing it. Enter your name and hit `Enter`:

```
>>> input('Enter your name: ')
Enter your name: DeusDev
'DeusDev'
```

The text you just wrote is shown (returned) on the screen. You can also save what the user inputs in a variable for later use:

```
>>> name = input('Enter your name: ')
Enter your name: DeusDev
>>> print('Your name is', name)
Your name is DeusDev
```

Keep in mind that the `input()` function returns string values. However you can use other Python functions to convert strings to integers, floats, etc, in case the input values represent numbers.

### All built-in functions

There are more built-in functions, and they are all listed on the Python official documentation: [https://docs.python.org/3/library/functions.html](https://docs.python.org/3/library/functions.html). Have some time to go over all of them, at least to have an idea of what Python is capable of.

## Conclusion

In this article you learned about Python functions. Python has a number of built-in functions you can use directly. Each function has its own purpose, and you will learn to use them at given time.

Functions can also be built to fulfill your own needs. You learned how to define custom functions using the `def` keyword. The body of a function usually needs a `return` statement in order to give one or more values back.

In the next chapter you will learn about Python methods, which are functions that work for specific objects.

## Exercises

The next list of exercises are intended for you to practice what you have learned on this article about functions.

1. In this article the functions defined in the examples all used the `return` statement to return a specific value. Sometimes a function can be defined without a `return` statement. Make a new function that takes one parameter `country`, and prints a message saying `'The country is India'` when the country parameter is equal to the string `'India'`. To do this, the body of the function will only contain a `print` statement. Test your function.
2. Make a new function that computes the square of a given number, `x^2=x*x`, this is the number multiplied by itself. Include a `return` statement in your function definition, and test the function with different values, including floats and negative.
3. Make a function with two parameters `x` and `y`, and compute the product of both numbers. Test the function against different numbers.
4. Use the same function of the exercise #3, but this time return two values: the product and the sum of `x` and `y`.
5. Make a function that takes a list as its argument, and return the number of elements it contains. Test the function with lists of different lengths.
6. Use the function of exercise #5 but this time call it by using a string as its argument. Is it working as expected? Why or why not?
7. Use the function of exercise #3 and give the parameters default values. Test the new function for different cases.
8. This exercise is intended to show you a special value returned by some functions in special cases. Open a new terminal and enter the Python interpreter. Define a new function without any parameters (you can call it `f` or however you prefer). In the block of the function make a single `return` statement without anything else. If you call the function like `f()` nothing will be shown. But what happens if you do `print(f())`? What is the function returning?