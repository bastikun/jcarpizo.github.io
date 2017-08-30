Switch between Multiple PHP Version on Ubuntu
=============================================

On your system, if you have installed multiple versions of PHP (eg PHP 7.1 and PHP 5.6 both). PHP 7.1 is running as default PHP for Apache and CLI. For any requirement, you need to use PHP 5.6. Then you don’t need to remove PHP 7.1. You can simply switch your PHP version to default used for Apache and command line.

For example, your server has PHP 7.1 and PHP 5.6 both version’s installed. Now following example will help you to switch between both versions.

=======================
From PHP 5.6 => PHP 7.1
=======================

Default PHP 5.6 is set on your system and you need to switch to PHP 7.1. Run the following commands to switch for Apache and command line.

Apache:
-------

::

    sudo a2dismod php5.6

    sudo a2enmod php7.1

    sudo service apache2 restart


Command Line:
-------------

::

    sudo update-alternatives --set php /usr/bin/php7.1

    sudo update-alternatives --set phar /usr/bin/phar7.1

    sudo update-alternatives --set phar.phar /usr/bin/phar.phar7.1


=======================
From PHP 7.1 => PHP 5.6
=======================

Default PHP 7.1 is set on your system and you need to switch to PHP 5.6. Now run the following commands to switch for Apache and command line.

Apache:
-------

::

    sudo a2dismod php7.1

    sudo a2enmod php5.6

    sudo service apache2 restart

Command Line:
-------------

::

    sudo update-alternatives --set php /usr/bin/php5.6

    sudo update-alternatives --set phar /usr/bin/phar5.6

    sudo update-alternatives --set phar.phar /usr/bin/phar.phar5.6
