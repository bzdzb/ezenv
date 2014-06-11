# ezenv
### A rapid pyenv + virutalenv instance creation tool

## Features
 * Rapid virtualenv deployments *with a single `ezenv` command*.
 * Quickly deploy a virualenv for any Python version using isolated `pyenv` based python installs.
 * Automatically installs `pyenv` and `pyenv-virtualenv` for you if you don't have them.
 * Will automatically fall back to using `git` for satisfying dependencies if `brew` is unavailable.
 * Just as simply deploy Django for any Django and Python version using `ezdjango`.


## Requirements
 * OS X (Linux and others should work, but are untested)
 * Python
 * Bash
 * Homebrew (http://brew.sh) or Git (http://git-scm.com)


## Installation
To install simply set `INSTALL_DIR` to where you would like to install. This should probably be somewhere in your `PATH` or you can add it to your path using the optional steps shown in the "**Add INSTALL_DIR to your PATH**" section below.

### Install
    git clone https://github.com/bzdzb/ezenv.git
    cd ezenv
    INSTALL_DIR=~/bin
    cp ezenv ezdjango $INSTALL_DIR
    chmod +x $INSTALL_DIR/ez{env,django}

### Add INSTALL_DIR to your PATH *(optional)*
    echo "export PATH=$INSTALL_DIR:\$PATH" >> ~/.bashrc
    . ~/.bashrc
    

## Usage
### Create a virtualenv
    $ ezenv example
    Installing pyenv... done.
    Installing pyenv-virtualenv... done.
    Adding pyenv init to ~/.bashrc... done.
    Initializing pyenv... done.
    Creating pyenv virualenv example. May take a few min... done.
    
    Get started using your new virtualenv with:
      source ~/.bashrc && pyenv activate example
    
### Using your new virtualenv
    $ source ~/.bashrc && pyenv activate example
    (example) $ pyenv which python
    /Users/bzdzb/.pyenv/versions/example/bin/python
    (example) $

### Create a virtualenv for specific Python version
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

### Create a Django-ready virtualenv
    $ ezdjango dj
    Installing Django... done.
    
    To activate, run:
      source ~/.bashrc && pyenv activate dj
    
    $ source ~/.bashrc && pyenv activate dj
    (dj) $ python
    Python 2.7.5 (default, Mar  9 2014, 22:15:05) 
    [GCC 4.2.1 Compatible Apple LLVM 5.0 (clang-500.0.68)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>> import django
    >>> django.get_version()
    '1.6.5'


### Create virtualenv with a specific Django version
    $ ezdjango dj1.5 1.5.8
    Installing Django... done.
    
    To activate, run:
      source ~/.bashrc && pyenv activate dj1.5
    
    $ source ~/.bashrc && pyenv activate dj1.5
    (dj1.5) $ python
    Python 2.7.5 (default, Mar  9 2014, 22:15:05) 
    [GCC 4.2.1 Compatible Apple LLVM 5.0 (clang-500.0.68)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>> import django
    >>> django.get_version()
    '1.5.8'


### Create virtualenv with specific Python and Django versions
    $ ezdjango djPyPy 1.6.5 pypy-2.3
    Installing Django... done.
    
    To activate, run:
      source ~/.bashrc && pyenv activate djPyPy
    
    $ source ~/.bashrc && pyenv activate djPyPy
    (djPyPy) $ python
    Python 2.7.6 (394146e9bb67, May 08 2014, 16:45:59)
    [PyPy 2.3.0 with GCC 4.2.1 Compatible Apple LLVM 5.0 (clang-500.2.79)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>>> import django
    >>>> django.get_version()
    '1.6.5'
    

## pyenv
ezenv uses pyenv and pyenv-virtualenv under the hood, so you can still use all of the pyenv commands for managing your pyenv and pyenv-virtualenv instances. 

### Listing installed python versions and virtualenv
    $ pyenv versions
      system
      3.4.1
      dj
      dj1.5
    * djPyPy (set by PYENV_VERSION environment variable)
      example
      example34
      pypy-2.3
      
### Listing available python versions
    # pyenv install --list
    Available versions:
      2.4
      2.4.1
      2.4.2
      ...
      ...
      stackless-3.3.5
      stackless-dev

### Removing a pyenv python version or virtualenv
    $ pyenv uninstall djPyPy
    pyenv: remove /Users/bzdzb/.pyenv/versions/djPyPy? y
    $ pyenv uninstall 3.4.1
    pyenv: remove /Users/bzdzb/.pyenv/versions/3.4.1? y

---

Copyright &copy; 2014, Brett Anderson (https://github.com/bzdzb)
All rights reserved.


