# pylibui

Python wrapper for [libui](https://github.com/andlabs/libui/).


## Some instructions

Clone pylibui:

    $ git clone https://github.com/joaoventura/pylibui

Clone libui inside pylibui:

    $ cd pylibui
    $ git clone https://github.com/andlabs/libui/

Make the libui shared library:

    $ cd libui
    $ make

The shared library will be in pylibui/libui/out. Now you can build pylibui:

    $ cd ..
    $ python3 setup.py build

The pylibui shared library will be in pylibui/build/libxxx. Cd into that
directory and try to import it:

    $ cd build/libxxx
    $ python3
    >>> import pylibui
    Traceback (most recent call last):
        File "<stdin>", line 1, in <module>
    ImportError: dlopen(...)
        Reason: image not found

You have to explicitely say where libui's shared library is:

    $ export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:../../libui/out/
    $ python3
    >>> import pylibui
    >>> pylibui.test()

You should see a window with a simple "Hello World" label.
