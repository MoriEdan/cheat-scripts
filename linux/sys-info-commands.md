Linux system info command cheats
================================

<h4>Version info</h4>
<pre>
$ lsb_release -a   #release version
$ uname -a   #kernel version
</pre>

<h4>Processes</h4>
<pre>
ps -ef    #process list
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

