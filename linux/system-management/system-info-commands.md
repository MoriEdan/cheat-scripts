Linux system info command cheats
================================

<h4>Version info</h4>
<pre>
$ cat /etc/issue   #distribution version
$ lsb_release -a   #distribution version
$ uname -a   #kernel version
</pre>

<h4>Processes</h4>
<pre>
$ ps aux    #detailed list of running processes
$ ps -ef    #process list
$ ps aux | grep root   #prints out all running root processes

$ killall apache2   #kills all apache2 processes

</pre>


<h4>Services</h4>
<pre>
$ service --status-all
$ service apache2 status    #checks status of service
$ update-rc.d -f apache2 remove   #removes service from startup cmd if in /etc/init.d
$ update-rc.d apache2 defaults  #add a service to startup
</pre>


<h4>File System</h4>
<pre>
$ df -h    #disk usage info
$ dpkg -get-selections   #installed packages
$ mount   #file systems
$ fdisk - l   #list attached drives
$ mount /dev/sda1  /mnt/usbkey   #mount usb drive that doesnt auto mount
</pre>


<h4>Log Files</h4>
<pre>
$ cat /etc/*syslog*.conf | grep -v “^#”   #list of logfiles
</pre>

<h4>Shell</h4>
<pre>
$ history   #view users shell command history
$ !5    #executes line 5 in history
$ script -a test   #record shell input, output to file “test", ctl + d to stop 
</pre>
