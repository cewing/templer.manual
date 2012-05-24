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

ZopeSkel is used to create empty projects for Zope. A number of templates are
included with ZopeSkel, please see documentation for more information.

The most basic template is plone_basic. plone_basic creates an empty python
egg with the option to add a GenericSetup profile to make an installable Plone
product.

for example::

 ./bin/zopeskel plone_basic namespace.newprod


This template asks you a series of questions and bases a new product from your
answers.

Unless you know what you are doing, select easy mode.

You can register a GenericSetup profile if you need it. If you do register a
profile, a profiles/default directory will be created, and initialize will be
added to __init__.py ::

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
    Creating directory ./namespace.newprod
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
