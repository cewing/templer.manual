.. Templer System Manual documentation master file, created by
   sphinx-quickstart on Fri Jan 20 21:11:47 2012.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Templer/ZopeSkel System Manual
==============================

This manual covers the templer code generation system. Templer is a
refactoring and improvement of the ZopeSkel_ code generation tool, used by the
Plone_ and Zope_ communities for years. However, unlike its predecessor
templer is not limited specifically to generating packages for Plone_ or
Zope_. With templer you can get a quick start building python-based projects
for a number of systems and frameworks.

Everyone--perhaps especially those who have used ZopeSkel_ in the past--should
take a look at the introduction pages. The templer system consists of a number
of inter-related packages, and you'll want to learn what is offered, and what
you'll need to do to get started.

If you are new to using the templer system, you'll want to spend some time
familiarizing yourself with the users manual.

If you are interested in extending the templer system with your own templates,
read the developers manual.

Templer and ZopeSkel
--------------------

.. sidebar:: Using ZopeSkel

    If you have worked with ZopeSkel_ in the past, you may continue to do so
    in the same way you always have. You will find that the selection of
    templates is a bit different, but the system works exactly as before.
    
    For more information on using ZopeSkel, see the ZopeSkel page in the
    Templer Users Manual.

In the beginning, there was ZopeSkel. You could install it and run commands to
create new Zope_ and Plone_ packages. And it was good. But it was also
monolithic. And so, at the `No Fun BBQ Sprint`_ in 2009, the decision was made
to split the package up in order to make it easier to work with only the parts
you wanted. At the same time, the sprinters decided that keeping consistency
in usage was a very important goal, and so the ZopeSkel_ package has been
preserved. Information about the rationale behind this decision is available
in the History section of the Templer Developer's Manual.  

At this point, ZopeSkel_ is simply a thin wrapper around the functionality
and templates provided by the Templer system.  Installing ZopeSkel_ installs
the Templer packages needed to reproduce the ZopeSkel_ experience.  All the 
templates and supporting code are in Templer packages and none remains in the
ZopeSkel_ package.



Contents:

.. toctree::
   :maxdepth: 2



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

.. _ZopeSkel: http://pypi.python.org/pypi/ZopeSkel
.. _Plone: http://plone.org/
.. _Zope: http://www.zope.org/
.. _No Fun BBQ Sprint: http://trizpug.org/Members/cbc/zopeskel-bbq-sprint