Getting Started
===============
To install simply set ``INSTALL_DIR`` to where you would like to install.
This should probably be somewhere in your ``PATH`` or you can add it to your
path using the optional steps shown in the "**Adding INSTALL_DIR to your PATH**" section below.

Installation
------------
.. code-block:: bash

  git clone https://github.com/bzdzb/ezenv.git
  cd ezenv
  INSTALL_DIR=~/bin
  cp ezenv ezdjango $INSTALL_DIR
  chmod +x $INSTALL_DIR/ez{env,django}

Addding INSTALL_DIR to your PATH *(optional)*
---------------------------------------------
.. code-block:: bash

  echo "export PATH=$INSTALL_DIR:\$PATH" >> ~/.bashrc
  . ~/.bashrc

.. include:: urls.rst
