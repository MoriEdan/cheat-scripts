Docker on OSX installation cheats


Installing boot2docker:
# assumes homebrew is installed
# requires that you be root/admin to install
$ brew update
$ brew install boot2docker

revert back to regular user

Install Docker:
$ sudo curl -o docker https://get.docker.io/builds/Darwin/x86_64/docker-latest
$ sudo chmod +x ./docker
$ sudo mv docker ~/bin
$ export DOCKER_HOST=tcp://127.0.0.1:4243
$ docker -v #ensure its installed correctly

or
$ brew install docker
$ docker -v #ensure its installed correctly


Initialize boot2docker VM:
$ boot2docker init
$ boot2docker up

Add path to bash_profile and source:
$ nano ~/.bash_profile
add to the file:
export DOCKER_HOST=tcp://127.0.0.1:4243


Forward ports to Localhost:
$ boot2docker ssh -L 8000:localhost:8000
