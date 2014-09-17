=================
Importing modules
=================

Import a module named ``my_module``::

    import my_module

Force re-import a module::

    reload(my_module)

Import all functions in a module::

    from my_module import *

Import only one function `my_func` from module::

    from my_module import my_func

Import a function `my_func` with another name::

    from my_module import my_func as my_func_2
