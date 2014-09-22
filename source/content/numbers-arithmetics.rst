Numbers and arithmetics
=======================

Now let's have a look at some objects in Python which are used to represent numbers.

Integers and decimal numbers
-----------------------------------

The two main ones are: ``int`` (integers) and ``float`` (decimal numbers)::

    >>> # this is an integer
    >>> A = 12
    >>> type(A)
    <type 'int'>

    >>> # this is a float
    >>> B = 12.5
    >>> type(B)
    <type 'float'>

The only difference in terms of notation if the use of a period for decimal numbers. A number is a decimal number even if there is no digit after the period::

    >>> # this is still a float
    >>> C = 12.
    >>> type(C)
    <type 'float'>

Arithmetic Operations
---------------------

Addition
^^^^^^^^

Adding numbers is easy and intuitive: simply use the ``+`` operator ::

    >>> 1 + 1
    2
    >>> 1 + 1 + 10
    12

Integers can be added to integers, floats can be added to floats, and integers can be added to floats (and vice-versa)::

    >>> # result is an integer
    >>> 12 + 13
    25
    >>> # result is a float
    >>> 12 + 0.5
    12.5
    >>> # result is a float
    >>> 0.5 + 12.5
    13.0

If both numbers are integers, the result is also an integer. If at least one of the numbers is a float, the result will be a float.

Subtraction
^^^^^^^^^^^

Subtracting numbers follows the same logic, just use the ``-`` operator::

    >>> 12 - 8
    4

The minus sign is also used to indicate negative numbers::

    >>> 12 - 25
    -13

Multiplication
^^^^^^^^^^^^^^

In Python, the multiplication operator is the ``*`` character, rather than ``×`` (multiplication sign) as usual in maths. But it works exactly the same way::

    >>> 12 * 8
    96
    >>> 12 * -25
    -300

Division
^^^^^^^^

Division in Python uses the ``/`` (forward slash) as its operator::

    >>> 11 / 2
    5

.. warning::

    The default division behavior in Python 2.x is *floor division* — the result is rounded down to the nearest integer. This is usually weird for beginners.

In Python 2.x, if you need the division result as a float, you'll need to convert one of the numbers to float first::

    >>> 11 / 2.
    5.5

In Python 3, the division operator uses float division as its default. As with other Python 3 features, it is possible to use float division as default in Python 2.x by importing it from the ``__future__`` module::

    >>> 11 / 2
    5
    >>> from __future__ import division
    >>> 11 / 2
    5.5

Division by zero is mathematically not possible and will always raise an error::

    >>> 1 / 0
    Traceback (most recent call last):
      File "<untitled>", line 1, in <module>
    ZeroDivisionError: integer division or modulo by zero

Integer division can be performed with the special operator ``//``::

    >>> 11 // 2
    5

Finally, use the ``%`` operator to get the rest of a division (modulo)::

    >>> 11 % 2
    1

Exponentiation
^^^^^^^^^^^^^^

To elevate a number to the power of another number, the operator ``**`` is used::

    print 2 ** 8
    print 10 ** 2
    print 2 ** 0.5

Combining operations
^^^^^^^^^^^^^^^^^^^^

Arithmetic operations can be combined into larger statements and calculations::

    print 7 + 10 - 100 * 3 / 200 ** 4

Python executes division and multiplication first, and addition and subtraction afterwards. If you want to add or subtract first, you must put these operations between parentheses -- Python will execute operations between parentheses first::

    >>> 9 * 9 + 2
    83
    >>> 9 * (9 + 2)
    99

Increment/decrement operators
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Sometimes when writing code it is necessary to increment or decrement a value (to add or subtract a value from an integer)::

    a = 10
    a = a + 2

In cases like this, it possible to write the same line using the increment ``+=`` operator::

    # a = a + 2
    a += 2 

...and a decrement operator ``-=`` is also available::

    # b = b - 1
    b -= 1

There is also an incrementing product operator ``*=``::

    # c = c * 10
    c *= 10

More math
---------

Python can do many other kinds of mathematical calculations, of course. Many of these mathematical functions live in `the math module`_. For example, trigonometric functions such as *sine*, *cosine*, *tangent*; constants such as *pi*, etc.

.. code::

    >>> import math
    >>> print math.pi
    3.14159265359

.. _the math module : https://docs.python.org/2/library/math.html
