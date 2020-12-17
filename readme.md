# Docker, nodejs, mongodb, express and swagger API

This project is an API built using docker, nodejs, mongodb, express and swagger. 

## How to run the application

### Cloning the repository
 1. Clone the repository using one of the options that github allows
 2. Enter the project folder, in linux use the command `cp .env.example .env` to generate the file with the example environment variables. 
**Note:** If you want to set other environment variables, simply use the above command and modify them in some text editor. 
3. In the file Docker-compose.yaml is exposed the port 3005 of the host (your machine), you can modify it by the one you want. Port 3000 is the port of the container where the application is running (ATTENTION: of the container) it should be left like this. 
	In the Docker-compose.yaml you can also define the mongo service (mongo-db), an external volume (dbdata) where the data will be stored in your machine so that when the container dies the information will not be lost and an external network (ing-web) that will be the network that the containers will share (this is a docker's own network that allows containers to communicate with each other).
	To be able to run the project you must create the volume and the network, for this you launch the command `docker network create ing-web` and for the `docker volume create dbdata`.
	![docker-compose](https://github.com/DanielSantaR/docker-nodejs/images/docker-compose.png)