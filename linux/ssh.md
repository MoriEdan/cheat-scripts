Linux SSH cheats
================

<h4>Install open ssh server</h4>
<pre>
$ sudo apt-get install openssh-server
</pre>

<h4>Generate SSH keys for a user:</h4>
<pre>
$ su - hduser   #change into user
$ ssh-keygen -t rsa -P ""    #empty key, otherwise enter string inbetween ""
</pre>


<h4>enable SSH access on local host</h4>
<pre>
$ cat $HOME/.ssh/id_rsa.pub >> $HOME/.ssh/authorized_keys    #adds key fingerprint to known hosts file
</pre>


