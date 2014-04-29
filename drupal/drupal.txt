Drupal installation cheats

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

Install Drupal:
$ rm -rf /var/www/
$ cd /var
$ drush dl drupal
$ mv /var/drupal*/ /var/www/

Configure Apache conf:
$ nano /etc/apache2/httpd.conf
add to the file:
ServerName localhost

Mysql Database:
$ sudo mysql_secure_installation #forces secure mysql
$ mysql -u root -p #login
mysql> create database drupal7;
mysql> grant all on drupal7.* to 'newuser'@'localhost' identified by 'password';
mysql> quit;

Change Mysql pwd:
$ mysqladmin -u root -p'ROOT' password 'yournewpassword'


Memcache Module configuration:
#requires that memcached be installed on the server
$ drush dl memcache
$ drush en memcache -y
$ nano settings.php
add to the file:
$conf['cache_backends'][] = 'sites/all/modules/memcache/memcache.inc';
$conf['cache_default_class'] = 'MemCacheDrupal';
$conf['cache_class_cache_form'] = 'DrupalDatabaseCache';


Varnish module configuration:
# requires that varnish be installed on server
$ drush dl varnish
$ drush en varnish -y
$ nano settings.php
add to the file:
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

turn on caching in drupal
cache for anons and blocks
set exp of cached pages and min lifetime (TTL)


Clean URL's #required to enable
$ a2enmod rewrite
$ nano /etc/apache2/sites-enabled/default
Change: 
(line 7 and line 11), "AllowOverride None" to "AllowOverride All".

$ service apache2 restart

$ nano /etc/apache2/apache2.conf
add to the file:
<Directory /var/www/drupal>
        AllowOverride All
   </Directory>
   AccessFileName .htaccess

If clean urls still dont work:
disable Overlay module
go to Clean URLS
change URL from: /?q=admin/config/search/clean-urls 
to: /admin/config/search/clean-urls
Check box should appear


Configuration Page loads slow or shows HTTP request error:
$ nano settings.php
add to the file:
$conf['drupal_http_request_fails'] = FALSE;


















