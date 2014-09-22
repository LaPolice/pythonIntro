Boolean logic
=============

When writing code with comparisons it is often useful to group two or more comparisons into expressions.

In Python, as in other programming languages, we can do this using the *boolean logic operators* ``and``, ``or`` and ``not``.

Boolean 'and'
-------------

The ``and`` operator allows us to check if two or more conditions are met simultaneously.

The ``and`` operator returns ``True`` only if all expressions are ``True``. In all other cases it returns ``False``.

+--------+--------+--------+
| and    | True   | False  |
+--------+--------+--------+
| True   | True   | False  |
+--------+--------+--------+
| False  | False  | False  |
+--------+--------+--------+

Here's an example: we want to do something *only if both values* are bigger than ``15``, otherwise we'll do something else::

    a = 17 # try different values here
    b = 17
    if a > 15 and b > 15:
        print "do something"
    else:
        print "do something else"

Boolean 'or'
------------

The ``or`` operator allows us to check if at least one among several conditions is met.

The ``or`` operator returns ``False`` only if all expressions are ``False``. In all other cases it returns ``True``.

+--------+--------+--------+
| or     | True   | False  |
+--------+--------+--------+
| True   | True   | True   |
+--------+--------+--------+
| False  | True   | False  |
+--------+--------+--------+

In the following example, we'll do something if *at least one value* is bigger than ``15``, otherwise we'll do something else::

    a = 17 # try different values here
    b = 17
    if a > 15 or b > 15:
        print "do something"
    else:
        print "do something else"

Boolean 'not'
-------------

The ``not`` operator simply inverts the value of an expression:

- if the expression is ``False``, it will be turned into ``True``
- if it is ``True``, it will be turned into ``False``

Here's a simple example::

    >>> a = True
    >>> print a
    True
    >>> print not a
    False

And here's a more realistic example, combining ``not`` and list membership testing::

    >>> L1 = ['a', 'b', 'c', 'd', 'e', 'f']
    >>> L2 = ['a', 'e', 'i', 'o', 'u']
    >>> for char in L1:
    ...     if char not in L2:
    ...         print char,
    b c d f

Grouping expressions
--------------------

Like aritmetic expressions, boolean expressions can be grouped using parentheses to indicate the order of the operations::

    if (a > b and b == 13) or b == 25:
        print "..."

    if a > b and (b == 13 or b == 25):
        print "..."
