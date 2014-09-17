===============
Language basics
===============

Now that you know where to write Python code, it's time to have a look at the Python language.

The look'n'feel of Python
-------------------------

Code written in Python looks similar to code written in other languages such as C or Pascal. This is intentional. Python borrows a lot from C in particular.

One major difference is that, instead of using braces for grouping statements, Python uses indentation. *In Python, whitespace is not optional.* This gives Python a characteristic clean, organized structure. 

For example, instead of writing statements in C like this::

    if (a < b) {
        max = b;
    } else {
        max = a;
    }

Python dispenses braces altogether, along with the trailing semicolons::

    if a < b:
        max = b
    else:
        max = a

.. seealso::

    `Interpreted Languages: A side-by-side reference sheet <http://hyperpolyglot.org/scripting>`_

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

Comments are marked by a ``#`` sign. Everything after the ``#`` is a comment and it's not executed.::

    # my first program!
    print 'hello world'

A comment can also appear in the middle of a line::

    print 'hello world' # hi there, I'm a comment

The ‘None’ object
-----------------

Most programming languages have a special object to signify nothing, emptyness. In Python, this is the ``None`` object::

    a = None

Note that this is different than an ``0``, or an empty string, or an empty list. ``None`` is really the absence of any value.

Object types
------------

Like in other programming languages, there are different kinds of objects in Python:

- *strings*
- *integers*
- *decimal numbers*
- *lists*
- *tuples*
- *dictionaries*
- *booleans*
- etc.

Each type of object has its own properties and methods. Strings are used to represent sequences of characters, integers represent real numbers, lists represent ordered collections of items etc.

The ``type()`` function returns the type of an object::

    >>> print type(None)
    <type 'NoneType'>
    >>> print type('hello')
    <type 'str'>
    >>> print type(123)
    <type 'int'>
    >>> print type(10.5)
    <type 'float'>
    >>> print type({})
    <type 'dict'>
    >>> print type(True)
    <type 'bool'>

The 'boolean' object
--------------------

The boolean object is a special object which can have only two values, ``True`` or ``False``, representing a binary state. In Pyhton, both boolean values are written always with a capital letter::

    >>> a = True
    >>> print type(a)
    <type 'bool'>
    >>> b = False
    >>> print type(b)
    <type 'bool'>

Error messages
--------------

In Python, error messages are objects like anything else – `Exception objects`_. There are different kinds of exceptions, each for one particular situation. When an exception message appears, read it carefully because it usually contains tips that help to understand and solve the problem.

.. _Exception objects : https://docs.python.org/2/library/exceptions.html

Here are a few examples of Exceptions::

NameError
^^^^^^^^^

Happens if we try to use a variable which has not been defined yet::

    >>> print b
    Traceback (most recent call last):
      File "<untitled>", line 1, in <module>
    NameError: name 'b' is not defined

ZeroDivisionError
^^^^^^^^^^^^^^^^^

Happens if we try to divide a number by zero::

    >>> print 1 / 0
    Traceback (most recent call last):
      File "<untitled>", line 1, in <module>
    ZeroDivisionError: integer division or modulo by zero

IndexError
^^^^^^^^^^

Happens when we try to access an item by an index bigger than the length of the collection.

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

And a few other errors:

- ``TypeError``
- ``AssertionError``
- ``ImportError``
- ``SyntaxError``
