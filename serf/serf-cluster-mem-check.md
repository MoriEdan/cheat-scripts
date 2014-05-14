Serf cluster memory check cheats
================================

<h4>Handler on Node 1</h4>
<pre>
$ mkdir /memlogs
$ cd /memlogs
$ nano handler.sh
# add to the file:
  #!/bin/bash
if [ "${SERF_USER_EVENT}" = "memory_check" ]; then
   serf event memresponse "$(awk '/MemTotal/ {printf( "%.2f\n", $2 / 1024 ) }'              
   /proc/meminfo) MB from $(wget -qO- http://ipecho.net/plain ; echo) at $(date)"
fi

$ chmod a+x handler.sh
</pre>

<h4>Handler on Node 2</h4>
<pre>
$ mkdir /memlogs
$ cd /memlogs
$ nano handler.sh
# add to the file
 #!/bin/bash
if [ "${SERF_USER_EVENT}" = "memresponse" ]; then
    cat >> mem.txt
    echo "\n" >> mem.txt
fi

$ chmod a+x handler.sh
</pre>

<h4>Start Node 1</h4>
<pre>
$ serf agent -log-level=debug -event-handler=./handler.sh -node=**SerfNode1** -bind=node1_ip_address:7496
</pre>

<h4>Start Node 2</h4>
<pre>
$ serf agent -log-level=debug -event-handler=./handler.sh -node=**SerfNode1** -bind=node2_ip_address:7496 &
</pre>

<h4>Join Nodes</h4>
<pre>
# on node 2
$ serf join node1_ipaddress:7496
</pre>

<h4>Trigger Event</h4>
<pre>
$ serf event memory
</pre>

<h4>Check Event</h4>
<pre>
$ nano mem.txt
</pre>











