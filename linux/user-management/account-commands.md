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
$ adduser user_name   #creates user with home directory and defaults

$ passwd user_name   #change users pwd
$ passwd -l user_name   #lock the users account
4 passwd -u user_name   #unlock the users account

$ rmuser  uname   #remove user, but leave files
$ userdel -r user_name   #remove user, files and home directory 
$ cat /etc/passwd    #view password file to ensure account has been removed
</pre>


<h4>Group maintenance:</h4>
<pre>
$ groupadd group_name    #create group
$ usermod -G group_name user_name   #adds user to group or changes current group
$ usermod -G group1,group1 user_name   #adds user to two groups
$ usermod -a  -G group2,group3 user_name   # adds user to two groups in addition to current group
$ groups   #prints out current users group
</pre>

<h4>Add to Sudoers</h4>
<pre>
$ sudo visudo
# add to the file:
user_name ALL=(ALL) ALL   #adds user to sudoers
group_name ALL=(ALL) ALL   #adds group and all of its users to sudoers
</pre>

















