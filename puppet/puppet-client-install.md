Puppet remote client install cheats
===================================

<h4>Install Puppet Client</h4>
<pre>
$ wget http://apt.puppetlabs.com/puppetlabs-release-saucy.deb
$ dpkg -i puppetlabs-release-saucy.deb
$ apt-get update
$ apt-get -y install puppet
</pre>

<h4>Add remote Puppet Master to Client hosts file</h4>
<pre>
$ nano /etc/hosts
# add to the file
server_ip_address    master_host_name
</pre>

<h4>Configure Puppet Client</h4>
<pre>
$ nano /etc/puppet/puppet.conf
# add to the file
[main]
certificate_revocation = false

[agent]
server = master_host_name
report = true
pluginsync = true
certname = your_cert_name

$ nano /etc/default/puppet
# add to the file:
START=yes

$ service puppet restart
</pre>
