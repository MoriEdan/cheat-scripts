Windows system commmands cheats
=============================

NT 5.1 XP<br>
NT 5.2 XP 64bit, Server 2003 and R2<br>
NT 6.0 Vista, Server 08<br>
NT 6.1 Windows 7, Server 08 r2<br>
NT 6.2 Windows 8, Server 2012<br>

<h4>Services & Proccesses:</h4>
<pre>
ver   #os version
echo %USERNAME%    #current user
sc query state=all   #show all services
tasklist /svc   #show processes and services
tasklist /m    #show processes and dlls
taskkill /PID pid /F   #kill specifc process
restart /r /t 0   #restart now
cmd.exe "wevutil qe Application /c:40 /f:text /rd:true"    #cli event viewer
lusrmgr.msc    #local user mgr
services.msc    #services control panel
taskmgr.exe    #task mgr
secpool.msc    #security policy mgr
eventvwr.msc   #event viewer
rund1132.dll user32.dll LockWorkstation    #lock workstation
reg add HKCU\Software\Policies\Microsoft\Windows\System /v DisableCMD /t REG_DWORD /d 0 /f   #re-enable command prompt
</pre>

<h4>Networking Commands:</h4>
<pre>
ipconfig /displaydns   #local DNS cahce
netstat -ano   #open connections
netstat -an! findstr LISTENING   #listening ports
route print   #routing table
arp -a   #arp table
netsh wlan show profiles   #wireless profiles
netsh wlan export profile folder=. key=clear   #export wifi pwd
</pre>

<h4>File System:</h4>
<pre>
dir /a /s /b c:\ *.pdf*   #search file system for all pdf’s
findstr /si password * .txt | *.xml | *.xls   #search certain file types for password string
find /I "string" file   #find "string" in the file 
fsutil fsinfo drives   #list drives and info
del path\*.* /a /s /q /f    #remove all files in path
dir /a /b c:\ windows\kb*   #search for all installed patches
tree /F /A c:\ > directory.txt   #exports full directroy tree of C:\
</pre>

<h4>Registry</h4>
<pre>
reg query HKLM /f password /t REG_SZ /s  #search registry for pwd
reg save HKLM\Security security.hive   #dumps security hive
</pre>


