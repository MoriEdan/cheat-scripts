Nagios install and config cheats
================================

<h4>Digital Ocean prep</h4>
<pre>
#add swap memory to the droplet
$ dd if=/dev/zero of=/swap bs=1024 count=2097152
$ mkswap /swap && chown root. /swap && chmod 0600 /swap && swapon /swap
$ echo /swap swap swap defaults 0 0 >> /etc/fstab
$ echo vm.swappiness = 0 >> /etc/sysctl.conf && sysctl -p
</pre>


<h4>Ubuntu installation</h4>
<pre>
$ apt-get install -y nagios3 nagios-nrpe-plugin
</pre>

<h4>Configuraton</h>
<pre>
$ usermod -a -G nagios www-data    #add nagios user to the www-data group
$ chmod -R g+x /var/lib/nagios3/   #give group permission to execute
$ sed -i 's/check_external_commands=0/check_external_commands=1/g' /etc/nagios3/nagios.cfg   #edit config file if set to 0
$ htpasswd -c /etc/nagios3/htpasswd.users nagiosadmin   #set nagiosadmin interface pwd
$ service nagios3 restart
$ service apache2 restart
</pre>

verify its working and access nagios admin panel at your_ip_address/nagios3










