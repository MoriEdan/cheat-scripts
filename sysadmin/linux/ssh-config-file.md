SSH config file cheats
======================

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
# add public key to server before attempting to log in
$ ssh your_host_name
</pre>

