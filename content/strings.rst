=======
Strings
=======

Strings are ordered collections of characters, used mostly to store textual information.

Strings syntax
--------------

Strings are typically delimited by single or double quotes (also in other programming languages)::

    print 'this is a string'
    print "this is also a string"

If a single or double quote appears as part of the string itself, it might conflict with the surrounding quotes. There are a few ways to avoid this.

Whenever possible, choose the quote which does not appear in the string content to delimit the string::

    print "don't worry be happy"
    print 'national "airquoting" competition'

Escaping quote characters
^^^^^^^^^^^^^^^^^^^^^^^^^

It is also possible to *escape* the quote character, so it used literally (as a quote character, not as a string delimiter). In Python strings, to escape a character, simply add a backslash before it::

    print "this is a \"string\" too"
    print "\ is an escape character inside strings"

Special characters
^^^^^^^^^^^^^^^^^^

The backslash character can also be used to invoke some special characters, such as the *newline* character ``\n`` and the *tabulator* ``\t``::

    >>> print "hello\n\tworld"
    hello
        world

Multi-line strings
^^^^^^^^^^^^^^^^^^

When working with longer multi-line strings, it can be cumbersome to break lines with ``\n``. After a few linebreaks, the legibility of the text is sacrificed.

In such cases, we can use *triple-quoted* strings: a special notation which makes it possible to use linebreak and tabulator characters literally::

    >>> print '''hello
    ...     python
    ... world'''
    hello
        python
    world

Operations with strings
-----------------------

Strings can perform a couple of operations, using the same notation as operations with numbers (this is called `operator overloading`_).

Adding strings
^^^^^^^^^^^^^^

Strings can be added to another string::

    >>> print 'a' + 'b'
    ab
    >>> a = "a string"
    >>> b = "another string"
    >>> print a + " " + b
    a string another string

Multiplying strings
^^^^^^^^^^^^^^^^^^^

Strings can be multiplied by integers::

    >>> print "hello " * 5
    hello hello hello hello hello

...but not by floats (even if they look like an integer)::

    >>> print "hello " * 5.0
    Traceback (most recent call last):
      File "<untitled>", line 1, in <module>
    TypeError: can't multiply sequence by non-int of type 'float'

Unicode strings
---------------

In Python 2.x there are 2 different kinds of string objects: the default ASCII-based ``str`` object, and the more recent Unicode-based ``unicode`` object.

There is only one syntatic difference between strings and Unicode strings: Unicode strings are written with a preceding ``u``::

    >>> print type('this is a normal string')
    <type 'str'>
    >>> print type(u'this is a unicode string')
    <type 'unicode'>

Often, using Unicode characters in normal strings will just work::

    print "Åbenrå © Ђ ק"

.. note::

    In Python 3, all strings are unicode strings. This was one of the biggest changes is the language.

String formatting
-----------------

Python offers a `string formatting syntax`_ which makes it easier to create strings out of smaller parts.

Formatting strings
^^^^^^^^^^^^^^^^^^

This syntax uses the character ``%s`` as a placeholder, and specifies the corresponding parts to be replaced after the string::

    >>> print "formatting %s string" % 'hello'
    formatting hello string

In the above example, only one part is used when formatting the string. In case there are two or more parts, they need to be wrapped in a tuple::

    >>> print "formatting '%s %s' string" % ( 'hello', 'world' )
    formatting 'hello world' string

Notice the ``s`` after the ``%`` in ``%s``. This means that the formatting expression treats the values as a string. This is the most used option, but other ones are also available.

Formatting numbers
^^^^^^^^^^^^^^^^^^

The option ``%f`` gives a few options for formatting decimal numbers::

    >>> print "hello %f" % 50.4625
    hello 50.462500

As we can see from the output, it uses 6 decimal places by default. 

We can shorten the amount of digits after the dot by a specified amount. Here we are limiting it to two digits only::

    >>> print "hello %.2f" % 50.4625
    hello 50.46

By using a ``+`` sign before the decimal dot, we can indicate that a plus/minus sign should be prepended to the number to indicate its polarity::

    >>> print "hello %+.2f" % 1.5
    hello +1.50
    >>> print "hello %+.2f" % -3.0
    hello -3.00

.. _string formatting syntax : https://docs.python.org/2/library/stdtypes.html#string-formatting-operations
