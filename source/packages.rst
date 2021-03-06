================
Templer Packages
================

The Templer system is made up of a number of small, distinct packages. Read
the list of packages below to discover which templates are provided in each.
Install the package which provides the functionality you need.

Package Listing
===============

.. _templer.core:

templer.core
    This package installs the core of the Templer system. It provides the base
    template and command classes, an extended system of vars which provide
    inline help and validation of template questions, and the core of the
    **structures** functionality.
    
    This package provides:
    
    * the ``basic_namespace`` and ``nested_namespace`` package templates
    * the ``egg_docs`` structure and structures for each of the supported 
      license options
    * the ``templer`` script, the command-line tool through which users may 
      generate skeleton packages

.. _templer.localcommands:

templer.localcommands
    This packages installs the Templer local command and local template. Any
    package which provides local commands **must** depend on this package.
    
    This package provides the ``add`` paster local command.

.. _templer.buildout:

templer.buildout
    The package installs functionality related to the zc.buildout_ system.
    
    The package provides:
    
    * the ``basic_buildout`` and ``recipe`` templates
    * the ``bootstrap`` structure, used by any template which provides a 
      buildout as part of its output

.. _templer.zope:

templer.zope
    This package installs functionality related to Zope_.
    
    This package provides:

    * the ``zope2_basic`` and ``zope2_nested`` templates

    Skeletons generated by these templates will include a buildout. The
    buildout will create a Zope 2 instance and include the generated package 
    in that instance.

.. _templer.plone:

templer.plone 
    This package installs functionality related to Plone_.

    This package provides:

    * the ``plone_basic``, ``plone_nested`` and ``archetype`` templates
    * the ``namespace_profile`` and ``nested_namespace_profile`` structures,
      which supply default GenericSetup profiles within a generated skeleton

    Skeletons generated by these templates will include a buildout. The
    buildout will create a Zope 2 instance with Plone installed. The generated
    package will be included in the instance, and may be available for
    activation in a Plone site. Skeletons will also include an operational
    test harness with one or more pre-written tests.

    .. _templer.plone.installlocalcommands:

    The package may be installed with the ``[localcommands]`` extra, in which
    case it will depend on templer.plone.localcommands_ and will have 
    :term:`local commands <local command>` available for generated skeletons.

.. _templer.plone.localcommands:

templer.plone.localcommands
    This package provides :term:`local commands <local command>` for templates
    from the templer.plone_ package. Provided commands include ``browserview``,
    ``browserlayer``, ``at_contenttype`` and ``at_schema_field``.

Package Dependencies
====================

This diagram shows the dependency tree for existing Templer packages.
Installing any Templer package will also install all of its dependencies.
The base system provided by ``templer.core`` depends on PasteScript_, 
PasteDeploy_ and Cheetah_.

::

             PasteScript
             PasteDeploy
               Cheetah
                  ^
                  |
            templer.core        templer.localcommands
                  ^                        ^
                  |                        |
          templer.buildout                 |
                  ^                        |
                  |                        |
            templer.zope      templer.plone.localcommands
                  ^              ^
                  |              |
            templer.plone [localcommands]


.. _Plone: http://plone.org/
.. _ZopeSkel: http://pypi.python.org/pypi/ZopeSkel
.. _Zope: http://www.zope.org/
.. _Python: http://www.python.org
.. _zc.buildout: http://www.buildout.org/
.. _PasteScript: http://pythonpaste.org/script/
.. _PasteDeploy: http://pythonpaste.org/deploy/
.. _Cheetah: http://www.cheetahtemplate.org/
