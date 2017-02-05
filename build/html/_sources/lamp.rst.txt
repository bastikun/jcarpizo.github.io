Install LAMP in one command
===========================

A few complex packages but all (bar linux!) can be installed with one command and then following the on-screen instructions:

``sudo apt-get install lamp-server^``

==================
Install phpMyAdmin
==================

To get started, we can simply install phpMyAdmin from the default Ubuntu repositories.

``sudo apt-get update``

``sudo apt-get install phpmyadmin php-mbstring php-gettext``


The only thing we need to do is explicitly enable the PHP mcrypt and mbstring extensions, which we can do by typing:

``sudo phpenmod mcrypt``

``sudo phpenmod mbstring``

``sudo service apache2 restart``

**You can now access the web interface by visiting your server's domain name or public IP address followed by /phpmyadmin:**

Re-configure phpMyadmin
-----------------------

``sudo dpkg-reconfigure phpmyadmin``

===============================
Secure your phpMyAdmin Instance
===============================

Configure Apache to Allow .htaccess Overrides
---------------------------------------------

We will edit the linked file that has been placed in our Apache configuration directory:

``sudo subl /etc/apache2/conf-available/phpmyadmin.conf``

We need to add an ``AllowOverride All`` directive within the ``<Directory /usr/share/phpmyadmin>`` section of the configuration file, like this: ::

    <Directory /usr/share/phpmyadmin>
        Options FollowSymLinks
        DirectoryIndex index.php
        AllowOverride All
    </Directory>

When you have added this line, save and close the file.

To implement the changes you made, restart Apache:

``sudo service apache2 restart``

Create an .htaccess file
------------------------

Now that we have enabled .htaccess use for our application, we need to create one to actually implement some security.

In order for this to be successful, the file must be created within the application directory. We can create the necessary file and open it in our text editor with root privileges by typing:

``sudo subl /usr/share/phpmyadmin/.htaccess``

Within this file, we need to enter the following information: ::

    AuthType Basic
    AuthName "Restricted Files"
    AuthUserFile /etc/phpmyadmin/.htpasswd
    Require valid-user

Create the .htpasswd file for Authentication
--------------------------------------------

Now that we have specified a location for our password file through the use of the AuthUserFile directive within our .htaccess file, we need to create this file.

We actually need an additional package to complete this process. We can install it from our default repositories:

``sudo apt-get install apache2-utils``

Afterward, we will have the **htpasswd** utility available.

The location that we selected for the password file was **/etc/phpmyadmin/.htpasswd**. Let's create this file and pass it an initial user by typing:

``sudo htpasswd -c /etc/phpmyadmin/.htpasswd username``


You will be prompted to select and confirm a password for the user you are creating. Afterwards, the file is created with the hashed password that you entered.

If you want to enter an additional user, you need to do so without the -c flag, like this:

``sudo htpasswd /etc/phpmyadmin/.htpasswd additionaluser``

Enable .httaccess rewrite
-------------------------

``sudo a2enmod rewrite``

``sudo service apache2 restart``

Solve phpmyadmin not found
--------------------------

Create a link in ``/var/www/html`` like this:

``sudo ln -s /usr/share/phpmyadmin /var/www/html``





