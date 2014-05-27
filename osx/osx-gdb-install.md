OSX GDB (GNU Debugger) install cheats
=====================================

<h4>Install tar package</h4>
<pre>
# assumes that you have no GDB installed on your system
$ gdb --version    #checks to see if its installed
$ cd /opt
$ curl -O http://ftp.gnu.org/gnu/gdb/gdb-7.7.tar.gz
$ tar -xzvf gdb-7.7.tar.gz
$ cd gdb-7.7
</pre>

<h4>Build and compile</h4>
<pre>
$ ./configure
$ make
$ sudo make install
$ gdb --version   #check installation
</pre>

<h4>Create GDB certificate</h4>
<p>
In Spotlight type: Keychain Access<br>
Select Keychain Access then Certificate Assistant then New Certificate<br>
Enter:<br>

Name: gdb-cert<br>
Identity Type: Self Signed Root<Br>
Certificate Type: Code Signing<br>
Check Let Me Override Default<br>

Click Continue until you reach Specify a Location for the Certificate<br>
Set Keychain to System and save<br

Go to My Certificates tab and right click and select Get Info<br>
Expand the Trust section<br>
Change Code Signing to Always Trust<br>
Exit it out of keychain utility<br>

<h4>Sign the certificate</h4>
<pre>
$ cd /usr/local/bin
$ codesign -s gdb-cert gdb
</pre>















