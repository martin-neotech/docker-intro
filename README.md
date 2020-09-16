# docker-intro

https://docs.docker.com/get-docker/


https://docs.docker.com/get-started/overview/#docker-architecture

**Image**

An image is a read-only template with instructions for creating a Docker container.


**Container**

A container is a runnable instance of an image.

+ You can create, start, stop, move, or delete a container using the Docker API or CLI.
+ A container is defined by its image as well as any configuration options you provide to it when you create or start it.
+ When a container is removed, any changes to its state that are not stored in persistent storage disappear.


Source: https://docs.docker.com/get-started/overview/#docker-objects

Run image named `ubuntu` in interactive mode and start `bash`

```
docker run -i -t ubuntu /bin/bash
```

Stop the interactive container

```
exit
```

Implicit this would do

```
docker pull ubuntu
```

```
docker container create
```


# Dockerfile

Docker builds images automatically by reading the instructions from a Dockerfile.

https://docs.docker.com/engine/reference/builder/

```
FROM ubuntu:20.04
COPY . /app
RUN make /app
CMD python /app/app.py
```


```
docker build -f /path/to/a/Dockerfile .
```

https://docs.docker.com/develop/develop-images/dockerfile\_best-practices/#understand-build-context


https://docs.docker.com/engine/reference/builder/#official-releases


https://docs.docker.com/engine/reference/builder/#copy


## Base Image

https://docs.docker.com/develop/develop-images/baseimages/


## Dockerhub Neo4j

https://hub.docker.com/\_/neo4j

```
4.1.1-enterprise
```

https://github.com/neo4j/docker-neo4j-publish/blob/d42c3ac9cde66e2a1dcb3f667fe73878dbf2218c/4.1.1/enterprise/Dockerfile



https://docs.docker.com/engine/reference/builder/#env

```
docker run \
    --publish=7474:7474 --publish=7687:7687 \
    --env=NEO4J_ACCEPT_LICENSE_AGREEMENT=yes \
    --volume=$HOME/neo4j/data:/data \
    --volume=$HOME/neo4j/logs:/logs \
    neo4j:enterprise
```


```
EXTENSION_SCRIPT
```

https://github.com/neo4j/docker-neo4j/blob/master/docker-image-src/4.2/docker-entrypoint.sh#L480


