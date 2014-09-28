Language basics
===============

Now that we know where to write Python code, let's have a look at the Python language.

The look'n'feel of Python
-------------------------

Code written in Python looks similar to code written in other languages such as C or Pascal. This is intentional. Python borrows a lot from C in particular.

One major difference is that, instead of using braces for grouping statements, Python uses indentation. *In Python, whitespace is not optional.* This gives Python a characteristic clean, organized structure. 

For example, instead of writing statements in C like this::

    if (a < b) {
        mmax = b;
    } else {
        mmax = a;
    }

Python dispenses braces altogether, along with the trailing semicolons::

    if a < b:
        mmax = b
    else:
        mmax = a

.. seealso::

    For a more extensive comparison between languages see `Interpreted Languages: A side-by-side reference sheet <http://hyperpolyglot.org/scripting>`_

The ‘print’ statement
---------------------

The command ``print`` simply 'prints' the argument passed in the output window.

This is all you need to write you first Python program, the famous 'hello world'::

    print 'hello world'

In Python 3, the ``print`` statement is written using the standard function syntax::

    print('hello world')

Comments
--------

Comments are parts of your code that are not executed. They usually contain notes by the programmer who wrote the code, for other programmers who are reading it. But they can also be used to turn parts of code on/off during development.

Comments are marked by a ``#`` sign. Everything after the ``#`` is a comment and is not executed.::

    # my first program!
    print 'hello world'

A comment can also appear in the middle of a line::

    print 'hello world' # hi there, I'm a comment

The ‘None’ object
-----------------

Most programming languages have a special object to signify nothing, emptyness. In Python, this is the ``None`` object::

    a = None

Note that this is different than ``0``, or an empty string, or an empty list. ``None`` is the absence of any value.


The 'boolean' object
--------------------

The boolean object is a special object which can have only two values, ``True`` or ``False``. Booleans are used to represent a binary state::

    >>> a = True
    >>> print type(a)
    <type 'bool'>
    >>> b = False
    >>> print type(b)
    <type 'bool'>

In Python, boolean values are always written with a capital first letter, so ``true`` or ``false`` will throw an error::

    >>> a = false
    Traceback (most recent call last):
      File "<untitled>", line 1, in <module>
    NameError: name 'false' is not defined

Data types
----------

There are several different data types in Python. Here are the main ones:

- *strings*
- *integers*
- *decimal numbers*
- *lists*
- *tuples*
- *dictionaries*
- *booleans*
- etc.

Each type of object has its own properties and methods. Strings are used to represent sequences of characters, integers represent real numbers, lists represent ordered collections of items etc.

The built-in function ``type()`` returns the type of a given object::

    >>> # None
    >>> print type(None)
    <type 'NoneType'>
    >>> # string
    >>> print type('hello')
    <type 'str'>
    >>> # integer
    >>> print type(123)
    <type 'int'>
    >>> # floating point
    >>> print type(10.5)
    <type 'float'>
    >>> # dictionary
    >>> print type({'key':'value'})
    <type 'dict'>
    >>> # boolean
    >>> print type(True)
    <type 'bool'>

Error messages
--------------

In Python, error messages are objects like anything else – `Exception objects`_. There are different kinds of exceptions, each for one particular situation. When an exception message appears, read it carefully: it usually contains tips that will help you to understand and solve the problem.

.. _Exception objects : https://docs.python.org/2/library/exceptions.html

Here are a few examples of Exceptions. Don't worry if you don't understand them yet, just try to familiarize yourself with the different kinds of errors::

NameError
^^^^^^^^^

Happens if we try to use a variable which has not been defined yet::

    >>> print b
    Traceback (most recent call last):
      File "<untitled>", line 1, in <module>
    NameError: name 'b' is not defined

ZeroDivisionError
^^^^^^^^^^^^^^^^^

Happens if we try to divide any number by zero::

    >>> print 1 / 0
    Traceback (most recent call last):
      File "<untitled>", line 1, in <module>
    ZeroDivisionError: integer division or modulo by zero

IndexError
^^^^^^^^^^

Happens when we try to access an item by an index bigger than the length of the collection::

    >>> L = ''
    >>> print L[1]
    Traceback (most recent call last):
      File "<untitled>", line 2, in <module>
    IndexError: string index out of range

KeyError
^^^^^^^^

Happens if we try to access a non-existing key from a dictionary::

    >>> D = {}
    >>> print D['key']
    Traceback (most recent call last):
      File "<untitled>", line 2, in <module>
    KeyError: 'key'

IndentationError
^^^^^^^^^^^^^^^^

Happens when Python is expecting an indented block and doesn't find one::

    >>> for i in range(3):
    >>> print i
    Traceback (most recent call last):
      File "<untitled>", line 2
        print i
        ^
    IndentationError: expected an indented block

And a few other ones:

- ``TypeError``
- ``AssertionError``
- ``ImportError``
- ``SyntaxError``
