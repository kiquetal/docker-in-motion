##### Structure of a Docker Compose File

   docker-compose.yml

    version: "3"
    services:
        web:
            image: ubuntu:latest
            ports:
                - "80:80"
            volumes:
                - ./:/var/www/html
            links:
                - mysql
            environment:
                - MYSQL_ROOT_PASSWORD=root
                - MYSQL_DATABASE=my-database
                - MYSQL_USER=my-user
                - MYSQL_PASSWORD=my-password
            command: ["/bin/bash"]
            entrypoint: ["/bin/bash", "-c", "while true; do sleep 1; done"]
        mysql:
            image: mysql:5.7
            ports:
                - "3306:3306"
            environment:
                - MYSQL_ROOT_PASSWORD=root
                - MYSQL_DATABASE=my-database
                - MYSQL_USER=my-user
                - MYSQL_PASSWORD=my-password
            volumes:
                - ./data:/var/lib/mysql
                - db-data:/var/lib/mysql/my-database
            command: ["/bin/bash"]
            entrypoint: ["/bin/bash", "-c", "while true; do sleep 1; done"]
        
    volumes:
        db-data:
