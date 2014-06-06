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


<h4>Account switching:</h4>
<pre>
# all change to root
$ sudo su 
$ sudo -s
$ sudo -i

$ su user   #change to another user
</pre>

<h4>User maintenance:</h4>
<pre>
$ passwd user_name   #change users pwd
$ passwd -l user_name   #lock the users account
4 passwd -u user_name   #unlock the users account

$ rmuser  uname   #remove user, but leave files
$ userdel -r user_name   #remove user, files and home directory 
$ cat /etc/passwd    #view password file to ensure account has been removed
</pre>


<h4>Group maintenance:</h4>
<pre>
$ addgroup group_name    #add user group

</pre>

<h4>Add to Sudoers</h4>
<pre>
$ sudo visudo
# add to the file:
username ALL=(ALL) ALL
</pre>

















