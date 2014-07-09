Digital Ocean SSH keys and remote login
==============================

<h4>Create key pair</h4>
<pre>

$ ssh-keygen -t rsa
# hit enter enter passphrase
# private key is in id_rsa
# public key is in id_rsa.pub

$ less ~/.ssh/id_rsa.pub
# copy the public key
</pre>
In Digital Ocean control panel:<br>
Click SSH keys<br>
Click Add SSH key<br>
Paste key into box and name it<br>

<h4>Cat key and Pipe into VPS</h4>
<pre>
cat ~/.ssh/id_rsa.pub | ssh root@your_ip_address "cat >> ~/.ssh/authorized_keys"
</pre>

<h4>SSH Configuration File</h4>
<pre>
$ nano .ssh/config
# add to the file

Host your_host_name
  User  your_user_name
  HostName  your_ip_address
  IdentityFile your_private_key_path
</pre>  

<h4>Login to server</h4>
<pre>
$ ssh your_host_name
</pre>

<h4>Remove password login</h4>
<pre>
$ ssh your_host_name
$ cd /etc/sshd_config
# edit this line:
PermitRootLogin without-password
</pre>


