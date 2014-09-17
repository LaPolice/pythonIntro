============
Conditionals
============

Using ``if`` for selection between possible situations::

    if a < b:
        print "a is lower than b"

    if a > b:
        print "a is bigger than b"

Using ``else`` for acting after the opossite situation::

    if a < b:
        print "A"
    else:
        print "B"

Using ``elif`` for acting in intermediate options::

    if a > b:
        print "A"
    elif a == 12:
        print "B"
    else:
        print "C"

    if a > b:
        print "A"
    elif a == 10:
        print "B 10"
    elif a == 11:
        print "B 11"
    elif a == 12:
        print "B 12"
    elif a == 13:
        print "B 13"
    else:
        print "C"
