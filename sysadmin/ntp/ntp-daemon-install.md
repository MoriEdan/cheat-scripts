NTP (network time protocol) installation cheats
=======================

<h4>Installation</h4>
<pre>
$ apt-get install ntp
</pre>

<h4>Configuration</h4>
<pre>
$ nano /etc/ntp.conf
# change server pool to:
server 0.us.pool.ntp.org
server 1.us.pool.ntp.org
server 2.us.pool.ntp.org
server 3.us.pool.ntp.org

$ service ntp restart
</pre>
