Log File command cheats
=======================

<p>
Log files located at /var/log
</p>

<h4>Log file commands</h4>
<pre>
$ tail -n 20 /var/log/cron   #prints out the last 20 lines of the cron file

$ cat fail2ban.log auth.log > custom.log   #concatenates the two log files into a custom log file
$ tail -f custom.log   #monitors the new custom log in real time

$ cat custom.log | grep fail  #cats the new log and pipes the stdout to grep and seachess for 'fail'
$ cat custom.log | BREAK-IN   #searches the stdout for 'BREAK-IN'
$ cat custom.log | grep fail | grep authentication  #cats the log file and pipes one grep stdout to another
</pre>
