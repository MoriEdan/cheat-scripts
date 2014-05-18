Mirth Connect VPS install cheats
===================================

<h4>Mirth Server VPS Ubuntu Installation</h4>
<pre>
$ add-apt-repository ppa:webupd8team/java
$ apt-get update
$ apt-get install oracle-java8-installer   #openjdk-7-jdk has a bug that was only fixed with java 8
$ apt-get install oracle-java8-set-default
$ java -version    #ensure that its showing 1.8.0
$ wget http://downloads.mirthcorp.com/connect/2.2.3.6825.b80/mirthconnect-2.2.3.6825.b80-unix.tar.gz -O mirth.tar.gz
$ tar -zxvf mirth.tar.gz -C /opt
</pre>

<h4>Startup</h4>
<pre>
$ cd /opt/Mirth\ Connect/
$ ./mcservice start
</pre>

<h4>Get jnlp File</h4>
<p>
Install jdk-7u55-macosx-x64.dmg for OS X<br>
Set Java security to medium<br>
Go to http://107.170.222.25:8080/<br>
Click Launch Mirth Connect Administrator button to download jnlp file<br>
Move jnlp file to Desktop<br>
Right click file and select Get Info<br>
Change Open With to Java Web Start<br>
Double click jnlp file to launch application<br>
user: admin<br>
pwd: admin<br>
Complete registration form and change pwd<br>
</p>
