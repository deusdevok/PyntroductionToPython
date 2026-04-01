# Chapter 11: Built-in Methods

In the previous part of the Python basic course we have gone through Python functions. There are functions that are bound to certain objects like a string or a list. Those functions let you perform certain actions and in some cases the object changes. These functions are called **methods**.

For example you may want to check if the letters of a **string** are all upper case. With **lists** you can add new items at specified positions. For **dictionaries** you can retrieve all `key:value` pairs or update values. And many more.

In this article you are going to study different **methods** you can use with different Python data types. The methods are said to be **built-in** because they come with Python itself.

## Python methods

Python is an object oriented programming language, which means that Python works with [objects](https://en.wikipedia.org/wiki/Object_(computer_science)). Objects have **values** and **methods**. You already know what a value is (a specific number, a string, a list, etc).

The topic of object oriented programming is outside the scope of this course, but I mention it so you have a very basic idea of what is behind Python methods. An object, besides having a value, has special functions assigned to it.

## String methods

### **upper**

Say you are working with the string `'Hello World!'` and you want to convert it to uppercase like `'HELLO WORLD!'`. While you can do it manually, you can automate this process with a single function like this:

```
>>> s = 'Hello World!'
>>> s.upper()
'HELLO WORLD!'
```

First you define your variable `s`, which in this case it is of string type. To apply the method you write the name of the variable, followed by a single period `.`, and finally the name of the method, in this case `upper()`.

All methods end with parentheses `()`, since they are actually functions (you learned about Python functions in the [previous chapter](chapter10) of this course). Methods can also take parameters as you will see later in this article.

You could ask yourself if the string which is assigned to the variable `s` of the example has changed. What happens if you print the value of `s` after applying the `upper()` method?

```
>>> s = 'Hello World!'
>>> s.upper()
'HELLO WORLD!'
>>> s
'Hello World!'
```

As you can see the value remains unchanged. If you need to store the value for later use, you need to use a variable:

```
>>> s_changed = s.upper()
>>> s_changed
'HELLO WORLD!'
```

You can also use methods on string values without the need to store them in variables in the first place:

```
>>> 'Hello World!'.upper()
'HELLO WORLD!'
```

All methods applied to strings **return** new values without affecting the original string, being on a variable or not. This is not always the case for other data types like lists. You will deal with methods for other data types shortly.

What happens if you try to use a method that doesn't exist? Python will throw an `AttributeError`:

```
>>> s.money()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'str' object has no attribute 'money'
```

### **lower**

There is also a method to convert a string to lowercase letters. The method is named `lower()`, and the way to use it is identical to any other method like the `upper()` you just learned.

```
>>> s = 'Hello World!'
>>> s.lower()
'hello world!'
```

### **count**

You can count how many times a specific character or substring appears in a string with the `count()` method:

```
>>> 'Hello World!'.count('o')
2
>>> 'Lord Lord Lost'.count('Lo')
3
```

### **find**

With the `find()` method you can search for a specific substring. The method will return the index position where the substring has been found, and -1 in case it is not found.

```
>>> 'Hello World!'.find('W')
6
>>> 'Hello World!'.find('ello')
1
>>> 'Hello World!'.find('John')
-1
```

### **index**

There is a very similar method to find a substring which is the `index()` method. This method works exactly the same as the `find()` method, but it raises a `ValueError` in case the substring is not found, instead of returning -1.

```
>>> 'Hello World!'.index('W')
6
>>> 'Hello World!'.index('ello')
1
>>> 'Hello World!'.index('John')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: substring not found
```

### **replace**

Substrings can be replaced using the `replace()` method. This method takes two required parameters: a substring present in the string, and a new string which will replace the former.

```
>>> 'Hello World!'.replace('World', 'John')
'Hello John!'
```

A third optional parameter can be set to determine how many occurrences of the string will be replaced, in case there are more than one. The default is to replace all occurrences.

```
>>> 'Hello World World World!'.replace('World', 'John', 2)
'Hello John John World!'
```

### **center**

You can return a centered string with an optional specified character to be filled with the `center()` method. The default character is a space. The required parameter is an integer number, which is the length of the resulting string.

```
>>> 'Hello'.center(20)
'       Hello        '
>>> 'Hello'.center(20, '-')
'-------Hello--------'
```

### **format**

The `format()` method is very useful when you need to print a message containing variables. There are various ways to make a format string. In this article you are going to learn some of the basic ones.

For example, use curly braces `{}` to place a variable name in your string. At the end of the string add a period and the `format` keyword to apply the method. The `format` method can take the variable names as its parameters in the format of key value pairs: `key=value`.

```
>>> s = "I'm {name} and I am {age} years old.".format(name='John', age=27)
>>> s
"I'm John and I am 27 years old."
```

Another way to format the same string is to only use the value as the parameter, and leaving the curly braces empty. Python will automatically fill each placeholder with each value in order.

```
>>> s = "I'm {} and I am {} years old.".format('John', 27)
>>> s
"I'm John and I am 27 years old."
```

You can use integer values to indicate the order of the parameters. The default order starts at 0:

```
>>> s = "I'm {0} and I am {1} years old.".format('John', 27)
>>> s
"I'm John and I am 27 years old."
```

If you need to use a different order, change the values inside the curly braces:

```
>>> s = "I'm {1} and I am {0} years old.".format(27, 'John')
>>> s
"I'm John and I am 27 years old."
```

## List methods

Let's work with an example list and see what you can do to it. Suppose you are working with a list of daily tasks:

```
todo = ['make coffee', 'take out trash', 'call Sean', 'pay bills']
```

### **append**

Let's add a new task to the **todo** list. The `append` method adds a new item to a list at the end of it.

```
>>> todo.append('buy milk')
>>> todo
['make coffee', 'take out trash', 'call Sean', 'pay bills', 'buy milk']
```

As you can see, the original list is changed (in this case with a new item at the end).

### **insert**

To include a new item in the list but at a specified position, use the `insert` method. The first parameter is the index you want to insert the new element, and the second is the element itself:

```
>>> todo.insert(2, 'go to the gym')
>>> todo
['make coffee', 'take out trash', 'go to the gym', 'call Sean', 'pay bills', 'buy milk']
```

### **pop**

To delete elements from the list, use the `pop` method. This method takes a single optional parameter indicating the index position of the element to be removed. If the index is not given, the default is -1, which is the last element of the list.

```
>>> todo.pop()
'buy milk'
>>> todo
['make coffee', 'take out trash', 'go to the gym', 'call Sean', 'pay bills']
>>> todo.pop(1)
'take out trash'
>>> todo
['make coffee', 'go to the gym', 'call Sean', 'pay bills']
```

Have you noticed that after using the `pop` method the removed element is printed to the screen? That is because this method *returns* the removed element. You could save it to a variable for later use:

```
>>> removed_element = todo.pop()
>>> todo
['make coffee', 'go to the gym', 'call Sean']
>>> removed_element
'pay bills'
```

### **remove**

What if you want to remove an element given its value? The `remove` method removes the first element found with a given value.

```
>>> todo.remove('go to the gym')
>>> todo
['make coffee', 'call Sean']
```

### **sort**

A very common task in programming is sorting data in a specified way. Let's apply the `sort` method to the original list and see the output.

```
>>> todo = ['make coffee', 'take out trash', 'call Sean', 'pay bills']
>>> todo.sort()
>>> todo
['call Sean', 'make coffee', 'pay bills', 'take out trash']
```

The `sort` method sorted the list of strings in ascending alphabetic order. You can also sort the list in descending order by giving the method the optional argument `reverse=True`.

```
>>> todo.sort(reverse=True)
>>> todo
['take out trash', 'pay bills', 'make coffee', 'call Sean']
```

## Dictionary methods

Let's work with a dictionary and see what you can do with it. Say you have a dictionary where the keys are the countries and the values are the respective capitals:

```
>>> countries = {'India': 'New Delhi', 'Argentina': 'Buenos Aires', 'Spain': 'Madrid'}
```

### keys

With the `keys` method you can retrieve all the keys present in the dictionary.

```
>>> countries.keys()
dict_keys(['India', 'Argentina', 'Spain'])
```

### values

You can also get the list of all the values in the dictionary with the values method.

```
>>> countries.values()
dict_values(['New Delhi', 'Buenos Aires', 'Madrid'])
```

### items

The `items` method returns a list of all the key-value pairs of the dictionary. Each key-value pair is in a tuple.

```
>>> countries.items()
dict_items([('India', 'New Delhi'), ('Argentina', 'Buenos Aires'), ('Spain', 'Madrid')])
```

### update

You can include new key-value pairs with the `update` method. The `update` method takes a parameter which is in the form of a new dictionary with a key-value pair to be added to the main dictionary. You can include more than one key-value pair at a time.

```
>>> countries.update({'France': 'Paris'})
>>> countries
{'India': 'New Delhi', 'Argentina': 'Buenos Aires', 'Spain': 'Madrid', 'France': 'Paris'}
```

### pop

To remove a key-value pair from the dictionary, you can use the `pop` method with a key as its parameter.

```
>>> countries.pop('Spain')
'Madrid'
>>> countries
{'India': 'New Delhi', 'Argentina': 'Buenos Aires', 'France': 'Paris'}
```

## Conclusion

In this article you learned some of the most common built-in methods Python has to offer. There are a lot more methods that weren't covered in this article. I invite you to investigate on them and learn what they do.

## Exercises

With this exercises you will practice more on built-in methods. Some of them were not covered in the article, but you can learn to use them anyway.

1. Take the string `'Python is beautiful!'`. Return a new string with all the letters uppercase.
2. Make the string `'Python is beautiful!'` look like a title. That is, make the first character of each work uppercase. You can use the `title()` method for this exercise.
3. Check if the string `'Python is the best'` starts with `'Py'`. You can use the `startswith()` method for this.
4. Given the list `[1, 2, 2, 2, 3, 4, 5, 2, 2, 1, 5, 9]`, count how many times the number 2 appears. You can use the `count()` method.
5. Use the same list of exercise #4, and remove all elements from it. You can use the `clear()` method.
6. Take the dictionary `d = {'name': 'Karen', 'age': 22}` and get the value of each key. For this exercise, use the method `get()`, which takes the key as its parameter.
7. Make a list with all the integer numbers from 1 to 100: `[1, 2, 3, ..., 99, 100]`. Use a `for` loop and the *append* list method. You should initialize your list with an empty list first: `[]`.