Docker cheats
=============


<h4>Docker Commands:

docker images #lists all images 
docker ps # lists running docker processes
docker ps -l #lists all containers running or not
docker ps -a #lists all containers running or not


Container Commands:
docker stop <container-id>
docker run <container-id>
docker rm <container-id> #remove


Launching & Interacting with Containers:
sudo docker run -i -t ubuntu /bin/bash #interactive tty shell 
sudo docker run -d -t -p 80:80 ubuntu /start.sh #run daemonized and expose port 80



Committing: 
docker commit 36e9e0129149 ubuntu-test #commits container to image





Destructive Commands:
sudo docker ps -a -q | sudo xargs docker rm #removes all containers
sudo docker rmi `sudo docker images -q` #removes all images


