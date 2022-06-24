### Introduction to docker.
##### Annotations
Should only handle one process in the system.

Use container linking.

Can be stop/destroy.

Use volume.

Configuration should be injected in the environment.

##### Container Exercise I

    docker run -d -p 8080:8080 --name my-container -v /home/user/my-volume:/var/www/html my-image




