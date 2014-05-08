Nagios Plugin configuration cheats
==================================

<h4>Host configuration</h4>
<pre>
# NRPE disk_check plugin
$ nano etc/nagios3/conf.d/client_host_name.cfg
# add to the file:

define service {
        use                             generic-service
        host_name                       client_host_name
        service_description             nrpe-disk
        check_command                   check_nrpe_1arg!check_all_disks!client_ipaddress
        
}

<h4>Client configuration</h4>
<pre>
$ etc/nagios/nrpe.cfg
# add to the file:
command[check_all_disks]=/usr/lib/nagios/plugins/check_disk -w 20% -c 10% -e
</pre>

<h4>Restart services</h4>
<pre>
# on client
$ etc/init.d/nagios-nrpe-server restart
# on host
$ service nagios3 restart
</pre>
