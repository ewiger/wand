Wand
====

Wand is a :mod:`ctypes`-based simple `MagickWand API`_ binding for Python. ::

    from wand.image import Image
    from wand.display import display

    with Image(filename='mona-lisa.png') as img:
        print img.size
        for r in 1, 2, 3:
            with img.clone() as i:
                i.resize(int(i.width * r * 0.25), int(i.height * r * 0.25))
                i.rotate(90 * r)
                i.save(filename='mona-lisa-{0}.png'.format(r))
                display(i)

You can install it from PyPI_ (and it requires MagickWand library):

.. sourcecode:: bash

   $ apt-get install libmagickwand-dev
   $ easy_install Wand

.. _MagickWand API: http://www.imagemagick.org/script/magick-wand.php
.. _PyPI: http://pypi.python.org/pypi/Wand


Why just another binding?
-------------------------

There are already many MagickWand API bindings for Python, however they
are lacking something we need:

- Pythonic and modern interfaces
- Good documentation
- Binding through :mod:`ctypes` (not C API) --- we are ready to go PyPy!
- Installation using :program:`pip` or :program:`easy_install`


Requirements
------------

- Python 2.6 or higher

  - CPython 2.6 or higher
  - PyPy 1.5 or higher

- MagickWand library

  - ``libmagickwand-dev`` for APT on Debian/Ubuntu
  - ``imagemagick`` for MacPorts/Homebrew on Mac
  - ``ImageMagick-devel`` for Yum on CentOS


User's guide
------------

.. toctree::
   :maxdepth: 2

   guide/install
   guide/read
   guide/write
   guide/resizecrop
   guide/resource
   roadmap
   changes


References
----------

.. toctree::
   :maxdepth: 2

   wand


Open source
-----------

Wand is an open source software written by `Hong Minhee`_ (initially written
for StyleShare_).  See also the complete list of contributors_ as well.
The source code is distributed under `MIT license`_ and you can find it at
`GitHub repository`_. Check out now:

.. sourcecode:: bash

   $ git clone git://github.com/dahlia/wand.git

If you find a bug, please notify to `our issue tracker`_. Pull requests
are always welcome!

Check out :doc:`changes` also.

.. image:: https://secure.travis-ci.org/dahlia/wand.png?branch=master
   :alt: Build Status
   :target: http://travis-ci.org/dahlia/wand

.. _Hong Minhee: http://dahlia.kr/
.. _StyleShare: https://stylesha.re/
.. _contributors: https://github.com/dahlia/wand/graphs/contributors
.. _MIT license: http://minhee.mit-license.org/
.. _GitHub repository: https://github.com/dahlia/wand
.. _our issue tracker: https://github.com/dahlia/wand/issues


Indices and tables
------------------

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

