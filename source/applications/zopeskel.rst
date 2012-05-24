.. _zopeskel:

========
ZopeSkel
========

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

    $ easy_install virtualenv

Next, create a virtual environment with the new ``virtualenv`` command::

    $ virtualenv --distribute zopeskelenv

Once virtualenv has finished creating your new virtual environment, you can
install zopeskel to your new virtual environment by::

    $ zopeskelenv/bin/easy_install zopeskel

Once this is complete, you will have ``zopeskel`` and ``paster`` commands in the
``bin`` directory of your virtualenv.


Basic Usage
-----------

ZopeSkel is used to create empty projects for Zope_ and Plone_. A number of templates are
included with ZopeSkel:

* ``basic_namespace``
* ``nested_namespace``
* ``basic_buildout``
* ``recipe``
* ``zope2_basic`` 
* ``zope2_nested`` 
* ``plone_basic``
* ``plone_nested`` 
* ``archetype``

The most basic template for Plone_ is plone_basic, which creates an
empty Plone add-on. Optionally you may add a GenericSetup profile to make your
add-on appear in the list of available add-ons in Plone's *Site Setup*. In
this case a profiles/default directory will be created in your new add-on. 

For example::

    $ ./bin/zopeskel plone_basic my.example

This template asks you a series of questions and creates a new add-on
:term:`package` from your answers. When prompted to choose a mode, unless you
know what you are doing, select easy mode (it is the default). You will see
output like the following::

    plone_basic: A package for Plone add-ons

    This template creates a package for a basic Plone add-on project with
    a single namespace (like Products.PloneFormGen).

    To create a Plone project with a name like 'collective.geo.bundle'
    (2 dots, a 'nested namespace'), use the 'plone_nested' template.

    This template supports local commands.  These commands allow you to
    add Plone features to your new package.

    If you are trying to create a Plone *site* then the best place to
    start is with one of the Plone installers.  If you want to build
    your own Plone buildout, use one of the plone'N'_buildout templates


    If at any point, you need additional help for a question, you can enter
    '?' and press RETURN.

    Expert Mode? (What question mode would you like? (easy/expert/all)?) ['easy']: easy

    Version (Version number for project) ['1.0']: 1.0
    Description (One-line description of the project) ['']: This is an example product built with ZopeSkel
    Register Profile (Should this package register a GS Profile) [False]: True
    Creating directory ./my.example
    Replace 1079 bytes with 1273 bytes (1/43 lines changed; 5 lines added)
    Replace 42 bytes with 119 bytes (1/1 lines changed; 4 lines added)
    ------------------------------------------------------------------------------
    The project you just created has local commands. These can be used from within
    the product.

    usage: paster COMMAND

    Commands:
      add  Allows the addition of further templates to an existing package

    For more information: paster help COMMAND
    ------------------------------------------------------------------------------

    **************************************************************************
    **  Your new package supports local commands.  To access them, change
    **  directories into the 'src' directory inside your new package.
    **  From there, you will be able to run the command `paster add
    **  --list` to see the local commands available for this package.
    **************************************************************************


Once complete you will have a brand new Plone package waiting for customization!

Local Commands
--------------

A :term:`local command` uses templates to allow you to add features to your
newly created add-on. To run a local command, you must first change directory
to inside your add-on::

    $ cd my.example/src

From here, you can use the ``paster`` command to show you which templates are
available to use::

    $ ../../bin/paster add --list
    Available templates:
        browserlayer:  A Plone browserlayer
        browserview:   A browser view skeleton

To run a specific local command, you provide the name of the template::

    $ ../../bin/paster add browserview
    Enter view_name (Browser view name) ['Example']: Example

When this command completes, you will find a new browser module, with the 
files required to add a browser view to your add-on::

    $ ls -1 my/example/browser/
    __init__.py
    configure.zcml
    exampleview.pt
    exampleview.py

.. _Zope: http://www.zope.org/
.. _Plone: http://www.plone.org/

