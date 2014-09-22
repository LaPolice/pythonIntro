Variables
=========

Variables are simply names with values assigned to them. A few examples::

    a = 12
    b = 15
    t = "a string"

Variables can be used in expressions. When the code is executed, they get substituted by the value they stand for::

    >>> a * b
    180

In Python, everything is an object. The following assignment ‘restarts’ the variable named ``a``, connecting it to another object::

    >>> a = a + 10
    >>> print a
    22

Naming variables
----------------

Variable names can’t start with a number. If you try it, a ``SyntaxError`` will be raised::

    >>> 1a = 12
    Traceback (most recent call last):
      File "<untitled>", line 1
        1a = 12
         ^
    SyntaxError: invalid syntax

Variable names can contain numbers, as long as they are not the first character::

    a1 = 12

Underscores are also allowed in variable names — and have a special meaning too, indicating private names (more about this later):: 

    _a = 12
    a_ = 13

Variable names are case sensitive. So ``x`` is a different variable than ``X``::

    >>> x = 12
    >>> X = 13
    >>> x, X, x == X
    12 13 False

Therefore, this will raise a ``NameError``::

    >>> y = 102
    >>> Y
    Traceback (most recent call last):
      File "<untitled>", line 2, in <module>
    NameError: name 'Y' is not defined

Assigning multiple items
------------------------

When declaring variables, several items can be assigned at once::

    x, y, z = 0, 100, 200

This only works if the amount of variables and the amount of values are the same::

    >>> x, y, z = 0, 100
    Traceback (most recent call last):
      File "<untitled>", line 1, in <module>
    ValueError: need more than 2 values to unpack

If two or more variables have the same value, they can be assigned at once::

    >>> x = y = z = 100
    >>> x, y, z
    100 100 100

Swapping values
---------------

In Python, we can swap the values of two variables at once with the following syntax::

    >>> a, b = 10, 20
    >>> a, b = b, a
    >>> print a, b
    20 10
