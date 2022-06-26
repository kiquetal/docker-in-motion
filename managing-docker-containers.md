#### Create container from image

    docker run -d -p 8080:8080 --name my-container -v /home/user/my-volume:/var/www/html my-image

    -i Keep STDIN open even if not attached
    -d Start container in detached mode
    -t Allocate a pseudo-TTY (inside the container)

#### How to create a container from an inbuilt image

    Remove all containers even if they are running.
    docker rm -f $(docker ps -aq)

    docker run -it hotwocodewell/manning-webserver-01:1.2 /bin/bash

#### How to name a container

    docker rename my-container my-new-container

#### How to remove a container

    docker rm -f my-container
    docker rm -f $(docker ps -aq)

#### How to start a container

    docker start my-container

#### How to stop a container

    docker stop my-container

#### How to restart a container

    docker restart my-container

