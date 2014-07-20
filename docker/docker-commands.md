Docker cheats
=============


<h4>Docker Commands:</h4>
<pre>
docker images   #lists all images 
docker ps   #lists running docker processes
docker ps -l  #lists all containers running or not
docker ps -a  #lists all containers running or not
</pre>

<h4>Container Commands:</h4>
<pre>
docker stop <container-id>
docker run <container-id>
docker rm <container-id> #remove
</pre>

<h4>Launching & Interacting with Containers:</h4>
<pre>
sudo docker run -i -t ubuntu /bin/bash #interactive tty shell 
sudo docker run -d -t -p 80:80 ubuntu /start.sh #run daemonized and expose port 80
</pre>

<h4>Committing:</h4>
<pre>
docker commit 36e9e0129149 ubuntu-test  #commits container to image
</pre>

<h4>Logging:</h4>
<pre>
docker logs container_name
docker logs -f container_name   #similar to tail -f
docker top container_id   #shows running processes in container
</pre>

<h4>Ports:</h4>
<pre>
docker port container_name port_number
</pre>

<h4>Destructive Commands:</h4>
<pre>
sudo docker ps -a -q | sudo xargs docker rm   #removes all containers
docker rmi image_id   #removes single image
sudo docker rmi `sudo docker images -q`   #removes all images
</pre>
