# Docker Directives

1. FROM
2. LABEL
3. MAINTAINER
4. **RUN :** will create a new layer on top current layer, run the command & save the result to newly generated layer.
5. **CMD :** used to give commad to container.
- Docker file can have only 1 CMD command.
- Also used to provide default instruction. this command is executed when container is created from image.
- CMD command is overriden by RUN commad when we run a container using docker run.

## RUN vs CMD

- RUN is executed during image build phase while CMD is executed when container is lauched from the built image.
- There can be multiple RUN commads in image while there can only be 1 CMD per Dockerfile. if multiple CMD commads are present then only last one will be executed.

6. **ARG : (Build Time Variable)** These are the variable that can be passed to image build process. **ARG** is only Directive that can come before **FROM** directive.

docker build -t <image>:<tag> --build-arg <variable>=<value>

Dockerfile

```
ARG USER
ARG VERSION
FROM ubuntu
...
....
```

7. **ENV :** To create environment variable in container.
ENV <KEY> <VALUE>
```
ENV JAVA_HOME /opt/java/
```
8. **ENTRYPOINT :**
9. **WORKDIR :** To define docker container's current working directory. if directory is not present then docker will make and go in directory using mkdir and cd.

WORKDIR /opt/home/

10. **COPY : (Build Time)** To copy files from local system to docker image system at build time.
COPY <source> <destination>

11. **ADD : (Build Time)**  To  download file from URL and copy it from local to docker file system.
ADD <source> <destnation>

12. *USER :** To add a non-root user.
- Docker uses root as default user.
- any command afer USER directive is executed by USER.

13. **VOLUME :**
14. **EXPOSE : **

    
