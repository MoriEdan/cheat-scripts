NVM (Node version manager) cheats
=================================

<h4>Create non-root user & add to sudoers:</h4>
<pre>
$ useradd -d /home/ -s /bin/bash  -m node-user
$ passwd node-user
$ su root 
$ sudo adduser node-user sudo
$ su node-user
</pre>

<h4>Install:</h4>
<pre>
$ apt-get update
$ chown node-user /home
$ sudo apt-get install g++ curl libssl-dev apache2-utils git-core
$ curl https://raw.github.com/creationix/nvm/master/install.sh | sh
</pre>

<h4>Activate NVM:</h4>
<pre>
$ source ~/.nvm/nvm.sh
</pre>

<h4>Install Node.js</h4>
<pre>
$ nvm install <version>
$ nvm alias default <version>
</pre>
