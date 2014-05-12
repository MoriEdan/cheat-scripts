Puppet remote Master install cheats
=========================================


<h4>Install Puppet Master</h4>
<pre>
$ apt-get upgrade
$ apt-get upgrade
$ wget http://apt.puppetlabs.com/puppetlabs-release-saucy.deb
$ dpkg -i puppetlabs-release-saucy.deb
$ apt-get update && sudo apt-get -y install puppetmaster
</pre>

<h4>Puppet Master Configuration</h4>
<pre>
$ nano /etc/puppet/puppet.conf
# add to the file
[main]
server = master_host_name

$ service puppetmaster stop
$ rm -rf /var/lib/puppet/ssl
$ service puppetmaster start
</pre>
