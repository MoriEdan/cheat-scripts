nslookup cheats
==========================

<h4>nslookup</h4>
<pre>
$ nslookup example.com   #find A record or ip address
$ nslookup your_ipaddress   #reverse domain lookup

$ nslookup -query=any example.com   #queries all DNS records
$ nslookup -query=mx example.com   #queries mail exchange record
$ nslookup -query=ns example.com   #queries name server record
$ nslookup -type=soa example.com   #queries start of authority record

$ nslookup -debug example.com   #debug mode

$ nslookup -port 54 example.com    #executing nslookup on non standard dns port
</pre>
