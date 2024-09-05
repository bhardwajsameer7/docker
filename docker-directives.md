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
     
