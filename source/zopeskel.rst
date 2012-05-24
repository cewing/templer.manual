==============
Using ZopeSkel
==============

Installing ZopeSkel
===================

ZopeSkel can be installed in one of two ways: with `buildout
<http://www.buildout.org/>`_ or with `virtualenv <http://virtualenv.org/>`_.

.. note ::

    Despite existing documentation to the contrary, it is not recommended to
    install ZopeSkel in your system python.

Buildout installation
---------------------

Add to your ``buildout.cfg``::

    parts =
       ...
       zopeskel

    [zopeskel]
    # installs paster and Zopeskel
    recipe = zc.recipe.egg
    eggs =
       PasteScript
       ZopeSkel

After re-running buildout, you will have ``zopeskel`` and ``paster`` commands in
the ``bin`` directory of your buildout.

Virtualenv installation
-----------------------

First, install virtualenv into your system::

    easy_install virtualenv

Next, create a virtual environment with the new ``virtualenv`` command::

    virtualenv --distribute zopeskelenv

Once virtualenv has finished creating your new virtual environment, you can
install zopeskel to your new virtual environment by::

    zopeskelenv/bin/easy_install zopeskel

Once this is complete, you will have ``zopeskel`` and ``paster`` commands in the
``bin`` directory of your virtualenv.


Basic Usage
-----------


You can use zopeskel to add new projects to your buildout ``src/`` folder.



