==============
Good practices
==============

A collection of tips and recommendations for writing Python code.

String methods
--------------

Use string methods instead of the ``string`` module.

String methods are always much faster and share the same API with unicode strings. 

Use ``''.startswith()`` and ``''.endswith()`` instead of string slicing to check for prefixes or suffixes: they are cleaner and less error prone. For example::

	Yes: if foo.startswith('bar'):
	No:  if foo[:3] == 'bar':

Checking object types
---------------------

Object type comparisons should always use ``isinstance()`` instead of comparing types directly::

	Yes: if isinstance(obj, int):
	No:  if type(obj) is type(1):
