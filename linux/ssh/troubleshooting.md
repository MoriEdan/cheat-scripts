SSH troubleshooting cheats
==========================

<h4>User logs in with SSH and is logged out instantly</h4>
<pre>
$ ssh -v user@host   #ssh into server with verbose mode turned off

$ nano /etc/hosts
# look for user, make sure last field is pointing to valid shell
# should say /bin/bash and not /bin/false or /bin/nologin
# make sure that the home directory is valid and has proper permissions

$ cat /var/log/syslog
$ cat /var/log/user
$ cat /var/log/messages
# check logs
</pre>

