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

#### How to run a command against a container

    docker run -it my-container /bin/bash

#### How to get into a container

    docker exec -it my-container /bin/bash

    docker exec -u root -it my-container /bin/bash

#### Using files in a docker container

    docker run -it -v /home/user/my-volume:/var/www/html my-image /bin/bash

#### How to create a volume
    docker volume create my-volume
#### How to create a network
    docker network create my-network
#### How to link a container to a network
    docker network connect my-network my-container

#### Different cmd instructions

    CMD [ "EXEC","PARAM1"]
    CMD command --param1 --param2

#### History of a container
    docker history my-container

#### 
