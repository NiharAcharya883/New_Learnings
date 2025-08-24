# Docker commands

--> docker run it --ubuntu
(Downloads the image of ubuntu and then build a container)

--> docker pull <image-name>  (pull a docker image from docker hub if not present in local)

--> docker images (view all the images)

--> docker run <image-name>  (create docker container from image)

--> docker run -it <image-name> (create docker container in interative mode)

--> docker ps -a (check all the containers)

--> docker ps (check all running containers)

--> docker start CONT_NAME or CONT_ID  (restart existing container)

--> docker stop CONT_NAME or CONT_ID  (stop running container)

--> docker rmi <image-name> (remove/destroy docker image) (must delete container first)

--> docker rm <container-name> (remove/destroy the container)

--> docker pull mysql:<version>  (pulls a specific version of the image)

--> docker run -d <image-name> (run a container in detach mode, ie. it runs in background)

--> docker run -d -e MYSQL_ROOT_PASSWORD=secret mysql (used to pass env variales to the container)

--> docker run -d --name <custom-name> image_name (can give custom name to our container)

--> docker run -p 8080:3306 <image-name>  (Port binding) (host-port : container-port) (ports of host machines must be different)


# Troubleshoot commands
--> docker logs CONT_ID  (can check the logs of a conatainer)

--> docker exec -it CONT_ID /bin/bash  (run additional commands on a existing running container) (can check the env variables)

--> docker exec -it CONT_ID /bin/sh


# Network commands
--> docker network ls  (list all networks)
--> docker network create <name>
--> docker rm <name> (delete a network)


--> docker run -d -p 27017:27017 --name mongo -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=qwerty --network mongo-network mongo  (create mongo container)

--> docker run -d -p 8081:8081 --name mongo-express -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=qwerty -e ME_CONFIG_MONGODB_URL-"mongodb://admin:qwerty@mongo:27017" --network mongo-network mongo-express  (create mongo express container)


# docker compose commands
--> docker compose -f file.Name.yaml up -d (run and start containers in docker-compose file in detach mode)
--> docker compose -f file.Name.yaml down -d (remove containers in docker-compose file in detach mode)


# dockerizing our App
--> docker build -t <image_name_u_want>:<version eg-(1.0)> .    (building image)
--> docker run -it <image_name>   (running container) 


# Publish images
--> docker login -u <username>  (then enter password)
--> docker push <image-name> (pushing image to repository in docker hub)
--> docker logout

# docker volume
--> docker run -it -v host-path:container_path ubuntu
--> docker volume ls (list all volumes)
--> docker volume create VOL_NAME (create volume)
--> docker volumn rm VOL_NAME  (remove volume)
--> docker volume prune  (remove unused local containers, targets anonymous volumes)