# HowTo Docker
#### from: https://docs.docker.com/get-started/

## Commands
Command | comments
------------ | -------------
docker version | Docker version
docker info | Docker info
docker build -t *tag-name* | Creates a Docker image tagged (-t) with friendly name
docker images | Docker image registry
docker rm *Container NAME or ID* | Remove an image
docker ps -a | List containers details
docker ps *or* docker container ls  | List the running containers
docker start *Container NAME or ID* | Start an existing container image
docker stop *Container NAME or ID* | Stop a container
docker run -d -p 4000:80 *tag-name* | Run app in detached mode (-d), mapping machine’s port 4000 to the container’s port 80 (-p) and create a new container identified with the *tag-name*
docker exec -it *name* sh | Go into the container and start a shell 

## Images
### Scality S3 server [DockerHub](https://hub.docker.com/r/scality/s3server/)

The default access key is _accessKey1_, with the secret key _verySecretKey1_

Run s3 server with a file backend on port 8000:
```bash
$ docker run -d --name s3server -p 8000:8000 scality/s3server
```
Run s3 server with an in-memory backend on port 8000:
```bash
$ docker run -d --name s3server-mem -p 8000:8000 scality/s3server:mem-latest
```
Note that the --name selected (in the example 's3server') will enable you to easily start and stop the given named container:
```bash
$ docker stop s3server[-mem]
$ docker start s3server[-men]
```

### MongoDB [DockerHub](https://hub.docker.com/_/mongo/)

Create an in-memory mongodb container named *mongo-mem*
```bash
$ docker run --name mongo-mem -d mongo
```
Create an mongodb container with a docker volumes (local directory: ${HOME}/DevLab/docker/volumes/mongo) mapped to the default MongoDb directory (/data/db) in the container
```bash
$ docker run --name mongo-db -d -v ${HOME}/DevLab/docker/volumes/mongo:/data/db mongo
```

### ElasticSearch
Start ElasticSearch image

```bash
$ docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" -e "cluster.name=angry-mike" -e "node.name=es-master" docker.elastic.co/elasticsearch/elasticsearch:6.2.1
```

## Links
https://www.metal3d.org/ Blog en francais (Docker, Angular ...)  
https://medium.com/dot-debug/running-chrome-in-a-docker-container-a55e7f4da4a8 Chrome in a container
https://engineering.riotgames.com/news/putting-jenkins-docker-container Jenkins in Docker
