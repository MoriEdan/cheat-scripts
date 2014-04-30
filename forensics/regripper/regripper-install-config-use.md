Regripper cheats
================

<h4>Install</h4>
<pre>
$ perl -MCPAN -e 'install Parse::Win32Registry'
$ unzip rr.tools.zip
$ perl -pi -e 's/\r\n/\n/g' rip.pl	#convert line endings to unix line endings
$ chmod +x rip.pl
$ which perl | sed 's/\//\\\//g' &gt; /tmp/perlloc && sed -i "s/ c:\\\\perl\\\\bin\\\\perl.exe/`cat /tmp/perlloc`/" rip.pl
</pre>

<h4>Download Plugins:</h4>
<pre>
$ wget https://regripper.googlecode.com/files/plugins20130429.zip -O plugins.zip
$ unzip  plugins.zip -d /plugins	#path must be /plugins/pluginname
</pre>

<h4>Usage:</h4>
<pre>
$ perl rip.pl -l 	#lists all plugins installed
$ perl rip.pl -r hive -p plugin-name
</pre>




