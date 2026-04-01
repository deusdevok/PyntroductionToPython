# Chapter 2: Using the terminal and Python interpreter

Python can be used directly from the terminal, without the need of using [text editors](chapter3) like Notepad, Sublime or VsCode. Using the terminal is a good practice when making the first steps to learn Python. In this article you are going to learn how to run basic Python commands using the terminal (PowerShell).

In the [previous article](chapter1) you went through the installation and setup of Python. You already used PowerShell to check the Python version by using `python --version`. Check it out if you missed it.

## First steps: The Python interpreter

Let's start using PowerShell right now. Go ahead and open a new terminal (PowerShell). The first thing you will see on the screen is something like the following:

```
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6

PS C:\Users\yourusername>
```

As you can see, you have an initial message with Copyright and some extra information. If you are in using an operating system different than Windows, you may see your terminal in some other format.

The last line is the place where you can enter different commands. **yourusername** will be your computer user name. At the end of that line you should see a blinking underscore, meaning it is ready to take a written input from the user. For example, you could write `pwd` to print the current working directory:

```
PS C:\Users\yourusername> pwd

Path
----
C:\Users\yourusername
```

When you write `pwd` and hit Enter, the terminal shows the current working directory on the screen. There are a lot of useful commands you can try besides `pwd`. But let's work with the one we are interested in: `python`. Go ahead and write `python` and hit Enter:

```
PS C:\Users\yourusername> python
Python 3.11.2 (tags/v3.11.2:878ead1, Feb  7 2023, 16:38:35) [MSC v.1934 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

The first thing you see after the command you just entered is the Python version and some extra information (never mind that now). The next thing you see is a couple of suggestions to try next. They are help, copyright, credits and license.

Lastly you may have noticed that there are three greater-than symbols `>>>` before the blinking underscore. This is how the Python interpreter looks like. This means that you are ready to enter Python commands. This is called [interactive mode](https://docs.python.org/3/tutorial/interpreter.html#interactive-mode).

## Getting help in the Python interpreter

Go ahead and try `help`, one of the suggested commands. Write the command and hit Enter.

```
>>> help
Type help() for interactive help, or help(object) for help about object.
```

Seems like you need to include a set of parentheses after `help` according to the message you just got. Let's do that now.

```
>>> help()

Welcome to Python 3.11's help utility!

If this is your first time using Python, you should definitely check out
the tutorial on the internet at https://docs.python.org/3.11/tutorial/.

Enter the name of any module, keyword, or topic to get help on writing
Python programs and using Python modules.  To quit this help utility and
return to the interpreter, just type "quit".

To get a list of available modules, keywords, symbols, or topics, type
"modules", "keywords", "symbols", or "topics".  Each module also comes
with a one-line summary of what it does; to list the modules whose name
or summary contain a given string such as "spam", type "modules spam".

help>
```

Writing `help()` (with parentheses at the end) on the Python prompt and hitting Enter shows something very interesting! First of all it is giving you a warm welcome to the Python help utility. Right below it suggests to check out the official tutorial for the current version.

> **Read everything**. Now is the time for me to suggest you a couple of things you should do that I did not when learning Python. Read everything in detail even if you don't understand it. For example if you keep reading the message given by the Python interpreter, you will find terms like *module*, *keyword* and *string*. You should not have to know their meaning yet, but is good to have those words ringing in your head. You will learn those in given time.

Lastly, notice that the prompt changed again. Now it says help> where you can write your search. Let's try writing "modules" as suggested, just to see what happens.

```
help> modules

Please wait a moment while I gather a list of all available modules...

test_sqlite3: testing with version '2.6.0', sqlite_version '3.39.4'
C:\Users\yourusername\AppData\Local\Programs\Python\Python311\Lib\site-packages\_distutils_hack\__init__.py:33: UserWarning: Setuptools is replacing distutils.
  warnings.warn("Setuptools is replacing distutils.")
__future__          _testmultiphase     genericpath         runpy
__hello__           _thread             getopt              sched
__phello__          _threading_local    getpass             secrets
_abc                _tkinter            gettext             select
_aix_support        _tokenize           glob                selectors
_ast                _tracemalloc        graphlib            setuptools
_asyncio            _typing             gzip                shelve
_bisect             _uuid               hashlib             shlex
_blake2             _warnings           heapq               shutil
_bootsubprocess     _weakref            hmac                signal
_bz2                _weakrefset         html                site
_codecs             _winapi             http                smtpd
_codecs_cn          _xxsubinterpreters  idlelib             smtplib
_codecs_hk          _zoneinfo           imaplib             sndhdr
_codecs_iso2022     abc                 imghdr              socket
_codecs_jp          aifc                imp                 socketserver
_codecs_kr          antigravity         importlib           sqlite3
_codecs_tw          argparse            inspect             sre_compile
_collections        array               io                  sre_constants
_collections_abc    ast                 ipaddress           sre_parse
_compat_pickle      asynchat            itertools           ssl
_compression        asyncio             json                stat
_contextvars        asyncore            keyword             statistics
_csv                atexit              lib2to3             string
_ctypes             audioop             linecache           stringprep
_ctypes_test        base64              locale              struct
_datetime           bdb                 logging             subprocess
_decimal            binascii            lzma                sunau
_distutils_hack     bisect              mailbox             symtable
_elementtree        builtins            mailcap             sys
_functools          bz2                 marshal             sysconfig
_hashlib            cProfile            math                tabnanny
_heapq              calendar            mimetypes           tarfile
_imp                cgi                 mmap                telnetlib
_io                 cgitb               modulefinder        tempfile
_json               chunk               msilib              test
_locale             cmath               msvcrt              textwrap
_lsprof             cmd                 multiprocessing     this
_lzma               code                netrc               threading
_markupbase         codecs              nntplib             time
_md5                codeop              nt                  timeit
_msi                collections         ntpath              tkinter
_multibytecodec     colorsys            nturl2path          token
_multiprocessing    compileall          numbers             tokenize
_opcode             concurrent          opcode              tomllib
_operator           configparser        operator            trace
_osx_support        contextlib          optparse            traceback
_overlapped         contextvars         os                  tracemalloc
_pickle             copy                pathlib             tty
_py_abc             copyreg             pdb                 turtle
_pydecimal          crypt               pickle              turtledemo
_pyio               csv                 pickletools         types
_queue              ctypes              pip                 typing
_random             curses              pipes               unicodedata
_sha1               dataclasses         pkg_resources       unittest
_sha256             datetime            pkgutil             urllib
_sha3               dbm                 platform            uu
_sha512             decimal             plistlib            uuid
_signal             difflib             poplib              venv
_sitebuiltins       dis                 posixpath           warnings
_socket             distutils           pprint              wave
_sqlite3            doctest             profile             weakref
_sre                email               pstats              webbrowser
_ssl                encodings           pty                 winreg
_stat               ensurepip           py_compile          winsound
_statistics         enum                pyclbr              wsgiref
_string             errno               pydoc               xdrlib
_strptime           faulthandler        pydoc_data          xml
_struct             filecmp             pyexpat             xmlrpc
_symtable           fileinput           queue               xxsubtype
_testbuffer         fnmatch             quopri              zipapp
_testcapi           fractions           random              zipfile
_testconsole        ftplib              re                  zipimport
_testimportmultiple functools           reprlib             zlib
_testinternalcapi   gc                  rlcompleter         zoneinfo

Enter any module name to get more help.  Or, type "modules spam" to search
for modules whose name or summary contain the string "spam".
```

Looks overwhelming! So, it is listing all of the available modules you have (you will see what [Python modules](chapter12) are later in this course). You may have a different list with fewer modules. Let's try "keywords" to see what you get.

```
help> keywords

Here is a list of the Python keywords.  Enter any keyword to get more help.

False               class               from                or
None                continue            global              pass
True                def                 if                  raise
and                 del                 import              return
as                  elif                in                  try
assert              else                is                  while
async               except              lambda              with
await               finally             nonlocal            yield  
```

A shorter list now. Let's try entering a keyword from this list to see what help you get.

```
help> for
The "for" statement
*******************

The "for" statement is used to iterate over the elements of a sequence
(such as a string, tuple or list) or other iterable object:

    for_stmt ::= "for" target_list "in" expression_list ":" suite
                ["else" ":" suite]

The expression list is evaluated once; it should yield an iterable
object.  An iterator is created for the result of the
"expression_list".  The suite is then executed once for each item
provided by the iterator, in the order returned by the iterator.  Each
item in turn is assigned to the target list using the standard rules
for assignments (see Assignment statements), and then the suite is
executed.  When the items are exhausted (which is immediately when the
sequence is empty or an iterator raises a "StopIteration" exception),
the suite in the "else" clause, if present, is executed, and the loop
terminates.

A "break" statement executed in the first suite terminates the loop
without executing the "else" clause\u2019s suite.  A "continue" statement
executed in the first suite skips the rest of the suite and continues
with the next item, or with the "else" clause if there is no next
item.

The for-loop makes assignments to the variables in the target list.
This overwrites all previous assignments to those variables including
those made in the suite of the for-loop:

    for i in range(10):
        print(i)
        i = 5             # this will not affect the for-loop
                            # because i will be overwritten with the next
                            # index in the range

Names in the target list are not deleted when the loop is finished,
but if the sequence is empty, they will not have been assigned to at
all by the loop.  Hint: the built-in function "range()" returns an
iterator of integers suitable to emulate the effect of Pascal\u2019s "for i
:= a to b do"; e.g., "list(range(3))" returns the list "[0, 1, 2]".

Related help topics: break, continue, while
```

Very nice! We get a lot of helpful information about this *for* keyword. If you read it now you may not understand many things, but we will cover this important keyword later on this course. Let's be patient!

Let's quit the help section to try some other Python commands (you can write `quit` or do CTRL+C).

```
help> quit

You are now leaving help and returning to the Python interpreter.
If you want to ask for help on a particular object directly from the
interpreter, you can type "help(object)".  Executing "help('string')"
has the same effect as typing a particular string at the help> prompt.
>>>
```

Remember that the three `>>>` signs means you are now on the Python interpreter again. When quitting the help interpreter you get a message indicating that you can use the help directly on the Python interpreter. Go ahead and give it a try.

## Basic Operations in Python

You want to learn Python and you may have already guessed that Python can make calculations fast. You can make many different operations with different data types in Python. In this section you are going to learn the very basics of Python operations.

### Operations with numbers

Let's see how to make some simple math with the Python interpreter. Let's start simple and try addition, subtraction, multiplication and division.

```
>>> 1+1
2
>>> 3-1
2
>>> 2*3
6
>>> 12/3
4.0
```

The symbols for addition and subtraction are `+` and `-`, as you may have already guessed. The symbol for multiplication is an asterisk `*`, and for division you use a single forward slash `/`. The four operations you tried on this example are giving correct results.

If you look closer on the last example, the answer is shown as **4.0** instead of just **4**. This has something to do with [floating point numbers](https://en.wikipedia.org/wiki/Floating-point_arithmetic) (more on this in the future).

You can also do more complex calculations, like combined operations. If you need to group operations, use parentheses `()`. You can even use multiple parentheses if needed.

```
>>> 1-8+3
-4
>>> 1-(8+3)
-10
>>> 1-8+3/4
-6.25
>>> 1/8+(3/4)*5
3.875
>>> (1/8+(3*5-1))
14.125
```

There are other useful operations you can use in Python. The most common are modulus (remainder), exponentiation and floor division operators.

```
>>> 10%3
1
>>> 2**3
8
>>> 10//3
3
```

Each of these operations can be summarized as:

* **modulus** (%) returns the remainder of the division between two numbers.
* **exponentiation** (\**, double asterisk) returns the result of multiplying the number on the left by itself a number of times given by the number on the right.
* **floor division** (//) returns the integer part of the division between two numbers.

### Operations with strings

Another type of data you can play with before moving on are *strings*. A string is a sequence of characters surrounded by single, double or triple quotes. Within the Python interpreter, try writing different strings and hit Enter to see the output.

```
>>> 'hello in single quotes'
'hello in single quotes'
>>> ''hello in double quotes''
    File "", line 1
    ''hello in double quotes''
        ^^^^^
SyntaxError: invalid syntax
>>> "hello in double quotes"
'hello in double quotes'
>>> '''hello in triple quotes'''
'hello in triple quotes'
```

The first thing we tried is writing some text between single quotes and hitting Enter. The terminal outputs the same thing as expected. Next we tried the same string using double quotes, but the double quotes are used with two single quotes, which Python doesn't like (it gives a **SyntaxError**. More on errors later). To use double quotes you have to use the special key (it is often done with SHIFT+2 on the keyboard). And lastly triple quotes, done with three single quotes.

A curious thing to note is that no matter if you use single, double or triple quotes, the output is shown with single quotes. What if you need to include quotes in the string? You can use single quotes for our Python string, and use double quotes inside, or the other way around.

```
>>> 'hello, this "word" has quotes'
'hello, this "word" has quotes'
>>> "hello, this 'word' has quotes"
"hello, this 'word' has quotes"
```

So, the title of this section contains the word "operations". Can you "operate" with strings like you did with numbers? You can concatenate strings with the `+` operator:

```
>>> 'hello'+'world'
'helloworld'
>>> 'hello'+' '+'world'
'hello world'
```

You can also use the `*` operator to repeat the same string a given number of times:

```
>>> 'hello'*3
'hellohellohello'
```

As you can see, Python strings can also be manipulated with some of the basic operations you learned so far.

## Python variables

The last topic on this section will be about the basics of using variables in Python. Variables are a way to store values for later use. For example you may need to use your name as a string multiple times in your program or script.

Let's begin by declaring the variable `myName` and assigning it the value of the string 'Carlos'. Then write `myName` and hit Enter to print the value inside of it:

```
>>> myName = 'Carlos'
>>> myName
'Carlos'
```

Declaring and assigning values to variables in Python is as simple as that. You don't have to worry about which data type the variable will be.

You can now concatenate a string 'Hello' with 'Carlos' using the variable `myName`:

```
>>> 'Hello ' + myName
'Hello Carlos'
```

The same thing can be done with numbers. Suppose you want to compute the discriminant of a quadratic equation. For this you can use three variables for each parameter `a`, `b` and `c`:

```
>>> a = 3
>>> b = -7
>>> c = 11
>>> b**2 - 4*a*c
-83
```

Using variables in Python is a great way to write better, reusable and more readable code. Variables are used everywhere as you will see in future chapters of this course.

To quit the Python interpreter you can use `quit()` (don't forget the parentheses like I did before):

```
>>> quit
Use quit() or Ctrl-Z plus Return to exit
>>> quit()
PS C:\Users\yourusername>
```

## Conclusion

In this article you learned the basics of Python by using the terminal (PowerShell) and the Python interpreter. Here is a list of what you have learned:

* How to get help from the Python interpreter with the use of the `help()` command.
* How to make simple operations with numbers.
* How to make operations with strings.
* How to define and make simple calculations with variables.

After closing the Python interpreter, all the work you did is lost. What about if you needed to continue the work you've done at another time? For this you can use text editors.

In the next chapter you will learn more advanced ways to work with Python. You will use the topics learned on this article, so be sure you are comfortable with them. See you next time!

## Exercises

This set of exercises are here to help you better understand the topics covered on this article.

1. Open the terminal (PowerShell).

2. Check that Python is correctly installed by showing the version on the screen.

3. Enter the Python interpreter.

4. Find the help document about STRINGS. There are two ways of getting to it: one from the help interpreter, and the other directly from the Python interpreter.

5. Make the following calculation using the Python interpreter: 6/2(2+1). Is the result correct or not? How can you be sure about the order of operations in a general case?

6. Make the following calculation with the Python interpreter: sqrt(-4)=(-4)^0.5. A number with an exponent of 0.5 is the same as taking its square root. What can you guess about the output Python is giving? You will learn more about this in future chapters.

7. Use your own name to print a custom welcoming message on the screen with the use of strings.

8. Combine your name and a friend's to print a message containing both. Use two variables to hold your names.

9. Use variables to calculate how many seconds had been gone within the present day. Make a variable to hold the hours, another for minutes, and another for seconds. For example if the current time is 16:33:21 then you can assign 16 to hours, 33 to minutes and 21 to seconds.

10. Quit the Python interpreter.