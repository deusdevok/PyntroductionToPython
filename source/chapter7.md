# Chapter 7: Working with dictionaries

The dictionary data type is very useful when dealing with data that comes in key-value pairs. Dictionaries are collections of data, in which the **keys** are unique identifiers related to each associated **value**. Dictionary keys are somewhat analogous to the index in a list, as you will see later in this tutorial'

Let's work with a simple example throughout this article, where a list of countries are associated with their respective capitals.

| Country | Capital |
| --- | --- |
| India | New Delhi |
| Argentina | Buenos Aires |
| Spain | Madrid |
| France | Paris |
| Kenya | Nairobi |

The countries are the **keys**, while their capitals are the **values**. Each value is associated with a *unique* key. While in this example both the countries and their capitals are unique, Python dictionaries can have repeated (non-unique) values, but the keys must be unique (you will see what happens if you try to insert a repeated key in a dictionary).

## Python dictionaries: the basics

To define a Python dictionary use curly braces: `{}`. Inside the curly braces include key-value pairs separated by a colon `:`. For the example of this article, the key (country) and the value (capital) are both strings:

```
>>> countries = {'India': 'New Delhi'}
>>> type(countries)
<class 'dict'>
>>> countries
{'India': 'New Delhi'}
```

As you can see, checking the type of the newly created dictionary says that is of the **dict** type. Let's define the dictionary variable `countries` with all the information. To add new key-value pairs, separate them with a comma:

```
>>> countries = {'India': 'New Delhi', 'Argentina': 'Buenos Aires', 'Spain': 'Madrid', 'France': 'Paris', 'Kenya': 'Nairobi'}
>>> countries
{'India': 'New Delhi', 'Argentina': 'Buenos Aires', 'Spain': 'Madrid', 'France': 'Paris', 'Kenya': 'Nairobi'}
```

After printing the `countries` variable on the screen, you can see all the information from the example table, and each country is associated with its corresponding capital.

Another way to create a dictionary is to begin with an empty dictionary, and add new key-value pairs one by one. To create an empty dictionary use a set of empty curly braces, `{}`. To add new items to the dictionary, write the name of the variable where the empty dictionary is stored, followed by square brackets. Inside the square brackets write the `key`, in this case the country in string format. Finally assign the corresponding `value`, which is the capital.

```
>>> countries = {}
>>> countries['India'] = 'New Delhi'
>>> countries['Argentina'] = 'Buenos Aires'
>>> countries['Spain'] = 'Madrid'
>>> countries['France'] = 'Paris'
>>> countries['Kenya'] = 'Nairobi'
>>> countries
{'India': 'New Delhi', 'Argentina': 'Buenos Aires', 'Spain': 'Madrid', 'France': 'Paris', 'Kenya': 'Nairobi'}
```

By doing the assignment for each country and its capital this way, you will end up with the same dictionary you had before. This way of creating dictionaries can be helpful when dealing with cases where the dictionary must be created in a programatic way instead of manually.

### What is the length of a dictionary?

The length of a dictionary is the number of the key-value pairs it contains.

For the example of this article, you should expect it to have a length of 5, which is the number of entries, or rows on the table. It is true that if you count both the countries (keys) and the capitals (values), you will end up with a total of 10, but the length of a dictionary is computed as the number of key-value *pairs*.

```
>>> countries = {'India': 'New Delhi', 'Argentina': 'Buenos Aires', 'Spain': 'Madrid', 'France': 'Paris', 'Kenya': 'Nairobi'}
>>> len(countries)
5
```

In a particular case that the dictionary is empty, its length is 0:

```
>>> empty_dict = {}
>>> len(empty_dict)
0
```

## Reading items from a dictionary

Now that you have learned how to define a dictionary with a bunch of key-value pairs, let's see how you can retrieve information from it. Imagine a scenario where you have a dictionary with all the countries and their capitals, and you want to check the capital of some specific country.

Having defined this simple example with 5 countries, let's check what is the capital of Spain. To do this, you need to find the *key* with the string value `Spain`, and obtain the associated *value*, which is the one after the colon. Write the name of the variable containing the dictionary, followed by square brackets. Inside the square brackets put the value of the key you are looking for:

```
>>> countries['Spain']
'Madrid'
```

Cool! Retrieving values from keys in a dictionary is analogous as getting a value from a list given its index. Let's see what would happen if you try to access an item with a non existent key:

```
>>> countries['China']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'China'
```

Python throws a `KeyError` claiming that the key China doesn't exist.

## Editing key-value pairs

Dictionaries key-value pairs can be edited. Let's see how you can do this.

### Adding new key-value pairs

You can add new key-value pairs to an already created dictionary. To do this, assign a new value (capital) to `countries[key]`, where the key is the new country. This is the same as adding new items to an empty dictionary.

```
>>> countries['Canada'] = 'Ottawa'
>>> countries
{'India': 'New Delhi', 'Argentina': 'Buenos Aires', 'Spain': 'Madrid', 'France': 'Paris', 'Kenya': 'Nairobi', 'Canada': 'Ottawa'}
```

In this example you added the country Canada as a key, and assigned the value Ottawa, both strings. The updated `countries` variable is shown with the old values along with the new one at the end.

### Updating key-value pairs

Remember that keys have to be unique. What would happen if you try to assign a new value to an already existing key? For example, let's assign the number 39 to Spain.

```
>>> countries
{'India': 'New Delhi', 'Argentina': 'Buenos Aires', 'Spain': 'Madrid', 'France': 'Paris', 'Kenya': 'Nairobi', 'Canada': 'Ottawa'}
>>> countries['Spain'] = 39
>>> countries
{'India': 'New Delhi', 'Argentina': 'Buenos Aires', 'Spain': 39, 'France': 'Paris', 'Kenya': 'Nairobi', 'Canada': 'Ottawa'}
```

What you are doing in this case is simply re-assigning a new value to an already existing key. This is analogous to updating a list item given its index.

### Removing elements from a dictionary

You can also remove elements from your dictionary. For this you use the `del` keyword. For example, let's delete the Spain element:

```
>>> del countries['Spain']
>>> countries
{'India': 'New Delhi', 'Argentina': 'Buenos Aires', 'France': 'Paris', 'Kenya': 'Nairobi', 'Canada': 'Ottawa'}
```

As you can see, the key Spain has been deleted, along with its corresponding value. When you delete elements from a dictionary by its key, what is deleted is the key-value pair. What happens if you try to delete an element that is not present in the dictionary? Let's try to delete the element with the Spain key again:

```
>>> del countries['Spain']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'Spain'
```

As expected, a `KeyError` is raised, since there isn't an element with the key Spain anymore.

## Dictionary key/value data types

In this article you have worked with a dictionary where the keys and values are all of the string data type. Python dictionaries can have other data types, such as integers, floats, lists, and even other dictionaries. Let's try some of those with a newly created dictionary.

```
>>> d = {}
>>> d[12] = 99.3
>>> d['pi'] = 3.14
>>> d['list'] = [1, 2, 3]
>>> d['dict'] = {'name': 'John', 'age': 19}
>>> d
{12: 99.3, 'pi': 3.14, 'list': [1, 2, 3], 'dict': {'name': 'John', 'age': 19}}
```

In this example, an empty dictionary `d` has been created. Next, a first item is added, with an integer key and a float as its value. Then a string as a key, and a float as the value. The third has a string as key and a list as its value. Finally, the last element has a string key and another dictionary as the value. By printing the dictionary `d` you can see everything works as expected.

So far so good. Let's try a list as a key:

```
>>> d[[4, 5, 6]] = 'key is list'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
```

Ups! Not good. Python doesn't like lists as dictionary keys. What about another dictionary as a key?

```
>>> d[{1: 'one', 2: 'two'}] = 'key is dict'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'dict'
```

Oh man! What about a tuple?

```
>>> d[(1, 2, 3)] = 'key is tuple'
>>> d
{12: 99.3, 'pi': 3.14, 'list': [1, 2, 3], 'dict': {'name': 'John', 'age': 19}, (1, 2, 3): 'key is tuple'}
>>> d[(1, 2, 3)]
'key is tuple'
```

Tuple works as a key for a dictionary. But not lists nor dictionaries. The rule is that the *dictionary key must be of an immutable type*, such as integers, strings and even tuples, but not list nor dictionaries. Remember that lists and dictionaries are *mutable* data types, meaning their items can be changed.

## Converting dictionaries to lists

Let's go back to the initial example, the one with the countries and their capitals. What would happen if you tried to convert that dictionary with key-value pairs (country-capital) to a list using the `list()` function? Let's see:

```
>>> countries = {'India': 'New Delhi', 'Argentina': 'Buenos Aires', 'Spain': 'Madrid', 'France': 'Paris', 'Kenya': 'Nairobi'}
>>> list(countries)
['India', 'Argentina', 'Spain', 'France', 'Kenya']
```

Interesting! The `list()` function applied to the dictionary returned a list with only the keys, sorted in the same order they were inserted in the first place. But the values seem to have been lost in the process.

You have seen the `list()` function here and in previous tutorials too. You may be wondering if there is a `dict()` function that converts lists to dictionaries. In fact there is. To use the `dict()` function you need to define the key-value pairs as the elements of a list, where each one of them is a tuple containing one key-value pair separated by a comma:

```
>>> numbers_dict = dict([('one', 1), ('two', 2), ('three', 3)])
>>> numbers_dict
{'one': 1, 'two': 2, 'three': 3}
```

There are other ways to use the `dict()` function, but let's leave those for another time.

## Conclusion

In this article you learned the basics of Python dictionaries. What they are, how to create a dictionary, how to edit its elements, delete, add, and more.

Things are getting more complicated as you advance through the course, so remember to practice what you have learned by doing the proposed exercises. Have fun!

## Exercises

After you read the article on dictionaries, you should practice what you have learned with the following exercises. Good luck!

1. In your own words, what is a Python dictionary and how is it different from a Python list?
2. In this article I used a very simple example where the Countries are related to their Capitals. Another common example is to make a dictionary where personal information of a student is stored, such as its name, age, scores, etc. Think of an example where you could make use of a Python dictionary and construct it. Save it in a new variable.
3. Check the type of the newly created dictionary and verify that is of the class **dict**.
4. Use the square bracket notation to retrieve some of the values given the corresponding keys. Use this method to verify that every key-value pair is defined as is supposed to.
5. What is the length of your dictionary? Try to answer the question before using the built-in Python function that gives you the answer automatically.
6. Going back to exercise #2, you may or may not have defined one of the values as a list or a dictionary. If you haven't, add a new item to your dictionary where the value is either a list or another dictionary.
7. Use the square bracket notation to access the list or dictionary you have stored as one of the values. You should have done this either in exercise #2 or #6.
8. Use the square bracket notation to access one of the list or dictionary values you have defined inside the original dictionary. For this you will have to make use of two sets of square brackets, similar to how you access list elements inside another list.
9. Convert your dictionary to a list, and save the contents to a new variable. What is the length of this list? Where are the elements of this list coming from?