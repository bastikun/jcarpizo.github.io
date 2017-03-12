Install eJabberd XMPP Server on Ubuntu 14
=========================================

login to your droplet via SSH as root.

Install eJabberd
----------------

``sudo apt-get -y install ejabberd``

Setup Admin User
----------------

``sudo ejabberdctl register admin localhost password``

Give Admin Privileges
---------------------

``sudo subl /etc/ejabberd/ejabberd.cfg``

::

    %% Admin user
    {acl, admin, {user, "admin", "localhost"}}.

    %% Hostname
    {hosts, ["localhost"]}.

Change Admin Password
---------------------

``sudo ejabberdctl change_password admin localhost iFPQzkH5PF1Yl3V3``

Restart eJabberd
----------------

``sudo service ejabberd restart``

Now you can navigate to your eJabberd Web Admin interface on droplet's IP address port 5280

``http://198.199.90.115:5280/admin``

Enable the multi user chat history
----------------------------------

**mod_muc** ::

    [
        {access, muc},
        {access_create, muc},
        {access_persistent, muc},
        {access_admin, muc_admin},
        {max_users, 500},
        {history_size, 9999},
        {default_room_options,
                        [
                            {logging, true},
                            {allow_private_messages, true}
                        ]
        }
    ]

**mod_muc_log** ::

    [
        {access_log, muc_log},
        {cssfile, false}, {dirtype, subdirs},
        {outdir, "/var/www/html/chat-room"},
        {timezone, universal}
    ]

Enable the host name
--------------------

``sudo subl /etc/hosts``

::

    127.0.0.1	localhost
    127.0.1.1	latitude-3470
    127.0.1.1 	ls-summit.dev
    127.0.1.1 	gmovies-web.dev

    # The following lines are desirable for IPv6 capable hosts
    ::1     ip6-localhost ip6-loopback
    fe00::0 ip6-localnet
    ff00::0 ip6-mcastprefix
    ff02::1 ip6-allnodes
    ff02::2 ip6-allrouters

