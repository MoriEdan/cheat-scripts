Apache hardening cheats
=======================


<h4>Basics:</h4>
<pre>
Document root: 
/var/www/html
/var/www

Config file:
/etc/apache2/apache2.conf

HTTP port:
80

HTTPS port:
443

Access and error log:
/var/log/apache2
</pre>


<h4>Slowloris prevention</h4>
<pre>
$ apt-get -y install libapache2-mod-qos
$ nano /etc/apache2/mods-available/qos.conf
# edit the file:
## QoS Settings
&lt;IfModule mod_qos.c&gt;
    # handles connections from up to 100000 different IPs
    QS_ClientEntries 100000
    # will allow only 50 connections per IP
    QS_SrvMaxConnPerIP 50
    # maximum number of active TCP connections is limited to 256
    MaxClients              256 
    # disables keep-alive when 70% of the TCP connections are occupied:
    QS_SrvMaxConnClose      180
    # minimum request/response speed (deny slow clients blocking the server,     
    # ie. slowloris keeping connections open without requesting anything):
    QS_SrvMinDataRate       150 1200
    # and limit request header and body (carefull, that limits uploads and 
    # post requests too):
    # LimitRequestFields      30
    # QS_LimitRequestBody     102400
&lt;/IfModule&gt;
</pre>
test with nmpa slowloris checking tool: http://nmap.org/nsedoc/scripts/http-slowloris-check.html

<h4>DDoS prevention</h4>
<pre>
# install mod-evasive
$ apt-get -y install libapache2-mod-evasive
$ mkdir -p /var/log/apache2/evasive
$ chown -R www-data:root /var/log/apache2/evasive
$ nano /etc/apache2/apache2.conf
# edit or verify:
Include mods-enabled/*.load
Include mods-enabled/*.conf

# add this script underneath module configuration
&lt;IfModule mod_evasive20.c&gt;
DOSHashTableSize    3097
DOSPageCount        2
DOSSiteCount        50
DOSPageInterval     1
DOSSiteInterval     1
DOSBlockingPeriod   60
DOSEmailNotify user@gmail.com
&lt;/IfModule&gt;

$ service apache2 restart
</pre>

<h4>Spam bot attack prevention</h4>
<pre>
$ apt-get -y install libapache2-mod-spamhaus
$ touch /etc/spamhaus.wl
# add to the file:
&lt;IfModule mod_spamhaus.c&gt;
  MS_METHODS POST,PUT,OPTIONS,CONNECT 
  MS_WhiteList /etc/spamhaus.wl 
  MS_CacheSize 256 
&lt;/IfModule&gt;

$ service apache2 restart
$ tail -200 /var/log/syslog
</pre>

<h4>Timestamping Correction</h4>
<pre>
$ apt-get -y install openntpd tzdata
$ dpkg-reconfigure tzdata
$ service openntpd restart
</pre>














