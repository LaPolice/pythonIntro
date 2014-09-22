Sets
====

Sets are a special kind of collection which contain only unique elements. They have special methods to perform set operations like *union*, *intersection*, *difference* etc.

Set basics
----------

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

To create an empty set, it is still required to use the ``set`` constructor::

    >>> print type(set())
    <type 'set'>

Set operations
--------------

Sets have methods to perform boolean set operations with other sets: *union*, *difference* and *intersection*::

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

.. note:: For the ``difference`` operation, the order of the sets matters. For the other operations, changing the order will not change the result.
