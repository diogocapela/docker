# docker

## commands

Build an image:
```
docker build -t myapp .
```

Build an image (with version):
```
docker build -t myapp:0.0.1 .
```

Run an image (creates a container):
```
docker run -it --rm --name NAME_OF_MY_CONTAINER -p 1337:3000 NAME_OF_IMAGE

// -it - interactive terminal
// --rm - remove when its done
// --name - name
// -p - port
```

Show all images:
```
docker images
```

cd into running container:
```
docker attach NAMEOFCONTAINER
```

Show running containers:
```
docker ps
```
Show all containers:
```
docker ps -a
```

Rename a container:
```
docker rename CONTAINER NEW_NAME
```

Remove a container:
```
docker rm CONTAINER
```

Get logs from a container:
```
docker logs CONTAINER
```

Show the latest created container (includes all states):
```
docker ps -l
```

Show n last created containers (includes all states):
```
docker ps -n=-1
```

Display total file sizes of running containers:
```
docker ps -s
```

Cd into a container
```
docker exec -i -t CONTAINER_NAME_OR_ID /bin/bash
```

Run a command inside a running container
```
docker exec CONTAINER_NAME
```

Create a new image from a container’s changes
```
docker ps
docker images
docker commit CONTAINER_ID [REPOSITORY[:TAG]]
docker commit c3f279d17e0a  svendowideit/testimage:version3
```


## dockerfiles

node.js
```
FROM node

WORKDIR /src

ADD . /src

RUN yarn

EXPOSE 3000

CMD ["npm", "start"]
```
