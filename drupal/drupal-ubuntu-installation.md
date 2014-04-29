Drupal installation cheats
==========================

<h4>Dependencies:</h4>
<pre>
$ apt-get install update
$ apt-get install git 
$ apt-get install mysql-client 
$ apt-get installmysql-server
$ apt-get install apache2 
$ apt-get install libapache2-mod-php5
$ apt-get install php5-mysql 
$ apt-get install php-apc 
$ apt-get install drush
$ apt-get install mc
</pre>

<h4>Install Drupal:</h4>
<pre>
$ rm -rf /var/www/
$ cd /var
$ drush dl drupal
$ mv /var/drupal*/ /var/www/
</pre>

<h4>Configure Apache conf:</h4>
<pre>
$ nano /etc/apache2/httpd.conf
add to the file:
ServerName localhost
</pre>


<h4>Mysql Database:</h4>
<pre>
$ sudo mysql_secure_installation #forces secure mysql
$ mysql -u root -p #login
mysql> create database drupal7;
mysql> grant all on drupal7.* to 'newuser'@'localhost' identified by 'password';
mysql> quit;
</pre>


<h4>Change Mysql pwd:</h4>
<pre>$ mysqladmin -u root -p'ROOT' password 'yournewpassword'
</pre>

<h4>Memcache Module configuration:</h4>
<pre>
#requires that memcached be installed on the server
$ drush dl memcache
$ drush en memcache -y
$ nano settings.php
add to the file:
$conf['cache_backends'][] = 'sites/all/modules/memcache/memcache.inc';
$conf['cache_default_class'] = 'MemCacheDrupal';
$conf['cache_class_cache_form'] = 'DrupalDatabaseCache';
</pre>


<h4>Varnish module configuration:</h4>
<pre>
# requires that varnish be installed on server
$ drush dl varnish
$ drush en varnish -y
$ nano settings.php
# add to the file:
$conf['cache_backends'][] = 'sites/all/modules/varnish/varnish.cache.inc';
$conf['cache_class_cache_page'] = 'VarnishCache';
$conf['reverse_proxy'] = TRUE;
$conf['page_cache_invoke_hooks'] = FALSE;
$conf['cache'] = 1;
$conf['cache_lifetime'] = 0;
$conf['page_cache_maximum_age'] = 21600;
$conf['reverse_proxy_header'] = 'HTTP_X_FORWARDED_FOR';
$conf['reverse_proxy_addresses'] = array('127.0.0.1');
$conf['omit_vary_cookie'] = TRUE;
</pre>

turn on caching in drupal<br>
cache for anons and blocks<br>
set exp of cached pages and min lifetime (TTL)<br>


<h4>Clean URL's #required to enable</h4>
<pre>
$ a2enmod rewrite
$ nano /etc/apache2/sites-enabled/default
# Change: 
# (line 7 and line 11), "AllowOverride None" to "AllowOverride All".

$ service apache2 restart
$ nano /etc/apache2/apache2.conf
# add to the file:
<Directory /var/www/drupal>
        AllowOverride All
   </Directory>
   AccessFileName .htaccess
</pre>

If clean urls still dont work:<br>
disable Overlay module<br>
go to Clean URLS<br>
change URL from: /?q=admin/config/search/clean-urls <br>
to: /admin/config/search/clean-urls<br>
Check box should appear<br>


<h4>Configuration Page loads slow or shows HTTP request error:</h4>
<pre>
$ nano settings.php
add to the file:
$conf['drupal_http_request_fails'] = FALSE;
</pre>

