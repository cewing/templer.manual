.. Templer System Manual documentation master file, created by
   sphinx-quickstart on Fri Jan 20 21:11:47 2012.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

=====================
Templer System Manual
=====================

.. sidebar:: Using ZopeSkel

    Templer is derived from an earlier system -- ZopeSkel_ -- which was designed
    specifically for the needs of the Zope_ and Plone_ communities.

    If you have worked with ZopeSkel_ in the past, you may continue to do so
    in the same way you always have. You will find that the selection of
    templates is a bit different, but the system works exactly as before.

    For more information on using ZopeSkel, see :ref:`zopeskel` in this 
    manual.

This manual covers the templer code generation system. Templer is a
general-purpose system for generating code skeletons for any Python_ project
from pre-defined templates. Through an interactive interface, the user
provides information which is used to generate a skeleton of files and folders
that fits their individual needs.

To get started quickly, see :doc:`Using Templer <quickstart>`.

Templer consists of a number of packages, each of which provides a set of
templates. Install the package that you need for the templates you want.

* Install :ref:`templer.core <templer.core>` to build basic Python_
  namespace and nested namespace packages
* Install :ref:`templer.buildout <templer.buildout>` to build basic
  buildouts and recipes to extend the zc.buildout_ system
* Install :ref:`templer.zope <templer.zope>` to build basic
  namespace and nested namespace packages for Zope_
* Install :ref:`templer.plone <templer.plone>` to build software
  projects for the Plone_ Content Management System
* Install :ref:`templer.plone[localcommands] <templer.plone.installlocalcommands>`
  to get access to local commands for adding features to your Plone_ software projects

If you are interested in extending the templer system with your own templates,
read the developers manual.

.. _ZopeSkel: http://pypi.python.org/pypi/ZopeSkel
.. _Zope: http://www.zope.org/
.. _Plone: http://www.plone.org/
.. _Python: http://www.python.org
.. _zc.buildout: http://www.buildout.org/

Contents
========

.. toctree::
   :maxdepth: 2
   
   quickstart
   packages
   developers/index
   information/index
   applications/index

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
