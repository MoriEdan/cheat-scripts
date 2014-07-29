mysql troubleshooting cheats
============================

workflow:<br>
check if mysql is running using netstat<br>
check if mysql is running on correct port<br>
check mysql logs at /var/log<br>
check bind address configuration<br> 
make sure skip networking is disabled<br>
make sure socket is correct in /etc/my.cnf file<br>
is firewall blocking incoming mysql connections on port 3306?<br>
does user have correct privileges to mysql?<br>

<h4>Check if mysql is running</h4>
<pre>
ps aux | grep mysql
or
$ netstat -tap | grep mysql
</pre>

<h4>Restart Mysql</h4>
<pre>$ service mysql restart
or
$ service /etc/init.d/mysql restart
</pre>

<h4>Check if mysql is running on correct port</h4>
<pre>
$ less /etc/mysql/my.cnf
or
$ less /etc/mysql/my.ini
#if incorrect edit the file using nano and restart service 
</pre>

<h4>Check logs</h4>
<pre>
tail /var/log/mysql.err
tail /var/log/mysql.log
</pre>

<h4>Check bind address</h4>
<pre>
$ less /etc/mysql/my.cnf
or
$ less /etc/mysql/my.ini
#if bind-address=localhost; edit with nano, add your ip address or delete alltogether and restart
</pre>

<h4>Disable skip networking</h4>
<pre>
$ less /etc/mysql/my.cnf
or
$ less /etc/mysql/my.ini
#make sure skip-networking is commented out; if not, edit with nano and restart
</pre>


<h4>Check socket variable</h4>
<pre>
$ less /etc/mysql/my.cnf
or
$ less /etc/mysql/my.ini
# if socket= /var/lib/mysql/mysqld.sock is set to anything else edit with nano and restart service
</pre>


<h4>Grant user permission to connect to mysql</h4>
<pre>
$ msyql -u root -p
# enter pwd
> GRANT ALL PRIVILEGES ON *.* TO 'testuser'@'localhost';   #local
> GRANT ALL PRIVILEGES ON *.* TO 'testuser'@'%' IDENTIFIED BY 'password' WITH GRANT OPTION;  #remotely
> GRANT ALL PRIVILEGES ON testdatabase.* TO 'testuser'@'%';   #remotely on specific database
</pre>

<h4>Resetting root pwd</h4>
<pre>
$ service mysql stop   #ubuntu stop
or 
$ service /etc/init.d/mysqld stop   #rhel stop
$ mysqld_safe --skip-grant-tables &   #start mysql in safe mode
> mysql -u root   #login
> use mysql;  #use mysql database
> update user set password=PASSWORD("new password") where USER='root'
> flush privileges
> quit

$ service mysql stop   #ubuntu stop
or 
$ service /etc/init.d/mysqld stop   #rhel stop

$ service mysql start   #ubuntu start
or 
$ service /etc/init.d/mysqld start   #rhel start

$ mysql -u root -p
# login with new credentials
</pre>

<h4>Removing Mysql completely</h4>
<pre>
$ apt-get remove --purge mysql-server mysql-client mysql-common
$ apt-get autoremove
$ apt-get autoclean
# reinstall mysql
</pre>


























