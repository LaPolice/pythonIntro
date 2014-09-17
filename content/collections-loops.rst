=====================
Collections and Loops
=====================

Python has several types of *collection* objects: ``string``, ``list``, ``tuple``, ``set``, ``dict``. All collection objects share a few properties.

Collection properties
---------------------

Number of items in a collection
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Collections are containers of things, so all collections have a certain *length* – the number of items it contains.

We can ask the amount of items in a collection with the ``len`` function::

    >>> print len('hello world')
    11
    >>> print len(['a', 1.7, 400])
    3

Testing item membership
^^^^^^^^^^^^^^^^^^^^^^^

We can also ask a collection if it contains a certain item::

    >>> print 'a' in 'abracadabra'
    >>> print 'z' in 'abracadabra'
    True
    False
    >>> print 10.0 in [0, 10, 20, 30]
    False
    >>> print 10 in (0, 10, 20, 30)
    True
    >>> print 10 in {0, 10, 20, 30}
    True

Looping over items
------------------

There are two main kinds of loops in Python, ``for`` loops and ``while`` loops.

The items in a collection can be acessed individually with a ``for`` loop::

    >>> L = ['z', (0, 10, 20), 31.4, None]
    >>> for item in L:
    ...     print item 
    z
    (0, 10, 20)
    31.4
    None
    >>> for char in 'abcdefg':
    ...     print char,
    a b c d e f g

.. Note:: Notice how, in the second loop, we used a comma after the ``print`` statement – this prevents a line break, so all outputs appear in the same line.

Dynamic variable assignment
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Loops assign a variable name dynamically in each iteration (repetition) of the loop. The name of this variable is arbitrary, but general Python wisdom applies: it is a good idea to choose meaningful variable names, for more readable code::

    fruits = ['apples', 'oranges', 'bananas', 'papayas']
    # what does 'f' mean?
    for f in fruits:
        print f
    # better
    for fruit in fruits:
        print fruit

Looping over number ranges
--------------------------

We can use the ``range`` function to create a number sequence and repeat a certain action a number of times::

    >>> for i in range(10):
    ...     print i,
    0 1 2 3 4 5 6 7 8 9

The ``range`` function creates a list of numbers dynamically. The code above corresponds to the example below, except that the list of numbers is not stored in a variable (so it cannot be reused later)::

    >>> L = range(10)
    >>> for i in L:
    ...     print i,
    0 1 2 3 4 5 6 7 8 9
    >>> print L
    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

Loop body
^^^^^^^^^

Everything that is inside the loop body gets executed for each round of the loop.

Here we are going over a series of numbers and doing some calculations::

    >>> for i in range(10, 40, 9):
    ...    print i, i * 0.5
    10 5.0
    19 9.5
    28 14.0
    37 18.5

Here's another example, using string formatting to build new strings from other strings in a list::

    beatle = ['John', 'Paul', 'George', 'Ringo']
    for beatle in beatles:
        print 'hello %s' % beatle

Nested loops
^^^^^^^^^^^^

Loops can be placed inside other loops – this is called *nested loops*. The inner loop is executed for each iteration of the outer loop, like anything else placed in the outer loops's body:: 

    >>> # outside loop
    >>> for i in range(2):
    ...     print i
    ...     # inside loop
    ...     for j in range(3):
    ...         print i, j
    0
    0 0
    0 1
    0 2
    1
    1 0
    1 1
    1 2

Here's another example with a third level of nesting::

    >>> for x in range(2):
    ...     for y in range(2):
    ...         for z in range(2):
    ...             print x, y, z
    0 0 0
    0 0 1
    0 1 0
    0 1 1
    1 0 0
    1 0 1
    1 1 0
    1 1 1

Items and indexes
^^^^^^^^^^^^^^^^^

Sometimes it is necessary to loop over a list of items to get the items themselves::

    >>> L = [ 'alpha', 'beta', 'gamma', 'omega' ]
    >>> for item in L:
    ...     print item
    alpha
    beta
    gamma
    omega

Sometimes we need to loop over the items and get only their index in the list. We can do this using the ``len`` function (to get the amount of items in the list) in combination with ``range`` (to create the index numbers)::

    >>> for index in range(len(L)):
    ...     print index
    0
    1
    2
    3

Sometimes we need both: the index of the item, and item itself. There are different ways to do this:

1. We can use the index to get the item from the list::

    >>> for index in range(len(L)):
    ...     print index, L[index]
    0 alpha
    1 beta
    2 gamma
    3 omega

2. We can create a variable to count the iterations, loop over the items themselves, and increment the counter manually after each round::

    >>> index = 0
    >>> for item in L:
    ...     print index, item
    ...     index += 1
    0 alpha
    1 beta
    2 gamma
    3 omega

3. Another option is to iterate through the items in the list, and ask their index using the the ``index`` method. This approach only works if the items in the list are unique::

    >>> for item in L:
    ...     print item, L.index(item)
    0 alpha
    1 beta
    2 gamma
    3 omega

4. And finally, we can use the ``enumerate`` function, which returns two values for each iteration, the index and the item itself. This is the recommended *pythonic* way of doing it::

    >>> for index, item in enumerate(L):
    ...     print index, item
    0 alpha
    1 beta
    2 gamma
    3 omega

While loops
-----------

As we've seen, ``for`` loops allow us to iterate through a list of items. In comparison, ``while`` loops allow us to iterate for as long a certain condition is true.

In the following example, the loop will run as long as ``n`` is greater than zero, and stop when this condition is not met::

    >>> n = 4
    >>> while n > 0:
    ...     print n
    ...     n -= 1
    4
    3
    2
    1

Beware of infinite loops!
^^^^^^^^^^^^^^^^^^^^^^^^^

If the condition in the ``while`` loop declaration does not change, we will get caught in an infite loop -- our program will run forever without leaving the loop, and crash at some point.

A matter of convenience
^^^^^^^^^^^^^^^^^^^^^^^

Everything that can be done with ``for`` loops can also be done with ``while`` loops. The right choice depends on the nature problem at hand:

- ``for`` loops are repeated a certain number of times::

    a = 0
    for a in range(5):
        print a
        a += 1

- ``while`` loops are repeated as long as a condition is met::

    a = 0
    while a < 5:
        print a
        a += 1

The 'break' statement
---------------------

The ``break`` statement is used to exit a loop before it reaches the end. 

Let's say you are looping over all items in a list, looking for a certain value or condition. Once this value is found or this condition is met, we have achieved our goal and can exit the loop.

In the following example, we are searching for the first item in a list of strings which contains the character ``k``::

    >>> names = ['Michael', 'Joseph', 'Boris', 'Jack', 'Fred', 'Peter', 'Andre']
    >>> for name in names:
    ...     if 'k' in name:
    ...         break
    >>> print name
    Jack

The 'continue' statement
------------------------

...
