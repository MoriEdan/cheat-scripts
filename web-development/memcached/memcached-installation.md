Memcached installation cheats
=============================

<h4>Dependencies:</h4>
<pre>
$ apt-get update
$ apt-get install build-essential
$ apt-get install apache2 
$ apt-get install libapache2-mod-php5
$ apt-get install php5-gd 
$ apt-get install php5-memcache 
$ apt-get install memcached 
</pre>

<h4>Install Memcached:</h4>
<pre>
$ sudo apt-get install memcached libmemcached-tools
$ sudo apt-get install php5-dev php-pear make
$ sudo pecl install memcache
</pre>

<h4>Create ini file:</h4>
<pre>
$ sudo nano /etc/php5/conf.d/memcache.ini
# add lines:
extension=memcache.so
memcache.hash_strategy="consistent"
</pre>


<h4>Edit conf file:</h4>
<pre>
$ sudo nano /etc/memcached.conf 
# Change this value to ~ 1/4 of your total available RAM
</pre>


<h4>Restart Memcached and Apache:</h4>
<pre>
$ sudo /etc/init.d/memcached restart
$ sudo /etc/init.d/apache2 restart
</pre>

You should see something like:<br>
tcp 0 0 localhost:11211 *:* LISTEN 25266/memcached

