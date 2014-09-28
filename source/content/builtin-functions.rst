Built-in functions
==================

The Python language comes with a number of `built-in functions`_ which are always available as part of the language.

We have already seen some of them in passing, so let's recap and have a look at some new ones.

.. _built-in functions: https://docs.python.org/2/library/functions.html

Type conversions
----------------

As we've seen in the beginning, the ``type`` functions allows us to ask the type of an object::

    >>> print type('hello')
    <type 'str'>
    >>> type(1)
    <type 'int'>
    >>> type(33.3)
    <type 'float'>

Python has several built-in functions to convert from one data type into another. These functions have the same name as the data types, so it's easy to remember them:

str()
^^^^^

The ``str`` function transforms something into a string, or creates a new string if called without any argument::

    >>> a = str(10)
    >>> print type(a), len(a)
    <type 'str'> 2
    >>> b = str()
    >>> print type(b), len(b)
    <type 'str'> 0

list()
^^^^^^

The ``list`` function transforms something into a list, or creates a new list if called without any argument::

    >>> print list('abcdefghijklmn')
    ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n']
    >>> L = list()
    >>> print L, type(L), len(L)
    [] <type 'list'> 0

dict()
^^^^^^

The ``dict`` function can create a dict out of different types of arguments, or a new dict empty if called without any argument::

    >>> # create a new dict from a list of keyword/value tuples
    >>> print dict([('hello', 1), ('world', 2)]
    {'world': 2, 'hello': 1}
    >>> # create a new dict using keyword arguments
    >>> print dict(hello=1, world=2)
    {'world': 2, 'hello': 1}
    >>> # create a new empty dict
    >>> d = dict()
    >>> print type(d), len(d), d
    <type 'dict'> 0 {}

float()
^^^^^^^

The ``float`` function transforms an integer or string into a decimal (floating point) number, or creates a new float with value ``0.0`` if called wihout any argument::

    >>> print float(27)
    27.0
    >>> print float()
    0.0

Conversion from string to float only works if the string looks like a number::

    >>> print float('27.0')
    27.0
    >>> print float('27')
    27.0
    >>> print float('abc')
    Traceback (most recent call last):
      File "<untitled>", line 3, in <module>
    ValueError: could not convert string to float: abc

bool()
^^^^^^

The ``bool`` function transforms any data type into a boolean value, or returns ``False`` if called without any argument::

    >>> print bool(1)
    True
    >>> print bool('')
    False

See `testing truthiness <comparisons.html#testing-truthiness>`_ for examples of conversions from other data types.

set()
^^^^^

The ``set`` function creates a new set object from a collection, or creates a new empty set if called without any argument::

    >>> print set('abracadabra')
    set(['a', 'r', 'b', 'c', 'd'])
    >>> print set([1, 5, 10, 50, 10, 5, 1])
    set([1, 10, 50, 5])
    >>> print set({'a': 5, 'b': 3, 'c': 1})
    set(['a', 'c', 'b'])
    >>> print set(((10, 20), (20, 25), (10, 20)))
    set([(20, 25), (10, 20)])
    >>> print set()
    set([])

tuple()
^^^^^^^

The ``tuple`` function creates a tuple from a collection, or creates a new empty tuple if called without any argument::

    >>> tuple([1, 2, 3])
    (1, 2, 3)
    >>> print tuple('abc')
    ('a', 'b', 'c')
    >>> print tuple({'a': 5, 'b': 3, 'c': 1})
    ('a', 'c', 'b')


Collections and loops
---------------------

len()
^^^^^

The ``len`` function returns the amount of items in a collection::

    >>> L = ['A', 'B', [1, 2, 3], 'D']
    >>> print len(L)
    4 
    >>> print len('I will not buy this record, it is scratched.')
    44

range() and xrange()
^^^^^^^^^^^^^^^^^^^^

The ``range`` function returns a sequence of numbers. The function ``xrange`` does exactly the same thing, but it is optimized for speed when dealing with very large ranges::

    >>> for i in range(7):
    ... print i,
    0 1 2 3 4 5 6
    >>> for i in xrange(7):
    ...     print i,
    0 1 2 3 4 5 6

enumerate()
^^^^^^^^^^^

The ``enumerate`` function adds a counter to a loop. It returns an *iterator object* which returns a tuple of (index, item) for each item in the collection::

    >>> L = ['A', 'B', 'C', 'D']
    >>> print enumerate(L)
    <enumerate object at 0x11ac07af0>
    >>> print list(enumerate(L))
    [(0, 'A'), (1, 'B'), (2, 'C'), (3, 'D')]

The ``enumerate`` function is typically used when looping over the items in a collection::

    >>> for index, item in enumerate(L):
    ...     print index, item
    0 A
    1 B
    2 C
    3 D
    >>> for index, item in enumerate('abcd'):
    ...     print index, item
    0 a
    1 b
    2 c
    3 d

sorted() and reversed()
^^^^^^^^^^^^^^^^^^^^^^^

The ``sorted`` function makes it easier to loop over a sorted version of a collection. It is a shorthand for creating a copy of the collection, sorting it, and looping over its items::

    >>> L = ['Mike', 'Bravo', 'Charlie', 'Tango', 'Alpha']
    >>> for item in sorted(L):
    ...     print item,
    Alpha Bravo Charlie Mike Tango
    >>> for item in sorted('abracadabra'):
    ...     print item,
    a a a a a b b c d r r

The ``reversed`` functions works in a similar way, but it returns a list with the inverse order::

    >>> for item in reversed(L):
    ...     print item,
    Alpha Tango Charlie Bravo Mike
    >>> for item in reversed('abracadabra'):
    ...     print item,
    a r b a d a c a r b a

zip()
^^^^^

The ``zip`` function takes two separate lists, and creates a new list with pairs of values (one from each list)::

    >>> L1 = ['A', 'B', 'D', 'E', 'F', 'G', 'H', 'I']
    >>> L2 = [1, 2, 3, 4, 5, 6]
    >>> print zip(L1, L2)
    [('A', 1), ('B', 2), ('D', 3), ('E', 4), ('F', 5), ('G', 6)]

The resulting list has the same amount of items as the smallest of the two lists.

The ``zip`` function is often used to create a dictionary from a list of keys and a list of values:

    >>> D = dict(zip(L1, L2))
    >>> print D
    {'A': 1, 'B': 2, 'E': 4, 'D': 3, 'G': 6, 'F': 5}

Numerical
---------

Some built-in functions are handy when working with numbers:

abs()
^^^^^

The ``abs`` function returns the absolute value of a number::

    >>> print abs(10)
    10
    >>> print abs(-10)
    10

sum()
^^^^^

The ``sum`` functions adds all items in a list of numbers::

    >>> L = [10, 300.7, 50, 33.1]
    >>> print sum(L)
    393.8

min()
^^^^^

The ``min`` function returns the smallest number in a list of numbers::

    >>> print min(L)
    10

max()
^^^^^

The ``max`` function returns the biggest number in a list of numbers::

    >>> print max(L)
    300.7
