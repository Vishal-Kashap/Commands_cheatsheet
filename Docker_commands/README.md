# Docker Basic Commands


#### To download images from docker hub.
Let’s say you need to pull the docker image from dockerhub (docker repository). The following example of pulling the Apache HTTP server image.

             docker pull httpd

#### To list docker images,
List all the docker images pulled on the system with image details such as TAG/IMAGE ID/SIZE etc.

           docker images

#### To run docker image,
Run the docker image mentioned in the command. This command will create a docker container in which the Apache HTTP server will run.
 
          docker run -it -d httpd

#### To check what's running.means list only active containers.
ps lists all the docker containers running with container details.

         docker ps

#### To check what's running or stopped.means list all containers.
List all the docker containers running/exited/stopped with container details.

         docker ps -a

#### Execute a new process in an existing container. Access the docker container and run commands inside the container. I am accessing the apache server container in this example.

        docker exec -it container_id bash

#### stop a container.
 
       docker stop [container-name|container-id]

#### Stopacontainer(timeout=1second)

       docker stop -t1

#### remove a container.
 
        docker rm [container-name|container-id]

#### Force stop and remove a container.

        docker rm -f [container-name|container-id]

#### remove all containers.

        docker rm -f $(docker ps-aq)

#### remove all stopped containers.

        docker rm $(docker ps -q -f “status=exited”)

#### Starting docker,
This command in docker starts the docker container with the container id mentioned in the command.

        docker start container_id

#### Removing image,
Remove the docker image with the docker image id mentioned in the command.

        docker rmi image_id

#### Kill
Stop the docker container immediately. Docker stop command stops the container gracefully, that’s the difference between a kill and stop commands.

         docker kill container_id

#### To show as container ids by using this command,

          docker ps -qa

#### To kill all running containers.

         docker kill $(docekr ps -q ) 

#### Stop all container in one time by using this command,
 
          docker stop $(docker ps -q)       (be carefully use it)

#### Run a container in detached mode,

         docker run --name name -d -p 8000:80 image_name

#### Follow the logs of a specific container.

         docker logs -f [container-name|container-id]

####################################################### BUILD DOCKERFILE ##############################################################
#### Build an image using a Dockerfile.  

        docker build -t myimage:latest .

#### Check the history of an image:

        docker history [username/]<image-name>[:tag]

#### list an images,

        docker images

#### tag an image .

        docker tag <image-name> <new-image-name>

#### push an image to a registry,

        docker push username/image_name

#### Login to a container registry server.If no server is specified then default is used

       docker login

#### To see more information about container on a volume.

        docker inspect container_id

#### To see CPU utilization contains docker.

       docker stats

#### TO tell free space in system,

      docker system df

######################################################### CREAT AND MANAGE VOLUMES ###############################################################

#### create a volume.

     docker volume create my-vol

#### list volumes.

     docker volume ls

#### inspect a volume.

     docker volume inspect my-vol

#### Remove a volume.  

      docker volume rm my-vol

####################################################### DOCKER CLEANUP #####################################################################

#### Prune images; ( To clean or prune unused (dangling ) images.
The docker image prune command allows you to clean up unused images. By default, docker image prune only cleans up dangling images. A dangling image is one that is not tagged and is not referenced by any container. To remove dangling images:
  
       docker image prune

#### To remove all images which are not used by existing containers, use the -a flag:

       docker image prune -a

#### By default, you are prompted to continue. To bypass the prompt, use the -f or --force flag.
You can limit which images are pruned using filtering expressions with the --filter flag. For example, to only consider images created more than 24 hours ago:

       docker image prune -a --filter "until=24h"

#### Prune Containers;
When you stop a container, it is not automatically removed unless you started it with the --rm flag. To see all containers on the Docker host, including stopped containers, use docker ps -a. You may be surprised how many containers exist, especially on a development system! A stopped container’s writable layers still take up disk space. To clean this up, you can use the docker container prune command.

        docker container prune

#### By default, all stopped containers are removed. You can limit the scope using the --filter flag. For instance, the following command only removes stopped containers older than 24 hours:

        docker container prune --filter "until=24h"

#### Prune volumes;
Volumes can be used by one or more containers, and take up space on the Docker host. Volumes are never removed automatically, because to do so could destroy data.

        docker volume prune

#### By default, all unused volumes are removed. You can limit the scope using the --filter flag. For instance, the following command only removes volumes which are not labelled with the keep label:

        docker volume prune --filter "label!=keep"

#### Prune everything:
The docker system prune command is a shortcut that prunes images, containers, and networks. Volumes are not pruned by default, and you must specify the --volumes flag for docker system prune to prune volumes.

          docker system prune

#### To also prune volumes, add the --volumes flag:

         docker system prune --volumes

################################################################## DOCKER-COMPOSE #######################################################

#### Start all services

          docker-compose up

#### If you want to remove the containers, networks, and volumes associated with this containerized environment, use the down command:

          docker-compose down

#### Run Docker Compose file.

          docker-compose up -d

#### list the entire process.

          docker ps

#### scale a service.

          docker-compose up -d -scale 

#### If you want to pause the environment execution without changing the current state of your containers, you can use:

          docker-compose pause

#### To resume execution after issuing a pause:

          docker-compose unpause

#### The stop command will terminate the container execution, but it won’t destroy any data associated with your containers:

             docker-compose stop

############################################################### END ########################################################################
  
