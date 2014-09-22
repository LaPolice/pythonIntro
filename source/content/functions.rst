Functions
=========

Built-in functions
------------------

The Python language has a number of `built-in functions`_ which are always available by default. 

.. _built-in functions: https://docs.python.org/2/library/functions.html

Of course, you can also create your own functions, as we'll see below.

Function basics
---------------

Function definition
^^^^^^^^^^^^^^^^^^^

Defining a function is easy, and looks like this::

    def my_func():
        print "Hi!"

Function docstring
^^^^^^^^^^^^^^^^^^

Documentation for functions are a three quoted string after the definition. It's a very good practice to start from the very first day::

    def my_func():
        """
        This function prints the string 'Hi!'.
        Documenting your functions and commenting your code is really helpful.
        """
        print "Hi!"    

A function that takes arguments
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Defining a function that gets two *arguments* or *parameters*::

    def my_second_func(x, y):
        print "Hi!", x, y

Calling a function
^^^^^^^^^^^^^^^^^^

To call a function, simply use its name followed by a pair of parentheses::

    my_func()

If a function takes parameters, you can pass them to the function in the parentheses::

    my_second_func(123, 456)

Function scope
^^^^^^^^^^^^^^

Functions have access to *global variables*. The variables defined inside a function are not accessibles outside that function::

    def sum_numbers(x, y):
        print global_var  # access to global variables
        result = x + y
        return result

    global_var = "Hi!"
    value = sum_numbers(1, 2)
    print value

The variable ``result`` was defined inside ``sum_numbers``, so it's not visible in the top level. That's the reason why that line will raise an error::

    print result

Functions calling functions
^^^^^^^^^^^^^^^^^^^^^^^^^^^

A function calling another function::

    def another_func(x, y):
        return sum_numbers(x, y) # calling the function 'sum_numbers'

    print another_func(1, 2)

The ``pass`` statement
^^^^^^^^^^^^^^^^^^^^^^

The ``pass`` statement becomes very handy when writing the structure of our code. It simple does nothing::

    def a_func(x, y):
        if x > y:
            print 'x is bigger than y'
        elif x == y:
            # we put this for further later development
            pass
        else:
            # we put this for further later development
            pass
