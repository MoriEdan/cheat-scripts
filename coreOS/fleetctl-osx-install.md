Fleet OSX install and config cheats
======================================

<h4>Install Dependencies</h4>
<pre>
$ brew install go etcdctl    #install as admin
</pre>

<h4>Install Fleet</h4>
<pre>
$ git clone https://github.com/coreos/fleet.git
$ cd fleet
$ ./build
$ mv bin/fleetctl /usr/local/bin/
</pre>

<h4>Setup SSH to Fleetctl</h4>
<pre>
$ nano ~/.ssh/config
# add to the file:

Host coreos
  User     core
  HostName coreOS_ip_address
  IdentityFile ~/.ssh/your_cert.pem
  
$ export FLEETCTL_TUNNEL=coreOS_ip_address
$ ssh-add ~/.ssh/your_cert.pem
</pre>

<h4>Fleetctl Commands</h4>
<pre>
$ fleetctl list-machines
</pre>
