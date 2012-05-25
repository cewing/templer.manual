======================
The History of Templer
======================

Templer is a system that grew out of the refactoring and improvement of the
ZopeSkel_ code generation tool, used by the Plone_ and Zope_ communities for
years. However, unlike its predecessor templer is not limited specifically to
generating packages for Plone_ or Zope_. With templer you can get a quick
start building python-based projects for a number of systems and frameworks.

Templer and ZopeSkel
====================

In the beginning, there was ZopeSkel. First created in 2006, it was used to
install and run commands to create new Zope_ and Plone_ packages. And it
was good. But it was also monolithic and inflexible. 

And so, at the `No Fun BBQ Sprint`_ in 2009, the decision was made to
:doc:`split the package up <splitting>` in order to make it easier to work
with only the parts you wanted. At the same time, the sprinters decided that
keeping consistency in usage was a very important goal, and so the ZopeSkel_
package has been preserved. Information about the rationale behind this decision
may be read in :doc:`splitting`.

Starting with version 3.0, ZopeSkel_ is simply a thin wrapper around the
functionality and templates provided by the templer system. Installing
ZopeSkel_ installs the templer packages needed to reproduce the ZopeSkel_
experience. All the templates and supporting code are in templer packages and
none remains in the ZopeSkel_ package.

.. _ZopeSkel: http://pypi.python.org/pypi/ZopeSkel
.. _Zope: http://www.zope.org/
.. _Plone: http://www.plone.org/
.. _Python: http://www.python.org
.. _zc.buildout: http://www.buildout.org/
.. _No Fun BBQ Sprint: http://trizpug.org/Members/cbc/zopeskel-bbq-sprint