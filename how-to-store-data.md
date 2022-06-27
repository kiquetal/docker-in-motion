#### Store data

  - Docker Volume
  - Bind mount
  - tmpfs

#### Docker Volume

    Using dockerArea within the host machine.
    Attach and share with different containers.

  docker volume create my-volume    
  
  docker run --name vol-test -v my-volume:/var/www/html ubuntu
  
  docker volume inspect my-volume

    
#### Bind mount

    Direct connection to the host filesystem.
    Can´t be shared with other containers.    

    docker run -d -p 8080:8080 --name my-container -v /home/user/my-volume:/var/www/html my-image
    Could be use directly from the host.
#### tmpfs

    Temporary filesystem.
    Used for caching.
    For non persistent data.


#### Copy from file's host to a volume
    docker cp /home/user/my-volume/index.html app-container:/var/www/html/index.html

#### Copy from container to file's host
    docker cp app-container:/var/www/html/index.html /home/user/my-volume/index

#### Share volume between containers
    
    docker run --name apache2 --link mysql -p 80:80 -v my-volume:/var/log/apache2 -d apache2
    docker run -it --name log_checker --volumes-from apache2 ubuntu
