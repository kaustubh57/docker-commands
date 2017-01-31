# docker-commands
------------------

## Basic commands
- `docker --version`
- `docker commit [CONTAINER_ID]`: Create new image from container
- `docker tag [IMAGE_D] [IMAGE_NAME]`: Tag name to the image

## Image specific commands
- `docker images`: List images
- `docker run [IMAGE_NAME]`: Run the docker image
- `docker run --detach [IMAGE_NAME]`: Run image in the background
- `docker run --publish [FORWARD_PORT]:[CONTAINER_PORT] [IMAGE_NAME]`: Run image with the published port
- `docker rmi [IMAGE_ID]`: Remove image

## Container specific commands
- `docker ps -a`: List all containers
- `docker start [CONTAINER_ID]`: Start container with id
- `docker stop [CONTAINER_ID]`: Stop container with id
- `docker rm [CONTAINER_ID]`: Remove container with id

## Other commands

## Install docker
- https://docs.docker.com/engine/installation/