Usage
=====

Creating a virtualenv
-------------------
.. code-block:: bash

   $ ezenv example
   Installing pyenv... done.
   Installing pyenv-virtualenv... done.
   Adding pyenv init to ~/.bashrc... done.
   Initializing pyenv... done.
   Creating pyenv virualenv example. May take a few min... done.
   
   Get started using your new virtualenv with:
     source ~/.bashrc && pyenv activate example

Using your new virtualenv
-------------------------
.. code-block:: bash

   $ source ~/.bashrc && pyenv activate example
   (example) $ pyenv which python
   /Users/bzdzb/.pyenv/versions/example/bin/python
   (example) $

Creating a virtualenv for specific Python version
-----------------------------------------------
.. code-block:: bash

   $ ezenv example34 3.4.1
   Installing pyenv... done.
   Installing pyenv-virtualenv... done.
   Adding pyenv init to ~/.bashrc... done.
   Initializing pyenv... done.
   Creating pyenv virualenv example34. May take a few min... done.
   
   Get started using your new virtualenv with:
     source ~/.bashrc && pyenv activate example34
   
   $ source ~/.bashrc && pyenv activate example34
   (example34) $ python -V
   Python 3.4.1 
   (example34) $

Creating a Django-ready virtualenv
--------------------------------
.. code-block:: bash

   $ ezdjango dj
   Installing Django... done.
   
   To activate, run:
     source ~/.bashrc && pyenv activate dj
   
   $ source ~/.bashrc && pyenv activate dj
   (dj) $ python
.. code-block:: python

   Python 2.7.5 (default, Mar  9 2014, 22:15:05) 
   [GCC 4.2.1 Compatible Apple LLVM 5.0 (clang-500.0.68)] on darwin
   Type "help", "copyright", "credits" or "license" for more information.
   >>> import django
   >>> django.get_version()
   '1.6.5'


Creating virtualenv with a specific Django version
------------------------------------------------
.. code-block:: bash

   $ ezdjango dj1.5 1.5.8
   Installing Django... done.
   
   To activate, run:
     source ~/.bashrc && pyenv activate dj1.5
   
   $ source ~/.bashrc && pyenv activate dj1.5
   (dj1.5) $ python
.. code-block:: python

   Python 2.7.5 (default, Mar  9 2014, 22:15:05) 
   [GCC 4.2.1 Compatible Apple LLVM 5.0 (clang-500.0.68)] on darwin
   Type "help", "copyright", "credits" or "license" for more information.
   >>> import django
   >>> django.get_version()
   '1.5.8'


Creating virtualenv with specific Python and Django versions
----------------------------------------------------------
.. code-block:: bash

   $ ezdjango djPyPy 1.6.5 pypy-2.3
   Installing Django... done.
   
   To activate, run:
     source ~/.bashrc && pyenv activate djPyPy
   
   $ source ~/.bashrc && pyenv activate djPyPy
   (djPyPy) $ python
.. code-block:: python

   Python 2.7.6 (394146e9bb67, May 08 2014, 16:45:59)
   [PyPy 2.3.0 with GCC 4.2.1 Compatible Apple LLVM 5.0 (clang-500.2.79)] on darwin
   Type "help", "copyright", "credits" or "license" for more information.
   >>>> import django
   >>>> django.get_version()
   '1.6.5'


pyenv
=====
ezenv uses pyenv_ and pyenv-virtualenv_ under the hood, so you can still use all
of the pyenv commands for managing your pyenv and pyenv-virtualenv instances.

Listing installed python versions and virtualenv
------------------------------------------------
.. code-block:: bash

   $ pyenv versions
     system
     3.4.1
     dj
     dj1.5
   * djPyPy (set by PYENV_VERSION environment variable)
     example
     example34
     pypy-2.3

Listing available python versions
---------------------------------
.. code-block:: bash

   $ pyenv install --list
   Available versions:
     2.4
     2.4.1
     2.4.2
     ...
     ...
     stackless-3.3.5
     stackless-dev

Removing a pyenv python version or virtualenv
---------------------------------------------
.. code-block:: bash

   $ pyenv uninstall djPyPy
   pyenv: remove /Users/bzdzb/.pyenv/versions/djPyPy? y
   $ pyenv uninstall 3.4.1
   pyenv: remove /Users/bzdzb/.pyenv/versions/3.4.1? y


.. include:: urls.rst
