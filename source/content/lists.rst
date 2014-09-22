Lists
=====

Lists are *ordered* and *mutable* collections in which the same item can appear multiple times. In other programming languages, lists are sometimes called *arrays*.

Besides lists, Python has a few other data types to represent collections, with slightly different properties. If you need an ordered but *immutable* collection, use a *tuple* instead of a list. If the items need to be unique, use *set* objects. Etc.

List basics
-----------

A list is delimited by square brackets. It can contain different kinds of objects::

    alist = [1, -2, "asdsd", 4.347, 50]

Accessing list items
^^^^^^^^^^^^^^^^^^^^

List items can be accessed by their index. In Python, the first item has index zero::

    print alist[0] # first item
    print alist[1] # second item
    print alist[2] # third item

Negative numbers can be used to access items backwards::

    print alist[-1] # last item
    print alist[-2] # penultimate etc.

Nested lists
^^^^^^^^^^^^

Lists can contain other lists, which can contain other lists, and so on. This is known as ‘nested’ lists::

    list_2 = [1, 2, 3, ["a", "b", "c"]]
    list_3 = [1, 2, 3, ["a", ["A", "B"], "b", "c"]]

Operations with lists
^^^^^^^^^^^^^^^^^^^^^

Lists can be added using the ``+`` operator, just like we would do with numbers::

    >>> print alist + ['b', 100]
    [1, -2, 'asdsd', 4.347, 50, 'b', 100]

Lists can also be multiplied by integers::

    >>> print alist * 3
    [1, -2, 'asdsd', 4.347, 50, 1, -2, 'asdsd', 4.347, 50, 1, -2, 'asdsd', 4.347, 50]

Subtraction and division operations are not supported with lists.

Creating copies of a list
^^^^^^^^^^^^^^^^^^^^^^^^^

Assigning another name to a list doesn’t create a copy, just a new reference to the same object::

    >>> anotherlist = alist
    >>> anotherlist.append(-9999) # add elements to the new list
    >>> print anotherlist
    >>> print alist
    [1, -2, 'asdsd', 4.347, 50, -9999]
    [1, -2, 'asdsd', 4.347, 50, -9999]

.. warning:: It is a common beginner's mistake to think that assigning a list to a new variable creates another list. It doesn't! Try to remember this and save yourself a lot of debugging time in the future.

There are different ways to create a real copy of a list. One of them is to use the built-in function ``list()`` to create a new list::

    >>> acopy = list(alist)
    >>> acopy.append(9999)
    >>> print acopy
    >>> print alist
    [1, -2, 'asdsd', 4.347, 50, -9999, 9999]
    [1, -2, 'asdsd', 4.347, 50, -9999]

List slicing
------------

A *slice* is a continuous range of items in a list. Here's how to get a slice from a list::

    >>> print alist
    >>> # get from second to fourth items in a list
    >>> print alist[2:4]
    [1, -2, 'asdsd', 4.347, 50]
    ['asdsd', 4.347]

The slicing notation uses list indexes, so use ``0`` to start from the first item, or simply leave the first index out::

    >>> # get from first to fourth items
    >>> print alist[0:4]
    >>> # this is the same as
    >>> print alist[:4]
    [1, -2, 'asdsd', 4.347]
    [1, -2, 'asdsd', 4.347]

To finish a slice at the last item, simply leave out the second index::

    >>> # get from third to last items
    >>> print alist[2:]
    ['asdsd', 4.347, 50]

The slicing notation can also be used to create a copy of a list::

    >>> newlist = alist[:]
    >>> newlist.append('hello')
    >>> print alist
    >>> print newlist
    [1, -2, 'asdsd', 4.347, 50]
    [1, -2, 'asdsd', 4.347, 50, 'hello']

String indexes and slices
^^^^^^^^^^^^^^^^^^^^^^^^^

Indexes and slices also work with strings, after all they are ordered sequences as well.

Characters in a string can be accessed by their index::

    >>> astring = "the quick brown fox jumps over the lazy dog"
    >>> print astring[2]  # third character
    >>> print astring[-1] # last character
    e
    g

Strings can also be sliced, using the same syntax as lists::

    >>> print astring[4:20]
    quick brown fox

Adding items to a list
----------------------

New items can be added to a list with the ``append`` method::

    >>> alist.append(1234)
    >>> print alist
    [1, -2, 'asdsd', 4.347, 50, 1234]

Similarly, the ``extend`` method can be used to append a list of items to a another list::

    >>> alist.extend(['one', 'two', 'three'])
    >>> print alist
    [1, -2, 'asdsd', 4.347, 50, 'one', 'two', 'three']

The ``insert`` method allows you to insert an item in a specific position, using a list index::

    >>> alist.insert(3, 'hello!')
    >>> print alist
    [1, -2, 'asdsd', 'hello!', 4.347, 50]

Finally, the slice notation can be used to replace a section of a list with another list::

    >>> alist[2:4] = ['one', 'two', 'three']
    >>> print alist
    [1, -2, 'one', 'two', 'three', 50]

Removing list items
-------------------

List items can be removed using the ``del`` command and the item's index::

    >>> L = ['Doc', 'Grumpy', 'Happy', 'Sleepy', 'Bashful', 'Sneezy', 'Dopey']
    >>> del L[0]
    >>> print L
    ['Grumpy', 'Happy', 'Sleepy', 'Bashful', 'Sneezy', 'Dopey']

To delete several continuous items, the slice notation can be used::

    >>> del L[1:4]
    >>> print L
    ['Grumpy', 'Sneezy', 'Dopey']

If you don't know the index of item, you can use the ``remove`` command and refer to the item itself::

    >>> L.remove('Grumpy')
    >>> print L
    ['Sneezy', 'Dopey']

'Popping' list items
^^^^^^^^^^^^^^^^^^^^

The ``pop`` method removes an item from a list, and at the same time returns it. This is used to make lists behave like stacks::

    >>> fruits = ['apple', 'banana', 'grapefruit', 'kiwi', 'melon', 'papaya', 'mango']
    >>> print fruits.pop()
    >>> print fruits
    mango
    ['apple', 'banana', 'grapefruit', 'kiwi', 'melon', 'papaya']
    >>> print fruits.pop()
    >>> print fruits
    papaya
    ['apple', 'banana', 'grapefruit', 'kiwi', 'melon']

The ``pop`` method can also take a index, to take out an item which is not the last one::

    >>> print fruits.pop(0)
    >>> print fruits
    apple
    ['banana', 'grapefruit', 'kiwi', 'melon']

Ordering lists
--------------

Lists items can easily be sorted using the ``sort`` method::

    >>> L = ['z', 'a', 'asdas', 100, 2.4, True, [], None]
    >>> L.sort()
    >>> print L
    [None, True, 2.4, 100, [], 'Asdas', 'a', 'z']

Notice the order in which the different types of Python objects are sorted: ``None``, ``bool``, ``float``, ``int``, ``list``, ``string``.

Here is a list of strings with different kinds of characteres at the starting position, and the sorted output::

    >>> L2 = ['A', 'abc', ':', '#', '0123', '1', '20', ' ' ]
    >>> L2.sort()
    >>> print L2
    [' ', '#', '0123', '1', '20', ':', 'A', 'abc']

Lists also have  a ``reverse`` method, to sort items in the inverse order::

    >>> L3 = ['Barcelona', 'Vienna', 'Rio de Janeiro', 'Sao Paulo', 'Berlin']
    >>> L3.reverse()
    >>> print L3
    ['Berlin', u'Sao Paulo', 'Rio de Janeiro', 'Vienna', 'Barcelona']

Both ``sort`` and ``reverse`` modify the list in-place -- this means that the list is modified, but no value is returned::

    >>> print L3.sort()
    None
    >>> print L3
    ['Barcelona', 'Berlin', 'Rio de Janeiro', 'Sao Paulo', 'Vienna']

.. warning:: This is another common beginner's mistake: ``sort()`` and ``reverse()`` don't return a value, they modify the lists in place.

In newer Pythons we can use the built-in method ``sorted()``, which returns a sorted copy of the given collection, as an alternative to ``sort()``::

    >>> for L in sorted(L3):
    ...     print L,
    Barcelona Berlin Rio de Janeiro Sao Paulo Vienna

A ``reversed()`` iterator is available as well::

    >>> for L in reversed(L3):
    ...     print L,
    Vienna Sao Paulo Rio de Janeiro Berlin Barcelona

Creating number sequences
-------------------------

Sequential lists of numbers can be created dynamically using the ``range`` function.

The following command creates a list of numbers, starting from ``0`` and ending *before* ``10``::

    >>> print range(10)
    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

Sometimes we need to start a sequence with a number different than zero. In this case, we need to use ``range`` with two arguments::

    >>> # from 5 to 10 (doesn't include 10!)
    >>> print range(5, 10)
    [5, 6, 7, 8, 9]

Finally, we can use a third argument to specify the interval between the numbers in the sequence::

    >>> # from 1 to 19 (doesn't include 19!)
    >>> # in intervals of 3
    >>> print range(1, 19, 3)
    [1, 4, 7, 10, 13, 16]
