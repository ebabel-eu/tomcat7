# Tomcat with Docker

Repository based on the tutorial from Xebia: http://nauts.io/workshop-docker-introduction/

## Install

Refer to https://docs.docker.com/engine/installation/ to install the Docker engine on your host machine.

```
docker pull tomcat
```

## Build docker image

```
docker build -t ebabel-eu/tomcat7 .
```


## Run docker image

```
docker run -t -i ebabel-eu/tomcat:latest
```

## Run docker image with port mapping

```
DOCKER_ID=$(docker run -P -t -d ebabel-eu/tomcat:latest)
echo $DOCKER_ID
docker ps
PORT=$(docker port $DOCKER_ID 8080)
echo $PORT
curl http://localhost:32771
-- this simpler version didn't work on macosx: curl http://localhost:$PORT
```

## List running docker images

```
docker ps
```

## Remove a docker image

```
docker rmi ebabel-eu/tomcat:latest
```


