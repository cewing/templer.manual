================
Templer Packages
================

The Templer system is made up of a number of small, distinct packages. These
packages may depend on other templer packages, so that they can include
functionality provided by those other packages. Each package is configured to
automatically include required dependencies, so simply installing the package
which provides your desired templates will automatically install any other 
templer packages it needs. 

Package Listing
===============

The packages in the templer system can be separated into three general
categories: `Core Functionality`_, `Template Packages`_ and `Local Commands`_.

.. _Core Functionality:

Core Functionality
------------------

templer.core
    This package installs the core of the Templer system. It provides the base
    template and command classes, an extended system of vars which provide
    inline help and validation of template questions, and the core of the
    **structures** functionality.  
    
    This package provides the ``basic_namespace`` and ``nested_namespace`` 
    package templates.
    
    This package provides the ``egg_docs`` structure and structures for each
    of the supported license options.
    
    This package provides the ``templer`` script, the command-line tool through
    which users may generate skeleton packages.

templer.localcommands
    This packages provides the Templer local command and local template. Any
    package which provides local commands must depend on this package.
    
    This package provides the ``add`` paster local command.
    
    This package provides no templates.

.. _Template Packages:

Template Packages
-----------------

templer.buildout

    This package provides the ``basic_buildout`` and ``recipe`` templates.
    
    This package provides the ``bootstrap`` structure, used by any template
    which provides a buildout as part of its output.

templer.zope

    This package provides the ``zope2_basic`` and ``zope2_nested`` templates.
    Skeletons generated by these templates may be used to create add-ons for 
    Zope 2 projects. 

    Skeletons will include a buildout which will install a Zope 2 instance
    and include the generated package in that instance.

.. _templer.plone:

templer.plone

    This package provides the ``plone_basic``, ``plone_nested`` and 
    ``archetype`` templates. The skeletons generated by these templates are
    suitable for use with the Plone_ CMS. 

    Skeletons will include a buildout which will install a Zope 2 instance
    with Plone installed. The generated package will be included in the
    instance, and may available for activation in a Plone site. Skeletons will
    also include an operational test harness with one or more pre-written
    tests.

    This package provides the ``namespace_profile`` and
    ``nested_namespace_profile`` structures, which supply default GenericSetup
    profiles within a generated skeleton.

    The package may be installed with the ``[localcommands]`` extra, in which
    case it will depend on templer.plone.localcommands_ and will have 
    local commands available for generated skeletons.

.. _Local Commands:

Local Commands
--------------

.. _templer.plone.localcommands:

templer.plone.localcommands

    This package provides local commands for templates from the templer.plone_
    package. Provided commands include ``browserview``, ``browserlayer``,
    ``at_contenttype`` and ``at_schema_field``.

Package Dependencies
====================

This diagram shows the dependency tree for existing Templer packages.
Installing any Templer package will also install all of its dependencies.

::

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
