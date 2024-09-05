# Docker  Commands

## Login
1. docker login

## Image

1. **Pull image from dockerhub or Update Image :** docker pull <IMAGE_NAME>:<VERSION>
2. **List all the images :** docker images or docker image ls
3. **Delete image :** docker rmi <IMAGE_NAME>:<VERSION> | <IMAGE_ID> or docker image rm <IMAGE_NAME>:<VERSION> | <IMAGE_ID>
4. **Force delete docker image :** docker rmi -f <IMAGE_NAME>:<VERSION> | <IMAGE_ID>
5. **Create and give name to a custom image :** docker build -t <IMAGE_NAME>:<VERSION>  - < Dockerfile
6. **Delete all the images :** docker rmi $(docker images -q)
7. **Push image to Docker Registry :** docker push username/my-image:latest
8. **To know image history :** docker history <IMAGE_NAME>:<VERSION>
9. **Get information about image in JSON :** docker inspect <IMAGE_NAME>:<VERSION>
10. **Save image to tar :** docker save <IMAGE_NAME> > abc.tar
11. **Load image from tar :** docker load --input abc.tar
12. **Load image from a tarball :**: docker import my-image.tar my-new-image:latest
13. **Tags an image with a new name or tag, which is essentially a reference to the same image. :** docker tag my-image:latest username/my-image:1.0
 import

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
14. **Rename container :** docker rename <OLD_NAME> <NEW_NAME>

17. **Get information about container in JSON :** docker inspect <CONTAINER_NAME>:<VERSION>

17. attach commit cp create diff exec export

## Create vs Start vs Run vs Build

1. Start : is used to start a stopped docker container. doesn't create a new container.
2. Create : is used to create a new container from image but does not start container.
3. RUN : is used to create a container from image and start it.
4. BUILD : is used to create images from Dockerfile.

## Stop vs Pause

1. docker stop: Stops a container by sending termination signals to its processes, ultimately halting all activity and placing the container in a stopped state.

2. docker pause: Pauses a container by freezing its processes, maintaining its current state, and allowing you to resume it later with docker unpause.

3. Choose docker stop when you want to shut down a container, and choose docker pause when you need to temporarily halt a container's activity without stopping it entirely.

## Load vs Import
**1. Preservation of Image History:**

**docker import:** Does not preserve the image's build history or metadata. You end up with a new image without any historical layers.
**docker load:** Preserves the full image history, including all layers, metadata, and tags.

**2. Typical Use Cases:**

**docker import:** Used for creating Docker images from non-Docker filesystems or when you don’t need to retain the original image’s history.
**docker load:** Used for transferring complete Docker images, such as when moving an image between environments or restoring an image from a backup.

## Clean Environment
1. **Removes unused Docker objects like containers, networks, images, and volumes :** docker system prune

```
WARNING! This will remove:
  - all stopped containers
  - all networks not used by at least one container
  - all dangling images
  - unused build cache

Are you sure you want to continue? [y/N]
```


## Registry Command

1. **Search for specific image or group of images in docker registry based on KEY** : docker search <KEY>
2. **Limit search :** docker search -filter is-automated=true ubuntu

"is-automated=true" is a filter that limits the results to images that are automatically built by Docker Hub's Automated Build system.
Automated Build:

An automated build is an image that is automatically built by Docker Hub based on the Dockerfile hosted in a linked GitHub or Bitbucket repository. This ensures that the image is directly built from source code and is often considered more trustworthy because it’s less likely to be tampered with manually.

eg for official images: docker search --filter "is-official=true" nginx


  
