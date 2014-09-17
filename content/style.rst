===========
Style Guide
===========

These are a few rules and guidelines to make your Python code more readable.

Indentation
-----------

- Use 4 spaces per indentation level.
- Never mix tabs and spaces.

Advice:

- Indent with spaces only.
- Configure your code editor to always replace tabs with spaces as you type.

Blank Lines
-----------

- Separate top-level function and class definitions with two blank lines.
- Method definitions inside a class are separated by a single blank line.
- Extra blank lines may be used (sparingly) to separate groups of related functions. 
- Use blank lines in functions, sparingly, to indicate logical sections.

Whitespace
----------

Avoid extraneous whitespace in the following situations:

Immediately inside parentheses, brackets or braces.::

    Yes: spam(ham[1], {eggs: 2})
    No:  spam( ham[ 1 ], { eggs: 2 } )

Immediately before a comma, semicolon, or colon::

    Yes: if x == 4: print x, y; x, y = y, x
    No:  if x == 4 : print x , y ; x , y = y , x

Immediately before the open parenthesis that starts the argument list of a function call::

    Yes: spam(1)
    No:  spam (1)

Immediately before the open parenthesis that starts an indexing or slicing::

    Yes: dict['key'] = list[index]
    No:  dict ['key'] = list [index]

More than one space around an assignment (or other) operator to align it with another.

Yes::

    x = 1
    y = 2
    long_variable = 3

No::

    x             = 1
    y             = 2
    long_variable = 3

Always surround these binary operators with a single space on either side: 

- assignment (``=``)
- augmented assignment (``+=``, ``-=`` etc.)
- comparisons (``==``, ``<``, ``>``, ``!=``, ``<>``, ``<=``, ``>=``, ``in``, ``not in``, ``is``, ``is not``)
- Booleans (``and``, ``or``, ``not``)

If operators with different priorities are used, consider adding whitespace around the operators with the lowest priority(ies).

Yes::

    i = i + 1
    submitted += 1
    x = x*2 - 1
    hypot2 = x*x + y*y
    c = (a+b) * (a-b)

No::

    i=i+1
    submitted +=1
    x = x * 2 - 1
    hypot2 = x * x + y * y
    c = (a + b) * (a - b)

Don't use spaces around the ``=`` sign when used to indicate a keyword argument or a default parameter value.

Yes::

    def complex(real, imag=0.0):
        return magic(r=real, i=imag)

No::

    def complex(real, imag = 0.0):
        return magic(r = real, i = imag)

Compound statements (multiple statements on the same line) are generally discouraged.

Yes::

    if foo == 'blah':
        do_blah_thing()
    do_one()
    do_two()
    do_three()

Rather not::

    if foo == 'blah': do_blah_thing()
    do_one(); do_two(); do_three()

Comments
--------

Comments should complement the code, making it easier to understand. Don’t write redudant comments. Good, readable code requires few comments.

Comments should be complete sentences: its first word should be capitalized and it should end with a period.

If a comment is short, the period at the end can be omitted.

Python coders from non-English speaking countries should make an effort to write comments in English.

Block comments
^^^^^^^^^^^^^^

Block comments consist of one or more paragraphs built out of complete sentences, and each sentence should end in a period. You should use two spaces after a sentence-ending period.

Block comments apply to the code that follows them, and are indented to the same level as that code. Each line of a block comment starts with a ``#`` and a single space.

Paragraphs inside a block comment are separated by a line containing a single ``#``.

Inline Comments
^^^^^^^^^^^^^^^

An inline comment is a comment on the same line as a statement. Inline comments should be separated by at least two spaces from the statement. They should start with a ``#`` and a single space.

Use inline comments sparingly: they are unnecessary and distracting if they state the obvious.

Don’t do this::

    x = x + 1 # Increment x

But sometimes, this is useful::

    x = x + 1 # Compensate for border

Documentation strings
---------------------

    A docstring is a string literal that occurs as the first statement in a module, function, class, or method definition. Such a docstring becomes the ``__doc__`` special attribute of that object.

source: `PEP 257 <http://www.python.org/dev/peps/pep-0257/>`_

For consistency, always use ``"""triple double quotes"""`` around docstrings.

There are two forms of docstrings: one-liners and multi-line docstrings.

One-line docstrings
^^^^^^^^^^^^^^^^^^^

The docstring is a phrase ending in a period.

It prescribes the function or method's effect as a command ("Do this", "Return that"), not as a description; e.g. don't write "Returns the pathname ...".::

    def kos_root():
        """Return the pathname of the KOS root directory."""
        global _kos_root
        if _kos_root: return _kos_root
        ...

Multi-line docstrings
^^^^^^^^^^^^^^^^^^^^^

Multi-line docstrings consist of a summary line just like a one-line docstring, followed by a blank line, followed by a more elaborate description.::

    def complex(real=0.0, imag=0.0):
        """Form a complex number.
    
        Keyword arguments:
        real -- the real part (default 0.0)
        imag -- the imaginary part (default 0.0)
    
        """
        if imag == 0.0 and real == 0.0: return complex_zero
        ...

Links
-----

- `Style Guide for Python Code (PEP 8) <http://www.python.org/dev/peps/pep-0008/>`_ – Python.org
- `PEP 8 modernisation <http://hg.python.org/peps/rev/fb24c80e9afb>`_
- `A Foolish Consistency is the Hobgoblin of Little Minds <https://en.wikipedia.org/wiki/Self-Reliance>`_ – Wikipedia
- `Docstring Conventions (PEP 257) <http://www.python.org/dev/peps/pep-0257/>`_ – Python.org 
