Linux IP tables cheats
======================

<h4>Commands:</h4>
<pre>
$ iptables-save -c > file    #dump iptables to file
$ iptables-restore file    #restores iptables from file
$ iptables -L -v    #list all iptables rules
$ iptables -F    #flush iptables rules
$ iptables -P INPUT DROP    #drop all packets
$ iptables -A INPUT -s "ipaddress" -j DROP   #block ip address and drop packets
</pre>



<h4>Allow SSH port 22 inbound</h4>
<pre>
$ iptables -A INPUT -i eth0 -p tcp --dport 22 -m state --state NEW,ESTABLISHED -j ACCEPT
$ iptables -A OUTPUT -o eth0 -p tcp --sport 22 -m state --state ESTABLISHED -j ACCEPT
</pre>

<h4>allow SSH port 22 outbound</h4>
<pre>
iptables -A OUTPUT -o eth0 -p tcp --dport 22 -m state --state NEW,ESTABLISHED -j ACCEPT
iptables -A INPUT -i eth0 -p tcp --sport 22 -m state --state ESTABLISHED -j ACCEPT
</pre>

<h4>Allow HTTP and HTTPS</h4>
<pre>
iptables -A INPUT -i eth0 -p tcp --dport 80 -m state --state NEW,ESTABLISHED -j ACCEPT
iptables -A OUTPUT -o eth0 -p tcp --sport 80 -m state --state ESTABLISHED -j ACCEPT
</pre>

<h4>Loopback access</h4>
<pre>
iptables -A INPUT -i lo -j ACCEPT
iptables -A OUTPUT -o lo -j ACCEPT
</pre>

<h4>DoS Prevention</h4>
<pre>
iptables -A INPUT -p tcp --dport 80 -m limit --limit 25/minute --limit-burst 100 -j ACCEPT
</pre>

<h4>Ignore Ping and ICMP traffic</h4>
<pre>
$ iptables  -I  INPUT  -i  ech0  -p   icmp  -s  0/0  -d  0/0   -j  DROP
</pre>

<h4>Block Single IP</h4>
<pre>
$ iptables -A INPUT -s offending_ip -j DROP   #blocks IP address
$ iptables -A INPUT -s offending_ip -p tcp --destination-port 25 -j DROP   #blocks single port for a single IP
</pre>

<h4>Unblock single IP</h4>
<pre>
$ iptables -D INPUT -s ip_address -j DROP
$ service iptables save
</pre>







