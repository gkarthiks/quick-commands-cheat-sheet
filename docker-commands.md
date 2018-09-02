<img src="./images/docker.png">
| Command | Description|
|---------|------------|
`docker build -t <imagename> . `| Create image using this directory's Dockerfile
`docker run -p 4000:80 <imagename>` | Run "friendlyname" mapping port 4000 to 80
`docker run -d -p 4000:80 <imagename>` | Same thing, but in detached mode
`docker ps` | See a list of all running containers
`docker stop <hash>` | Gracefully stop the specified container
`docker ps -a` | See a list of all containers, even the ones not running
`docker kill <hash>` | Force shutdown of the specified container
`docker rm <hash>` | Remove the specified container from this machine
`docker rm $(docker ps -a -q) ` | Remove all containers from this machine
`docker images -a` | Show all images on this machine
`docker rmi <imagename>` | Remove the specified image from this machine
`docker rmi $(docker images -q)` | Remove all images from this machine
`docker login  ` | Log in this CLI session using your Docker credentials
`docker tag <image> username/repository:tag` | Tag <image> for upload to registry
`docker push username/repository:tag` | Upload tagged image to registry
`docker run username/repository:tag` | Run image from a registry
`docker build --force-rm -t ` | To remove all the intermediate
`docker stack deploy -c docker-compose.yml <stack_name>` | To deploy the docker-compose for deploying the Swarm
`docker swarm init` | To initialize the swarm
`docker stack ps <stack_name>` | To see the list of services started in the defined stack
`docker node ls` | To see the node
`docker stack rm <stack_name>` | Tear down an application #To takedown the app
`docker swarm leave --force` | To take down the swarm
`docker stack ls` | List all running applications on this Docker host
`docker stack services <appname>` | List the services associated with an app
`docker run -v /var/run/docker.sock:/var/run/docker.sock --rm dduvnjak/dockerfile-from-image <image_id>` | Revers engineers the Dockerfile from the image.
`docker image prune` | Removes all dangling images
`docker volume prune` | Removes all unattached docker volumes
