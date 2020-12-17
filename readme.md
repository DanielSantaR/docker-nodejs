# Docker, nodejs, mongodb, express and swagger API

This project is an API built using docker, nodejs, mongodb, express and swagger. 

## Pre-requisites
* Git - [Installation guide here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* Docker - [Installation guide here](https://docs.docker.com/engine/install/)
* Docker-compose - [Installation guide here](https://docs.docker.com/compose/install/)

## How to run the application

### Cloning the repository
 1. Clone the repository using one of the options that github allows
 2. Enter the project folder, in linux use the command `cp .env.example .env` to generate the file with the example environment variables. 
**Note:** If you want to set other environment variables, simply use the above command and modify them in some text editor. 
3. In the file Docker-compose.yaml is exposed the port 3005 of the host (your machine), you can modify it by the one you want. Port 3000 is the port of the container where the application is running (ATTENTION: of the container) it should be left like this. 
	In the Docker-compose.yaml you can also define the mongo service (mongo-db), an external volume (dbdata) where the data will be stored in your machine so that when the container dies the information will not be lost and an external network (ing-web) that will be the network that the containers will share (this is a docker's own network that allows containers to communicate with each other).
	To be able to run the project you must create the volume and the network, for this you launch the command `docker network create ing-web` and for the `docker volume create dbdata`.

	![local-docker-compose](https://github.com/DanielSantaR/docker-nodejs/blob/readme/images/local-dc.png)

4. Finally run `docker-compose -f Docker-compose.yaml up --build` and go to [localhost:3005/api-docs](localhost:3005/docs) (replace 3005 with your chosen port)

### Using the DockerHub image

1. This way it is not necessary to clone the repository, the only thing you must do is create a docker compose very similar to the previous one, change is the image, now it will be the one in the docker hub repository:

    ![remote-docker-compose](https://github.com/DanielSantaR/docker-nodejs/blob/readme/images/remote-dc.png)

    **Note:** The tag in this example is the latest but you can specify the tag by exploring ["https://hub.docker.com/r/danielsantar98/docker-node/tags"](https://hub.docker.com/r/danielsantar98/docker-node/tags)

2. The rest of the steps are the same as in the previous section. You can run the container with the command `docker-compose -f Docker-compose.yaml up`
    **Note:** Make sure you are in the directory of the docker-compose file.

