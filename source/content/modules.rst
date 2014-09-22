Modules
=======

Python comes ‘with batteries included’ – if some commonly needed functionality is not available as part of the language, it is often available in a separate *module*.

Python comes with several modules with dedicated tools to deal with the operating system, to access an FTP server, to read and write XML, to create random numbers etc.

Besides the *standard* modules or libraries which come pre-installed with Python, there are also many specialized *external* libraries developed by users and made available in the web. This is the case with RoboFab and vanilla, for example, which we’ll see later during the workshop. These external modules need to be downloaded and installed on the system to become accessible.

Importing modules
-----------------

Before use a module, you need to *import* it into your script. This is done with the ``import`` command.

For example, here we are importing the ``os`` module form the standard library::

    import os

After this line, the contents of the ``os`` module becomes available to our script. For more about importing modules, have a look at the :doc:`notes about modules <modules>` in this documentation.

Standard modules
----------------

There are many standard modules. We'll give a brief of overview of some of these modules below. For reference, here is a `full list of standard Python modules`_.

.. _full list of standard Python modules : https://docs.python.org/2/library/

os
^^

The ``os`` module contains many useful functions for dealing with the file system. Here are a few examples:

Lists all the content of a folder::

    print os.listdir(path)

Recursively list all the contents of a folder::

    path = '/my_path/'
    print os.walk(path)

Returns the path where the script is running (*current working directory*)::

    print os.getcwd()

Create a new folder::

    new_folder = u"/Users/yourusername/Desktop/test"
    os.mkdir(new_folder)

Rename a folder or file::

    new_folder2 = u"/Users/yourusername/Desktop/test2"
    os.rename(new_folder, new_folder2)

Remove a folder::

    os.rmdir(new_folder2)

Remove a file::

    os.remove(path)

os.path
^^^^^^^

The `os.path` module have functions for manipulating file and folder names::

    import os.path
    file = '/my-file.png'
    path = '/my-folder/'

Check if a file or folder exists::

    print os.path.exists(file)
    print os.path.exists(path)

Returns only the file name, without the folder path where it's contained::

    print os.path.basename(file)

Returns the containing folder name::

    print os.path.dirname(file)

Splits the whole file path as folder and file name::

    print os.path.split(file)

Splits the file name as file name and extension::

    print os.path.splitext(file)

For more information, visit the `os.path <http://docs.python.org/2/library/os.path.html>`_ documentation.

string
^^^^^^

The ``string`` module offers common string manipulation tools.

...

random
^^^^^^

Import ``random`` and ``randint`` functions from the ``random`` module::

    from random import random, randint

The ``random()`` function returns a pseudo-random floating point number between ``0.0`` and ``1.0``::

    print "a random number between 0.0 and 1.0:"
    print random()

The ``randint()`` function, on the other hand, returns a pseudo-random number between two integers::

    print "a random number between 0 and 4:"
    print randint(0, 4)
    print "a random number between 10 and 20:"
    print randint(10, 20)

Random numbers can be used for randomly selecting between two or more options::

    print "choose randomly between A and B, 6 times:"
    for i in range(6):
        if random() > 0.5:
            print "A"
        else:
            print "B"

math
^^^^

The ``math`` module has lots of, of course, math operations and constants which are needed for advanced calculations as trigonometry::

Import all functions contained in the ``math`` module::

    from math import *

    print pow(9, 2)
    print sqrt(81)
    print floor(4.80)
    print ceil(4.80)

plistlib
^^^^^^^^

...

itertools
^^^^^^^^^

...

doctest
^^^^^^^

...


distutils
^^^^^^^^^

...

ftp
^^^

...

subprocess
^^^^^^^^^^

...

External modules
----------------

Installing modules (manually)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Create a simple text file, containing the path to the root folder where the module lives.

.. note:: The easiest way to get the correct path is by dragging the folder from Finder into a code editor or Terminal -- so you’ll get the path without having to type it.

Save this file with the name of the module and the extension ``.pth`` in the ``site-packages`` folder for the desired Python(s). For example::

    /Library/Python/2.7/site-packages/hTools2.pth

And that’s it.

This method creates a **reference** to the folder in which the module lives.

Installing modules (with a package manager)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

...


markdown
^^^^^^^^

- `markdown.py <https://pypi.python.org/pypi/Markdown>`_

...
