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
- `docker run -ti -v /home/docker/example:/shared_folder ubuntu bash`: Host machine's "/home/docker/example" folder can be accessed in the docker container using "/shared_folder" using `-v`
- `docker run -ti --volumes-from [CONTAINER_NAME] ubuntu bash`: New container will share folder from another container
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

## Volumes
- Virtual **discs** to store and share data
- Two main varieties:
    - *Persistent*: Where you can put data there, and it will be available on the host, and when the container goes away, the data will still be there.
    - *Ephemeral*: These exist as long as the container is using them. But when no container is using them, they evaporate. So they're sort of ephemeral. They'll stick around as long as they're being used but they're not permanent.
- Not part of images: No part of volumes will be included when you download an image and no part of volumes is gonna be involved if you upload an image. They're for your local data, local to this host.

## dockerfile
- Small program to create an image
- Create docker build file with name `Dockerfile`
- `docker build -t [NAME_OF_RESULT] .`: `-t` stands for tag. When you've finished building this thing, tag it with this name so that it's easy to find afterward. Dot (`.`) at the end specifies the location of docker file.

## Install docker
- https://docs.docker.com/engine/installation/

## Tutorial
- https://www.lynda.com/Docker-tutorials/Welcome/485649/514162-4.html