Install MySQL on Mac OS X
=========================

1. Download the MySQL DMG for Mac OS X
2. Install MySQL

Creating aliases for mysql and mysqladmin. However there are other commands that are helpful such as mysqldump. Instead, I updated my path to include /usr/local/mysql/bin.

::

    export PATH=/usr/local/mysql/bin:$PATH

.. note::

   You will need to open a new Terminal window or run the command above for your path to update.

I also run **mysql_secure_installation**. While this isn’t necessary, it’s good practice.

=====================
Connect PHP and MySQL
=====================

You need to ensure PHP and MySQL can communicate with one another.

::

    cd /var
    mkdir mysql
    cd mysql
    ln -s /tmp/mysql.sock mysql.sock


::

    cd /var
    sudo mkdir mysql
    sudo chmod 755 mysql
    cd mysql
    sudo ln -s /tmp/mysql.sock mysql.sock

If you have /var/mysql/mysql.sock but no /tmp/mysql.sock then


::

    cd /tmp
    ln -s /var/mysql/mysql.sock mysql.sock

===================================
Additional Configuration (optional)
===================================

The default configuration for Apache 2.4 on OS X Yosemite seemed pretty lean. For example, common modules like **mod_rewrite** were disabled. You may consider enabling this now to avoid forgetting they are disabled in the future.

I edited my Apache Configuration:

::

    vi /etc/apache2/httpd.conf

I uncommented the following lines (remove #):

::

    LoadModule deflate_module libexec/apache2/mod_deflate.so
    LoadModule expires_module libexec/apache2/mod_expires.so
    LoadModule rewrite_module libexec/apache2/mod_rewrite.so


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

