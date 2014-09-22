Collections and Loops
=====================

Python has several data types to represent *collections*: lists, tuples, sets, dictionaries and even strings (collections of characters).

All collection objects share some properties and have similar behaviour, let's have a look at them.

Collection properties
---------------------

Number of items in a collection
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Collections are containers of things, so all collections have a certain *length* – the number of items contained in them.

We can ask the amount of items in a collection with the ``len`` function::

    >>> print len('hello world')
    11
    >>> print len(['a', 1.7, 400])
    3

Testing item membership
^^^^^^^^^^^^^^^^^^^^^^^

We can also ask a collection if it contains a certain item::

    >>> print 10.0 in [0, 10, 20, 30]
    False
    >>> print 10 in (0, 10, 20, 30)
    True
    >>> print 10 in {0, 10, 20, 30}
    True

In the same way, we can ask a string if it contains a certain character::

    >>> print 'a' in 'abracadabra'
    True
    >>> print 'z' in 'abracadabra'
    False

For loops
---------

There are two main kinds of loops in Python, ``for`` loops and ``while`` loops.

Use ``for`` loops to access the items in a collection individually. Here we are accessing all items in a list::

    >>> L = ['z', (0, 10, 20), 31.4, None]
    >>> for item in L:
    ...     print item 
    z
    (0, 10, 20)
    31.4
    None

And here the same thing with all characters in a string::

    >>> for char in 'abcdefg':
    ...     print char,
    a b c d e f g

.. Note:: Notice how we used a comma after the ``print`` statement in the second example – this prevents a line break, so all outputs appear in the same line.

Dynamic variable assignment
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Loops assign a variable name dynamically in each iteration (repetition) of the loop. The name of this variable is arbitrary, but general Python wisdom applies: it is a good idea to choose meaningful variable names for more readable code::

    fruits = ['apples', 'oranges', 'bananas', 'papayas']
    for f in fruits: # what does 'f' mean?
        print f
    # better:
    for fruit in fruits:
        print fruit

Looping over number ranges
^^^^^^^^^^^^^^^^^^^^^^^^^^

The ``range`` built-in function creates a sequence of numbers.::

    >>> L = range(4)
    >>> print L
    [0, 1, 2, 3]

This can be used to repeat a certain action a number of times::

    >>> for i in range(4):
    ...     print 'spam', i
    spam 0
    spam 1
    spam 2
    spam 3

The ``range`` function can take one, two or three arguments.

- If only one argument is given, the function returns a list starting at zero, and ending at the number given as argument minus one::

    >>> print range(10)
    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

- If two numbers are given, the first number indicates the starting number (inclusive), while the second indicates the last  number minus one as before::

    >>> print range(4, 10)
    [4, 5, 6, 7, 8, 9]

- If a third number is given, it indicates the step (increment) between the numbers in the sequence::

    >>> print range(4, 20, 3)
    [4, 7, 10, 13, 16, 19]

Loop body
^^^^^^^^^

The 'body' of a loop is the indented part after the loop enunciation. It gets executed once for each round of the loop. 

Here's an example in which we print some info before, during and after the loop::

    >>> # outside of the loop
    >>> print 'preparing...'
    >>> for i in range(4):
    ...    # body of the loop
    ...    print i, 'doing something...'
    >>> # outside of the loop
    >>> print '...finished.'
    preparing...
    0 doing something...
    1 doing something...
    2 doing something...
    3 doing something...
    ...finished.

Here's another example, using string formatting syntax to create new strings with items from a list::

    beatles = ['John', 'Paul', 'George', 'Ringo']
    for beatle in beatles:
        print 'hello %s' % beatle

Nested loops
^^^^^^^^^^^^

Loops can be placed inside other loops – this is called *nested loops*. The inner loop is executed once for each round of the outer loop:: 

    >>> # outside loop
    >>> for i in range(2):
    ...     print i, 'outer'
    ...     # inside loop
    ...     for j in range(3):
    ...         print i, j, 'inner'
    0 outer
    0 0 inner
    0 1 inner
    0 2 inner
    1 outer
    1 0 inner
    1 1 inner
    1 2 inner

Here's another example with a third level of nesting::

    >>> for x in range(2):
    ...     for y in range(2):
    ...         for z in range(2):
    ...             print 'x%s y%s z%s' % (x, y, z)
    x0 y0 z0
    x0 y0 z1
    x0 y1 z0
    x0 y1 z1
    x1 y0 z0
    x1 y0 z1
    x1 y1 z0
    x1 y1 z1

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

Sometimes we need to loop over the items and get only their *index* (position) in the list. We can do this using the ``len`` function (to get the amount of items in the list) in combination with ``range`` (to create the index numbers)::

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

While ``for`` loops allow us to iterate through a list of items, ``while`` loops allow us to iterate for as long a certain condition is true.

In the following example, the loop will run as long as ``n`` is greater than zero, and stop when this condition is not met::

    >>> n = 4
    >>> while n > 0:
    ...     print n
    ...     n -= 1
    4
    3
    2
    1

.. warning:: Beware of infinite loops! Make sure you to break the loop condition at some point.

If the condition in the ``while`` loop declaration does not change, we will get caught in an infite loop -- our program will run forever without leaving the loop, and the computer will freeze or crash at some point. So make sure you change the truth condition to break out of the loop at some point. In the above example, we are decreasing the value of ``n`` at each round, so after a few rounds it stops being bigger than ``0``.

A matter of convenience
^^^^^^^^^^^^^^^^^^^^^^^

Everything that can be done with ``for`` loops can also be done with ``while`` loops. The right choice depends on the nature problem at hand:

- ``for`` loops are repeated a certain number of times::

    a = 0
    for a in range(5):
        print a
        a += 1

- ``while`` loops are repeated as long as a certain condition is met::

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

The for / else statement
^^^^^^^^^^^^^^^^^^^^^^^^

Loops in Python can have an additional ``else`` statement, which gets executed only if the loop completes normally. If the loop exits before the end (for example with a ``break`` statement), the ``else`` block is not executed.

Building on the example above, we could have an ``else`` statement that gets executed only if no matching item has been found::

    for name in names:
        if 'k' in name:
            print name
            break
    else:
        print "didn't find any match"

It is also possible to write ``while`` loops with an ``else`` statement.

The 'continue' statement
------------------------

The ``continue`` statement is used to skip the remaining execution of code for the current iteration, and continue with the next iteration in the same loop.

Using the same example, all names will be printed *except* the one which contains a ``k``::

    >>> names = ['Michael', 'Joseph', 'Boris', 'Jack', 'Fred', 'Peter', 'Andre']
    >>> for name in names:
    ...     if 'k' in name:
    ...         continue
    ...     print name
    Michael
    Joseph
    Boris
    Fred
    Peter
    Andre
