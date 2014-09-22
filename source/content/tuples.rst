Tuples
======

Tuples, like lists, are ordered collections of items. But different than lists, tuples are *immutable*.

Tuple basics
------------

Tuples are delimited by parentheses::

    >>> aTuple = (1, 2, 'Hi')
    >>> print type(aTuple)
    <type 'tuple'>

We can actually write tuples without the parentheses. As long as there is a comma, one or more items will be interpreted as a tuple::

    >>> anotherTuple = 3, 4, 'Hello', 5
    >>> print type(anotherTuple)
    <type 'tuple'>

Like in lists, items in tuples can be accessed by their index::

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
---------------

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
----------------------------

Tuples are useful to pack a group of values into a single ‘thing’. For example, colors are usually expressed as tuples of R,G,B values, positions as tuples of X,Y coordinates, and so on. Since tuples are immutable, these values are kept together.

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
