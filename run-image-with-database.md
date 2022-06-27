#### How to link containers

    The name of the containers will be used as the hostname

#### Link
    
    docker run --name web-server -p 80:80 --link mysql

#### Create network
    
    docker network create -d bridge my-network
    
#### Connect to network
    
    docker network connect my-network web-server
