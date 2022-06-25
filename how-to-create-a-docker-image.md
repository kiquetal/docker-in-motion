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
    
    ENV DOC_ROOT /var/www/html
    ADD code/sites/mysite ${DOC_ROOT}/mysite
  

#### Difference between ADD and COPY
    For downloading and unzip use ADD
    

##### ARG VS ENV
    
    Prefer use args for build images
    
    ARG with the same name of ENV is not overwritten.


    docker build --build-arg DOC_ROOT=/var/www/html -t my-image .

    ARG JQUERY_VERSION=3.2.0
    ENV JQUERY_VERSION ${JQuERY_VERSION}


    IF ARG IS NOT EXISTS will raise an error.

  
  
