##### Remove unused images

        docker image rm <image_id>
        docker rmi <image_id>
        
        docker images -q  | xargs docker rmi
        docker rmi $(docker images -q)

        docker rm $(docker ps -a -q)

#### Docker tag for remote repository

    docker tag source_image[:tag] target_image[:tag]

#### Log into docker regsitry

    docker login -u <username> -p <password> registry.domain.com

#### Push docker image

    docker tag <local_image>:<tag> <repository>/<remote_image>:<tag>
    docker push registry.domain.com/my-image:<tag>

#### Pull docker image

    docker pull registry.domain.com/my-image:<tag>

#### How to update a docker image    
    
    docker pull registry.domain.com/my-image:<tag>
    docker tag registry.domain.com/my-image:<tag> 
    docker push registry.domain.com/my-image:<tag>
