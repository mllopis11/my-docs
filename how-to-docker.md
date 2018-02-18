# HowTo Docker
#### from: https://docs.docker.com/get-started/

## Commands
Command | comments
------------ | -------------
docker --version | Docker version
docker build -t *tag-name* | Creates a Docker image tagged (-t) with friendly name
docker images | Docker image registry
docker container ls | List the running containers
docker container stop *Container NAME or ID* | Stop a container
docker run -d -p 4000:80 *tag-name* | Run app in detached mode (-d), mapping machine’s port 4000 to the container’s port 80 (-p)

## Images
* S3Server (AWS): https://hub.docker.com/r/scality/s3server/

## Memo
Start ElasticSearch image

```bash
docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" -e "cluster.name=angry-mike" -e "node.name=es-master" docker.elastic.co/elasticsearch/elasticsearch:6.2.1
```

## Links
https://www.metal3d.org/ Blog en francais (Docker, Angular ...)  
https://medium.com/dot-debug/running-chrome-in-a-docker-container-a55e7f4da4a8 Chrome in a container
https://engineering.riotgames.com/news/putting-jenkins-docker-container Jenkins in Docker
