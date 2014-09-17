=============
Boolean logic
=============

Two true comparisons::

    if a > 15 and b > 15:
        print "if a and b are bigger than 15"
    else:
        print "if a or b are not bigger than 15"

At least one of the two comparisons are true::

    if a > 15 or b > 15:
        print "a or b are bigger than 15"
    else:
        print "Neither a nor b are bigger than 15"

    print "result:", a > 15 or b > 15

Inverting a logic boolean declaration::

    print "not True:", not True
    print "not False:", not False
    print "not not False:", not not False
    print "not not not False:", not not not False

Grouping sub-expressions using parentheses::

    if (a > b and b == 13) or b == 25:
        print "..."

    if a > b and (b == 13 or b == 25):
        print "..."

Parentheses inside parentheses::

    # if a > b and (b == 13 or (b == 25 and a == 12)):
    #   ...

The ``break`` statement
-----------------------

Use ``break`` to skip a loop the first time the comparison occurs::

    a = 10
    for i in range(50):
        a *= 2
        if a > 50:
            print 'a reached bigger than 50, a = %s' % a
            break
        else:
            print 'a is lower than 50, a = %s' % a
    print 'the iteration was skipped'

Note: The ``break`` statement skipped the loop which is within the ``for`` statement, not the ``if`` comparison. 
