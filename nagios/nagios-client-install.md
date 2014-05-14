Nagios Client install cheats
============================

<h4>Client installation</h4>
<pre>
$ apt-get install -y nagios-plugins nagios-nrpe-server
</pre>

<h4>Client configuration</h4>
<pre>
$ nano /etc/nagios/nrpe.cfg
# edit the allowed_hosts entry to point to the nagios host ip address
$ iptables -N NRPE
$ iptables -I INPUT -s 0/0 -p tcp --dport 5666 -j NRPE
$ iptables -I NRPE -s host_ip_address -j ACCEPT
$ iptables -A NRPE -s 0/0 -j DROP
$ /sbin/iptables-save
$ service nagios-nrpe-server restart
</pre>

