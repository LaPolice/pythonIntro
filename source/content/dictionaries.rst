Dictionaries
============

So far we've looked at several data types in Python: strings, integers, floats, lists, tuples, booleans. Now let's have a look at dictionaries.

A dictionary is an *unordered* collection of *key/value pairs*. *Unordered collection* means that in a dictionary, different than in lists or tuples, the items have no order.

The items of a dictionary are accessed by their *keys*, not by their order. Every value in a dictionary has a key, and vice-versa. The key is usually a string, the value can be anything (including another dictionary).

Dictionary basics
-----------------

Dictionaries are written with curly brackets. Here's how we create an empty dict::

    myDict = {}

And here's a new dictionary with some values::

    myDict = {
        'key 1' : 'value',
        'key 2' : 'another value',
    }

We can add new items to a dictionary with the following syntax::

    myDict['key 3'] = 'some other value'

Individual items can be accessed by their keys::

    >>> print myDict['key 2']
    another value

If there is no item with the given key, a ``KeyError`` is raised::

    >>> print myDict['key 4']
    Traceback (most recent call last):
      File "<untitled>", line 2, in <module>
    KeyError: 'key 4'

Dictionary methods
------------------

Every dictionary has a few methods which we can use to access and manipule their data.

We can get all keys or all values of a dictionary as lists::

    >>> print dict.keys()
    ['key 1', 'key 2', 'key 3']
    >>> print myDict.values()
    ['value', 'another value', 'some other value']

We can also get all items in a dictionary is a list of key/value tuples::

    >>> print myDict.items()
    [('key 1', 'value'), ('key 2', 'another value'), ('key 3', 'some other value')]

The ``has_key`` method allows us to ask if a dictionary has an item with this key::

    >>> print myDict.has_key('key 1')
    True
    >>> print myDict.has_key('key 4')
    False

Here's another way to write the same thing, by asking if the list of keys has a certain key::

    >>> print 'key 1' in myDict.keys()
    True
    >>> print 'key 4' in myDict.keys()
    False

Avoiding KeyErrors
------------------

We can use conditionals to avoid getting a ``KeyError`` for non-existing keys::

    if 'key 4' in myDict.keys():
        print myDict['key 4']
    else:
        print 'key not in dict'

Dictionaries also have a ``get`` method, which returns ``None`` if the key does not exist::

    >>> print myDict.get('key 1')
    another value
    >>> print myDict.get('key 4')
    None

Iterating through a dictionary
------------------------------

Depending on what is more useful to the problem at hand, we can iterate through a dictionary's keys retrieving their values::

    >>> for key in myDict.keys():
    >>>     print key, myDict[key]
    key 1 value
    key 2 another value
    key 3 some other value

...or we can iterate through key/value pairs directly::

    >>> for key, value in myDict.items():
    >>>     print key, value
    key 1 value
    key 2 another value
    key 3 some other value
