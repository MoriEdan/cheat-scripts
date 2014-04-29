Varnish cheats
===========================

<h4>Install</h4>
<pre>
$ apt-get update
$ apt-get install varnish 
</pre>

<h4>Configuration</h4>
<pre>
$ nano /etc/default/varnish
# add to the top of the file:
START=yes
DAEMON_OPTS="-a :80 \
-T localhost:6082 \
-f /etc/varnish/default.vcl \
-S /etc/varnish/secret \
-s file,/var/lib/varnish/$INSTANCE/varnish_storage.bin,128M"

$ nano /etc/apache2/ports.conf
# change:
NameVirtualHost *:8080
Listen 8080

$ nano /etc/apache2/sites-available/...
# change:
<VirtualHost *:8080>

$ service apache2 restart
$ service varnish restart

$ nano  /etc/varnish/default.vcl
# see default.vcl file in this repo; copy and paste it in this file

$ service apache2 restart
$ service varnish restart
</pre>


<h4>Route traffic from port 80 to 6081:</h4>
<pre>
$ iptables -I PREROUTING -t nat -i eth0 -p tcp --dport 80 -j REDIRECT --to-port 6081.
</pre>

verify that www.site.com/6081 is caching: http://www.isvarnishworking.com/
