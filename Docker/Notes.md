# Docker
--> Platform that enables developers to build, ship and run applications inside containers.
--> Containers are lightweight, self sufficient, portable environments that include everything needed to run a piece of software: code, runtime , libraries , env variables and config files.


# Docker container
--> It is a runtime instance of a Docker image.
--> It is a live, running environment created from an image. You can start, stop, move abd delete containers.
--> Portable
--> Lightweight (very less overhead)
--> Isolated




# Docker image
--> It is a read only template that contains the instructions for creating a Docker container.
--> It is a bluprint or snapshot of your application and its dependencies.
--> It is immutable and reusable.
--> Executable file - to build docker container
--> A Dockerfile is usually used to define how the image is built.


--> docker image sare build of different layers. (base layer at the bottom and container layer is at the top)

# Difference between Docker and virtual machine
--> docker only virtualizes application layer while VM virtualizes both application layer and Host OS Kernel


# Docker Network
--> Docker has networking model to connect containers, such that they can communicate with each other.
--> bridge (default for containers) - if don't specify network, containers connect here. 
--> bridge driver ()


# Docker compose
--> It is a tool for defining and running multiple-container applications.
--> docker-compose.yaml
--> All the containers in the docker compose file will be created in the same network.
Example :-  

version: "3.8"
services:
    mongo:
        image:mongo
        ports:
        -27017:27017
        environment:
        -MONGO_INITDB_ROOT_USERNAME=admin  or
            MONGO_INITDB_ROOT_USERNAME:admin
        -MONGO_INITDB_ROOT_PASSWORD=qwerty

    mongo-express:
        image:mongo-express
        ports:
        -8081:8081
        environment:
            ME_CONFIG_MONGODB_USERNAME:admin


# Dockerizing our App
test_app ---> docker_image ---> container   (through Dockerfile)
--> important Dockerfile instructions
FROM <base_image>
WORKDIR (path in the image where files will be copied and commands will be executed)
COPY  (host to image)
RUN   (tells builder to run specific command)
CMD   (sets the default command container using this image will run)
EXPOSE  (expose image ports)
ENV  (define environement variables)



# Docker Volumes
--> Volumes are persistent data stores for containers.
--> If we restart/delete our docker containers, data present in it will be lost. So must store them in volumes.
--> we can map multiple containers to same volume.