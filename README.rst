============================================
uvent: A gevent core implemented using libuv
============================================

uvent is a `gevent <http://gevent.org>`_ core implementation using the `libuv <https://github.com/joyent/libuv>`_ library.

uvent uses `pyuv <https://github.com/saghul/pyuv>`_, a Python interface for libuv. libuv is a high performance asynchronous
networking library used as the platform layer for NodeJS.

libuv provides the same core functionality as libev, with some really nice
additions:

- High performance IO on Windows (not select)
- Asyncronous file operations
- Builtin thread pool
- Asynchronous getaddrinfo
- Nicer to use API
- Etc.

Source code for uvent is on `GitHub <http://github.com/saghul/uvent>`_.


Motivation
==========

This is an experimental project to test the feasibility of using libuv as a
core for gevent.

Main functionality is working but not all tests are passing and there are some
implementation caveats mostly due to the tight integration between gevent and
libev. Implementation notes can be found in the NOTES.rst file.


Installation
============

uvent requires pyuv >= 0.9.0, so right now the only way to get it is
by installing them straight from GitHub:

::

    pip install git+https://github.com/saghul/pyuv.git


**Note:** uvent only works with gevent >= 1.0, earlier versions are not supported.


Using it
========

In order to use uvent add the following lines at the beginning
of your project, before importing anything from Gevent:

::

    import uvent
    uvent.install()


Author
======

Saúl Ibarra Corretgé <saghul@gmail.com>


License
=======

uvent uses the MIT license, check LICENSE file.

