Go language Ubuntu install cheats
=================================

<h4>Install</h4>
<pre>
$ wget https://storage.googleapis.com/golang/go1.2.2.linux-amd64.tar.gz
$ tar -C /usr/local -xzf go1.2.2.linux-amd64.tar.gz

$ nano ~/.profile
# add to the file:
export PATH=$PATH:/usr/local/go/bin

$ source ~/.profile
$ go version    #check to make sure its installed 
</pre>
