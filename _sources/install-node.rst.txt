Installing Node.js via package manager
======================================

===========================================
Debian and Ubuntu based Linux distributions
===========================================

::

    curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -

    sudo apt-get install -y nodejs

Alternatively, for Node.js 8:
-----------------------------

::

    curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -

    sudo apt-get install -y nodejs``

Optional: install build tools
-----------------------------

To compile and install native addons from npm you may also need to install build tools:

::

    sudo apt-get install -y build-essential
