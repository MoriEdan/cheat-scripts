Apache SSL certs cheats
=======================

<h4>Install dependencies</h4>
<pre>
$ apt-get update
$ apt-get install apache2
</pre>

<h4>Activate SSL</h4>
<pre>
$ a2enmod ssl
$ service apache2 restart
</pre>

<h4>create certificate</h4>
<pre>
$ mkdir /etc/apache2/ssl
$ openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/apache2/ssl/apache.key -out /etc/apache2/ssl/apache.crt
# enter ip address or domain when prompted for "Common Name"

$ nano /etc/apache2/sites-available/default-ssl
# inside the virtualhost tags edit the ServerName:
ServerName yoursite.com:443
# add to the file:
SSLEngine On
  SSLCertificateFile /etc/apache2/ssl/yoursite.com.crt
  SSLCertificateKeyFile /etc/apache2/ssl/yoursite.com.key
  SSLCertificateChainFile /etc/apache2/ssl/yoursite.com.ca-bundle
</pre>

<h4>Enable virtualhost</h4>
<pre>
$ a2ensite default-ssl
$ service apache2 reload
</pre>


