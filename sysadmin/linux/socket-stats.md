Linux socket statistics cheats
==============================
<pre>
$ watch ss -tp  #detect network connections in real time
$ ss | less    #all connections
$ ss -nt    #connections without resolving host name
$ ss -ltn  #only listening sockets
$ ss -ltp   #print process name and pid
$ ss - s    #summary and stats
$ ss -tl4    #ipv4 only
$ ss -tl6    #ipv6 only
$ ss -t4 state established    #sockets in a connected state
$ ss -t4 state time-wait      #sockets waiting
</pre>

