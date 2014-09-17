==================
Naming conventions
==================

A naming convention is a set of rules for choosing the character sequence used for identifiers which denote variables, types, functions, and other entities in source code and documentation.

Reasons for using a naming convention:

- to reduce the effort needed to read and understand source code
- to enhance source code appearance (for example, by disallowing overly long names or unclear abbreviations)

The choice of naming conventions can be an enormously controversial issue, with partisans of each holding theirs to be the best and others to be inferior. Colloquially, this is said to be a matter of "religion". Many companies have also established their own set of conventions to best meet their interests.

Style Guide for Python Code
---------------------------

- code is read much more often than it is written
- consistency helps to improve the readability of code
- there are rules to produce consistency across the wide spectrum of Python code

Different levels of consistency in order of importance:

1. Consistency within one module or function.
2. Consistency within a project.
3. Consistency with this style guide.

Naming styles
-------------

There are a lot of different naming styles. It helps to be able to recognize what naming style is being used, independently from what they are used for.

The following naming styles are commonly distinguished:

- ``b`` (single lowercase letter)
- ``B`` (single uppercase letter)
- ``lowercase`` (all leters in lowercase)
- ``lower_case_with_underscores``
- ``UPPERCASE``
- ``UPPER_CASE_WITH_UNDERSCORES``
- ``UpperCamelCase``
- ``lowerCamelCase``
- ``Capitalized_Words_With_Underscores``
- ``st_mode``, ``st_size``, ``st_mtime`` (prefix to group related names)

.. note:: When using abbreviations in CamelCase, capitalize all the letters of the abbreviation. Thus ``HTTPServerError`` is better than ``HttpServerError``.

Meaning of underscores
^^^^^^^^^^^^^^^^^^^^^^

Single or double underscores at the beginning and/or at the end of names have special meanings in Python:

``_single_leading_underscore``

    Weak “internal use” indicator. For example, ``from M import *`` does not import objects whose name starts with an underscore.

``single_trailing_underscore_``

    Used by convention to avoid conflicts with Python keyword, e.g. ``class_`` instead of ``class``.

``__double_leading_underscore``

    When naming a class attribute, invokes name mangling (inside class ``FooBar``, ``__boo`` becomes ``_FooBar__boo``)

``__double_leading_and_trailing_underscore__``

    “Magic” objects or attributes that live in user-controlled namespaces. E.g. ``__init__``, ``__import__`` or ``__file__``. Never invent such names; only use them as documented.

Names to avoid
^^^^^^^^^^^^^^

Never use the characters ``l`` (lowercase letter el), ``O`` (uppercase letter oh), or ``I`` (uppercase letter eye) as single character variable names.

In some fonts, these characters are indistinguishable from the numerals one ``1`` and zero ``0``. When tempted to use ``l``, use ``L`` instead.

Python conventions
------------------

- class names should use ``UpperCamelCase``
- constant names should be ``CAPITALIZED_WITH_UNDERSCORES``
- other names should use ``lowercase_separated_by_underscores``
- private variables/methods should start with an undescore: ``_myvar``
- some special class methods are surrounded by two underscores: ``__init__``

Package and Module Names
^^^^^^^^^^^^^^^^^^^^^^^^

Modules should have short, all-lowercase names. Underscores can be used if it improves readability.

Python packages should also have short, all-lowercase names, although the use of underscores is discouraged.

Class Names
^^^^^^^^^^^

Almost without exception, class names use the CapWords (CamelCase) convention. 

Classes for internal use have a leading underscore in addition.

Exception Names
^^^^^^^^^^^^^^^

Because exceptions should be classes, the class naming convention applies here. However, you should use the suffix "Error" on your exception names (if the exception actually is an error).

Global Variable Names
^^^^^^^^^^^^^^^^^^^^^

The conventions are about the same as those for functions.

Modules should use the ``__all__`` mechanism to prevent exporting globals, or use the older convention of prefixing such globals with an underscore.

Function Names
^^^^^^^^^^^^^^

Function names should be lowercase, with words separated by underscores as necessary to improve readability.

Function and method arguments
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Always use ``self`` for the first argument to instance methods.

Always use ``cls`` for the first argument to class methods.

If a function argument's name clashes with a reserved keyword, it is generally better to append a single trailing underscore rather than use an abbreviation or spelling corruption. Thus ``class_`` is better than ``clss``. (Perhaps better is to avoid such clashes by using a synonym.)

Method Names and Instance Variables
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Use the function naming rules: lowercase with words separated by underscores as necessary to improve readability.

Use one leading underscore only for non-public methods and instance variables.

Constants
^^^^^^^^^

Constants are usually defined on a module level and written in all capital letters with underscores separating words. Examples: ``MAX_OVERFLOW`` and ``TOTAL``.

Links
-----

- `Naming convention (programming) <https://en.wikipedia.org/wiki/Naming_conventions_(programming)>`_ – Wikipedia
- `PEP 8: Style Guide for Python Code <http://legacy.python.org/dev/peps/pep-0008/>`_ – Python.org
- `Self-Reliance <https://en.wikipedia.org/wiki/Self-Reliance>`_ – Wikipedia
