# docker-commands
------------------

## Basic commands
- `docker --version`
- `docker commit [CONTAINER_ID] [NEW_IMAGE_NAME]:[TAG_NAME]`: Create new image from container
- `docker tag [IMAGE_D] [IMAGE_NAME]`: Tag name to the image

## Image specific commands
- `docker pull`: To get images
- `docker push`: To push images to the repository
- `docker images`: List images
- `docker run [IMAGE_NAME]`: Run the docker image
- `docker run --detach [IMAGE_NAME]`: Run image in the background
- `docker run --publish (or -p) [FORWARD_PORT]:[CONTAINER_PORT] [IMAGE_NAME]`: Run image with the published port
- `docker run --memory maximul-allowed-memory [IMAGE_NAME]`: Memory limits parameter - `--memory`
- `docker run --cpu-shares [IMAGE_NAME]`: CPU limits parameter - `--cpu-shares` relative to other containers
- `docker run --cpu-quota [IMAGE_NAME]`: hard limits. e.g. Container only gets to use 10% of the total CPU, even if 90% of the CPU time is idle
- `docker rmi [IMAGE_ID]`: Remove image by id
- `docker rmi [IMAGE_NAME]:[TAG_NAME]`: Remove image by name and tag name

## Container specific commands
- `docker ps -a`: List all containers
- `docker start [CONTAINER_ID]`: Start container with id
- `docker stop [CONTAINER_ID]`: Stop container with id
- `docker attach [CONTAINER_NAME]`: Attach (or get in to) the container with name
    - To detach from the container, hit `control P`, `control Q,` it exits you out of the container by detaching you from it, but leaves it running, so that you can attach back again and pick up where you left off.
- `docker exec [CONTAINER_NAME] [COMMAND]`: Execute the command in the running container.
- `docker exec -ti [CONTAINER_NAME] [COMMAND]`: Similar to above command. `t`: Allocate a pseudo-TTY and `i`: Keep STDIN open even if not attached
- `docker kill [CONTAINER_ANEM]`: Kill (or stop) the container
- `docker rm [CONTAINER_ID]`: Remove container with id

## Networking commands
- `docker port [CONTAINER_NAME]`: Show ports for that container
- `docker run --rm -ti --link [CONTAINER_NAME] --name [NEW_MACHINE's_CONTAINER_NAME] ubuntu`: To link new machine with previous container using `--link`
- `docker network create [NETWORK_NAME]`: Create private docker network
- `docker run --rm -ti --net=[DOCKER_PRIVATE_NETWORK_NAME] --name [NEW_CONTAINER_NAME] ubuntu`: Joint new container to the docker's private network using `--net`

## Other commands
- `docker logs [CONTAINER_NAME]`: Check logs of the docker container 

## Install docker
- https://docs.docker.com/engine/installation/