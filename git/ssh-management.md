Git SSH management cheats
=========================

<h4>Create SSH keys:</h4>
<pre>
$ ssh-keygen -t rsa     #will be located in ~/.ssh
</pre>

<h4>Change Remote Origin for SSH</h4>
<pre>
$ nano .git/config:
change:
[remote "origin"]
        url = ssh://git@bitbucket.org/user/repo.git
        fetch = +refs/heads/*:refs/remotes/origin/*

</pre>

<h4>SSH-agent</h4>
<pre>
$ eval $(ssh-agent)       #start the ssh agent
$ ssh-add       #add private key to the agent

ssh-agent -k    # kills the agent
</pre>


<h4>Auto start SSH agent with new session:</h4>
<pre>
$ nano ~/.bashrc
# add to the file and source:
SSH_ENV=$HOME/.ssh/environment

# start the ssh-agent
function start_agent {
    echo "Initializing new SSH agent..."
    # spawn ssh-agent
    /usr/bin/ssh-agent | sed 's/^echo/#echo/' > ${SSH_ENV}
    echo succeeded
    chmod 600 ${SSH_ENV}
    . ${SSH_ENV} > /dev/null
    /usr/bin/ssh-add
}

if [ -f "${SSH_ENV}" ]; then
     . ${SSH_ENV} > /dev/null
     ps -ef | grep ${SSH_AGENT_PID} | grep ssh-agent$ > /dev/null || {
        start_agent;
    }
else
    start_agent;
fi
</pre>
