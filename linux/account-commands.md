Linux account commands cheats
=============================

<h4>Account info</h4>
<pre>
$ id   #returns current username, group
$ w    #logged on users
$ who -a    #user info
$ last -a    #last users logged on
$ getent passwd    #users in the passwd database
</pre>


<h4>Account maintenance:</h4>
<pre>
# all change to root
$ sudo su 
$ sudo -s
$ sudo -i

$ su user   #change to another user
$ passwd user    #change pwd
$ addgroup hadoop    #add user group
$ adduser --ingroup hadoop hduser    #add user and then add user to group
$ rmuser  uname   #remove user
</pre>

<h4>Add user to Sudoers</h4>
<pre>
$ sudo visudo
# add to the file:
<your_user_name> ALL=(ALL) ALL
</pre>

















