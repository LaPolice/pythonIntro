Functions
=========

Now that we've learned about Python's built-in functions, let's see how we can write our own functions.

What is a function?
-------------------

Functions are *modular pieces of logic*. They help to make code less redundant, more organized, more flexible and easier to maintain. 

Typically, a function is defined once, and used several times in a program. A function can also live in one place (for example in an external module) and be used somewhere else.

Functions are a Good Thing. They help us to follow DRY *(Don't Repeat Yourself)* and KISS *(Keep It Simple Stupid)* principles. They help us to think more clearly and work more efficiently.

Some recommendations
^^^^^^^^^^^^^^^^^^^^

**A function should not try to do many different things at once.** Ideally, a function should do one thing really well, and nothing else (see "Single responsability principle"). This makes it easier to reuse this function in another context, to solve a similar problem.

**Name your functions wisely.** Think of functions as the 'verbs' in your code. Choose clear descriptive names.

Function basics
---------------

To use a function we need to do two things:

1. define the function
2. call the function

Defining a function
^^^^^^^^^^^^^^^^^^^

A function is defined with the ``def`` statement. A simple function definition looks like this::

    def say_hi():
        print "Hi!"

In the first line we also have the name of the function (``say_hi``) and a pair of parentheses (which in this case is empty).

After that we have the *body* of the function, which contains the code that gets executed every time the function is called.

The body of a function cannot be completely empty. If we wish to create a function that does nothing at all, we need to use the ``pass`` statement in its body::

    def do_nothing():
        pass

Calling a function
^^^^^^^^^^^^^^^^^^

Once a function has been defined, we can call it anywhere in our program, as many times as we want.

To call a function, simply write its name followed by a pair of parentheses::

    >>> say_hi()
    Hi!

If we wish to call this function several times, we can simply put it in a loop::

    >>> for i in range(4):
    ...     say_hi()
    Hi!
    Hi!
    Hi!
    Hi!

And at anytime, we can edit our function definition, so it outputs a different message::

    >>> def say_hi():
    ...     print "hello there"
    ... 
    >>> for i in range(4):
    ...     say_hi()
    hello there
    hello there
    hello there
    hello there

Returning values
----------------

The functions we've seen above *do* something: they print a message. But they don't *return* any value.

Functions that only do something
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Let's have a look at another example::

    >>> m = say_hi()
    hello!
    >>> print m
    None

Here we are calling the same function again, but we are assigning the value it returns to a variable. When we call the function, it prints the message as previously. When we print the value stored in the variable, we get ``None`` -- because the function didn't return a value.

Functions that return one or more things
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Now let's write another function that doesn't do anything, but which returns a value. Instead of printing a string, our function will ``return`` it::

    def make_hi():
        return 'Hi!'

When we call this function, no message gets printed. But it returns a value, which we can store in a variable to use later::

    >>> m = say_hi()
    >>> print m
    Hi!

Of course, our functions can also do both things at once: do something *and* return a value::

    >>> def make_spam():
    ...     # do something
    ...     print 'making spam...'
    ...     # return a value
    ...     return 'hmmm tasty spam!'
    ... 
    >>> mySpam = make_spam()
    making spam...
    >>> print mySpam
    hmmm tasty spam!

A function can also return more than one value (a tuple of values)::

    >>> def make_color():
    ...     r = 1.0
    ...     g = 0.5
    ...     b = 0.0
    ...     return r, g, b
    ...             
    >>> c = make_color()
    >>> print c
    (1.0, 0.5, 0.0)
    >>> print type(c)
    <type 'tuple'>

Function arguments
------------------

So far all our simple functions have been doing their work without any input from the "outside world" -- these functions take no arguments or parameters.

But we can write functions that take one or more arguments as input, and use these to do something else.

Let's build on a previous example. We want to make a function that says "Hi" to someone, so we need to find a way to inform this person's name to the function. We do this by declaring a variable name between the parentheses in the function definition::

    def say_hello(name):
        print "hello", name

Now this function can only do its work if we give it a name. It requires an argument. If we don't pass any, it will throw an error::

    >>> say_hello()
    Traceback (most recent call last):
      File "<untitled>", line 4, in <module>
    TypeError: say_hello() takes exactly 1 argument (0 given)

The error message is clear about the problem: we haven't given any argument to the function. Let's try again::

    >>> say_hello('Waldemar')
    hello Waldemar
    >>> say_hello('Ahmed')
    hello Ahmed
    >>> say_hello('Leoni')
    hello Leoni

Functions can take more than one argument, of course. Here's an example of a function that takes three arguments::

    >>> def say_hello(first_name, last_name, title):
    ...     print "hello", title, first_name, last_name
    ... 
    >>> say_hello('John', 'Smith', 'Mr.')
    hello Mr. John Smith
    >>> say_hello('Marie', 'Curie', 'Mrs.')
    hello Mrs. Marie Curie

Function scope
--------------

Everything that goes into a function's body is not accessible to the 'outside world' -- the part of the program that is outside the function definition::

    # global scope
    # ...

    def my_func():
        # function scope
        # ...

    # global scope
    # ...

.. warning:: Beginners often struggle to understand this topic, so we recommend you to pay extra attention.

So, function scope is isolated from the global scope. Let's illustrate this point with some code::

    >>> def my_func():
    ...     # function scope
    ...     a = 20
    ...     print a
    ... 
    >>> # program scope
    >>> my_func()
    20
    >>> print a
    Traceback (most recent call last):
      File "<untitled>", line 8, in <module>
    NameError: name 'a' is not defined

The variable ``a`` in this case is a *local* variable: it has been declared inside the function, and it is not available to the global scope outside the function.

Variables defined in the global scope, on the other hand, are available to a function::

    >>> def my_func():
    ...     # function scope
    ...     print b
    ...         
    >>> # program scope
    >>> b = 10
    >>> my_func()
    10

But use this with great care. If a function requires one or more values to do its work, it is recommended to pass those values explicitly to the function as arguments. This practice makes code more modular, easier to read and to maintain::

    >>> b = 10
    >>> def my_func(b):
    ...     print b
    ...         
    >>> my_func(b)
    10

What is important to understand here is that the global variable ``b`` and the local variable ``b`` are now isolated from each other. If we change ``b`` inside the function, the global variable will remain unchanged::

    >>> b = 10
    >>> def my_func(b):
    ...     b += 10 
    ...     # local variable
    ...     print b
    ...         
    >>> my_func(b)
    20
    >>> # global variable
    >>> print b
    10

To avoid confusion, it is recommended to name global and local variables differently::

    >>> def quack(ducks):
    ...     print 'quack ' * ducks
    ... 
    >>> n = 5 # amount of ducks
    >>> quack(n)
    quack quack quack quack quack 

Keyword arguments
-----------------

...

Compositions with functions
---------------------------

A function calling another function::

    def another_func(x, y):
        return sum_numbers(x, y) # calling the function 'sum_numbers'

    print another_func(1, 2)

Docstrings
----------

Documentation for functions are a three quoted string after the definition. It's a very good practice to start from the very first day::

    def my_func():
        """
        This function prints the string 'Hi!'.
        Documenting your functions and commenting your code is really helpful.
        """
        print "Hi!"

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
