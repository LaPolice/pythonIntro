============
Dictionaries
============

A dictionary is an *unordered* collection of key/value pairs.

Creating an empty dictionary::

    dict = {}

Storing key/value pairs::

    # dict[key] = key value
    dict['a'] = 'alpha'
    dict['g'] = 'gamma'
    dict['o'] = 'omega'
    print dict

Accessing an item::

    print dict['a']

Adding a new pair key/value to the dictionary::

    dict['A'] = 6

Get all the keys in our dictionary::

    print dict.keys()

Checking the existence of a key in a dictionary::

    print 'A' in dict
    print dict.has_key('A')

If the key doesn’t exist, a ``KeyError`` is raised::

    print dict['z']

Using conditionals to avoid ``KeyError``::

    if 'z' in dict:
        print dict['z']

The method ``get(key)`` returns ``None`` instead of ``KeyError``::

    print dict.get('z')

Links
-----

- `Python syntax and semantics <https://en.wikipedia.org/wiki/Python_syntax_and_semantics>`_ – Wikipedia
- `Learn X in Y minutes (where X=python) <http://learnxinyminutes.com/docs/python/>`_
