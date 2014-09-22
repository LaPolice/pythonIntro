Conditionals
============

Sometimes, when writing a program, we need to do different things depending on a given situation or value. We need to be able to split the *control flow* of the program into two or more branches: "if this happens, go that way; otherwise, go that other way; if none of the above, go straight ahead".

Let's see how we can do this in Python.

The 'if' statement
------------------

The ``if`` statement allows us to run a certain piece of code only if a certain condition is met.

Here we are checking if the value of a variable is ``True`` or ``False``, and only in the first case printing something::

    hello = True
    if hello is True:
        print "hello world"

We can ask any other 'question' that returns a boolean value as an answer: a comparison, a membership test, a function etc.

Here we are using a conditional to make sure that the calculation is performed only if the divisor is greater than zero::

    a = 17
    b = 3
    if b > 0:
        print a / b

The 'if / else' statement
-------------------------

If we want to do something else when a condition is not met, when can use the ``else`` statement with another block of code::

    hello = True
    if hello:
        print "hello world"
    else:
        print "goodbye world"

The 'if / elif / else' statement
--------------------------------

Finally, if we want to handle more than just two conditions, we can use the ``elif`` statement between ``if`` and ``else``::

    daytime = 0
    if daytime == 0:
        print "good morning world"
    elif daytime == 1:
        print "good afternoon world"
    elif daytime == 2:
        print "good evening world"
    else:
        print "good night world"

Nested conditionals
-------------------

Like loops and aritmetic expressions, conditionals can be nested and combined with other conditionals::

    hello = True
    newMember = True
    if hello:
        if newMember:
            print 'hello, welcome'
        else:
            print 'hello, welcome back'
    else:
        print 'goodbye'
