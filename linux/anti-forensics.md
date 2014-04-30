Linux anti-forensics cheats
===========================

<pre>
unset HISTFILE   #must log out after setting
export HISTFILESIZE=0   #sets history max lines to 0
export HISTSIZE=0   #sets history max commands to 0
echo "" > /var/log/auth.log   #clear auth.log 
echo "" > /~.bash_history   #clear bash history of current user
rm ~/.bash_history -rf   #delete bash history file
history -c   #clear current session history
ln /dev/null ~/.bash_history -sf   #permantly send all bash history commands to dev null
</pre>

