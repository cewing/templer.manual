=============
Using Templer
=============

The fastest way to get started with templer is to install it using 
`virtualenv <http://virtualenv.org/>`_. ::

    $ easy_install virtualenv # if you have not already installed this
    $ virtualenv --distribute templerenv
    $ source templerenv/bin/activate
    (templerenv)$ easy_install templer.core

This installs the core of the templer system. See the list of :doc:`available
packages <packages>` to determine which templer package best suits your needs.

You will now find ``templer`` and ``paster`` commands in your virtualenv. Use 
the templer command to create a basic Python namespace package. ::

    (templerenv)$ templer basic_namespace my.package

After answering a few questions, you will have your new package.
