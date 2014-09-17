===========
Comparisons
===========

Comparing values
----------------

Sometimes we'll need to compare two values. Here are a few examples:

Let's start by storing a few numbers in variables::

    a = 12
    b = 20
    c = 20

We can now compare these values in different ways. The result is always a boolean value.

Are the numbers equal?::

    >>> a == b
    False
    >>> b == c
    True

Are the numbers different (not equal)?::

    >>> a != b
    True
    >>> b != c
    False

Is the first number bigger than the second?::

    >>> a > b
    False
    >>> b > c
    False

Is the first number smaller than the second?::

    >>> a < b
    True
    >>> b < c
    False

Is the first number bigger than or equal to the second?::

    >>> a >= b
    False
    >>> b >= c
    True

Is the first number smaller than or equal to the second?::

    >>> a <= b
    True
    >>> b <= c
    True

Identity of objects
-------------------

Besides comparing the *value* of two objects, we can also check for their identity. Two objects can have the same value and still have different *identities* -- that is, they are not the same thing. Here's an example:

The integer ``10`` and the decimal number ``10.0`` have the same nummerical value::

    >>> 10 == 10.0
    True

To check for the identity between two objects, we use the logical operator ``is``. As we can see below, even though the numbers have the same value, they are not the same thing::

    >>> 10 is 10.0
    False
