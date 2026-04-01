# Chapter 12: Modules

Python has a way to encapsulate a set of objects such as functions, variables, etc, in a single file with a given name. These objects can be used in your programs without the need to include all the code in your script.

In this article you are going to learn how to create a Python module, and how to use it in your programs. You will also learn about some of the most commonly used Python modules and its useful functions.

## Python modules

### Creating and using a custom module

To make a custom Python module, create a new file and give it a name like **deusdev.py** or whatever name you want it to have. It is important that the file has the **py** extension. This is the file that will contain all the functions to be used later.

In your module file, create a new function. For now let's make a simple function that prints a welcoming message like you did before in this course:

```python
# deusdev.py

def greet(name):
  print('Hello {}. Welcome to Python!'.format(name))
```

How can this module with its function be used in another script? Let's suppose the file is saved in the Desktop. Open a new file, also in the Desktop, and give it some name like **test.py**. This will be the file containing the script that will call the function `greet()` from the **deusdev.py** module.

First you need to *import* the module. To do that, use the `import` keyword, followed by the name of the module, in this case `deusdev` (without the *.py* extension). Now that the module is included in your script, you can use the function defined in it.

The function `greet()` can be used in the same way as a method. Use the module name `deusdev` followed by a period, and then the name of the function `greet()`.

```python
# test.py

import deusdev

deusdev.greet('John')

# Hello John. Welcome to Python!
```

Another way to use a module's function is to assign it to a variable. You can assign the function using `deusdev.greet` (without parentheses) to a variable called `greet_func` (or something different). Then you can call the function using `greet('John')`.

```python
# test.py

import deusdev

greet_func = deusdev.greet
greet_func('John')

# Hello John. Welcome to Python!
```

There are other ways you can import functions from your module. To import the `greet` function from the `deusdev` module, use the keyword `from`, followed by the module's name `deusdev`, then `import` and finally the function you want to import, in this case `greet`. Then use the function without the module's name.

```python
# test.py

from deusdev import greet

greet('John')
# Hello John. Welcome to Python!
```

If you have more than one function in your module, you can import each function separating them with a comma. Let's add a new function to the module that checks if a given number is even:

```python
# deusdev.py

def greet(name):
  print('Hello {}. Welcome to Python!'.format(name))

def isEven(n):
  return n%2 == 0
```

Then in your main file import and call both functions:

```python
# test.py

from deusdev import greet, isEven

greet('John')
# Hello John. Welcome to Python!

print(isEven(41))
# False
```

You can use the wildcard `*` to import all the functions at once, instead of writing each of them:

```python
# test.py

from deusdev import *

greet('John')
# Hello John. Welcome to Python!

print(isEven(41))
# False
```

You can also use the `as` keyword to give the module a different name to use it in the main program. This can be useful when module names are somewhat long and you want to reduce the typing in your program.

```python
# test.py

import deusdev as dd

dd.greet('John')
# Hello John. Welcome to Python!
```

The `as` keyword can be combined with the `from` keyword to import a module's function with a different name:

```python
# test.py

from deusdev import greet as greetings

greetings('John')

# Hello John. Welcome to Python!
```

### pycache files

You may have noticed that when you run your scripts importing a custom module, a new folder is created with the name **__pycache__**. Inside this folder there is a file with the name **deusdev.cpython-311.py** (you may see it with a slightly different name depending on your module's name and the Python version you are using). This is done to make the loading of modules faster, using something called *cache*. I won't get into much details in this course, but you can read more about this in the [official Python documentation](https://docs.python.org/3/tutorial/modules.html#compiled-python-files).

Next you are going to learn about some of the most common Python's built-in modules.

## The random module

The [random module](https://docs.python.org/3/library/random.html) is used to generate pseudo-random numbers. Let's see some of the functions you can use with this popular module.

This time you can work with the Python interpreter, without the need to make a new file. First, import the `random` module.

```
>>> import random
```

Once the module is imported, you can begin to use its functions. Let's see some of them.

### random.random()

The `random()` function returns a random floating point number between 0 and 1. 0 is included, meaning that sometimes you can get that exact value, but the 1 is not included in the range, so you will never get a 1 with this function.

```
>>> random.random()
0.5727401830032317
>>> random.random()
0.4977649539769565
>>> random.random()
0.11762935447218192
```

### random.uniform(a, b)

The `uniform()` function is similar to the `random()` function, but with `uniform()` you can return a floating point number between two arbitrary numbers `a` and `b`.

```
>>> random.uniform(4, 10)
9.377423126967187
>>> random.uniform(4, 10)
6.98125740847348
>>> random.uniform(4, 10)
5.565696392526846
```

### random.randrange(start, stop, step)

The `randrange()` function returns a random integer value between `start` (optional, default is 0) and `stop` (not included in the range), and you can give an optional parameter `step` (default is 1).

```
>>> random.randrange(5)
0
>>> random.randrange(5)
3
>>> random.randrange(5, 50)
17
>>> random.randrange(5, 50)
33
>>> random.randrange(5, 50, 10)
5
>>> random.randrange(5, 50, 10)
15
```

### random.randint(a, b)

This is equivalent to the `randrange()` function with `a` and `b+1` as the parameters `start` and `stop`, because in this case `a` and `b` are both included.

```
>>> random.randint(5, 10)
6
>>> random.randint(5, 10)
5
>>> random.randint(5, 10)
10
```

### random.choice(seq)

With the `choice()` function you can randomly select an element from a sequence, such as a list. For example, say you have a list of names and you want to select one of them randomly:

```
>>> random.choice(['John', 'Karen', 'Sean', 'Jane'])
'Karen'
>>> random.choice(['John', 'Karen', 'Sean', 'Jane'])
'Karen'
>>> random.choice(['John', 'Karen', 'Sean', 'Jane'])
'Jane'
>>> random.choice(['John', 'Karen', 'Sean', 'Jane'])
'Karen'
>>> random.choice(['John', 'Karen', 'Sean', 'Jane'])
'Sean'
```

### random.shuffle(seq)

The `shuffle()` function takes a sequence, such as a list, and shuffles it (mixes its elements) in place (meaning that it doesn't return a new sequence).

```
>>> names = ['John', 'Karen', 'Sean', 'Jane']
>>> random.shuffle(names)
>>> names
['Sean', 'Jane', 'Karen', 'John']
```

## The math module

The [math module](https://docs.python.org/3/library/math.html) comes in handy when dealing with special mathematical operators. Let's import the math module to start.

```
>>> import math
```

Keep in mind that this module only works for real numbers. If you need to work with complex numbers, use the [cmath module](https://docs.python.org/3/library/cmath.html#module-cmath).

Let's see some of the functions the math module has for you.

### math.ceil(x)

The `ceil(x)` function returns the smallest integer value greater than or equal to the argument `x`.

```
>>> math.ceil(5.2)
6
>>> math.ceil(5)
5
>>> math.ceil(1.9)
2
```

### math.factorial(n)

This function returns the factorial of the integer value `n`.

```
>>> math.factorial(5)
120
>>> math.factorial(3)
6
>>> math.factorial(0)
1
```

### math.gcd()

Returns the greatest common divisor between two numbers. Since the Python version 3.9 this function can take more than two parameters.

```
>>> math.gcd(4, 18)
2
>>> math.gcd(6, 18)
6
>>> math.gcd(4, 18, 8)
2
```

### math.exp(x)

Returns the [number e](https://en.wikipedia.org/wiki/E_(mathematical_constant)) to the power of `x`. The number `e` is approximately equal to 2.718.

```
>>> math.exp(2)
7.38905609893065
>>> math.exp(0)
1.0
```

### math.sin(x)

Returns the sine of the number `x`.

```
>>> math.sin(7.32)
0.8607873878989017
>>> math.sin(0)
0.0
```

### math.pi

Returns the constant [number pi](https://en.wikipedia.org/wiki/Pi). Although the number pi has an infinite number of decimals, this module gives this number with a fixed number of decimals.

```
>>> math.pi
3.141592653589793
```

## The numpy module

The [numpy module](https://numpy.org/) is widely used among developers who work with data analysis. Go ahead and import the `numpy` module.

```
>>> import numpy
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'numpy'
```

Ups! It seems that `numpy` is not included with Python. Before using the `numpy` module, you have to install it. The [official numpy installation website](https://numpy.org/install/) gives different options to install it. In this article I'm going to use `pip`. Execute `pip install numpy` in the terminal (outside the Python interpreter):

```
PS C:\> pip install numpy
Collecting numpy
  Downloading numpy-1.24.2-cp311-cp311-win_amd64.whl (14.8 MB)
     ---------------------------------------- 14.8/14.8 MB 17.7 MB/s eta 0:00:00
Installing collected packages: numpy
Successfully installed numpy-1.24.2
```

If everything goes well, you should see a message similar to the one in the example, with information such as the module version that has been installed.

Let's go to the Python interpreter and try to import the numpy module, now that you have it installed.

```
>>> import numpy
>>>
```

No errors, that is good! Actually, let's import the module with a different name, which is the most commonly way to do it:

```
>>> import numpy as np
>>>
```

Now you are ready to use the numpy functions with the `np` name. I encourage you to check you the [numpy user guide for beginners](https://numpy.org/doc/stable/user/absolute_beginners.html). The website has a lot of examples and a very good and extensive documentation. In this article you are going to learn the very basics of numpy.

### numpy.array()

You can construct arrays that are similar to Python lists with the numpy module. They are called *numpy arrays*. For example, you can construct an array from a list of values:

```
>>> np.array([23, 14, -2, 0, 9])
array([23, 14, -2,  0,  9])
```

You can also create an array filled with zeros:

```
>>> np.zeros(4)
array([0., 0., 0., 0.])
```

### numpy.arange()

This function is used to construct a numpy array with a range of values. This works in a similar way as the `range()` function.

```
>>> np.arange(3)
array([0, 1, 2])
>>> np.arange(2, 10)
array([2, 3, 4, 5, 6, 7, 8, 9])
>>> np.arange(4, 31, 3)
array([ 4,  7, 10, 13, 16, 19, 22, 25, 28])
```

### numpy.linspace()

Another way to define a numpy array is with the `linspace()` function. This function takes a `start` and `end` parameters, and a third parameter which is the number of elements the array will contain. The values will be evenly spaced between each other.

```
>>> np.linspace(1, 15, num=5)
array([ 1. ,  4.5,  8. , 11.5, 15. ])
```

There is a lot you can do with the numpy module. Feel free to go over the documentation if you are interested, and have fun!

## Conclusion

In this article you learned about the very basics of Python modules. You learned how to create a custom model, and how to import a model in your main Python scripts. Finally, you learned about three of the most popular Python modules and its basic functions.

This is the last chapter of the Python basic course. There is an extra chapter which is intended for you to practice what you have learned all the way by making a couple of practice projects. Finally, don't forget to take the exercises on this chapter too!

## Exercises

This set of exercises are intended for you to practice the concepts learned on this chapter about Python modules.

1. Create a new file with the **.py** extension. Give it a name of your choosing, like **deusdev.py**. This is going to be used as a Python module. In this new Python module, create a function that prints a message saying something about the module. For example, the message can be an explanation of what your module can do, like **'This Python module has a set of functions that solves some mathematical equations'**.
2. Make a second function in your module. Make this function compute some mathematical formula with parameters. For example, you could make it compute the [discriminant for a quadratic equation](https://en.wikipedia.org/wiki/Discriminant). That is, given three float parameters `a`, `b` and `c`, the function should return the square root of `b^2-4ac`.
3. Make a new file with a name of **main.py** or something similar. This is going to be the main script where you call the functions from your module. What is the first thing you need to do in order to be able to use the functions in your new module?
4. Call the function you defined in exercise #1. You should be able to see the message printed on the screen.
5. Call the function you made in exercise #2. Use different parameters and test if everything is working as expected.
6. In this exercise you are going to learn how to use the [`random.gauss()` function](https://docs.python.org/3/library/random.html#random.gauss) from the [random](https://docs.python.org/3/library/random.html) module. This function can take two optional parameters: the mean and the standard deviation from a normal distribution. Read the documentation to see more details, and try the function with different values to see the outputs.
7. Go to the [math module](https://docs.python.org/3/library/math.html) page and look for a function to compute the logarithm of a number. Read the docs and use the function with different parameters to see the outputs.
8. In this exercise you will learn about the [datetime module](https://docs.python.org/3/library/datetime.html). Go ahead and import the datetime module in a new Python interpreter or a new Python file. After importing the module, write `dir(datetime)` and hit `Enter`. The [dir function](https://docs.python.org/3/tutorial/modules.html#the-dir-function) will give you a list of names available from that module. For example, try `datetime.datetime.now()`, you should see the current date and time. Try to investigate what other things you can do with this module from the documentation.