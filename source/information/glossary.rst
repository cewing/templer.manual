===================
Definition of Terms
===================

.. glossary::
   :sorted:
  
   var
       A question to be answered by the user when generating a skeleton from a
       template. A var provides a description of the information required, help
       text and validation rules to ensure accurate user input.

   local command
       A Paste_ class which provides additional functionality *within* a generated
       skeleton.
   
   package
       A `Python package <http://docs.python.org/tutorial/modules.html#packages>`_.
   
   skeleton
       The generated files and folders resulting from a user running a template.
   
   structure
       1) A Python class which controls the generation of a tree of files and
       folders.
   
       2) A unit of folders and files provided by the templer system for use in a
       template or templates.  Structures provide shared, static resources that
       may be used by any package in the templer system.
   
       Structures differ from templates in that they do not provide vars.
   
   template
       1) A Python class which controls the generation of a skeleton.  Templates
       contain a list of vars to gather input from a user. Templates are run by
       executing the ``templer`` command and providing the template name as an
       argument: ``templer basic_namespace my.package``
   
       2) The files and folders provided by a templer package as content to be
       generated. The answers provided by a user in response to vars are used to
       fill placeholders in this content.


.. _Paste: http://pythonpaste.org/