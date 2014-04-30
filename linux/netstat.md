Linux netstat cheats
====================

<pre>
$ netstat -a | more  #all tcp and udp ports
$ netstat -ant     #all tcp connections
$ netsat -tulpn    # connections with pid
$ netstat -au   #udp connections
$ netstat -lt   #tcp ports listening
$ netstat -lu   #udp ports listening
$ netstat -lx   #unix listening ports
$ netstat -s    #stats by protocol
$ netstat -tp   #service name with pid
$ netstat -r    #kernel routing table
$ netstat -i    #network interface transactions
$ netstat -c    #continous mode
$ netstat -ap | grep http   #find programs listening on http
</pre>
