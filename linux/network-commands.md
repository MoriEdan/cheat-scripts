Linux networking command cheats
===============================

<h4>Various commands</h4>
<pre>
$ lsof -i    #lists established connections
</pre>


<h4>Change mac address of wireless card</h4>
<pre>
$ ifconfig wlan0 down
$ ifconfig wlan0 hw ether 00:00:00:00:00:00
$ ifconfig wlan0 up
</pre>

<h4>DNS commands</h4>
<pre>
$ dig -x 64.141.178.194    #domain lookup
$ dig @64.141.178.194 domain -t AXFR    #zone transfer
$ echo "nameserver 8.8.8.8" > /etc/resolv.conf    #add dns server

</pre>

<h4>tcpkill</h4>
<pre>
$ tcpkill -i eth0 port 21    #killl outgoing ftp connection
$ tcpkill host 192.168.1.2   #kill packets arriving from or leaving ip address
</pre>

<h4>Enable IP forwarding</h4>
<pre>
$ cat /proc/sys/net/ipv4/ip_forward    #check the status
$ echo 1 > /proc/sys/net/ipv4/ip_forward   #enable forwarding
</pre>

<h4>Permanant IP Forwarding</h4>
<pre>
$ nano /etc/sysctl.conf:
add to the file:
net.ipv4.ip_forward = 1

$ sysctl -p /etc/sysctl.conf
$ /etc/init.d/procps.sh restart
</pre>














