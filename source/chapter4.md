# Chapter 4: Data Types

Python can be used for a wide range of tasks involving different types of data. It can be used to make large and complicated computations using numbers, automating text operations, storing data in the form of lists, and many more.

There are a set of different types of data to work with each specific task. For numeric tasks you use numbers (integers, decimals), for text operations you use data in form of strings, and so on. In this article you will learn the basics of how to work with different kinds of data types in Python.

## What you will learn

In this article you will learn the following topics:

* What are the different available Python built-in data types
* How to check the type of a variable or value using the `type()` function
* How data types are casted into other data types

## Numeric Data Types

Numbers are everywhere, and Python is not the exception. There are different kinds of numbers you can work with. Let's enter the Python interpreter in a terminal to understand how each type of number work.

### Integer

Integer numbers are those which don't have decimal part. They can be positive, negative and zero. Let's begin by assigning an integer number to a new variable called `x`.

```python
>>> x = 1
>>> x
1
```

If you don't know what a variable is or how to work with them, check out a [previous tutorial](chapter2). Now the variable `x` has the *value* of 1 assigned to it.

What you can do now is to use a Python function called `type()`. This function takes as argument the variable (or the value), and returns the *data type*. Write `type` followed by the name of the variable inside parentheses, and then hit Enter:

```python
>>> type(x)
<class 'int'>
```

As you can see Python prints `<class 'int'>`, which means the variable is an **int** (short for integer). You will learn about functions in [another tutorial](chapter10) of this course.

### Float

You can repeat the same process with a real number. Let's try the number 3.14. If you assign this value to the variable called `y` and check for its type, this is what you obtain:

```python
>>> y = 3.14
>>> type(y)
<class 'float'>
```

Python tells you that the data type for 3.14 is called **float**. This is a floating point number, which is used to represent real numbers.

### Complex

Python also has implemented the complex data type to represent complex numbers, which have real and imaginary parts. To make a complex number, write it as a sum of the real part and the imaginary part. The imaginary part has to be accompanied by a *j* (the imaginary unit):

```python
>>> z = 1 + 0.5j
>>> type(c)
<class 'complex'>
```

Keep in mind that the imaginary unit in Python is written with a *j* instead of an *i*.

Given a complex number, there are different methods you can use to extract information such as the real part, the imaginary part, the complex conjugate, etc. You will learn about [methods](chapter11) in another tutorial.

## Conversion from one type to another: casting

There are a set of functions that convert one type of variable (number) to another. They are `int()`, `float()` and `complex()`. Functions in Python have to be called using parentheses, and inside them you put the variable or value.

### Integer to float

```python
>>> x = 1
>>> float(x)
1.0
```

The result of calling the function `float()` on the variable `x` (which contains the integer value of 1) is 1.0. Python represents float numbers with a decimal point. So when the value doesn't have any decimal digits it adds a 0.

> In some situations the decimal point is represented with a comma instead of a point. In Python you always have to use the decimal point to represent decimals, because the comma is reserved for other situations like using lists and sets.

### Float to integer

```python
>>> y = 3.14
>>> int(y)
3
```

In this case the result of the function `int()` applied to a float is just the integer part. Keep in mind that this is not the same as rounding the number. Take for example the float 9.99 and apply the function `int()`:

```python
>>> int(9.99)
9
```

The result is still 9, and not 10 as it would have been if you rounded the number 9.99.

### Integer to complex

```python
>>> x = 1
>>> complex(x)
(1+0j)
```

When using the `complex()` function on an integer, the result is a complex number where the real part is the original value, and the imaginary part is 0. Note that Python explicitly prints 0j indicating that you are dealing with a complex number.

### Float to complex

```python
>>> y = 3.14
>>> complex(y)
(3.14+0j)
```

This is similar to the previous example, just in this case the real part is a floating point number instead of an integer.

### Complex to integer

```python
>>> z = 1 + 0.5j
>>> int(z)
Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
TypeError: can't convert complex to int
```

We just got a `TypeError`! Well, this makes sense because there is no way to convert directly from a complex number to an integer. You could however take the real part, or the imaginary part, or even compute the modulus, and then convert that result to an integer. Either way you need to specify what you what to do and tell it to Python.

## Text Data Type

Python represents textual data using the *string* data type. You have already worked with strings in a previous tutorial. Let's check the type of a sample string:

```python
>>> s = 'Hello World!'
>>> type(s)
<class 'str'>
```

The output tells us that the data type is called **str** (short for string). You can also convert strings to numbers. For example:

```python
>>> s = '7'
>>> int(s)
7
>>> float(s)
7.0
>>> complex(s)
(7+0j)
```

Of course you can't convert a string that is not a number to a number type like an integer:

```python
>>> s = 'Not a number'
>>> int(s)
Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: 'Not a number'
```

Python throws an error (a `ValueError` in this case) claiming that the string is invalid to use with the `int()` function.

You can also convert  a numeric value to a string by using the `str()` function:

```python
>>> str(3)
'3'
>>> str(3.14)
'3.14'
>>> str(3+4j)
'(3+4j)'
```

## Sequence Data Types

Another kind of data type that is very used in Python programs are *sequence* data types. This data types are used to hold sequence of values like numbers, strings and even combinations of both. You will learn about sequence data types with more detail in another tutorial.

### List

The first sequence data type you will deal with is **list**. Let's make an example with a list of integer values. To define a list, enclose the elements inside square brackets `[]`, and separate each value with a comma `,`.

```python
>>> my_list_numbers = [1, 2, 3]
>>> type(my_list_numbers)
<class 'list'>
```

In this example I have added a space between the comma and the next value. This is not necessary but it can improve readability. When calling the `type()` function on the list just defined, Python tells it is of a **list** data type.

### Tuple

Another sequence data type is **tuple**. Tuples are similar to lists, with the difference that tuples are *immutable*, while lists are *mutable*. You will deal with this concepts in more detail in another tutorial. For now, let's define a tuple in a similar way as the list, but in this case we use parentheses `()` instead of square brackets:

```python
>>> my_tuple_strings = ('John', 'Carol', 'Eva', 'Charles')
>>> type(my_tuple_strings)
<class 'tuple'>
```

### Range

Another widely used sequence type is **range**. `range()` is a function that can take one or more integer parameters. The details of the range function are left for another tutorial. For now let's just define it with one integer parameter and check its type:

```python
>>> my_range_var = range(6)
>>> type(my_range_var)
<class 'range'>
```

Python tells us that the data type is *range* as expected.

## Mapping Data Type: dictionary

The **dictionary** data type is widely used in Python. For example, it is used in applications that work with APIs (Application Programming Interfaces), and it resembles the JSON format. An example of such an application is a Weather App.

To create a dictionary, enclose the data inside curly brackets `{ }` (braces). Inside the curly brackets you have to set **key: value** pairs separated by commas. Use a colon `:` to separate the key and the value. For example, you can define the keys to be the name of a person and the country he lives in, while the values for each key can be anything which makes sense:

```python
>>> my_dictionary = {"name": "Charles", "country": "Argentina"}
>>> type(my_dictionary)
<class 'dict'>
```

By calling `type` on the dictionary variable Python tells it is of class **dict** (short for dictionary).

The keys in a dictionary have to be unique. If you try to assign different values with the same key, Python will only keep the last one:

```python
>>> my_dictionary = {"name": "Charles", "name": "Einstein"}
>>> my_dictionary
{'name': 'Einstein'}
```

> **Error but no error**. As you may have noticed, Python didn't throw an error in the last example. When working with Python programs you will make a lot of errors (and that is completely fine). Sometimes Python will help you correct those errors by throwing error messages. But there are some special situations like in the last example, where Python doesn't have a problem with what you are doing. This is one of the hardest aspects of programming: how do you know you are making a mistake if nobody tells you?

You can, however, have repeated values for different keys:

```python
>>> my_dictionary = {"name": "Charles", "teacher": "Charles"}
>>> my_dictionary
{'name': 'Charles', 'teacher': 'Charles'}
```

## Set Data Types

### Set

Sets are similar to lists. The items are stored inside curly brackets and separated with commas.

```python
>>> my_set = {'John', 'Carol', 'Eva', 'Charles'}
>>> type(my_set)
<class 'set'>
```

The items in a set have to be unique as opposed to a list, where the items can be repeated. If you try to repeat the same item in a set, Python will not keep more than one of it:

```python
>>> s = {'a','b','c','b','c','d'}
>>> s
{'c', 'b', 'd', 'a'}
```

The set data type is very useful when you need to retrieve the *distinct values* that are present, for example, in a list.

### Frozen set

**Frozen Sets** are similar to sets, only in this case the items are unchangeable.

```python
>>> my_frozen_set = frozenset({'John', 'Carol', 'Eva', 'Charles'})
>>> type(my_frozen_set)
<class 'frozenset'>
```

You will be dealing with modifying sets, lists and others in later tutorials.

## Boolean Data Types

Sometimes you need to check whether an expression is valid or not. For example you would check an equality between two variables, like two names belonging to the same dictionary. If there are two values with the same name, you would return `True`. In case they are different, return `False`.

The data type that deals with this kind of values is referred to as **boolean** data type. Boolean values can have two possible values: `True` or `False`. Is important to remember the capital T for True, and the capital F for False.

```python
>>> a = True
>>> type(a)
<class 'bool'>
>>> b = False
>>> type(b)
<class 'bool'>
```

You will learn how to properly work with boolean variables in another tutorial.

## Binary Data Types

There is a set of data types that deal with [bytes](https://en.wikipedia.org/wiki/Byte). Let's leave the details about this data types for another tutorial. Here are the three data types for reference.

### Bytes

```python
>>> my_bytes_var = b"DeusDev"
>>> type(my_bytes_var)
<class 'bytes'>
```

### Bytearray

```python
>>> my_byte_array = bytearray(123)
>>> type(my_byte_array)
<class 'bytearray'>
```

### Memoryview

```python
>>> my_memory_view = memoryview(bytes(123))
>>> type(my_memory_view)
<class 'memoryview'>
```

## None Data Type

The last data type listed in this tutorial is the **NoneType** data type. The value of this data type is called `None` (capital N). This is used to assign a null value to a variable.

You may be wondering why would you even need this kind of data at all. You will see how this works and why is useful in later tutorials. For now let's see just one example:

```python
>>> my_none_var = None
>>> type(my_none_var)
<class 'NoneType'>
```

## Conclusion

In this article you have gone through the basics of several data types supported by Python. Some of them are used a lot and others not so much, but is good to have a basic understanding of each data type and what they mean before moving on.

The next step is to learn different functions and methods each data type has to offer. For example, you may need to round a float number to two decimals, capitalize a string, add values to a list, retrieve some information from a dictionary, etc.

## Exercises

Here is a list of exercises intended for you to practice some of the topics covered in this article. You have learned about each Python data type using the terminal. I recommend you try this exercises in a new Python file and run the script with the terminal. If you don't know how to do this, refer to the article about how to use [text editors and IDEs](chapter3).

1. Create a new variable called `my_int` and assign any integer value to it. You can try a positive integer, a negative integer and even the number 0. Check that the variable is actually an integer by printing its type.

2. Create a variable and assign a float number to it. Call the variable however you like. Keep in mind that variable names usually have meaningful names according to its value. Check its type.

3. Create a complex variable and check its type. Remember that complex numbers have real and imaginary parts, each of which can be either integer or float. Try creating a complex variable with no imaginary part, but the type being complex anyway.

4. Convert the float variable to an integer, and assign the new value to a new variable. Check the type of the new variable (it should be int).

5. Create a variable called `my_greeting` and assign a string like 'Hello World' to it. Print its contents and type. You can try enclosing your string with single quotes, double quotes, triple quotes. You can even try triple double quotes around it.

6. Create a list. Remember that lists are enclosed with square brackets, and each item is separated with a comma. Try using numbers, strings, and even combinations of both, meaning you can use integers, floats and strings in the same list. Check its type.

7. Create a dictionary. Let your imagination fly! I recommend you try different options for the keys and values (integers, strings, complex, even lists). The more you try, the more you will likely to get errors. Don't worry, you will learn by force! If you want a suggestion, try to make a dictionary such that it generates this error: *TypeError: unhashable type: 'list'*

8. Back to exercise #1, you created a variable called `my_int` and assigned a value to it. If you lost that variable for some reason, recreate it. Now create another variable called `my_boolean` and assign the following to it: `bool(my_int)`. Print the contents of `my_boolean`, and check its type. As you can see you can cast different values to boolean variables. You will see more on this in another tutorial.