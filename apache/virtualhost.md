Apache virtualhost cheats
=========================

<h4>Install Apache</h4>
<pre>
$ apt-get update
$ apt-get install apache2
</pre>

<h4>Create and edit config file, multiple virtual hosts</h4>
<pre>
# make sure directories exist and contain the website's files:
/var/www/yoursite.com/html/files...
/var/www/othersite.com/html/files...

$ cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/yoursite.com.conf
$ nano /etc/apache2/sites-available/yoursite.com.conf
# edit the file:

&lt;VirtualHost *:80&gt;
ServerName yoursite.com
ServerAlias www.yoursite.com
DocumentRoot /var/www/yoursite.com/html
ErrorLog ${APACHE_LOG_DIR}/error.log
CustomLog ${APACHE_LOG_DIR}/access.log combined
&lt;/VirtualHost&gt;

$ cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/othersite.com.conf
$ nano /etc/apache2/sites-available/yoursite.com.conf
# edit the file:

&lt;VirtualHost *:80&gt;
ServerName othersite.com
ServerAlias www.othersite.com
DocumentRoot /var/www/othersite.com/html
ErrorLog ${APACHE_LOG_DIR}/error.log
CustomLog ${APACHE_LOG_DIR}/access.log combined
&lt;/VirtualHost&gt;
</pre>

<h4>Redirect all http traffic to https</h4>
<pre>
#place inside virtualhost tags
&lt;Location /&gt;
    Redirect permanent / https:/securesite.com/
  &lt;/Location&gt;
</pre>

