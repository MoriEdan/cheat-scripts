Git command cheats
================================

<h4>Install</h4>
<pre>
$ apt-get install git
</pre>


<h4>Identity Configuration:</h4>
<pre>
$ git config --global user.name your_username
$ git config --global user.email your_email address
</pre>

<h4>View username and email</h4>
<pre>
$ git config user.name
$ git config user.email
</pre>

<h4>Remote Origin:</h4>
<pre>
# adding remote origin
$ git remote add origin https://github.com/user/repo.git

# reset remote origin
$ git remote set-url origin git://new.url.here

# view remotes
$ git remote -v
</pre>


<h4>Resync .gitignore</h4>
<pre>
$ git rm -r --cached
$ git add --all # or git add .
$ git commit -m "resync"
$ git push
</pre>

<h4>Push: </h4>
<pre>
$ git add --all # or git add .
$ git commit -m "first"
$ git push
</pre>
 
<h4>Cloning:</h4>
<pre>
# clone into directory
$ git clone https://github.com/repo.git /opt/repo-folder
</pre>

<h4>Add Existing Repo to Github: </h4>
<pre>
$ git init
$ git add --all
$ git commit -m "adding new"
$ git remote add origin https://github.com/user/repo.git
$ git push origin master
</pre>


<h4>Push Default message</h4>
<pre>
# gets rid of simple push error message
$ git config --global push.default simple
</pre>


