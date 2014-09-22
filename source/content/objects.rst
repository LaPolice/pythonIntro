Objects
=======

Object-oriented programming is one among many existing programming paradigms. 

History
-------

- Xerox PARC, Alan Kay
- SmallTalk programming language, Dan Ingalls

Concepts
--------

- model programs after real-world objects
- objects as containers for data and methods
- inheritance and object composition

Example
-------

::

    class Rect:

        width = 100
        height = 100

        def __init__(self):
            pass

        def draw(self, (x, y)):
            rect(x, y, self.width, self.height)

    R = Rect()
    R.draw(200, 200)
