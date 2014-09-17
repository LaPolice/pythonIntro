============
Environments
============

Where can we run Python code?
-----------------------------

Python can be used in many different environments. Some applications already come with an embedded Python interpreter, so you can use Python as a scripting language to automate things that you would otherwise have to make by hand.

Most font editors support scripting with Python: `RoboFont`_, `FontLab`_, `Glyphs`_, `FontForge`_.

.. _RoboFont : http://robofont.com/
.. _FontLab : http://fontlab.com/python-scripting/
.. _Glyphs : http://glyphsapp.com/
.. _FontForge : http://www.fontforge.org/python.html

Python is also supported by other kinds of applications, such as `Blender`_ and `Rhino`_ (3D modelling), `SublimeText`_ (code editor), `DropBox`_ (file hosting) and many others.

.. _Blender : http://wiki.blender.org/index.php/Doc:2.6/Manual/Extensions/Python
.. _Rhino : http://wiki.mcneel.com/developer/python
.. _SublimeText : http://www.sublimetext.com/
.. _DropBox : https://www.dropbox.com/

Python can also by used directly in the command-line, to run scripts or in interactive mode. (more about this `below <#python-in-terminal>`_)

Python-powered applications
---------------------------

DrawBot
^^^^^^^

DrawBot is an enviroment to create 2D graphics with Python code. It was originally developed by Just van Rossum to teach programming to design students at the `KABK`_.

.. _KABK : http://kabk.nl/

The current version of DrawBot is developed in collaboration with Frederik Berlaen, who is also the author of RoboFont (see below). To learn more about DrawBot, have a look at the `DrawBot documentation`_. For the brave, DrawBot’s source-code is `available on Github`_.

.. _DrawBot documentation : http://drawbot.com/
.. _available on Github : https://github.com/typemytype/drawbot

DrawBot is available only on MacOSX. It also exists as a `RoboFont extension`_ and as an `experimental web-based app`_ (TinyPy), both also made by Frederik.

.. _RoboFont extension : https://github.com/typemytype/drawBotRoboFontExtension
.. _experimental web-based app : http://tinypy.appspot.com/

Similar applications have been developed for other enviroments, such as `ShoeBot`_ for Linux and `Spryte`_ for Windows. But the syntax used by these applications can be slightly different, breaking compatibility with DrawBot scripts.

.. _ShoeBot : http://shoebot.net
.. _Spryte : http://spryte.hxgraphics.com/

RoboFont
^^^^^^^^

RoboFont itself is written in Python, and has a Python scripting environment. Have a look at the `RoboFont documentation`_ to learn more.

.. _RoboFont documentation : http://robofont.com/

Many aspects of the program's interface and behaviour can be customized with code. Documentation about the RoboFont API can be found `here`_.

.. _here : http://doc.robofont.com/api/

RoboFont implements the `RoboFab object model`_, a standardized way of working with fonts. It also adds a couple of `extra methods and attributes`_ to some objects.

.. _RoboFab object model : http://robofab.com/objects/model.html
.. _extra methods and attributes : http://doc.robofont.com/api/robofab-extras/

RoboFont also makes it very easy to `create`_ and `install`_ Extensions. There are many open-source `RoboFont extensions`_ available on github.

..  _RoboFont extensions : http://doc.robofont.com/extensions/
.. _create : http://doc.robofont.com/extensions/building-extensions/
.. _install : http://doc.robofont.com/extensions/installing-extensions/

FontLab
^^^^^^^

In FontLab, Python scripts can be written and run with help of the ‘Edit Macro’ window.

FontLab itself is not written in Python, but it has a `Python API`_ which gives access to most of its functions. However, this API is not very well documented, and is not very *pythonic*.

.. _Python API : http://www.e-font.de/flpydoc/

As an alternative, FontLab can also be scripted with help of the `RoboFab library`_, which first needs to be downloaded and installed. RoboFab offers a more natural API, and also makes it possible to write scripts that work outside of FontLab (NoneLab).

.. _RoboFab library : http://robofab.org/

Glyphs
^^^^^^

The popular font editor Glyphs also has a Python scripting interface. As with FontLab, there are two ways to work with Python in Glyphs: by using `its own object model and scripting API`_, or by using RoboFab, which `needs to be installed first`_.

.. _its own object model and scripting API : http://docu.glyphsapp.com/
.. _needs to be installed first : http://glyphsapp.com/resources/scripting

Python in Terminal
------------------

Python can be used directly in a console or command-line interface, outside of an existing application.

On MacOSX, this can be done via the Terminal, which can be found in your *Applications / Utilities* folder.

After launching Terminal, you will see something like this::

    Last login: Wed Jul 23 05:01:17 on ttys000
    username:~ username$ 

This is your default command-line prompt, with your own username.

There are two ways to use Python on the console: interactive mode, or running an existing script.

Interactive mode
^^^^^^^^^^^^^^^^

To enter interactive mode in Terminal, simply type ``python`` in the command-line::

    username:~ username$ python

You will probably see something like this::

    Python 2.7.5 (default, Aug 25 2013, 00:04:04) 
    [GCC 4.2.1 Compatible Apple LLVM 5.0 (clang-500.0.68)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>> 

This command gives us some information about the current Python installation, and returns an interactive Python prompt.

We can type Python code in this prompt, and it gets executed as it goes.

Let's start with a simple *hello world*::

    >>> "hello world"
    'hello world'

The same goes for mathematical expressions, in fact for any Python expression::

    >>> 1 + 1
    2

.. Note::

    In interactive mode, it is not necessary to use the ``print`` statement -- expressions are executed and return the result.

It is also possible to write multi-line code in the interactive mode. Notice how the prompt changes to indicate that it is waiting for input::

    >>> for i in range(7):
    ...     print i,
    ... 
    0 1 2 3 4 5 6

Running existing scripts
^^^^^^^^^^^^^^^^^^^^^^^^

The interactive mode is useful for writing quick tests and short scripts, but it is not really suitable for working with larger pieces of code. When that is the case, it is better to write scripts as separate ``.py`` files, and use Terminal only to run them.

Let's suppose we have the following Python script, which prints "hello world" as output::

    print 'hello world'

This script is stored as a separate ``hello.py`` file.

To call this file from Terminal, we simply call the command ``python``, followed by the path to the script file. A tip: instead of typing out the full path, you can simply drag the file from Finder to the Terminal::

    username:~ username$ python /Users/username/Desktop/hello.py

The output will be, as expected::

    hello world

Python in SublimeText
---------------------

It is also possible to run Python cript from inside SublimeText (our favorite code editor). To run a script, use the key combination ``Cmd+B`` — this will start your file in the console at the bottom of the editor.
