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
$ git config --global credential.helper "cache --timeout=3600"
</pre>

<h4>View username and email</h4>
<pre>
$ git config user.name
$ git config user.email
</pre>

<h4>HTTPS Remote Origin:</h4>
<pre>
# adding remote origin
$ git remote add origin https://github.com/user/repo.git

# reset remote origin
$ git remote set-url origin https://github.com/user/repo.git

# view remotes
$ git remote -v
</pre>

<h4>Cloning</h4>
<pre>
# clone into directory
$ git clone https://github.com/repo.git /opt/repo-folder
# clone with HTTPS
$ git clone https://github.com/username/repo.git
# clone with SSH
$ git clone git@github.com:username/repo.git
</pre>

<h4>Push</h4>
<pre>
$ git add --all # or git add .
$ git commit -m "first"
$ git push
</pre>
 
<h4>Pull changes</h4>
<pre>
$ git pull origin master
</pre>

<h4>Clone raw GitHub content</h4>
<pre>
$ curl -o https://raw.githubusercontent.com/username/path_to_file /output_path
</pre>

<h4>Resync .gitignore</h4>
<pre>
$ git rm -r --cached
$ git add --all # or git add .
$ git commit -m "resync"
$ git push
</pre>

<h4>Push Default message</h4>
<pre>
# gets rid of simple push error message
$ git config --global push.default simple
</pre>


