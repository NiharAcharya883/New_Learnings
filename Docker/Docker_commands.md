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