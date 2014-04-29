Puppet installation cheats
==========================

<h4>Install</h4>
<pre>
$ wget apt puppetlabs.com/puppetlabs-release-precise.deb
$ dpkg -i puppetlabs-release-precise.deb
$ apt-get update
</pre>

<h4>Install Puppet Agent</h4>
<pre>
$ apt-get install puppet
</pre>

<h4>Puppet File Structure</h4>
<pre>
$ mkdir puppet
$ cd puppet
$ mkdir manifests 
$ nano manifests/site.pp
</pre>

<h4>Execute Puppet script</h4>
<pre>
$ puppet apply --modulepath modules/ manifests/site.pp
</pre>
