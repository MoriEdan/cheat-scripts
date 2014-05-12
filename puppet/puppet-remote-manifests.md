Puppet remote Manifests cheats
==============================

<h4>Module install<h4>
<pre>
$ puppet module install puppetlabs-mysql
</pre>

<h4>Manifests file</h4>
<pre>
$ nano /etc/puppet/manifests/site.pp
# add to the file 
 
  class { '::mysql::server':
  root_password   => 'foo',
  override_options => {
      'mysqld' => { 'max_connections' => '1024' } ,
    }
}
</pre>

<h4>Node file</h4>
<pre>
$ nano /etc/puppet/manifests.node.pp

# add to the file:
node host_name {
include mysql
}
</pre>

<h4>Execute Puppet commands on remote host</h4>
<pre>
$ puppet agent -t 
</pre>









