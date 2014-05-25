coreOS Vagrant cluster cheats
=============================

<h4>Clone repo</h4>
<pre>
$ git clone https://github.com/coreos/coreos-vagrant
</pre>

<h4>Configure cluster</h4>
<pre>
$ cd coreos-vagrant
$ nano config.rb.sample
# Uncomment and edit the following line:

$num_instances=3

$ mv config.rb.sample config.rb
</pre>

<h4>Set etcd token</h4>
<pre>
$ curl https://discovery.etcd.io/new
$ nano user-data.sample
# Uncomment and copy etcd discovery token:

discovery: https://discovery.etcd.io/your_discovery_token

$ mv user-data.sample user-data
</pre>

<h4>Launch Cluster</h4>
<pre>
$ vagrant up
</pre>

<h4>SSH into machines</h4>
<pre>
$ vagrant ssh core-01
$ vagrant ssh core-02
$ vagrant ssh core-03
</pre>
