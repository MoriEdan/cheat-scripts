Cron & Crontab cheats
=====================

<p>
Locations:<br>
/etc/crontab   #editable only by root<br>
/var/spool/cron   #location of user cron<br>
/var/log/syslog   #location of cron logs in ubuntu<br>
</p>

<h4>Edit Crontab</h4>
<pre>
$ crontab -e   #opens the user crontab file for editing
</pre>

<h4>Crontab construction</h4>
<pre>
*/1    *    *     *    *    #runs every minute, hour, day and month 
*/1    2,6  *     *    *    #runs every minute on hours 2 and 6 every day every month
*/1    2-6  *     *    *    #runs every minute between hrs 2 & 6 every day every month
*/1    *    1     *    *    #runs every minute, every where on first day of every month
*/1    *    *     *    5    #runs every minute, every hour, every day, every month on Friday
*/1    /3   *     *    *    #runs every minute on every 3rd day


*/1    *    *     *    5 echo 'test' >> test.txt 
#runs every minute, hour, day, month on friday and executes a command
</pre>
