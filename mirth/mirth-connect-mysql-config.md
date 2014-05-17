MySql Mirth Connect db configuration cheats
===========================================

<h4>MySql Installation</h4>
<pre>
$ top   #make sure mysqld is not running ie Docker container etc
$ apt-get install mysql-server mysql-client
# set up root pwd and uname
$ service mysql start
</pre>

<h4>Create Mirth database</h4>
<pre>
$ mysql -u root -p
mysql> CREATE DATABASE mirthdb DEFAULT CHARACTER SET utf8;
mysql> GRANT ALL ON mirthdb.* TO mirthuser@'localhost' IDENTIFIED BY 'pass' WITH GRANT OPTION;
mysql> GRANT ALL ON mirthdb.* TO mirthuser@'%' IDENTIFIED BY 'pass' WITH GRANT OPTION;
mysql> quit;
</pre>

<h4>MySql Database Configuration</h4>
<pre>
$ ./mcservice stop
$ top   #find pid for mcserver 
$ kill -SIGKILL pid
$ cd /opt/Mirth\ Connect/conf
$ nano mirth.properties
# edit in the file:

database = mysql
database.url = jdbc:mysql://localhost:3306/mirthdb   
database.username = mirthuser
database.password = pass

$ ./mcserver start
$ ./mcservice start
# database schema will be created

$ mysql -u root -p
mysql> SHOW TABLES FROM mirthdb;
# verify that the schema is correct
</pre>

