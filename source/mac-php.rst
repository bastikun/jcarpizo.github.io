Update PHP on Mac OS X
======================

How to upgrade or install a different version of PHP on Mac OS X.

==============
Installing PHP
==============

First, choose the version of PHP you want to install. In this example, I’ll install PHP 7.1 as that is the latest stable version of PHP. However, if you want to install PHP 7.0 that is available as well.

::

    curl -s http://php-osx.liip.ch/install.sh | bash -s 7.1

==================
Configuring Apache
==================

Provided you are using the pre-installed version of Apache, PHP OSX will add the /etc/apache2/other/+php-osx.conf configuration file which will automatically be loaded by Apache.

If you had previously enabled PHP (as I did), you’ll need to comment out the following line in /etc/apache2/httpd.conf:

::

    LoadModule php5_module /usr/local/php5/libphp5.so


==================
Updating your PATH
==================


Although Apache will now run the new version of PHP, the command line will not. In order for the command line to use the new version of PHP you will need to update your PATH.

::

    export PATH=/usr/local/php5/bin:$PATH

If you don’t want to run the command above every time you open a new terminal, you can update the PATH in your .bash_profile.

::

    vi ~/.bash_profile


===============
Configuring PHP
===============

Finally, you will want to update some of the PHP configuration values. PHP OSX installs a PHP INI file for you to change. To edit this file, run:

::

    sudo vi /usr/local/php5/php.d/99-liip-developer.ini

If you kept all of your local PHP configuration within a single INI file (as I did), you can simply append it to the PHP OSX file with:

::

    sudo cat /Library/Server/Web/Config/php/local.ini >> /usr/local/php5/php.d/99-liip-developer.ini

That’s it!

Now you’ll just need to review your PHP code to ensure it’s compatible with your newly installed PHP version. And for that, I recommend PHP Shift.


.. meta::
    :description: My Online Technical Docs
    :keywords: PHP, MySQL, Git, Laravel, Symfony, Composer, HTML5, JavaScript, Phalcon, CakePHP, Java, Unix Shell Scripting, Node Js, CSS, eJabberd XMPP Server, SPHINX - Python Documentation Generator, Docker
        :author: Jasper Carpizo

.. raw:: html

   <meta property="og:image" content="jcarpizo.jpg"/>
   <meta property="og:title" content="My Online Technical Docs"/>
   <meta property="og:site_name" content="Jasper Carpizo"/>
   <meta property="og:url" content="https://jcarpizo.github.io"/>
   <meta property="og:type" content="blog"/>