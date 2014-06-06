Permission management cheats
============================

<p>
to view permissions of a directory execute ls -al or ll<br>

d: directory<br>
-: file<br>
r: read<br>
w: write<br>
x: execute<br>
</p>

<p>
1st three lines: owner<br>
2nd three lines: group<br>
3rd three lines: world<br>
</p>

<p>
4: read<br>
2: write<br>
1: execute<br>
0: no permission<br>
</p>

<h4>Permissions commands</h4>
<pre>
$ chmod o+r file_name   #gives world permission to read
$ chmod o-r file_name   #removes permission to read

$ chmod 755 file_name   #rwx to owner, rx to group and world
$ chmod -R 755 directory_name  #changes permissions recursively to directory
</pre>








