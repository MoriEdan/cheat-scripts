SSH troubleshooting cheats
==========================

Workflow:<br>
turn on verbose mode and log-in<br>
check syslog, user and messages logs at /var/log<br>
check /etc/hosts file for proper shell path<br>
check /etc/passwd file for proper shell path<br>
make sure IPtables isnt configured to block SSH traffic<br>

<h4>User logs in with SSH and is logged out instantly</h4>
<pre>
$ ssh -v user@host   #ssh into server with verbose mode turned off

$ cat /var/log/syslog
$ cat /var/log/user
$ cat /var/log/messages
# check logs

$ nano /etc/hosts
or
$ cat /etc/hosts | grep user
# look for user, make sure last field is pointing to valid shell
# should say /bin/bash and not /bin/false or /bin/nologin
# make sure that the home directory is valid and has proper permissions

$ nano /etc/passwd
or
$ cat /etc/passwd | grep user
# make sure user shows /bin/bash
</pre>

