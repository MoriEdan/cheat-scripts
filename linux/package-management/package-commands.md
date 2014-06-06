Package command cheats
======================

<h4>Apt commands:</h4>
<pre>
$ apt-get update   #updates the repository metadata
$ apt-get upgrade  #updates all packages that are out of date
$ apt-get clean    #removes all package files except the lock file
$ apt-get auto-clean   #removes packages no longer available on system
$ apt-get dist-upgrade -y   #upgrades the linux distribution

$ apt-cache search package_name  #search for packages available in repository
$ apt-get -s install php5   #simulates installing php5 to see messages
$ apt-get source php5   #downloads source files so you can compile the program yourself

$ vi /etc/apt/sources.list   #edit sources file
$ apt-cache stats    #prints out repository totals info
$ apt-cache pkg-names   #lists all names of packages in the apt-cache
$ apt-cache depends php5   #prints out a packages dependencies
$ apt-cache unmet    #prints out unmet dependencies
</pre>

<h4>Dpkg commands</h4>
<pre>
$ dpkg --get-selections   #displays all packages on your system
$ dpkg --remove package_name   #removes package files, binaries but not config file
$ dpkg --purge  package_name  #removes everything including config file

$ dpkg-reconfigure package_name   #reconfigures the program using its config file
</pre>

<h4>Dpkg Package Installation</h4>
<pre>
$ cat /etc/issue   #determine distribution
$ uname -a   #determine 32 or 64 bit

#find .deb package (if debian based)
$ dpkg -i package_name.deb
#if it fails because of dependencies
$ apt-get update
$ apt-get upgrade
$ apt-get install -f
$ dpkg -i package_name.deb
$ which package_name   #check installation
</pre>

<h4>Aptitude commands:</h4>
<pre>
$ aptitude search package_name 
$ aptitude install package_name

$ aptitude update   #updates repository metadata
</pre>

<h4>Package Commands:</h4>
<pre>
$ tar cf file.tar files    #create tar package
$ tar czf file.tar.gz files  #creates tar.gz package
$ tar cjf file.tar.bz2 files   #creates .bz2 package
$ tar xf file.tar    #extract
$ tar xzf file.tar.gz    #extract
$ tar xjf file.tar.bz2    #extract
$ zip -r filename.zip directory    #creates zip archive of the directory and sub directories
 </pre>
