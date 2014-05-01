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


<h4>Packet Manipulation</h4>
<pre>
$ tcpdump -i eth0 -XX -w dump.pcap   #capture packets in ascii and hex 
$ tcpdump -nvvX -s0 -i  eth0 tcp portrange 22-23   #capture tcp traffic on ports 22/23
$ dumpcap -I eth0 -a duration:30 -w file dump.pcap   #capture packets for 30 and dump to file
$ file2cable -i eth0 -f dump.pcap   #replay pcap from file
$ tcpreplay --topspeed --loop=0 --intf=eth0 dump.pcap --mbps=10|100|1000   #fuzz, dos from file
</pre>



