Serf Agent Node configuration
=============================

<h4>Node 1</h4>
<pre>
serf agent -node=**SerfNode1** -bind=node1_ip_address:7496 
</pre>

<h4>Node 2</h4>
<pre>
serf agent -node=**SerfNode2** -bind=node2_ip_address:7496 -rpc-addr=127.0.0.1:7373 &
</pre>

hit enter push process to background

<h4>Join Nodes</h4>
<pre>
# on Node 2
$ serf join node1_ip_address:7496
</pre>

<h4>Test Event</h4>
<pre>
# on Node 2
$ serf event hello
</pre>













