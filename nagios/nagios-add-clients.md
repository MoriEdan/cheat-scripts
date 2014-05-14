Nagios adding clients to monitor cheats
=======================================

<h4>Adding clients to config file</h4>
<pre>
$ nano /etc/nagios3/conf.d/client_name
# add to the file the minimum: 

define host {
        use                     generic-host
        host_name               client_host_name
        alias                   client_host_name
        address                 client_ip_address
        }

define service {
        use                             generic-service
        host_name                       client_host_name
        service_description             PING
        check_command                   check_ping!100.0,20%!500.0,60%
        }

define service {
        use                             generic-service
        host_name                       client_host_name
        service_description             SSH
        check_command                   check_ssh
        notifications_enabled           0
        }

define service {
        use                             generic-service
        host_name                       client_host_name
        service_description             Current Load
        check_command                   check_load!5.0!4.0!3.0!10.0!6.0!4.0
        }
    
$ service nagios3 restart
</pre>
