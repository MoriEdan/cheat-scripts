Linxu system commmands cheats
=============================

NT 5.1 XP<br>
NT 5.2 XP 64bit, Server 2003 and R2<br>
NT 6.0 Vista, Server 08<br>
NT 6.1 Windows 7, Server 08 r2<br>
NT 6.2 Windows 8, Server 2012<br>

<h4>System Commmands:</h4>
<pre>
ver   #os version
echo %USERNAME%    #current user

sc query state=all   #show all services

tasklist /svc   #show processes and services
tasklist /m    #show processes and dlls
taskkill /PID pid /F   #kill specifc process

reg query HKLM /f password /t REG_SZ /s  #search registry for pwd
fsutil fsinfo drives   #list drives and info

dir /a /s /b c:\ *.pdf*   #search file system for all pdf’s
dir /a /b c:\ windows\kb*   #search for all installed patches
findstr /si password * .txt | *.xml | *.xls   #search certain file types for password string
tree /F /A c:\ > directory.txt   #exports full directroy tree of C:\

reg save HKLM\Security security.hive   #dumps security hive
</pr>

<h4>Networking Commands</h4>
<pre>
ipconfig /displaydns   #local DNS cahce
netstat -ano   #open connections
netstat -an! findstr LISTENING   #listening ports
route print   #routing table
arp -a   #arp table
netsh wlan show profiles   #wireless profiles
netsh wlan export profile folder=. key=clear   #export wifi pwd
</pre>












