Install PHP 5.6 or PHP 7.1 on Ubuntu 16.04, 14.04 using PPA
===========================================================

Installing PHP 5.6 or PHP 7.1 using PPA on Ubuntu 16.10, 16.04 LTS, 14.04 LTS or 12.04 LTS systems. If you have already have higher version installed on your system and you need to install lower version, then you have to remove higher version first and remove apt repository from system.

=========================
Install PHP 5.6 on Ubuntu
=========================

Use the following set of command to add PPA for PHP 5.6 in your Ubuntu system and install PHP 5.6.


``$ sudo apt-get install python-software-properties``

``$ sudo add-apt-repository ppa:ondrej/php``

``$ sudo apt-get update``

``$ sudo apt-get install -y php5.6``


Check Installed PHP Version:
----------------------------

``$ php -v``

::

    PHP 5.6.29-1+deb.sury.org~xenial+1 (cli)
    Copyright (c) 1997-2016 The PHP Group
    Zend Engine v2.6.0, Copyright (c) 1998-2016 Zend Technologies
    with Zend OPcache v7.0.6-dev, Copyright (c) 1999-2016, by Zend Technologies


=========================
Install PHP 7.1 on Ubuntu
=========================

Use the following set of command to add PPA for PHP 7.1 in your Ubuntu system and install PHP 7.1.

``$ sudo apt-get install python-software-properties``

``$ sudo add-apt-repository ppa:ondrej/php``

``$ sudo apt-get update``

``$ sudo apt-get install -y php7.1``


Check Installed PHP Version:
----------------------------

``$ php -v``

::

    PHP 7.1.0-5+deb.sury.org~xenial+1 (cli) ( NTS )
    Copyright (c) 1997-2016 The PHP Group
    Zend Engine v3.1.0-dev, Copyright (c) 1998-2016 Zend Technologies
    with Zend OPcache v7.1.0-5+deb.sury.org~xenial+1, Copyright (c) 1999-2016, by Zend Technologies



