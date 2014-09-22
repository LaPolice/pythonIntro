Comparisons
===========

When we have two or more variables, it is often necessary to write code that makes comparisons between them.

When comparing two objects it is important to make a distinction between value and identity:

- they can have different value and different identities
- they can have the same value, but have separate identities
- they can have the same value *and* the same identity

Let's have a look at how to ask these questions in Python:

Comparing values
----------------

Let's start by storing a few numbers in variables::

    a = 12
    b = 20
    c = 20

We can now compare these values in different ways. The result of a comparison expression is always a boolean value.

Are the numbers equal? This question is asked with the ``==`` operator::

    >>> a == b
    False
    >>> b == c
    True

Are the numbers different (not equal)? This question is asked with the ``!=`` operator::

    >>> a != b
    True
    >>> b != c
    False

Is the first number bigger than the second? This question is asked with the ``>`` operator::

    >>> a > b
    False
    >>> b > c
    False

Is the first number smaller than the second? This question is asked with the ``<`` operator::

    >>> a < b
    True
    >>> b < c
    False

Is the first number bigger than or equal to the second? This question is asked with the ``>=`` operator::

    >>> a >= b
    False
    >>> b >= c
    True

Is the first number smaller than or equal to the second? This question is asked with the ``<=`` operator::

    >>> a <= b
    True
    >>> b <= c
    True

Comparing identity
------------------

Besides comparing the *value* of two objects, we can also compare their identity.

Two objects can have the same value and still have different *identities* -- they are not the same thing. For example:

The integer ``10`` and the decimal number ``10.0`` have the same nummerical value::

    >>> 10 == 10.0
    True

To compare the identity between the objects we use the logical operator ``is``::

    >>> 10 is 10.0
    False

As we can see, the two objects have different identities -- one is a ``float``, and the other is an ``int``.

The 'truthiness' of values
--------------------------

Every value in every data type in Python can be converted to a boolean. Empty objects are usually converted to ``False``, while anything else is converted to ``True``.

Here are some examples with different data types::

    >>> # string
    >>> print bool('hello')
    >>> print bool('')
    True
    False
    >>> # list
    >>> print bool(['a', 'b', 'c'])
    >>> print bool([])
    True
    False
    >>> # tuple
    >>> print bool((1, 2, 3))
    >>> print bool(())
    True
    False
    >>> # dict
    >>> print bool({'A' : 1, 'B' : 2})
    >>> print bool({})
    True
    False
    >>> # integer
    >>> print bool(100)
    >>> print bool(0)
    True
    False
    >>> # float
    >>> print bool(1.1)
    >>> print bool(0.0)
    True
    False
    >>> # None
    >>> print bool(None)
    False

.. seealso:: `testing item membership <collections-loops.html#testing-item-membership>`_
