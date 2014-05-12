Puppet certs configuration cheats
==========================================

<h4>Cert reset on Master</h4>
<pre>
$ puppet cert clean --all
</pre>

<h4>Cert reset on Agent</h4>
<pre>
$ rm -rf /var/lib/puppet/ssl/*
$ puppet agent --no-daemonize --server master_host_name --onetime --verbose
</pre>

<h4>Sign cert on Master</h4>
<pre>
$ puppet cert --list
</pre>

