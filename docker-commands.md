# Docker  Commands

## Image

1. **Pull image from dockerhub or Update Image :** docker pull <IMAGE_NAME>:<VERSION>
2. **List all the images :** docker images
3. **Delete image :** docker rmi <IMAGE_NAME>:<VERSION> | <IMAGE_ID>
4. **Force delete docker image :** docker rmi -f <IMAGE_NAME>:<VERSION> | <IMAGE_ID>
5. **Create and give name to a custom image :** docker build -t <IMAGE_NAME>:<VERSION>  - < Dockerfile
6. **Delete all the images :** docker rmi $(docker images -q)


## Container

1. **To create, run docker container interactively from image:** docker run -d --name <CONTAINER_NAME> -it <IMAGE_NAME>:<VERSION>

--it : iteractive mode
-d : detached mode or in background or daemon

2. **List all the containers running :** docker ps -a or docker container ls -a
3. **Stop container :** docker stop <CONTAINER_NAME> | <CONTAINER_ID>
4. **Start container :** docker start <CONTAINER_NAME> | <CONTAINER_ID>
5. **Pause container :** docker pause <CONTAINER_NAME> | <CONTAINER_ID>
6. **Unpause container :** docker unpause <CONTAINER_NAME> | <CONTAINER_ID>
7. **Restart conatainer :** docker restart <CONTAINER_NAME> | <CONTAINER_ID>
8. **Delete container :** docker rm <CONTAINER_NAME> | <CONTAINER_ID>
9. **Stop and delete a running container :** docker stop <CONTAINER_NAME> | <CONTAINER_ID> && docker rm <CONTAINER_NAME> | <CONTAINER_ID>
10. **Force Delete container :** docker rm -f <CONTAINER_NAME> | <CONTAINER_ID>
11. **Stop all the containers :** docker stop $(docker ps -q)
12. **Delete all the stopped containers :** docker rm $(docker ps -a -q)
13. **To kill docker container :** docker kill <CONTAINER_NAME> | <CONTAINER_ID>

## Create vs Start vs Run

1. Start : is used to start a stopped docker container. doesn't create a new container.
2. Create : is used to create a new container from image but does not start container.
3. RUN : is used to create a container from image and start it.

## Stop vs Pause

1. docker stop: Stops a container by sending termination signals to its processes, ultimately halting all activity and placing the container in a stopped state.

2. docker pause: Pauses a container by freezing its processes, maintaining its current state, and allowing you to resume it later with docker unpause.

3. Choose docker stop when you want to shut down a container, and choose docker pause when you need to temporarily halt a container's activity without stopping it entirely.







  
