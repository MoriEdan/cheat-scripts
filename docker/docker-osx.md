Docker on OSX installation cheats
=================================

<h4>Installing boot2docker:</h4>
<pre>
# assumes homebrew is installed
# requires that you be root/admin to install
$ brew update
$ brew install boot2docker
</pre>

revert back to regular user

<h4>Install Docker:</h4>
<pre>
$ sudo curl -o docker https://get.docker.io/builds/Darwin/x86_64/docker-latest
$ sudo chmod +x ./docker
$ sudo mv docker ~/bin
$ export DOCKER_HOST=tcp://127.0.0.1:4243
$ docker -v #ensure its installed correctly

or

$ brew install docker
$ docker -v #ensure its installed correctly
</pre>


<h4>Initialize boot2docker VM:</h4>
<pre>
$ boot2docker init
$ boot2docker up
</pre>


<h4>Add path to bash_profile and source:</h4>
<pre>
$ nano ~/.bash_profile
# add to the file:
export DOCKER_HOST=tcp://127.0.0.1:4243
</pre>


<h4>Forward ports to Localhost:</h4>
<pre>
$ boot2docker ssh -L 8000:localhost:8000
</pre>
