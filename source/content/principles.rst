Programming principles
======================

Programming is not an exact science like maths. It does have a ‘hard’ logical side, but the process of designing and developing software has many subjective aspects which bring it closer to a craft. In this sense, it is not very different from type design or font production.

Because of this, there are no absolute rules about how programs should be designed and developed. *If it works, it works* – and in many cases this is all you need.

As designers who write code, we are usually satisfied if a program works as originally intended – and we are happy to go back to work on the design aspects of our work.

But for ‘real’ programmers, it is not enough if a program works; it needs to work fast, it needs to be easy to maintain and to improve, it needs to be *beautiful*. Programs are text, and there is a literary dimension to writing code. 

In beautiful code, the program logic is expressed in a clear, concise form. It is easy to understand what the program is doing, the code is pleasant to read.

Programming wisdom
------------------

So, while there are no absolute laws, there are well-known good programming practices, distilled over decades of work by experienced professional programmers. It would be foolish not to learn about them.

These best practices and ‘pearls of programming wisdom’ are often expressed as short sentences and acronyms. Let’s have a look at some of them:

- **Don’t Repeat Yourself.** (Also known as the DRY principle.)

- **Keep It Simple Stupid.** (Also known as the KISS principle.)

- **Do the simplest thing that could possibly work.**

- **If it ain't broke, don’t fix it.**

- **You ain't gonna need it.**

- **Worse is Better.** (Simplicity > Correctness > Consistency > Completeness)

General principles
------------------

Abstraction
^^^^^^^^^^^

    Each significant piece of functionality in a program should be implemented in just one place in the source code. Where similar functions are carried out by distinct pieces of code, it is generally beneficial to combine them into one by abstracting out the varying parts.

-- Benjamin C. Pierce, in Types and Programming Languages (2002)

Modularization
^^^^^^^^^^^^^^

Divide a program into reusable pieces: functions, modules, libraries.

Technical debt
^^^^^^^^^^^^^^

A term to describe to what extent a piece of code is up-to-date with latest technologies, practices and standards. The bigger the ‘technical debt’ of a software project, the more difficult it is to maintain (keep it running) and extend (change or add functionality) it.

Links
-----

- `Abstraction principle <https://en.wikipedia.org/wiki/Abstraction_principle_(computer_programming)>`_
- `Worse is Better <https://en.wikipedia.org/wiki/Worse_is_better)>`_
