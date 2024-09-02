# Create basic docker image, build and run

## Create a docker file
**vi Dockerfile**
```
# Base image is ubuntu
# FROM, MAINTAINER, RUN, CMD are called DIRECTIVES.
FROM ubuntu

MAINTAINER sameer

RUN apt-get update

CMD ["echo","Basic Image"]

```

## Build Dockerfile
**docker build - < Dockerfile**

```
[+] Building 26.0s (6/6) FINISHED  docker:desktop-linux
 => [internal] load build definition from Dockerf  0.0s
 => => transferring dockerfile: 132B               0.0s
 => [internal] load metadata for docker.io/librar  2.1s
 => [internal] load .dockerignore                  0.0s
 => => transferring context: 2B                    0.0s
 => [1/2] FROM docker.io/library/ubuntu:latest@s  12.7s
 => => resolve docker.io/library/ubuntu:latest@sh  0.0s
 => => sha256:8a37d68f4f73ebf3d4e 1.34kB / 1.34kB  0.0s
 => => sha256:820a8779863b9b666fd1585 424B / 424B  0.0s
 => => sha256:1a799365aa63eed3c0e 2.31kB / 2.31kB  0.0s
 => => sha256:9f23a71f1e313efe 28.84MB / 28.84MB  10.5s
 => => extracting sha256:9f23a71f1e313efedd46a7ba  2.1s
 => [2/2] RUN apt-get update                      10.9s
 => exporting to image                             0.1s 
 => => exporting layers                            0.1s 
 => => writing image sha256:4a95be30e7541c869d441  0.0s 
```

## Check Docker images
**docker images**

```
REPOSITORY       TAG       IMAGE ID       CREATED         SIZE
<none>           <none>    4a95be30e754   8 minutes ago   140MB
```


