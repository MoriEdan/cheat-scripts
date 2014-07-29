Linux umask cheats
==================

<h4>System wide umask usng PAM</h4>
<pre>
$ less /etc/login.defs | grep UMASK
# grep for the settings

$ nano /etc/login.defs
# change UMASK to desired value
</pre>
