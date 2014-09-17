===============
Tuples and Sets
===============

There are other kinds of collection objects in Python besides lists. Let's have a look at two of them, *tuples* and *sets*.

Tuples
------

Like lists, tuples are ordered collections of items. But different than lists, they are *immutable*.

Tuples are delimited by parentheses::

    >>> aTuple = (1, 2, 'Hi')
    >>> print type(aTuple)
    <type 'tuple'>

Tuple items can also be accessed by their index::

    >>> print aTuple[2]
    Hi

But unlike lists, items in tuples can’t be modified directly. This doesn't work::

    >>> aTuple[2] = 'bye'
    Traceback (most recent call last):
      File "<untitled>", line 5, in <module>
    TypeError: 'tuple' object does not support item assignment

To modify a tuple, it is necessary to redefine all its items::

    >>> aTuple = (1, 2, 'bye')
    >>> print aTuple
    (1, 2, 'bye')

One-item tuples
^^^^^^^^^^^^^^^

Tuples with only one item require a comma to be recognized as a tuple. For example, this is not a tuple::

    >>> aTuple = ('oops')
    >>> print type(aTuple)
    <type 'str'>

To get the desired result, simply add a comma::

    >>> aTuple = ('hi',)
    >>> print type(aTuple)
    <type 'tuple'>

.. Warning::

    Forgetting the comma in one-item tuples is a common mistake, so read this section again and make sure you don't forget it.

Packing and unpacking tuples
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Tuples are useful to pack a group of values into a single ‘thing’. For example, colors are usually expressed as tuples of RGB values, positions as tuples of XYZ coordinates, and so on. Since tuples are immutable, this helps to keep these values together.

Here's an example of *packing* values into a tuple::

    >>> pos = (0, 100, 150)
    >>> print pos
    (0, 100, 150)

If we need to use the values individually, we can *unpack* a tuple into variables::

    >>> x, y, z = pos
    >>> print x, y, z
    0 100 150

This only works if the amount of variables names to the left of the equality match the amount of values inside the tuple. Here we have less variable names than values::

    >>> x, y = pos
    Traceback (most recent call last):
      File "<untitled>", line 5, in <module>
    ValueError: too many values to unpack

…and here we have more variable names than values. Notice the different error messages::

    >>> x, y, z, w = pos
    Traceback (most recent call last):
      File "<untitled>", line 5, in <module>
    ValueError: need more than 3 values to unpack

Sets
----

Sets are a special kind of collection which contain only unique elements. They have special methods to perform set operations like *union*, *intersection*, *difference* etc.

Sets can be created from a list or tuple using the ``set`` constructor. Notice how all duplicated items are removed, and appear only once int the resulting set::

    >>> set_1 = set([1, 3, 2, 3, 4, 3])
    >>> print set_1
    set([1, 2, 3, 4])

New syntax for creating sets
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Since Python 2.7, non-empty sets can be created by enclosing a sequence of comma-separated values in curly brackets::

    >>> set_2 = {1, 8, 4, 5, 6}
    set([8, 1, 4, 5, 6])

Curly brackets are also used to create dictionaries. So a pair of empty curly brackets will create a dictionary, not a set::

    >>> print type({})
    <type 'dict'>

To create an emtpy set, it is still required to use the ``set`` constructor::

    >>> print type(set())
    <type 'set'>

Set operations
^^^^^^^^^^^^^^

Sets have methods to perform boolean set operations with other sets: union, difference and intersection::

The ``union`` operation returns a new set with elements from both sets::

    >>> print set_1
    >>> print set_2
    set([1, 2, 3, 4])
    set([8, 1, 4, 5, 6])
    >>> print set_1.union(set_2)
    set([1, 2, 3, 4, 5, 6, 8])

The ``intersection`` operation returns a new set with elements which are common to both sets::

    >>> print set_1.intersection(set_2)
    set([1, 4])

The ``difference`` operation returns a new set with elements which are in the first set, and not in the second::

    >>> print set_1.difference(set_2)
    set([2, 3])
    >>> print set_2.difference(set_1)
    set([8, 5, 6])
