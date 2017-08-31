Unix / Linux File permissions
=============================

.. note::

    | Use the chmod command to set file permissions.
    | The chmod command uses a three-digit code as an argument.
    | The three digits of the chmod code set permissions for these groups in this order:

1. Owner (you)
2. Group (a group of other users that you set up)
3. World (anyone else browsing around on the file system)

Each digit of this code sets permissions for one of these groups as follows. Read is 4. Write is 2. Execute is 1.

The sums of these numbers give combinations of these permissions:

* **0** = *no permissions whatsoever; this person cannot read, write, or execute the file*
* **1** = *execute only*
* **2** = *write only*
* **3** = *write and execute* ``(1+2)``
* **4** = *read only*
* **5** = *read and execute* ``(4+1)``
* **6** = *read and write* ``(4+2)``
* **7** = *read and write and execute* ``(4+2+1)``

Chmod commands on file apple.txt (use wildcards to include more files)

+---------------------+---------------------------------------------------------------------------------+
| Command             |Purpose                                                                          |
+=====================+=================================================================================+
|chmod 700 apple.txt  | Only you can read, write to, or execute apple.txt                               |
+---------------------+---------------------------------------------------------------------------------+
|chmod 777 apple.txt  | Everybody can read, write to, or execute apple.txt                              |
+---------------------+---------------------------------------------------------------------------------+
|chmod 744 apple.txt  | Only you can read, write to, or execute apple.txt Everybody can read apple.txt; |
+---------------------+---------------------------------------------------------------------------------+
|chmod 444 apple.txt  | You can only read apple.txt, as everyone else.                                  |
+---------------------+---------------------------------------------------------------------------------+

==========================
Detecting File Permissions
==========================

You can use the ls command with the -l option to show the file permissions set. For example, for apple.txt, I can do this:

::

    $ ls -l apple.txt
    -rwxr--r--   1 december december       81 Feb 12 12:45 apple.txt
    $

The sequence -rwxr--r-- tells the permissions set for the file apple.txt. The first - tells that apple.txt is a file. The next three letters, rwx, show that the owner has read, write, and execute permissions. Then the next three symbols, r--, show that the group permissions are read only. The final three symbols, r--, show that the world permissions are read only.
