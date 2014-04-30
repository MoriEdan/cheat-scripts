Scalpel cheats
==============

<h4>Install:</h4>
<pre>
$ apt-get install scalpel
</pre>

<h4>Usage:</h4>
<pre>
# edit config file and uncoment extension type to look for:
$ nano /etc/scalpel/scalpel.conf
</pre>

<h4>Workflow:</h4>
<pre>
$ blkls -a image-name &gt; output-image	#carve out unallocated space and saved it to an output image
$ scalpel -c scalpel.conf recovered output-image	#take output image and run scalpel on it
</pre>

