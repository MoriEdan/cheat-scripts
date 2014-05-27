Go Mac OSX install cheats
=========================

<h4>Install Go</h4>
<p>
Download most current package:
https://storage.googleapis.com/golang/go1.2.2.darwin-amd64-osx10.8.pkg
</p>

<h4>Create Workspace</h4>
<pre>
mkdir ~/workspace
</pre>

<h4>PATH variables</h4>
<pre>
$ nano ~/.bash_profile
# add to the file:

export GOPATH="$HOME/workspace"
export PATH=$PATH:$GOPATH/bin 

$ source ~/.bash_profile
</pre>
