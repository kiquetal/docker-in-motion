##### DockerFile

  A dockerfile is text file with a set of instructions to build a docker image.
  Recipe for baking a docker image.
 
    FROM ubuntu:16.10
    
    LABEL maintener  "kiquetal"
    
    RUN apt-get update && apt-get install -y curl
    
    RUN apt-get install -y git

 For build

    docker build -t my-image .
    docker build -f dir/Dockerfile -t my-image .

 Best practices
  
  Use less instructions for fewer layers.

    FROM ubuntu:16.10

    LABEL maintener  "kiquetal"
    
    RUN apt-get update \
          && apt-get install -y \
          && apt-get install -y git
    
  
