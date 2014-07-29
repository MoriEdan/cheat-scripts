Apache troubelshooting cheats
=============================

workflow:<br>
check logs at /var/log<br>
is apache installed?<br>
is apache running?<br>
check for syntax and config errors with automatic tools<br>
are ports open?<br>
is DNS configured properly<br>
check DocumentRoot path is correct in Virtualhost config file<br>
check DirectoryIndex path is correct in Virtualhost config file<br>
does Apache have correct permissions to serve files?<br>
is .htaccess file being used and is it overriding settings?<br>
is mysql running?<br>

<h4>Service</h4>
<pre>
$ service apache2 restart   #restart ubuntu
$ service httpd restart   #restart rhel

$ service apache2 reload  #reload ubuntu
$ service httpd reload  #reload rhel
</pre>

<h4>Logging</h4>
<pre>
$ tail -f /var/log/apache2/error.log   #check apache error logs; ubuntu
$ tail -f /var/log/httpd/error_log   #check apache error logs; rhel

$ tail -f /var/log/apache2/access.log   #check apache access logs; ubuntu
$ tail -f /var/log/httpd/access_log   #check apache access logs; rhel
</pre>

<h4>Debugging</h4>
<pre>
$ apachectl -t   #automatic syntax checker  ubuntu
$ httpd -t   #automatic syntax checker   rhel

$ apachectl configtest   #auto config file checker ubuntu

$ apache2ctl -S    #checks virtualhost settings; ubuntu
$ httpd -S    #checks virtualhost settings; rhel

$ nano /etc/apache2/apache2.conf
# edit the file and change "LogLevel" to debug
$ service apache2 restart
</pre>


<h4>Check if processes are running</h4>
<pre>
$ netstat -plunt | grep apache2
$ netstat -plunt | grep httpd
</pre>

<h4>Check if ports are running</h4>
<pre>
$ nc -z your_ip_address 80
$ nc -z your_ip_address 443
</pre>

<h4>Check DNS</h4>
<pre>
$ host -t A yoursite.com
</pre>

<h4>Check permissions</h4>
<pre>
$ ls -al /var/www/yourrsite.com
</pre>

<h4>check mysql</h4>
<pre>
$ netstat -plunt | grep mysql 

</pre>
